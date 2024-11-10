# anglr-offline-install
Angular Offline Install

Installing Angular CLI offline requires you to first download the Angular CLI package and its dependencies on a computer with internet access, then transfer them to the offline computer. Here’s a step-by-step guide:

### Step 1: Prepare on an Online Computer

1. **Install Node.js on the Online Computer**
   - Go to [Node.js](https://nodejs.org/) and download the latest LTS version.
   - Install Node.js on your computer. This will also install npm (Node Package Manager), which is required for Angular CLI.

2. **Create a Directory to Download the Angular CLI Package**
   - Open a terminal and create a directory to store Angular CLI and its dependencies. For example:
     ```bash
     mkdir C:\angular-cli-offline
     ```

3. **Download Angular CLI Package and Dependencies**
   - In the terminal, navigate to this directory:
     ```bash
     cd C:\angular-cli-offline
     ```
   - Run the following npm command to download Angular CLI and all of its dependencies without installing them globally:
     ```bash
     npm install @angular/cli --global-style --no-bin-links --prefix ./angular-cli
     ```
   - This will download the Angular CLI package and its dependencies into the `C:\angular-cli-offline\angular-cli` directory without actually installing it globally on this computer.

4. **Package the Directory for Transfer**
   - After npm finishes downloading the dependencies, copy the `angular-cli` directory to a USB drive or any other medium to transfer it to the offline computer.

### Step 2: Set Up Node.js on the Offline Computer

1. **Install Node.js**
   - Using the Node.js installer you downloaded earlier, install Node.js on the offline computer. Ensure you have the same version as on the online computer.

2. **Configure npm to Use the Offline Angular CLI Package**
   - Copy the `angular-cli` directory from the USB drive to a folder on the offline computer, for example, `C:\angular-cli-offline`.

3. **Install Angular CLI Offline**
   - Open a terminal (Command Prompt or PowerShell) on the offline computer and navigate to the location of your Angular CLI package:
     ```bash
     cd C:\angular-cli-offline\angular-cli
     ```
   - Install Angular CLI globally from the local folder:
     ```bash
     npm install -g --offline @angular/cli
     ```

### Step 3: Verify the Angular CLI Installation

1. **Check the Angular CLI Version**
   - Run the following command to ensure Angular CLI is installed correctly:
     ```bash
     ng version
     ```
   - You should see information about the installed Angular CLI version.

2. **Create an Angular Project Offline**
   - To ensure everything is set up properly, try creating a new Angular project:
     ```bash
     ng new my-offline-app --skip-install
     ```
   - Navigate to your new project folder:
     ```bash
     cd my-offline-app
     ```
   - Then install the project dependencies from your local `node_modules` cache:
     ```bash
     npm install --offline
     ```

### Summary

With this setup, you should be able to create, build, and serve Angular projects on your offline computer using Angular CLI.
