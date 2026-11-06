# UD1 · Adquirir un equipo comprometido

**Alumno:** Eduardo Moreno Rodríguez
**Módulo:** Análisis Forense Informático (AFI) · IES Rafael Alberti
**Caso:** P02 · equipo FORENSE-06 (máquina virtual FORENSIC_10)
**Marca:** `AFI-EduardoMorenoRodriguez-20261102`

## Contenido

| Documento | Qué contiene |
|---|---|
| [notas-de-trabajo.md](notas-de-trabajo.md) | Cuaderno de la intervención, en orden y con hora: qué se hizo, qué se vio, qué se decidió y por qué, con comandos exactos, incidencias y errores |
| [acta-adquisicion.pdf](acta-adquisicion.pdf) | Acta firmada: cada evidencia, cómo y cuándo se obtuvo, con qué herramienta y su hash |
| [registro-custodia.pdf](registro-custodia.pdf) | Registro de cadena de custodia firmado, desde la adquisición hasta la devolución |
| [hashes/](hashes/) | `hashes.sha256` de toda la carpeta de evidencias, los registros de las herramientas (FTK Imager, script de volátiles, Velociraptor, EDD, bloqueo USB), `hashes-herramientas.txt` (inventario de las herramientas del disco de respuesta), `herramienta-respuesta-en-vivo-ps2.sha256` (script de volátiles adaptado a PowerShell 2.0) y `fotos.sha256` (fotos de los precintos y la entrega) |
| [capturas/](capturas/) | Capturas y fotos numeradas según las filas de las notas de trabajo. 13 están censuradas por privacidad: ver [capturas/CENSURADAS.md](capturas/CENSURADAS.md) |

## Evidencias adquiridas

| ID | Evidencia | Herramienta |
|---|---|---|
| EV-RAM-01 | Memoria RAM | WinPmem mini (`winpmem_mini_x64_rc2.exe`) |
| EV-VOL-01 | Datos volátiles | `respuesta-en-vivo-ps2.ps1` (script del profesor adaptado a PowerShell 2.0) |
| EV-RED-01 | Tráfico de red (capturado desde el host) | dumpcap |
| EV-TRIAJE-01 | Triaje | Velociraptor v0.77.3 legacy, artefacto `Windows.Triage.Targets` (`_KapeTriage`) |
| EV-DISCO-01 | Imagen del disco (E01 verificada) | FTK Imager 8.3.0.27 |
| EV-USB-01 | Imagen del pendrive encontrado (E01 verificada, con bloqueo de escritura comprobado) | FTK Imager 8.3.0.27 + bloqueo-usb.ps1 |

La marca se ha localizado en la RAM, en el triaje (`$MFT`), en la imagen del disco y en la imagen del pendrive.

> Las evidencias no se publican, por su tamaño y su naturaleza. En este repositorio solo hay sus hashes y los registros de las herramientas. Para comprobar la integridad: `sha256sum -c hashes.sha256`, desde la carpeta de evidencias.
>
> `hashes.sha256` incluye `hashes/FORENSIC_10.vmx.original` (copia del .vmx tal como se recibió, antes de la corrección de la fila 0b2 de las notas), con SHA-256 333fa46fd43708509b4793ed48aaa5adf8f5ea9bf19e39805b3fc447570b4efa. Ese fichero no se publica: es configuración de la VM investigada, así que se trata como evidencia y queda solo en la carpeta de evidencias.
>
> **Censura por privacidad:** las capturas censuradas se detallan en [capturas/CENSURADAS.md](capturas/CENSURADAS.md).
