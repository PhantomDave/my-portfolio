# CV source

`cv.html` is the print-ready source for `public/Davide_Rodo_CV.pdf`.

Edit the HTML, then regenerate the PDF with headless Chrome:

```bash
chromium --headless --no-pdf-header-footer \
  --print-to-pdf=../public/Davide_Rodo_CV.pdf cv.html
```
