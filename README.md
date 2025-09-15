# **Workshop Booking**

> This website is for coordinators to book a workshop(s), they can book a workshop based on instructors posts or can propose a workshop date based on their convenience.


### Features
* Statistics
    1. Instructors Only
        * Monthly Workshop Count
        * Instructor/Coordinator Profile stats
        * Upcoming Workshops
        * View/Post comments on Coordinator's Profile
    2. Open to All
        * Workshops taken over Map of India
        * Pie chart based on Total Workshops taken to Type of Workshops.

* Workshop Related Features
    > Instructors can Accept, Reject or Delete workshops based on their preference, also they can postpone a workshop based on coordinators request.

__NOTE__: Check docs/Getting_Started.md for more info.

---

## UI/UX Enhancement Overview
This iteration focuses on improving readability, mobile usability, and visual hierarchy while keeping the existing structure and routes intact.

### What changed (high-level)
- Refined base layout (`workshop_app/templates/workshop_app/base.html`) and safe toastr messaging.
- Consistent form styling via a reusable `add_class` filter (`workshop_app/templatetags/custom_filters.py`).
- Improved login, register, and profile edit pages for clarity and mobile ergonomics.
- Subtle visual polish in `base.css` (spacing, shadows, table readability).

### Design principles used
- Clarity over clutter: emphasize primary actions and reduce visual noise.
- Consistency: unify spacing, typography rhythm, and component styling.
- Mobile-first: ensure comfortable tap targets and legible inputs on small screens.
- Feedback: show success/error messages clearly and accessibly.

### Responsiveness approach
- Leverage Bootstrap grid/utilities already present.
- Ensure form fields use `.form-control` and buttons use full-width where appropriate on mobile.
- Use responsive containers and `.table-responsive` wrappers for wide tables.

### Trade-offs
- Slightly increased CSS and DOM to improve clarity (minimal impact on load time).
- Kept Bootstrap 4 stack; avoided heavier JS frameworks to preserve performance and scope.

### Challenges and approach
- Avoiding template/JS interpolation conflicts in message rendering: switched to a data-attribute approach and a tiny, safe JS to trigger Toastr.
- Keeping layout changes minimal yet impactful by focusing on typography, spacing, and component hierarchy.

---

## Setup Instructions

### Prerequisites
- Python 3.8+
- pip / virtualenv
- PostgreSQL (or SQLite for local testing)

### Local development
```bash
# clone
git clone https://github.com/FOSSEE/workshop_booking.git
cd workshop_booking

# optional: create venv
python -m venv .venv
. .venv/Scripts/activate  # Windows PowerShell: .venv\Scripts\Activate.ps1

# install deps
pip install -r requirements.txt

# database setup (SQLite by default works out of the box)
python manage.py migrate

# create superuser (optional)
python manage.py createsuperuser

# run
python manage.py runserver
```

If using PostgreSQL, create a DB and configure credentials in `workshop_portal/settings.py` or via `local_settings.py`.

---

## Screenshots (Before/After)
Screenshots are stored in `docs/screenshots/`.

Drive Link: https://drive.google.com/drive/folders/1a4-7JdKosfNAmLFU8FVJLLCZOlMH33z_?usp=sharing

---

## Submission
- Push your changes to a public GitHub repository (fork or new repo).
- Ensure progressive commits with clear messages.
- Email the repository link to pythonsupport@fossee.in.

---

## Notes on Originality
Changes prioritize maintainability and incremental improvements. The code is intentionally minimal, readable, and respectful of the existing architecture.
