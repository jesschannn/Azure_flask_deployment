# azure_flask_deployment
Introducing Flask and Azure Deployment

Deployed URL: [Jessica504 Flask](jessica-504-flask.azurewebsites.net)
# How to Set Up and Connect Google Shell to Github Repo

1. Create a Github Repository and git clone the URL of the Github repository into a your Google Shell by using the code below.
```
git clone <url>
```
2. In your Google shell, create an app.py file. In this app.py file, you want to import ```flask```, ```render_template```, and ```pandas```. Within this app.py file, there are ``` @app.route``` that can be defined. You want to create an ```@app.route``` for every "page" that you want your application to have. An example of the structure is:
```
@app.route('/')
def index():
    return render_template('base.html')
```
3. In your Google shell, create a templates folder. Within the templates folder, I set up three html files named ```about.html```, ```base.html```, and ```data.html``` for each of the three "pages" I plan to include in my application. In the html files, you can include a head, body, and footer where you can customize the title, content, and styling of your application.
4. In your Google shell, upload the data file that you used.
5. In your Google shell, create a ```requirements.txt file```. Inside the file, type in what you decided to import. In my case, I typed in "python-dotenv", "pandas", "flask", and "gunicorn".
6. Save everything.
7. In the terminal, type in "python app.py". Click on the website that is returned and determine if any other changes need to be made.
8. Use ```git add .```, ```git commit -m '<message>'```, and ```git push``` to push all of the changes in the Google shell to the Github repository.

# How to Set Up and Deploy Azure App Service
1. In the Google shell terminal, type in ```curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash.```
2. Type in ```az```.
3. Type in ```az login --use-device-code``` to connect a Microsoft Azure account to Google shell.
4. A separate window will open to a Microsoft page. Copy and paste the code from the Google shell into the Microsoft page and confirm that you want to authenticate. Once authentification is complete, you can go back to the Google shell terminal.
5. Type ```az account list --output table``` into the shell terminal.
6. Type ```az account set --subscription <subscriptionId>```. Replace "subcriptionId" with the subscriptionId under the desired account that was listed under the ```az account list --output table``` command.
7. Log into Azure Web Portal and create a new resource group.
8. In the Google shell terminal, type in ```az group list```
9. Type in ```az webapp up --name- <resource group> -flask --runtime PYTHON:3.9 --sku B1```
10. A resource group will be created and zip deployment will begin.
11. Go to App Services to track the deployment process.
12. Once deployment is complete, a link to the Azure domain will show on the App services page and in the Google shell terminal.
13. Since an Azure folder will be created in the Google shell, use ```git add .```, ```git commit -m '<message>'```, and ```git push```.
