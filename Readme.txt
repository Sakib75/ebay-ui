1. Install node package modules
 - move to "client" directory and run "npm install" command
 - move to "server" directory and run "npm install" command

2. Database configuration
 - move to "server" directory
 - open .env file and do configuration

3. Register client and server services
 3.1 client service
  - move to "/etc/systemd/system"
  - sudo vim chart-client.service
  - copy and paste the chart-client.service content (file attached)
  - IMPORTANT:
    please check the "ExecStart" and "WorkingDirectory"

    ExecStart=/usr/local/bin/npm start
    WorkingDirectory=/home/ubuntu/Charts-and-Tables-for-Data-Visualization-from-SQL-table/client

    You can check the "npm" location with "which npm" command. For above case, npm is located at "/usr/local/bin/npm"
 
 3.2 server service
  - move to "/etc/systemd/system"
  - sudo vim chart-server.service
  - copy and paste the chart-server.service content (file attached)
  - please check the "ExecStart" and "WorkingDirectory"

4. Start services
  - sudo systemctl start chart-client.service
  - sudo systemctl start chart-server.service
