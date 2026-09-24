
---

# To-Do List
**Submission for "4-511 DSC 4156"**

This is a beginner-friendly Django web application that functions as a classic To-Do List. Built using Django 6.1.1 and styled with Bootstrap 5, it allows users to manage a simple list of tasks through a clean, intuitive web interface. 

## 🎯 Key Features

*   **Add Tasks:** Users can add new to-do items using a search-style form embedded directly in the top navigation bar.
*   **View Tasks:** The homepage displays all tasks in a clean table format.
*   **Complete/Uncomplete Tasks:** 
    *   Click the **"Strike"** button to mark a task as completed (visually crossing it out using an `<s>` tag).
    *   Click the **"Unstrike"** button to revert it back to active.
*   **Delete Tasks:** Every task has a dedicated **"Delete"** button to remove it entirely from the database.
*   **About Page:** A simple static page displaying a brief greeting (*"Tungkol saakin"*) and the creator's name (*"strelitzia"*).

## 🛠️ Technical Stack & Architecture

*   **Backend Framework:** Django 6.1.1 (Python)
*   **Database:** SQLite (`db.sqlite3`)
    *   Utilizes a single `List` model with two fields:
        *   `item`: A character field (max length 200) for the task description.
        *   `completed`: A boolean field tracking whether the task is done (defaults to `False`).
*   **Frontend:** Standard Django HTML templates (`base.html`, `home.html`, `about.html`) styled via a Bootstrap 5 CDN.
*   **Forms:** Uses Django's `ModelForm` (`ListForm`) to easily validate and save new task entries from the frontend UI to the database.
*   **Routing:** The URLs are mapped cleanly to specific Python views:
    *   `/` -> `home` (handles both displaying tasks and adding new ones via POST)
    *   `/about/` -> `about`
    *   `/delete/<id>/` -> `delete`
    *   `/strike/<id>/` -> `strike`
    *   `/unstrike/<id>/` -> `unstrike`

## 🗂️ Project Structure

```text
MyFirstDjango/
├── MyFirstDjango
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── todo_list
│   ├── migrations
│   │   ├── __init__.py
│   │   └── 0001_initial.py
│   ├── templates
│   │   ├── about.html
│   │   ├── base.html
│   │   └── home.html
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── db.sqlite3
├── initial.txt
├── manage.py
└── requirements.txt
