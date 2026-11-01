# WesternUEvents

A web app for collecting campus events at Western University into one shared calendar, with a weekly email digest and forms for students to suggest events and sources. Built with Flask in early 2016.

> Archived: no longer maintained. The client cancelled the project before it was finished.

## What it does

- **Calendar** (`/`): a FullCalendar month/week/day view, intended to be fed from a JSON events endpoint (`/api/events`, still a stub).
- **Share** (`/share`): WTForms form with reCAPTCHA for submitting an event title and URL.
- **Email** (`/email`): embedded Mailchimp signup for a weekly events newsletter.
- **Data model**: SQLAlchemy models for events, groups (event sources), categories, emails and user-suggested events and groups awaiting review, with sqlalchemy-migrate scripts (`db_create.py`, `db_migrate.py`, `db_upgrade.py`, `db_downgrade.py`).
- Development and production modes switched through a `config.py` (not committed).

The plan was to scrape event listings from campus groups and sites with BeautifulSoup and publish them as JSON feeds per source. The scrapers were not written before the project was cancelled.

## Tech stack

Python, Flask (2016-era), Flask-SQLAlchemy, Flask-WTF, sqlalchemy-migrate, Jinja2, FullCalendar, Moment.js, jQuery, Mailchimp.

## Running

This likely no longer runs without changes: it uses the removed `flask.ext.*` import style and needs a `config.py` defining `ENV`, `SQLALCHEMY_DATABASE_URI`, `SQLALCHEMY_MIGRATE_REPO` and reCAPTCHA settings.

## Unfinished / ideas

From the original notes:

- Scraping scripts and a JSON feed per source
- Search and category filters on the calendar
- Individual event pages
- Facebook group integration
- Review workflow for suggested sources, events and links, with each source added as a Mailchimp interest group

## Context

Built January-March 2016 as client work for an events calendar serving Western University students. The client cancelled the project, and it stopped at the prototype stage.
