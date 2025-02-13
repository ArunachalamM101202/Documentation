# **Deploy a Python Streamlit App to Streamlit Cloud**

This guide walks you through **writing a Streamlit app**, **connecting to GitHub**, and **deploying it to Streamlit Cloud** in simple steps.

---

## **📌 Step 1: Write a Simple Streamlit App in VS Code**
### **1️⃣ Install Python & Streamlit**
Before writing code, ensure **Python** is installed. Download it from:  
🔗 [Python Official Website](https://www.python.org/downloads/)

Next, open **VS Code**, launch a terminal using Terminal-> New Terminal
![Streamlit Deployment](images/new_terminal.png)


Create a virtual environment in python using [Creating Python Virtual Environment](https://arunachalamm101202.github.io/Documentation/guide/create-venv/) and install Streamlit using the following command:

```bash
pip install streamlit
```

### **2️⃣ Create a Python File**
- Create a new folder for your project (File-> Open Folder).
![Streamlit Deployment](images/new_folder.png)

- Create a folder in your local machine
![Streamlit Deployment](images/local_folder.png)

- Inside the folder, create a Python file, e.g., `app.py`.
![Streamlit Deployment](images/create_app.png)

- Add this simple Streamlit app:

```python
import streamlit as st

st.title("🚀 My First Streamlit App")
st.write("Hello, Streamlit Community!")
```

After you add your python code, you need to setup a requirements.txt file which contains the libraries needed to install before for the web app to work. To generate a requirements.txt, do the following steps:

- Open ChatGPT or Claude
- Paste the following prompt. Replace with your python code
```
Generate a requirements.txt file for the following python code without any versions for the libraries:

Code:

import streamlit as st
st.title("🚀 My First Streamlit App")
st.write("Hello, Streamlit Community!")
```

The LLM will generate the names of all the required libraries in requirements.txt needed to deploy your application.
```
streamlit
```

![Streamlit Deployment](images/requirements.png)

Go to VSCode, and Create a file named `requirements.txt` and add the libraries provided by ChatGPT/Claude and save the file.

![Streamlit Deployment](images/req_file_generated.png)

### **3️⃣ Run the App Locally**
To test the app before deployment, run:

```bash
streamlit run app.py
```
![Streamlit Deployment](images/running.png)

![Streamlit Deployment](images/running_web.png)

This should open a local webpage showing your app. If everything works, proceed to the next step. Ensure your virtual environment is running before executing the streamlit command

---

## **📌 Step 2: Upload Your Code to GitHub**
### **1️⃣ Create a GitHub Account**
🔗 [Sign up on GitHub](https://github.com/) (if you don't have an account).

### **2️⃣ Initialize a Git Repository in VS Code**
- Open VS Code terminal (Terminal->New Terminal) in your project folder.
- Run the following commands to initialize Git:

```bash
git init
git add .
git commit -m "Initial commit"
```

![Streamlit Deployment](images/git_command_1.png)

### **3️⃣ Create a GitHub Repository**
- Go to [GitHub](https://github.com) → Login to your account ->
![Streamlit Deployment](images/github_main.png)

Click your profile at the top right -> Select "Your Repositories" 
![Streamlit Deployment](images/github_your_repo.png)


Click **New Button** to create new repository.
![Streamlit Deployment](images/github_new.png)


- Give it a name, e.g., `my-test-app`.
- Select **Public or Private** Private keeps the repository and the code within it hidden.
- Select `Python` from the drop down of `.gitignore` template. This is needed to ensure unwanted python library files are not added to github.
![Streamlit Deployment](images/github_setup.png)

- Click **Create Repository**.
![Streamlit Deployment](images/create_repo.png)

### **4️⃣ Connect VS Code to GitHub & Push Code**
- Back in VS Code terminal, run:

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_APP_NAME.git
git branch -M main
git pull origin main --rebase
git push -u origin main
```
![Streamlit Deployment](images/github_pull_push.png)
The above commands will first connect to your repository in Github, fetch the latest code from your github repository and update it in your local machine's VS Code, and then push the code changes you made to the repository in Github.


Now your code is on GitHub! ✅

---

## **📌 Step 3: Deploy to Streamlit Cloud**
### **1️⃣ Sign in to Streamlit Cloud**
- Go to **Streamlit Community Cloud**:  
  🔗 [https://streamlit.io/cloud](https://streamlit.io/cloud)
- Click **"Sign in with GitHub"**.
- Authorize Streamlit to access your GitHub account.

### **2️⃣ Create a New App**
- Click **"Create App"** at the top right.
![Streamlit Deployment](images/create_app_streamlit.png)

- Select **"Deploy a public app from GitHub"**
![Streamlit Deployment](images/streamlit_github.png)

- Select your GitHub repository (`streamlit-app`).
- Choose the `main` branch.
- Select the python file `app.py`
![Streamlit Deployment](images/streamlit_setup.png)


- Give a good nice domain name for the app, for example `my-test-app-1234`

## **📌 Step 4: Add Python version and API Keys & Secrets (If Needed)**

- Click **Advanced settings**:
- Set **Python Version** (e.g., `3.11` or `3.12`).
  - If your app requires external API keys, you can **add secrets** here.

In Advanced Settings of Streamlit Deployment, add all your secrets (API Keys etc from your .env file) in a toml format. Here is an example:

```toml
OPENAI_API_KEY="your-openai-api-key"
```
Click Save after adding the secrets in advanced settings

![Streamlit Deployment](images/secrets.png)

## **📌 Step 5: Finalize & Share**
- Click **Deploy** and wait for Streamlit to set up your app.
- Once done, Streamlit will provide a **live URL** to share your app.

Example:  
🔗 [https://my-test-app-1234.streamlit.app](https://my-test-app-1234.streamlit.app)
![Streamlit Deployment](images/deployed_app.png)
---

## **🎉 Congratulations!**
You have successfully:
✅ Written a Streamlit app in VS Code  
✅ Pushed it to GitHub  
✅ Deployed it on Streamlit Cloud  
✅ Added secret keys securely  

Now, you can **share your app** with anyone! 🚀


