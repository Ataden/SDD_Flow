WARNING! These servers may be already running (using hot reload), always check before you start new:
    - backend: http://127.0.0.1:8000/ (uvicorn, start with activating backend/venv first)
    - frontend: http://127.0.0.1:3000/ 
    - ...
So check with `ss` if there are processes on ports 8000, 3000.
If some of the servers are not running, start them but after you finish ALWAYS kill all the processes you started.

Backend logs are available by http://localhost:8000/logs/?n=10 (last 10 lines, adjust if needed)