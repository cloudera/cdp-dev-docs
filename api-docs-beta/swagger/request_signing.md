# CDP API Request Signing Specification V1

HTTPS requests sent to the CDP control plane API must be signed to be accepted. The signature helps to implement authentication and to mitigate replay attacks, among other features. This document specifies how to sign requests correctly.

## Step 1. Create a canonical request string

Start by creating a canonical request string, encoded using UTF-8, using information from the API request. Use the following format:

```
<httpMethod>\n
<contentType>\n
<timestamp>\n
<path>\n
<authMethod>
```

where `\n` is a newline character. Each of the fields is described in more detail next.

### HTTP method

Control plane API requests currently always use the `POST` method, so start the canonical request string with that, followed by a newline.

```
POST
```

### Content type

Control plane API requests currently require the content type `application/json` in their HTTP Content-Type headers. So, append that value to the string, followed by a newline.

```
application/json
```

### Timestamp

The current time is the next element of the canonical request string. The value must be specified in the GMT timezone and formatted in accordance with [RFC 1123 section 5.2.14](https://tools.ietf.org/html/rfc1123#page-55). Append the formatted timestamp to the string, followed by a newline.

```
Tue, 3 Jun 2008 11:05:30 GMT
```

The same value must be passed in the `x-altus-date` header of the API request.

### Path

Next, append the path portion of the API request URL to the canonical request string, followed by a newline. Use the same case that is used in the request itself.

```
/api/v1/datahub/createAWSCluster
```

### Authentication method

The final component of the canonical request string is the authentication method used by the signing key. Supported values are:

* rsav1
* ed25519v1

```
ed25519v1
```

## Step 2. Calculate a signature string

Next, create a digital signature from the (UTF-8) bytes of the canonical request string using the private key of the caller. Supported algorithms (using JCA / Bouncy Castle naming standards):

* SHA256withRSA for the "rsav1" authentication method, using an RSA private key
* Ed25519 for for "ed25519v1" authentication method, using a 256-bit ED25519 key

Finally, encode the bytes of the signature using [URL-safe base 64](https://tools.ietf.org/html/rfc4648#section-5) to create a signature string. URL-safe base 64 uses the characters `-` and `_` instead of `+` and `/`, respectively.

Here is an example signature string.

```
3iDOInVdC1dYT2MDgiWKqZsYDbhSSZacV9B6uCnq3rlFeIIkWfE4za2t-PJbbPPiFcvZEuJcPbfy6hbbo-wmDQ==
```

## Step 3. Create an encoded authentication parameters string

An encoded authentication parameters string is another piece of information that must be submitted as part of a signed control plane API request.

Start by constructing a JSON object with the following structure.

```
{
  "access_key_id": "<accessKeyId>",
  "auth_method": "<authMethod>"
}
```

where:

- `<accessKeyId>` is the access key ID for the caller
- `<authMethod>` is the same authentication method used when constructing the canonical request string

Serialize the JSON object to a UTF-8 encoded string. This is the authentication parameters string. There is no requirement for how whitespace is used in the string, beyond what JSON normally requires for correct syntax.

```
{"access_key_id": "1b069abc-7638-4502-be64-c694cd368cc1", "auth_method": "ed25519v1"}
```

Finally, encode the (UTF-8) bytes of that string using URL-safe base 64 to generate the encoded authentication parameters string.

```
eyJhY2Nlc3Nfa2V5X2lkIjogIjFiMDY5YWJjLTc2MzgtNDUwMi1iZTY0LWM2OTRjZDM2OGNjMSIsICJhdXRoX21ldGhvZCI6ICJlZDI1NTE5djEifQ==
```

## Step 4. Add the signature to the HTTP request

After calculating the signature string and the encoded authorization parameters string, add them to the API request using the `x-altus-auth` HTTP header.

The value for the header is the concatenation of the encoded authentication parameters string and the signature string, separated by a single period character.

```
<encoded authentication parameters string>.<signature string>
```

Also, ensure that the following related headers are set:

* "Content-Type" must be set to "application/json"
* "x-altus-date" must be set to the same timestamp value used in constructing the canonical request string

```
x-altus-auth: eyJhY2Nlc3Nfa2V5X2lkIjogIjFiMDY5YWJjLTc2MzgtNDUwMi1iZTY0LWM2OTRjZDM2OGNjMSIsICJhdXRoX21ldGhvZCI6ICJlZDI1NTE5djEifQ==.3iDOInVdC1dYT2MDgiWKqZsYDbhSSZacV9B6uCnq3rlFeIIkWfE4za2t-PJbbPPiFcvZEuJcPbfy6hbbo-wmDQ==
Content-Type: application/json
x-altus-date: Tue, 3 Jun 2008 11:05:30 GMT
```

---

## Implementations

Reference implementations of this specification:

* [Signer.java](https://github.com/cloudera/cdp-sdk-java/blob/master/src/main/java/com/cloudera/cdp/authentication/Signer.java) - Java SDK
* [cdpcurl/cdpv1sign.py](https://github.com/cloudera/cdpcurl/blob/master/cdpcurl/cdpv1sign.py) - cdpcurl (Python)

