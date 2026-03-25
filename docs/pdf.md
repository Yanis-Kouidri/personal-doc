# PDF

## Scanned PDF

To reduce PDF size of scanned papers, add OCR and realign pages use [ocrmypdf](https://github.com/ocrmypdf/ocrmypdf)

Reduce size, clean and realign pages, rotate-pages and add french OCR :

```bash
ocrmypdf ocrmypdf --clean --deskew --optimize 3 --jbig2-lossy --rotate-pages -l fra --jpeg-quality 10 input.pdf output.pdf
```

You can play with `--jpeg-quality` to select a trade-off between quality and size from 1 (lowest size) to 100 (better quality)

You have to install tesseract-ocr-fra

```bash
sudo apt install tesseract-ocr-fra
```
