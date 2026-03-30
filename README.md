# ArtOfSree Django Art Store Project

## Quick Start (Development)
1. `pip install -r requirements.txt`
2. `python manage.py migrate`
3. `python manage.py collectstatic --noinput`
4. `python manage.py runserver`

**Static CSS Fix**: 
- ai_website/ now uses absolute paths `./ai_website/css/` etc. Works on zip/extract/rename.
- Django templates use `{% static %}` + cache-bust (?v=6).
- Clear browser cache (Ctrl+Shift+R) for new styles.

## Deployment Zip/Extract Instructions
1. Run `python manage.py collectstatic --noinput` (populates staticfiles/).
2. Zip entire project **including static/ and staticfiles/**.
3. Extract to new folder: ai_website/index.html opens with new styles (no relative path breaks).
4. For Django: `python manage.py runserver` serves /static/ correctly.
5. Prod: Set AWS env vars, deploy to EC2/Heroku, S3 handles static/media.

## Why Previous CSS Broke
- Relative paths in ai_website/ failed on folder rename/move.
- Browser cached old CSS.
- Fixed with absolute paths + cache-bust params.

Open http://127.0.0.1:8000 for Django site.
