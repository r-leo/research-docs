Sistema de Información Económica (SIE) del Banco de México
==========================================================

El `Sistema de Información Económica <https://www.banxico.org.mx/SieInternet>`_ (SIE) del `Banco de México <https://www.banxico.org.mx>`_ es un repositorio de indicadores y series de tiempo de carácter abierto. Cuenta con una API para acceder a los datos de forma automatizada. Para hacer uso de la misma se requiere un token de consulta que el mismo Banco `proporciona gratuitamente <https://www.banxico.org.mx/SieAPIRest/service/v1/token>`_.


Uso de la API
-------------

De acuerdo con la documentación disponible de la API del SIE, existen cuatro formas posibles de hacer una llamada a la API:

Consulta de metadatos de series:

``banxico.org.mx/SieAPIRest/service/v1/series/S1,[S2,[S3,...]]``

Consulta de series completas:

``banxico.org.mx/SieAPIRest/service/v1/series/S1,[S2,[S3,...]]/datos``

Consulta de datos oportunos:

``banxico.org.mx/SieAPIRest/service/v1/series/S1,[S2,[S3,...]]/datos/oportuno``

Consulta de series en un intervalo de fechas:

``banxico.org.mx/SieAPIRest/service/v1/series/S1,[S2,[S3,...]]/datos/fechai/fechaf``

Donde ``S1,[S2,[S3,...]]`` corresponde a los IDs de las series a consultar, ``fechai`` es la fecha inicial de la consulta y ``fechaf`` es la fecha final de la consulta. Ambas fechas deben expresarse en formato ISO: ``YYYY-MM-DD``, por ejemplo, ``2022-03-28``.

La respuesta de la API es por defecto en formato JSON, pero puede obtenerse en formato HTML o XML usando el parámetro opcional ``mediaType``:

* ``mediaType=html`` para obtener una respuesta HTML.
* ``mediaType=json`` para obtener una respuesta JSON (este es el formato por defecto si no se especifica el parámtero ``mediaType``).
* ``mediaType=xml`` para obtener una respuesta XML.

De forma similar, se puede especificar el idioma de la respuesta con el parámetro opcional ``locale``:

* ``locale=es`` para obtener una respuesta en español (esta es la opción por defecto).
* ``locale=en`` para obtener una respuesta en inglés.

.. note::

    Todas las llamadas a la API del SIE requieren de un token de consulta válido. Este se envía como un parámetro más en la URL: ``banxico.org.mx/SieAPIRest/[...]?token=x``, donde ``x`` es una cadena de 64 caracteres.