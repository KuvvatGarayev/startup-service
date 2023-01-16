# startup-service

## running python on startup
https://stackoverflow.com/questions/24518522/run-python-script-at-startup-in-ubuntu

follow the steps in this video:
https://www.youtube.com/watch?v=-aKb-k8B8xo&t=378s

Step 1: create a service file under /etc/systemd/system/my-startup.service
Step 2: change the content to below, using sudo vi my-startup.service or sudo gedit my-startup.service
[Unit]
Description=Jetbot Startup Collision Avaidance

[Service]
ExecStart=/bin/bash -c 'python3 -u /home/jetbot/collision_avoidance.py'
WorkingDirectory=/home/jetbot/
Restart=always
User=jetbot

[Install]
WantedBy=multi-user.target

Step3: Enable the serive
sudo systemctl enable my-startup.service
