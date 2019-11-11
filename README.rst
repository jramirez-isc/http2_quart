PythonTiles
===========

This is an example inspired by `GopherTiles <https://http2.golang.org/gophertiles>`_ demonstrating Quart's HTTP/2 push promise capabilities.

This example requires the `Pillow library <https://pypi.org>`_

- `pip install -r requirements.txt`
- `QUART_APP=http2_push quart run`

The application exposes two endpoints:

- `https://localhost:5000/` using standard HTTP/2
- `https://localhost:5000/push` using HTTP/2 push promises


-- To create certificates
openssl req -newkey rsa:4096 -new -nodes -x509 -days 36500 -keyout key.pem -out cert.pem

-- To see the content of a cert:
keytool -printcert -v -file cert.pem

-- To add the cert to cacert java files
keytool -importcert -file cert.pem -alias randomaliasname -keystore C:\java\jdk-11\lib\security\cacerts -storepass changeit

-- To create a truststore from cert.pem 
keytool -importcert -trustcacerts -file cert.pem -keystore truststore.jks

-- To run java app and trust in truststore
java -Djavax.net.ssl.trustStore=truststore.jks -Djavax.net.ssl.trustStorePassword=changeit MyApp