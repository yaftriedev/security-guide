# Características
- **Requisito**: No recopilar datos (IP, consulta)
- **Requisito**: DoT y DoH
- Bloqueo de Malware

# Comparación
| Característica | [Quad9](https://quad9.net/) | [Cloudflare](https://www.cloudflare.com/es-es/application-services/products/dns/) |
|---|---|---|
| País / jurisdicción | 🇨🇭 Suiza | 🇺🇸 EE. UU. |
| Log IP | 🟢 No | 🟡 Limitado |
| Log Consulta | 🟢 No | 🟡 ≤25 h |
| Bloqueo Malware | 🟢 Si | 🔴 No |

# Quad9
| Característica | Recommended | Secured w/ECS | Unsecured |
|---|---|---|---|
| Bloquea Malware | 🟢 Si | 🟢 Si | 🔴 No |
| ECS (EDNS Client Subnet)¹ | 🟢 No | 🟡 Si | 🟢 No |
| Validación DNSSEC | 🟢 Si | 🟢 Si | 🟢 Si |
| IPv4 | 9.9.9.9 | 9.9.9.11 | 9.9.9.10 |
| IPv4 Alternativa | 149.112.112.112 | 149.112.112.11 | 149.112.112.10 |
| IPv6 | 2620:fe::fe | 2620:fe::11 | 2620:fe::10 |
| IPv6 Alternativa | 2620:fe::9 | 2620:fe::fe:11 | 2620:fe::fe:10 |
| DNS over TLS | tls://dns.quad9.net | tls://dns11.quad9.net | tls://dns10.quad9.net |
| DNS over HTTPS | https://dns.quad9.net/dns-query | https://dns11.quad9.net/dns-query | https://dns10.quad9.net/dns-query |

¹. Para mayor privacidad sin ECS (EDNS Client Subnet) 


---

```
A fecha de 09/2026, por corregir errores y contrastar info
```