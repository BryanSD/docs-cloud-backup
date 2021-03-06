# Rackspace Cloud Backup API documentation

[![Build Status](https://travis-ci.org/rackerlabs/docs-cloud-backup.svg?branch=master)](https://travis-ci.org/rackerlabs/docs-cloud-backup)


## Purpose

This GitHub repository contains the source files for the following Rackspace Cloud Backup API documentation:

**VERSION 2 of Cloud Backup - Not yet launched externally**

* [Cloud Backup Getting Started Guide] - Not yet drafted.
* [Cloud Backup Developer Guide - internal only](http://docs-internal.rackspace.com/rcbu/api/v1.0/rcbu-devguide-v2/content/overview.html)
* [Cloud Backup API Reference - internal only](http://docs-internal.rackspace.com/rcbu/api/v1.0/rcbu-devguide-v2/content/operations.html)
* [Cloud Backup Release Notes] - Not yet drafted.

**VERSION 1 of Cloud Backup**

* [Cloud Backup Getting Started Guide](https://developer.rackspace.com/docs/cloud-backup/v1/developer-guide/#document-getting-started)
* [Cloud Backup Developer Guide](https://developer.rackspace.com/docs/cloud-backup/v1/developer-guide/#document-developer-guide)
* [Cloud Backup API Reference](https://developer.rackspace.com/docs/cloud-backup/v1/developer-guide/#document-api-reference)
* [Cloud Backup Release Notes](https://developer.rackspace.com/docs/cloud-backup/v1/developer-guide/#document-release-notes)

## Contributing

Contributions are welcome! 

* To suggest changes or report a problem, submit an [issue](https://github.com/rackerlabs/docs-cloud-backup/issues). 

* To make changes to a project, create your own fork of the repository. Then, submit a [pull 
request](https://github.com/rackerlabs/docs-cloud-backup/compare?expand=1) to have your changes reviewed 
and merged into the master branch as appropriate.

To contribute content, all you need is an editor and a 
basic understanding of the project layout and [reStructuredText](http://sphinx-doc.org/rest.html) syntax.

You can use the GitHub editor or any text editor to work with documentation source files. For quick syntax checking, try the 
[Online restructuredText editor](http://rst.ninjs.org/). 

**Note:** If you want to build the project, you need to install the [Sphinx documentation generator](http://www.sphinx-doc.org/en/stable/install.html). 

## Source format

The Rackspace developer documentation is developed and built using the [Python Sphinx documentation generator](http://sphinx-doc.org/). Content is 
written in [reStructuredText](http://sphinx-doc.org/rest.html), the markup syntax and parser component of 
[Python Docutils](http://docutils.sourceforge.net/index.html).

The repository includes the documentation source files, 
Sphinx configuration and build files, as well any required Sphinx 
extensions and build tools. 

## Structure

Source files for the Sphinx documentation project are in the ``api-docs`` directory. Here are the key files that define 
the Sphinx project and content architecture for the documentation: 

**VERSION 2 of Cloud Backup - Not yet launched externally**

Content | File
--- | ---
|Sphinx documentation configuration file| [conf.py](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v2/conf.py) (Typically, this file does not require changes.)
|Index page for the main content structure| [index.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v2/index.rst)
|About the API index| [overview/index.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v2/overview/index.rst)
|Developer Guide introduction|[developer-guide.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v2/developer-guide.rst)
|Concepts section| [concepts.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v2/concepts.rst)
|General API information index|[general-api-info/index.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v2/general-api-info/index.rst)
|API Reference introduction|[api-reference.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v2/api-reference.rst)
|API Reference index|[api-operations/index.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v2/api-operations/index.rst)
|API operations methods, including code samples|[api-operations/methods](https://github.com/rackerlabs/docs-cloud-backup/tree/master/api-docs/cloud-backup-v2/api-operations/methods) 
|**make.bat**|Windows build script
|**Makefile**| Linux and OS X build


**VERSION 1 of Cloud Backup**

Content | File
--- | ---
|Sphinx documentation configuration file| [conf.py](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/conf.py) (Typically, this file does not require changes.)
|Index page for the main content structure| [index.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/index.rst)
|About the API index| [overview/index.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/overview/index.rst)
|Getting Started introduction| [getting-started.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/getting-started.rst)
|Getting Started index|[getting-started/index.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/getting-started/index.rst)
|Developer Guide introduction|[developer-guide.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/developer-guide.rst)
|Concepts section| [concepts.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/concepts.rst)
|General API information index|[general-api-info/index.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/general-api-info/index.rst)
|API Reference introduction|[api-reference.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/api-reference.rst)
|API Reference index|[api-operations/index.rst](https://github.com/rackerlabs/docs-cloud-backup/blob/master/api-docs/cloud-backup-v1/api-operations/index.rst)
|API operations methods, including code samples|[api-operations/methods](https://github.com/rackerlabs/docs-cloud-backup/tree/master/api-docs/cloud-backup-v1/api-operations/methods) 
|Release notes introduction and index|[release-notes.rst](https://github.com/rackerlabs/docs-cloud-backup/tree/master/api-docs/cloud-backup-v1/release-notes)
|Release notes by version|[release notes folder](https://github.com/rackerlabs/docs-cloud-backup/tree/master/api-docs/cloud-backup-v1/release-notes)
|**make.bat**|Windows build script
|**Makefile**| Linux and OS X build

### Support and feedback

If you find a problem, open a GitHub [issue](https://github.com/rackerlabs/docs-cloud-backup/issues).

If you need additional assistance, contact us at 
[devdoc@rackspace.com](mailto:devdoc@rackspace.com).



