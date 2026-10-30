# Gestor de Contraseñas Local
- [**KeePassXC**](https://keepassxc.org/): Disponible en Windows, MacOS, Linux y Extensión de Navegador
- [**KeePassDX**](https://www.keepassdx.com/): Disponible en Fdroid, PlayStore y Repo (github)

### KeePassXC almacena las contraseñas en un archivo de base de datos cifrado con extensión .kdbx.
- Contenido: contraseñas, usuarios, URL, notas y otros datos organizados en grupos.
- Cifrado: utiliza AES-256, ChaCha20 o Twofish, según la configuración.
- Protección: se desbloquea mediante una contraseña maestra y, opcionalmente, una clave de archivo o un dispositivo compatible.
- Acceso: solo se puede consultar el contenido después de desbloquear la base de datos.
- Almacenamiento: el archivo se guarda localmente y puedes sincronizarlo mediante servicios como Nextcloud o una memoria USB.

# Gestor de Contraseñas Online: Bitwarden vs. Proton Pass vs. 1Password

| Característica | [Bitwarden](https://bitwarden.com) | [Proton Pass](https://proton.me/pass) | [1Password](https://1password.com/) |
|---|---|---|---|
| País | EE. UU. | Suiza | Canadá |
| Open Source | Sí | Sí | No |
| Cifrado | 🟢 AES-256-CBC | 🟢 AES-256-GCM | 🟢 AES-256-GCM |
| E2EE / Zero-Knowledge | 🟢 Sí | 🟢 Sí | 🟢 Sí |
| Auditorías externas | 🟢 Sí | 🟢 Sí | 🟢 Sí |
| Autohospedaje | 🟢 Sí | 🔴 No | 🔴 No |
| Passkeys y TOTP | 🟢 Sí | 🟢 Sí | 🟢 Sí |
| Alias de correo | 🔴 No | 🟢 Sí | 🔴 No |
| Precio Año (€/mes) | 0€ / 1.65€ | 0€ / 3€ | 2.75€ / 4.3€ |

# Alias de Correo: Simplelogin vs. Addy.io

## Plan gratuito

| Característica | [SimpleLogin](https://simplelogin.io/) | [Addy.io](https://addy.io/) |
|---|---|---|
| País | Suiza | Reino Unido |
| Alias | 🟡 10 | 🟢 Ilimitados |
| Ancho de banda | 🟢 Ilimitado | 🟡 10 MB/mes |
| Responder desde alias | 🟢 Sí | 🔴 No |
| Dominios propios | 🔴 No | 🔴 No |
| Código abierto | 🟢 Sí | 🟢 Sí |

## Planes de pago

| Característica | [SimpleLogin Premium](https://simplelogin.io/) | [Addy.io Lite / Pro](https://addy.io/) |
|---|---|---|
| País | Suiza | Reino Unido |
| Alias | 🟢 Ilimitados | 🟢 Ilimitados |
| Ancho de banda | 🟢 Ilimitado | 🟡 100 MB / 🟢 Ilimitado |
| Responder desde alias | 🟢 Sí | 🟢 Sí |
| Dominios propios | 🟢 Ilimitados | 🟡 1 / 🟢 20 |
| Cifrado PGP | 🟢 Sí | 🟢 Sí |
| Precio Año (€/mes) | 2.70€ | 1€ / 3€ |

# 2º Factor de Autentificación con TOTP

## Como funciona TOTP (Time-based One-Time Password)
- Un secreto compartido (K), normalmente una clave de 20 bytes.
- La hora actual, convertida en un contador (C).
- Una función HMAC, por ejemplo HMAC-SHA1.
- Un truncamiento que produce normalmente un código de 6 dígitos.

```
C = floor(UnixTime / 30)
OTP = trunc(HMAC-SHA1(K, C)) mod 10^6
```

## Programas / Apps
- [Aegis Authenticator](https://getaegis.app)
- [FreeOTP](https://freeotp.github.io)
- [Proton Authenticator](https://proton.me)
- [Bitwarden Authenticator](https://bitwarden.com/products/authenticator/)