# New_hashes_LuckyDefender

Sistema de actualización de firmas para **Lucky Defender V1**, un motor antivirus minimalista desarrollado en PowerShell y Batch.  
Este repositorio contiene los **hashes y cadenas nuevas** que se integran en el archivo `signatures.txt` de Lucky Defender, permitiendo que el motor detecte y elimine amenazas adicionales como el archivo de prueba EICAR.

---

## 📌 Objetivo
Mantener un repositorio centralizado y limpio de firmas de malware (hashes y cadenas sospechosas) que Lucky Defender pueda descargar y añadir de forma discreta, sin reemplazar el archivo completo de firmas local.

---

## 🚀 Cómo funciona
1. Lucky Defender ejecuta un script de actualización (`update.ps1` o `update.bat`).
2. El script descarga este archivo `new_hashes.txt` desde GitHub.
3. Los nuevos hashes se insertan automáticamente en la sección `[HASHES]` de `signatures.txt`.
4. El motor escanea el sistema y elimina cualquier archivo infectado que coincida.

---

## 📂 Contenido
- `new_hashes.txt` → archivo con las firmas nuevas que se añaden al motor.
- Ejemplo de integración en PowerShell:
  ```powershell
  Invoke-WebRequest -Uri "https://raw.githubusercontent.com/Tubers53/New_hashes_LuckyDefender/main/new_hashes.txt" -OutFile ".\new_hashes.txt"
