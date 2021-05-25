
- Configure the config.json with the OpenID Connect's urls, and jwks.json with the certificates details.
- Run `docker build . -t openidpython3`
- Run `docker run -it -p 443:4443 openidpython3:latest`
- Open [https://localhost](https://localhost)