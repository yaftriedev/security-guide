# Navegador
- Bloqueo de Cookies de terceros, rastreadores y fingerprinting
- Telemetría mínima
- Sin cuenta obligatoria

## Escritorio: Brave vs. Firefox vs. Librewolf vs. Mullvad Browser
| Característica | [Brave](https://brave.com/es/) | [Firefox](https://www.firefox.com/es-ES/) | [Mullvad Browser](https://mullvad.net/es/browser) | [LibreWolf](https://librewolf.net/) |
|---|---|---|---|---|
| Cookies de terceros | 🟢 Bloqueadas | 🟡 Aisladas | 🟢 Bloqueadas | 🟢 Bloqueadas |
| Rastreadores | 🟢 Bloqueados | 🟡 Requiere configuración | 🟢 Bloqueados | 🟢 Bloqueados |
| Fingerprinting | 🟡 Protección integrada | 🟡 Protección básica | 🟢 Protección avanzada | 🟢 Protección avanzada |
| Telemetría | 🟡 Opcional | 🔴 Menos, configurable | 🟢 Desactivada | 🟢 Desactivada |
| Cuenta obligatoria | 🟢 No | 🟢 No | 🟢 No | 🟢 No |

## Móvil: Brave vs. Firefox vs. Ironfox

| Característica | [Brave](https://brave.com/es/) | [Firefox](https://www.firefox.com/es-ES/) | [IronFox](https://ironfoxoss.org/) |
|---|---|---|---|
| Cookies de terceros | 🟢 Bloqueadas | 🟡 Aisladas | 🟢 Bloqueadas |
| Rastreadores | 🟢 Bloqueados | 🟢 Bloqueados | 🟢 Bloqueados |
| Fingerprinting | 🟢 Avanzado | 🟡 Configurable | 🟢 Avanzado |
| Telemetría | 🟡 Desactivable | 🟡 Configurable | 🟢 Mínima |
| Cuenta obligatoria | 🟢 No | 🟢 No | 🟢 No | 🟢 No |

# Buscador
- **Requisito**: No recopilar datos personales ni identificables (IP, cookies para tracking)
- **Requisito**: No requerir Iniciar Sesión
- Índice Usado

## DuckDuckGo vs. StartPage vs. Brave Search
| Característica | [DuckDuckGO](https://duckduckgo.com/) | [StartPage](https://eu.startpage.com/) | [Brave Search](https://search.brave.com/) |
|---|---|---|---|
| Pais | EEUU | Paises Bajos | EEUU |
| Datos Recopilados | 🟡 Busqueda anónima, IP temporalmente, <br> puede procesar (pais, SO, agente) | 🟢 Datos anonimos de SO y Agente | 🟡 Busqueda anonima, IP temporalmente, SO y idioma |
| Requiere Cuenta | 🟢 No | 🟢 No | 🟢 No |
| Índice Usado | Bing y Independiente | Google | Independiente |

# DNS (Domain Name Server)
- **Requisito**: No recopilar datos (IP, consulta)
- **Requisito**: DoT y DoH
- Bloqueo de Malware

## Quad9
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

