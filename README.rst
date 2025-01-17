BuildVu Python Client
=====================

Convert PDF to HTML5 or SVG with Python, using the BuildVu Python Client to
interact with IDRsolutions' `BuildVu Microservice Example`_.

The BuildVu Microservice Example is an open source project that allows you to
convert PDF to HTML5 or SVG by running `BuildVu`_ as an online service.

IDR Solutions offer a free trial service for running BuildVu with Python, 
more infomation on this can be found `here.`_

--------------

Installation
------------

Using PIP:
~~~~~~~~~~

::

    pip install buildvu

For other methods / ways to install, check out the `Python Docs`_.

--------------

Usage
-----

Basic:
~~~~~~

First, import BuildVu and setup the converter details by creating a new
``BuildVu`` object :

::

    from BuildVuClient import BuildVu
    buildvu = BuildVu('http://localhost:8080/buildvu-microservice')

You can now convert files by calling the methods available. ``convert()`` will 
start the conversion process. For example to convert to html5 : 

::

    # Convert the file with the input method specified
    results = buildvu.convert(input=BuildVu.UPLOAD, file='path/to/file.pdf')

    # Return a URL where you can view the converted output.
    print(results['downloadUrl'])

Alternatively, you can specify a url from which the server will download the 
file to convert.

::

    # Convert the file with the input method specified
    results = buildvu.convert(input=BuildVu.DOWNLOAD, url="http://link.to/filename")

    # Return a URL where you can download the converted output.
    print(results['downloadUrl'])

Once you have converted the file you can also specify a directory to download 
the converted output to:

::

    # Download the converted output to a specified directory:
    buildvu.downloadResult(results, 'path/to/output/dir')

Additional parameters can be used in ``convert()``, they are defined in our 
`API`_

--------------

Who do I talk to?
=================

Found a bug, or have a suggestion / improvement? Let us know through the
Issues page.

Got questions? You can contact us `here`_.

--------------

Code of Conduct
===============

Short version: Don't be an awful person.

Longer version: Everyone interacting in the BuildVu Python Client
project's codebases, issue trackers, chat rooms and mailing lists is
expected to follow the `code of conduct`_.

--------------

Copyright 2018 IDRsolutions

Licensed under the Apache License, Version 2.0 (the "License"); you may
not use this file except in compliance with the License. You may obtain
a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

.. _BuildVu Microservice Example: https://github.com/idrsolutions/buildvu-microservice-example
.. _BuildVu: https://www.idrsolutions.com/buildvu/
.. _Python Docs: https://packaging.python.org/tutorials/installing-packages
.. _here: https://idrsolutions.zendesk.com/hc/en-us/requests/new
.. _code of conduct: CODE_OF_CONDUCT.md
.. _API: https://github.com/idrsolutions/buildvu-microservice-example/blob/master/API.md
.. _here.: https://www.idrsolutions.com/buildvu/convert-pdf-in-python/
