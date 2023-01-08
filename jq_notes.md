[Unit]
Description=Gunicorn instance for a simple hello world app
After=network.target

[Service]
User=ec2-user
Group=www-data
WorkingDirectory=/home/ec2-user/helloworld
ExecStart=/home/ec2-user/helloworld/gunicorn -b localhost:8000 app:app
Restart=always

[Install]
WantedBy=multi-user.target