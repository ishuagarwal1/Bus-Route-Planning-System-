# BusRoute Website - written in C (free, no libraries)

- Backend + HTTP server + REST API: src/server.c, src/backend.c (C, raw sockets, Dijkstra routing)
- Database layer: src/db.c  -> text-file database in data/ (stops.txt, routes.txt, bookings.txt)
- Frontend website: public/ (HTML, CSS, JavaScript) served by the C server

## Step 1: one-time free setup
- Windows: install MSYS2 (https://www.msys2.org), open "MSYS2 UCRT64" and run:
      pacman -S mingw-w64-ucrt-x86_64-gcc
  then add C:\msys64\ucrt64\bin to your Windows PATH and restart VS Code.
- Linux: sudo apt install gcc      macOS: xcode-select --install
- Check: gcc --version

## Step 2: run
- Double-click run.bat (Windows) or ./run.sh (Linux/macOS), OR
- In VS Code: File > Open Folder > this folder, press Ctrl+Shift+B.
Then open http://localhost:8080   (stop the server with Ctrl+C)

## API
GET /api/stops | /api/routes | /api/plan?from=1&to=10&by=distance|time|fare | /api/bookings
POST /api/bookings {passenger,from,to,by}    DELETE /api/bookings/:id
POST /api/stops, /api/routes  (header x-admin-key: admin123)
