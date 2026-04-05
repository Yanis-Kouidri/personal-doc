# PDF

## Scanned PDF

To reduce PDF size of scanned papers, add OCR and realign pages use [ocrmypdf](https://github.com/ocrmypdf/ocrmypdf)

For a **scanned** PDF, to reduce size, clean and realign pages, rotate-pages and add french OCR :

```bash
ocrmypdf --clean --deskew --optimize 3 --jbig2-lossy --rotate-pages -l fra --jpeg-quality 10 scanned.pdf output.pdf
```

You can play with `--jpeg-quality` to select a trade-off between quality and size from 1 (lowest size) to 100 (better quality)

You have to install tesseract-ocr-fra

```bash
sudo apt install tesseract-ocr-fra
```

For a **regular** PDF, to reduce size :

```bash
ocrmypdf --skip-text --optimize 3 regular.pdf output.pdf
```
