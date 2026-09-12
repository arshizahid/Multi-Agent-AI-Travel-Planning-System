To copy only the essential source code and configuration files (ignoring heavy directories like langgraph_env3 and .git), the cleanest and fastest method is to create a .tar.gz archive on your Windows machine, upload that single archive, and extract it on the VPS.

Run these steps in your Windows PowerShell:

1. Create a compressed archive containing only the required code files:
cd "C:\Users\zahid\Downloads\AI-Travel-Planning-System (langGraph and APIs)"
tar -czf project.tar.gz agents.py config.py custom_weather_mcp_server.py docker-compose.yml Dockerfile frontend.py graph.py mcp_client.py requirements.txt state.py .env .env_examples aviationstack-mcp

2. Upload the tiny archive via scp (it will transfer instantly):
scp -P 20078 project.tar.gz root@148.113.8.216:/opt/

3. Log into your VPS and extract it directly into your project directory:
ssh -p 20078 root@148.113.8.216
cd /opt/
mkdir -p AI-Travel-Planning-System
tar -xzf project.tar.gz -C AI-Travel-Planning-System/
cd AI-Travel-Planning-System/

###Edit the file in VPS
1.Open the file in Nano:Type the command to open your configuration file:
nano docker-compose.yml

2. Edit the content

3.Save your changes:
Press Ctrl + O, then press Enter to confirm and write the changes to the file.

4.Exit the editor:Press Ctrl + X to close Nano and return to your normal terminal prompt.