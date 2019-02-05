# Django-form
Just creating form with django

Add 'keep' to your INSTALLED_APPS setting like this:

INSTALLED_APPS = [
    ...
    'keep',
]
Add STATIC_ROOT, STATIC_URL, MEDIA_ROOT, MEDIA_URL to your setting like this:

STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
STATIC_URL = '/static/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
MEDIA_URL = '/media/'
Include the media URLconf in your project urls.py like this:

from django.conf.urls.static import static
from django.conf import settings
urlpatterns = [
    ...
] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
Include the keep URLconf in your project urls.py like this:

path('keep/', include('keep.urls')),
Create the keep models like this:

python manage.py migrate
Start the development server like this:

python manage.py runserver
Visit http://127.0.0.1:8000/keep/ to start keeping your data.
