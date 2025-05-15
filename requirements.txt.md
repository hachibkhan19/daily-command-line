# How to Move installed single file in requirements.txt from terminal command
```
pip freeze | grep django-celery-beat >> requirements.txt
pip freeze | grep (package-name) >> requirements.txt
```
