# Place your certificates here!

Replace example.com with the hostname of your Gemini Capsule.
```
openssl req -x509 -newkey rsa:4096 -sha256 -days 3650 -nodes \
  -keyout key.pem -out cert.pem -subj "/CN=example.com"
```