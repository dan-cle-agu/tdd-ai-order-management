# Local Development Setup

If you prefer to run the project locally on your own computer, first ensure that you have installed:

- Python (version 3.13 preferred to match the Workspace environment, though previous versions may work)
- A code editor, such as Visual Studio Code

Then perform the following steps:

Clone the starter repository from GitHub and navigate to the project root (starter/ folder):

```
git clone https://github.com/udacity/cd14599-project-starter
cd cd14599-project-starter\starter
```

Create and activate a virtual environment:
```
python -m venv venv
.\venv\Scripts\Activate.ps1
```

Install dependencies from the requirements.txt file located in the backend folder:

```
pip install -r backend\requirements.txt
```

Run the Flask app from the project root (the folder containing the backend folder):
```
python -m backend.app
```

Open your web browser and go to http://127.0.0.1:5000.

# Notes on Local Setup

Flask runs in debug mode with autoreload enabled. Save changes to any file, and the server will restart automatically.

If port `5000` is already in use on your machine, open `backend/app.py` and change the port parameter in `app.run()` (e.g., to `8000` or `8080`).