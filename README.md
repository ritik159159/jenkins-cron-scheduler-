# jenkins-cron-scheduler-
A Jenkins setup that integrates with GitHub and uses cron syntax to schedule automated jobs and test executions.

# Changing boot configuration 
By default, your Jenkins runs at https://localhost:8080/. This can be changed by editing jenkins.xml , which is located in your installation directory.

# Unlock Jenkins
C:\Program Files (x86)\Jenkins\secrets\initialAdminPassword


🛠️ Step-by-Step Jenkins Setup for Java + GitHub Auto Trigger

🔧 1. Install Required Plugins
        Go to Manage Jenkins → Manage Plugins → Available tab.

Search and install:
        GitHub plugin
        Git plugin
        GitHub Integration Plugin
        Generic Webhook Trigger Plugin (optional for advanced triggers)

🏗️ 2. Create a New Jenkins Job
        Go to Dashboard → New Item
        Enter a name (e.g., Java-Auto-Build)
        Select Freestyle project and click OK

📦 3. Configure Source Code Management
In the job config:

        Go to Source Code Management → Git
        Enter your GitHub repository URL
        Add credentials if the repo is private
        Verify Branch Name : */main || */master


🚀 4. Set Build Trigger
Scroll to Build Triggers

        Check GitHub hook trigger for GITScm polling

🧪 5. Define Build Steps
        Go to Build → Add build step → Execute shell || Execute Windows batch command

🌐 6. Configure GitHub Webhook
        Go to your GitHub repo → Settings → Webhooks
        Click Add webhook
        Payload URL: http://<your-jenkins-server>/github-webhook/
        Content type: application/json
        Trigger: Just the push event
        Click Add webhook


✅ 7. Test the Setup
        Push code to GitHub
        Jenkins should automatically trigger the job and execute your Java program
