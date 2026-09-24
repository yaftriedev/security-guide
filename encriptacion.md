# Conceptos Básicos
- **Criptografía**: Práctica y estudio de técnicas que permiten garantizar la confidencialidad, integridad, autenticación y no repudio de la información que se encuentra almacenada, en tránsito y en uso.
- **Criptosistema**: Conjunto de algoritmos y claves que implementan un servicio de seguridad (como la confidencialidad). Incluye, al menos, un algoritmo de cifrado y otro de descifrado, con sus claves asociadas.
-Criptosistema simétrico: misma clave (o casi la misma) para cifrar y descifrar; clave compartida y secreta.
Criptosistema asimétrico: claves distintas para cifrar y descifrar; la clave de cifrado puede ser pública y la descifrado debe permanecer secreta. Computacionalmente inviable obtener la clave privada a partir de la pública.
    - **Criptosistema simétrico**: Misma clave (o casi la misma) para cifrar y descifrar; clave compartida y secreta.
    - **Criptosistema asimétrico**: Claves distintas para cifrar y descifrar; la clave de cifrado puede ser pública y la descifrado debe permanecer secreta. Computacionalmente inviable obtener la clave privada a partir de la pública.

# Principios Básicos de la Criptografía
- **Confidencialidad**: Garantizar que la información no sea accesible ni revelada a individuos no autorizados, tanto en su almacenamiento como en su transmisión.
- **Integridad**: Garantizar la exactitud y completitud de la información a lo largo de todo su ciclo de vida, evitando modificaciones no autorizadas, ya sean accidentales o intencionadas.
    - **Protección contra errores accidentales:** Error-correcting codes y Checksums (ej: CRCs).
    - **Protección contra alteraciones intencionadas:** Funciones hash y MACs.
- **Disponibilidad**: Garantizar que la información y los sistemas que la gestionan estén accesibles siempre que los usuarios autorizados necesiten acceder a ellos.
- **No repudio:** Propiedad de seguridad que impide que alguien niegue haber realizado una acción, normalmente haber enviado un mensaje o haber firmado un documento.

# Funciones HASH
Las **funciones hash** se corresponden con un tipo de función criptográfica atípica que no tiene una clave secreta. Su definición es pública y cualquiera puede computarla.
-  Recibe un valor de cualquier longitud y retorna un valor de longitud fija denominado hash.
- Son eficientes (rápidas) de computar.
- Es muy costoso en términos computacionales y de tiempo invertir el funcionamiento de una función hash y obtener el valor de entrada a partir del hash previamente computado.

## Funciones HASH mas conocidas
- **MD5**: Produce un hash de 128 bits. Suele utilizarse para verificar la integridad de la información. Presenta ciertas colisiones y su uso en la actualidad es poco recomendado. `md5sum <file>`
- **SHA-1**: Produce un hash de 160 bits. Se utilizó durante muchos años en protocolos como SSL/TLS. A principios de los años 2000 se encontraron técnicas de ataque que permitían encontrar colisiones y se dejó de recomendar su uso. `sha1sum <file>`
- **SHA-2**: Agrupa una familia de funciones que producen hashes de 224 bits (SHA-224), 256 bits (SHA-256), 384 bits (SHA-384) y 512 bits (SHA-512). Estas funciones hash son las recomendadas en la actualidad, preferiblemente a partir de SHA-256. `sha256sum / sha512sum <file>`
- **SHA-3**: Permite producir hashes de 224 bits (SHA3-224), 256 bits (SHA3-256), 384 bits (SHA3-384) y 512 bits (SHA3-512).  El objetivo de SHA-3 no es remplazar SHA-2, simplemente diversificar el rango de funciones hash disponibles.

# Cifrado de Archivos Simétrico
- **AES (Advanced Encryption Standard)**: Algoritmo de cifrado simétrico más utilizado y el estándar de cifrado propuesto por el gobierno de los EEUU (Advanced Encryption Standard).
- **DES (Data Encryption Standard)**: Fue el estándar de cifrado simétrico entre 1980 y 1990. A día de hoy esta roto debido al tamaño de su clave.

```bash 
# Cifrar Archivo
gpg --symmetric <archivo>
gpg --symmetric --cipher-algo AES256 <archivo>

# Descifrar Archivo
gpg --decrypt <archivo-encriptado> > <archivo>

# Limpiar contraseña guardada en gpg-agent
gpgconf --kill gpg-agent
```

# Claves SSH (Asimétrico)

```bash
# Conectarse a un pc
ssh user@ip
ssh user@name-config

# Generar Claves SSH
ssh-keygen -t ed25519
ssh-copy-id -i /ruta/clave usuario@IP

# Guardar Hosts `.ssh/config`
Host <nombre>  
       HostName <IP/Dominio>
       User <usuario>
       IdentityFile </ruta/clave>  
```

```bash
# Instalar SSH Server
sudo apt install openssh-server

# Configuraciones utiles en /etc/ssh/sshd_config
Port 22  
ListenAddress 0.0.0.0  
PermitRootLogin prohibit-password  
PubkeyAuthentication yes  
PasswordAuthentication yes  
PermitEmptyPasswords no  
UsePAM yes
```

# Claves PGP (Asimétrico)
Usa el argumento `--armor` o `-a` para exportar a ASCII (.asc) claves, archivos cifrados y firmas
```bash
# Crear Clave PGP
gpg --full-generate-key

Por favor seleccione tipo de clave deseado:
   (1) RSA and RSA
   (2) DSA and Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
   (9) ECC (sign and encrypt) *default*
  (10) ECC (sólo firmar)

# Listar Claves: [SC] = Firmar, [E] = Encriptar
gpg --list-public-keys
gpg --list-secret-keys --with-keygrip

# Exportar Clave Pública
gpg --export <correo/fingerprint>

# Importar Clave Pública
gpg --import <clave>

# Eliminar
gpg --delete-secret-key <fingerprint> # solo para claves creadas por ti
gpg --delete-key <fingerprint>
```

```bash
# Cifrar: -e = --encrypt
gpg -e -r <fingerprint/correo> <archivo>

# Descifrar (requiere clave privada): -d = --decrypt
gpg -d <archivo-encriptado> > <archivo>

# Firmar (requiere clave privada): -b = --detach-sign 
gpg -u <fingerprint/correo> -b <archivo>
gpg -b <archivo>

# Verificar
gpg --verify <firma> <archivo>
```
