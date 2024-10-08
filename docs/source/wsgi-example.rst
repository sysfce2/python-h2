Example HTTP/2-only WSGI Server
===============================

This example is a more complex HTTP/2 server that acts as a WSGI server,
passing data to an arbitrary WSGI application. This example is written using
`asyncio`_. The server supports most of PEP-3333, and so could in principle be
used as a production WSGI server: however, that's *not recommended* as certain
shortcuts have been taken to ensure ease of implementation and understanding.

The main advantages of this example are:

1. It properly demonstrates HTTP/2 flow control management.
2. It demonstrates how to plug h2 into a larger, more complex
   application.


.. literalinclude:: ../../examples/asyncio/wsgi-server.py
   :language: python
   :linenos:
   :encoding: utf-8


You can use ``cert.crt`` and ``cert.key`` files provided within the repository
or generate your own certificates using `OpenSSL`_:

.. code-block:: console

   $ openssl req -x509 -newkey rsa:2048 -keyout cert.key -out cert.crt -days 365 -nodes

.. _asyncio: https://docs.python.org/3/library/asyncio.html
.. _OpenSSL: https://openssl-library.org/source/index.html
