# CDP Developer Documentation

This repository houses detailed developer-oriented documentation for
[Cloudera Data Platform](https://www.cloudera.com/products/cloudera-data-platform.html)
(CDP).

* [API documentation](./api-docs)
* [beta API documentation](./api-docs-beta)
* [audit event details documentation](./audit-details-docs)
* [Java SDK javadoc](https://cloudera.github.io/cdp-sdk-java/)
* [CLI documentation](./cli-docs)
* [beta CLI documentation](./cli-docs-beta)

For overall CDP documentation, visit [docs.cloudera.com](https://docs.cloudera.com/).

## Beta API

The beta API offers features that are not yet available in the standard CLI and still under development. They are not yet supported, may not work, and are subject to change in incompatible ways, including removal. Do not rely on beta features for production use.

## SDKs

* [Java](https://github.com/cloudera/cdp-sdk-java)
* Python: Use the CDP CLI
* others to come

## CDP CLI

The CDP command line interface (CLI) is available from PyPI.

* [CDP CLI](https://pypi.org/project/cdpcli/)
* [CDP Beta CLI](https://pypi.org/project/cdpcli-beta/)

Instructions for installation are [available from CDP Management Console help documentation](https://docs.cloudera.com/cdp/latest/cli/topics/mc-installing-cdp-client.html). The standard, public CLI and the beta CLI should be installed in separate Python environments (e.g., virtualenvs) to avoid conflicts.

Source code is also available in a [Github repository](https://github.com/cloudera/cdpcli).

Once the CLI is installed, you can `import cdpcli` in your own Python code to use the CLI as a Python SDK. This mode of use is not yet fully supported, so be aware that the internal CLI code may change in the future.

## Documentation expansion in progress

Check back in the future for more documentation.
