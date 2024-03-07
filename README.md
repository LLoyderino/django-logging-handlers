# Django logging handlers

Django logging handlers is a collection of handlers for logging messages to various services, such as Telegram, Slack, Discord, and more.

![Static Badge](https://img.shields.io/badge/Code_style-Google-blue)
![Static Badge](https://img.shields.io/badge/Commit_style-Conventional-fe5196)

## Quick start

1. Install package

```bash
pip install django-logging-handlers
```

2. Add `django-logging-handlers` to your INSTALLED_APPS

```python
INSTALLED_APPS = [
    "django_logging_handlers",
]
```

3. Register the handlers to your logging settings

```python
LOGGING = {
    "version": 1,
    "disable_existing_loggers": False,
    "handlers": {
        "telegram": {
            "level": "ERROR",
            "class": "django_logging_handlers.handlers.TelegramHandler",
            "token": "<telegram bot token>",
            "chat": "<chat id>",
            "message": "", # optional: additional message, blank by default
            "file_name": "project_name", # optional: file name, defaults to "traceback.html"
        },
    },
    "loggers": {
        "django.request": {
            "handlers": ["telegram"],
            "level": "ERROR",
            "propagate": True,
        },
    },
}
```

## Live Features

- Telegram

## Planned features

- Slack
- Discord
