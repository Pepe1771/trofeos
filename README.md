# Troféus NFC · PrismaPrint 3D

Cada troféu lleva una etiqueta NFC con un enlace `https://trofeos.tudominio.pt/?id=CODIGO`.
Al leerla se abre la página del troféu con el ganador, el evento y las fotos.

## Archivos
- `index.html` – página pública del troféu (português). Soporta pódio (medalla de oro/plata/bronce) y participação (distintivo "Participante").
- `gestor.html` – TU panel (español): crear competiciones, generar códigos, importar atribuciones del cliente y publicar.
- `atribuir.html` – página para el CLIENTE (português): atribuir cada troféu a su ganador desde el móvil.
- `dados/CODIGO.json` – datos de cada troféu.
- `fotos/CODIGO/` – fotos de cada troféu.
- `logos/` – logos de los clientes.
- Ejemplos: `?id=exemplo1` (pódio), `?id=exemplo3` (participação), `?id=exemplo2` (resultados em breve).

## Flujo de trabajo
1. **Tú** (gestor.html → Nueva competición): nombre, fecha, lugar, plantilla del cliente y, por categoría, cuántas piezas de PÓDIO y cuántas de PARTICIPAÇÃO. Se genera un código largo secreto (etiqueta) y un número corto 0001, 0002… por pieza.
2. **Tú**: "Descargar paquete para GitHub" y súbelo. Graba cada etiqueta (botón "Copiar enlace") y marca el número 0001… en la base del troféu. Entrega los troféus en blanco.
3. **Tú**: "Enviar al cliente (atribución)" descarga un archivo de la competición. Mándaselo al cliente junto con el enlace `…/atribuir.html`.
4. **El cliente** (atribuir.html, português, cualquier móvil): abre el archivo, ve las piezas por su número, y a cada troféu le pone el ganador (y el lugar, si es de pódio). En Android puede acercar el troféu para seleccionarlo. Al terminar, "Exportar" y te envía el archivo + las fotos.
5. **Tú** (gestor.html → abrir competición → "Importar atribuciones del cliente"): se cargan todos los nombres. En cada pieza, "Rellenar" ya trae el nombre; añades la foto y publicas. Descarga el .zip y súbelo a GitHub.

## QR de respaldo
En cada competición, "QR para pegatinas" genera una hoja A4 (o PNG sueltos) con un QR por pieza y su número debajo. El QR lleva el mismo enlace que la etiqueta NFC. Imprime al 100 % en papel adhesivo y pega cada QR en la pieza con el mismo número. Para trofeos reales, usa siempre el subdominio definitivo: un QR impreso no se puede cambiar.

## Importante
- El repositorio es público: todo lo subido (nombres y fotos) se puede ver. Solo con consentimiento (menores: de su tutor).
- `index.html`, `gestor.html` y `atribuir.html` llevan `noindex`, y hay `robots.txt`, para que no salgan en Google.
- Las competiciones se guardan en el navegador del gestor: exporta copia de seguridad a menudo (no la subas a GitHub).
- Renueva siempre el dominio: si caduca, dejan de funcionar todos los troféus.
