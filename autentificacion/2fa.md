# Como funciona TOTP (Time-based One-Time Password)
- Un secreto compartido (K), normalmente una clave de 20 bytes.
- La hora actual, convertida en un contador (C).
- Una función HMAC, por ejemplo HMAC-SHA1.
- Un truncamiento que produce normalmente un código de 6 dígitos.

```
C = floor(UnixTime / 30)
OTP = trunc(HMAC-SHA1(K, C)) mod 10^6
```

# Programas / Apps
- [Aegis Authenticator](https://getaegis.app)
- [FreeOTP](https://freeotp.github.io)
- [Proton Authenticator](https://proton.me)
- [Bitwarden Authenticator](https://bitwarden.com/products/authenticator/)