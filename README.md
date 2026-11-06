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
| [hashes/](hashes/) | `hashes.sha256` de toda la carpeta de evidencias y los registros de las herramientas (FTK Imager, script de volátiles, Velociraptor, EDD, bloqueo USB) |
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
> **Censura por privacidad:** en la copia publicada de `hashes/FORENSIC_10.vmx.original` se ha sustituido la clave de producto de la línea `annotation` por `[CENSURADO]`. La original no se ha modificado y sigue en la carpeta de evidencias, con el SHA-256 333fa46fd43708509b4793ed48aaa5adf8f5ea9bf19e39805b3fc447570b4efa que figura en `hashes.sha256`. La copia publicada tiene el SHA-256 5368340ac5a7c8c7b7fafaf08b15549a46f70b78c05b58134fc7c111e2e0ae2f. Las capturas censuradas se detallan en [capturas/CENSURADAS.md](capturas/CENSURADAS.md).
