# Product Images Gallery

All product images extracted from `media/products/` (~60 images) and categories from `media/categories/` (12 images).

## View Gallery
Open `static/product_gallery.html` in browser - shows categories/products grids, search, modal zoom. Fully static, works on GitHub Pages/AWS S3/any host/zip extract.

## Structure
```
static/product_images/
├── products/    # All product jpg/webp (gowthamibrother.jpg etc.)
└── categories/  # Category images
```

Images load reliably (no MEDIA_URL issues). Deploy: push to GitHub (S3/AWS fix-ready), zip ok.

To serve in Django: `{% load static %}` `<img src="{% static 'product_images/products/gowthamibrother.jpg' %}" />`

Ready for production!
