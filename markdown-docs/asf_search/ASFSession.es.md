# ASFSession

## Descripción

Esta clase extiende `requests.session` para proporcionar opciones de autorización específicas de ASF de manera conveniente. `ASFSession` es una subclase de `Session`. Puede encontrar más información [aquí](https://docs.python-requests.org/en/master/user/authentication/)

***

## Métodos

### <span style="color: #236192; font-size: 20px;">auth_with_creds()</span>

Autentica la sesión (self) utilizando las credenciales de usuario/contraseña de [Earthdata Login](https://urs.earthdata.nasa.gov/).

**args:**

- username: Nombre de usuario de [Earthdata Login](https://urs.earthdata.nasa.gov/)
- password: Contraseña de [Earthdata Login](https://urs.earthdata.nasa.gov/)

**retorna:**

- retorna self para conveniencia

***

### <span style="color: #236192; font-size: 20px;">auth_with_token()</span>

Autentica la sesión (self) utilizando un token `Authorization: Bearer` de Earthdata Login.

**args:**

- token: Token de Earthdata Login para descargas autenticadas, consulta [Tokens de Earthdata Login](https://urs.earthdata.nasa.gov/user_tokens)

**retorna:**

- retorna self para conveniencia

***

### <span style="color: #236192; font-size: 20px;">auth_with_cookiejar()</span>

Autentica la sesión (self) utilizando un cookiejar preexistente.

**args:**

- cookies: Un objeto compatible con `http.cookiejar`

**retorna:**

- retorna self para conveniencia