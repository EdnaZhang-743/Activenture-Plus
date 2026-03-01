**README**


**Project Title**

Activenture Plus – South Island Free Community Fitness Platform

COMP639 · Studio Project · Semester 2, 2025 · Group: Gold


**Project Overview**

Activenture Plus is a web-based event management system for a fictional community initiative that runs free weekly fitness events (5 km runs, walks, cycling, etc.). It streamlines logistics and improves the experience for participants, volunteers, and admins.

This repository provides:

- Volunteer coordination
- Participant registration and tracking
- Event creation and scheduling
- Race timing and results import (CSV) with automatic ranking
- Helpdesk request management with assignment and notifications


**Key Features**

✅ Authentication & Roles

- Secure login/session handling
- Platform roles: Participant, Support Technician, Super Admin
- Group roles: Manager, Volunteer, Member

✅ Event Management

- Create/edit/delete events (role-based)
- Date/time/type/location/capacity + search/filter
- Clear admin/manager permissions

✅ Volunteer & Membership

- Group manager tools for members/volunteers
- Volunteer activity/history and statistics

✅ Timing & Results

- CSV template download, validate-only mode, and import
- Import policies: Standard Import (add-only), Overwrite Existing (replace matches and add new)
- Multiple time formats supported: HH:MM[:SS], YYYY-MM-DD HH:MM[:SS], DD/MM/YYYY HH:MM[:SS]
- UI displays durations consistently as HH:MM:SS

✅ Helpdesk

- Request lifecycle (new/assigned/blocked/solved)
- Auto/manual assignment, priorities (urgent/medium/low)
- Notifications on assignment/unassignment/escalation

✅ Notifications

- Global inbox with read/unread/delete/bulk actions
- Live navbar badge refresh

✅ Design & Usability

- Bootstrap 5 responsive UI
- Polished top navigation and dropdown UX


**Technology Stack**

- Backend: Python (Flask)
- Frontend: HTML, CSS (Bootstrap 5), JavaScript
- Database: MySQL (mysqlclient)
- Hosting: PythonAnywhere
- Version Control: GitHub


**Project Structure**

COMP639_Project_2_Gold/
└── activenture/
    ├── __init__.py
    ├── analytics.py
    ├── assign_request.py
    ├── auth.py
    ├── connect.py                 # local DB credentials (create per developer)
    ├── db.py
    ├── events.py
    ├── group_manager.py
    ├── groups.py
    ├── helpdesk.py
    ├── noti.py
    ├── participant.py
    ├── profile.py
    ├── results.py
    ├── search.py
    ├── super_admin.py
    ├── support_tech.py
    ├── user.py
    ├── util.py
    ├── validation.py
    ├── static/
    │   ├── css/
    │   └── images/
    └── templates/


**Features Implemented**

✅ Authentication & Role-based Access

- Clear platform/group role-driven navigation and permissions

✅ User/Group/Event Management

- Super Admin/Support Technician broad privileges (admin bypass respected)
- Group creation/approval/editing, event creation/management

✅ Timing & Results

- CSV template/validation/import
- Import modes: Standard Import (add-only), Overwrite Existing (replace + add)
- Summary/ranking/averages/best/slowest time displays

✅ Helpdesk & Notifications

- Assignment/unassignment/priority change notifications
- Forced notification creation for critical actions with DB commits
- Category normalization (event/group/volunteer/system)


**Installation & Setup**

Prerequisites

- Python 3.10+
- MySQL 5.7+ / 8.0+
- pip

1) Clone Repository

```
git clone <your-repo-url>
cd COMP639_Project_2_Gold
```

2) Virtual Environment

```
python -m venv .venv
.venv\Scripts\activate      # Windows
source .venv/bin/activate    # macOS/Linux
```

3) Install Dependencies

```
pip install -r requirements.txt
```

4) Database Configuration

Create `activenture/connect.py` with your local MySQL credentials (example):

```python
dbuser = 'your_mysql_username'
dbpass = 'your_mysql_password'
dbhost = 'localhost'
dbname = 'activenture_plus'
dbport = 3306
```

5) Run the Application

From the project root (e.g., `COMP639_Project_2_Gold`):

```
python run.py
# Open http://127.0.0.1:5000
```


**Deployment on PythonAnywhere (Summary)**

1) Clone repo and set up virtualenv

2) Create Web App (Manual configuration) and bind WSGI to `activenture.app`

3) Create MySQL on the Databases tab → add `activenture/connect.py` with server creds

4) Map Static Files (`/static` → `activenture/static`)

5) Reload


**Testing Accounts**

Use course-provided or demo accounts as appropriate for your environment.


**License**

This project is for teaching and academic demonstration purposes only.



**Image References**

Events Images

- 5km_run.jpg — Getty Images. (n.d.). Starting line [Photograph]. Getty Images. https://media.gettyimages.com/id/185206979/photo/starting-line.jpg?s=2048x2048&w=gi&k=20&c=Gn5HZaO4v0SpxbwVFofeX6Lg-vy01NS3-PF8VfavFlE=
- cycling.jpg — Eventfinda. (n.d.). Event image [Photograph]. Eventfinda. https://cdn.eventfinda.co.nz/uploads/events/transformed/1378368-607961-35.jpg?utm_source=chatgpt.com
- cycling2.jpg — Unsplash. (n.d.). Group of bicycle riders on road [Photograph]. Unsplash. https://unsplash.com/photos/group-of-bicycle-riders-on-road-GkP6Sbqh1xI
- fun_run.jpg — Wixstatic. (n.d.). Fun run image [Photograph]. Wixstatic. https://static.wixstatic.com/media/a52e9d_6c271b2b8b1d4a388a9769ffb9dd5f01~mv2.jpg?utm_source=chatgpt.com
- marathon.jpg — Mercy Hospice. (n.d.). Running marathon [Photograph]. Mercy Hospice. https://mercyhospice.org.nz/wp-content/uploads/akl-thon-2021-social-124-2.jpg
- park_walk.jpg — Wandering World. (n.d.). Nearly at the end of the Hooker Valley Track [Photograph]. Wandering World. https://wandering.world/wp-content/uploads/2016/08/Nearly-at-the-end-of-the-Hooker-Valley-Track-768x512.jpg?utm_source=chatgpt.com
- swimming.jpg — Unsplash. (n.d.). Person in swimming goggles in water [Photograph]. Unsplash. https://unsplash.com/photos/person-in-swimming-goggles-in-water-bGOBoZorNoQ
- coming_soon.jpg — Dreamstime. (n.d.). Hand turns cube... coming soon to now [Photograph]. Dreamstime. https://www.dreamstime.com/hand-turns-cube-changes-expression-coming-soon-to-now-image370301386

Home Page Images

- hero_home.jpg — Pixabay. (n.d.). Marathon/running sports [Photograph]. Pixabay. https://pixabay.com/photos/running-marathon-sports-runners-6660187/
- main_home.jpg — Unsplash. (n.d.). A group of people running down a street [Photograph]. Unsplash. https://unsplash.com/photos/a-group-of-people-running-down-a-street-D0LUtrVkxgo
- about_home.jpg — Dignity Health. (n.d.). Volunteer group classes [Photograph]. Dignity Health. https://www.dignityhealth.org/content/dam/dignity-health/arizona/images/volunteer%20group%20classes.jpg
- default.png — OpenAI. (n.d.). Default image (AI-generated with ChatGPT) [Digital image]. OpenAI.