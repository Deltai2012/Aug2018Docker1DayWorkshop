A bigger site
=============

Build a more real-world app that consumes external resources.

Choose from one of these two options to explore making http calls between containers:


Option 1: Build your app
------------------------

1. Fire up your favorite IDE.
2. Build a quick sample website.
3. Build a quick api.
4. Build a Dockerfile for each.
5. Run the api container.
6. Get the IP address of the api container using `docker container list` and `docker container inspect --format "{{ .NetworkSettings.IPAddress }}" ...` replacing `...` with the container id or name.
7. Change the website's url to the api.
8. Run the website container.


Option 2: Build my app
----------------------

I have here a .net core back-end and a node front-end.  Use my app, and build and run these sites.

1. Open up `backend/Dockerfile` and add the content necessary to spin up the .net app.  You don't need to have .net installed to do so.

2. Open `frontend/Dockerfile` and add the content necessary to spin up the node app.

3. `docker build ...` the back-end container.

4. `docker run ...` the back-end container, directing traffic to port 5000.

5. Run `docker container list` and note the container id or name of the back-end container.

6. Run `docker container inspect --format "{{ .NetworkSettings.IPAddress }}" ...` replacing `...` with the container id or name to get the IP address of the back-end container.

7. Open `frontend/routes/index.js` and change the IP address on line 6 with the IP address of the back-end container, keeping the `http://` and `:5000`.

8. `docker build ...` the front-end container.

9. `docker run ...` the front-end container, directing traffic to port 3000.

10. Visit [http://localhost:3000/](http://localhost:3000/) to cast your vote.


Stretch goal (Windows only)
---------------------------

Can you run these as Windows containers?
