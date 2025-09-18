# Azure DevOps Demo Generator Setup Guide

<img width="985" height="834" alt="image" src="https://github.com/user-attachments/assets/b5c75000-4b8f-43ef-bd6f-c51289139e18" />


This guide provides the steps to set up and run the Microsoft Azure DevOps Demo Generator on macOS, similar instructions can be followed for Windows and Linux 🛠️

## Prerequisites

Before you begin, ensure you have the following in place:

* **Azure DevOps Organization**: You must have an Azure DevOps organization with administrative permissions.
* **Third-Party Application Access**: In your Azure DevOps organization, navigate to **Organization Settings > Policies** and ensure that **'Third-party application access via OAuth'** is enabled.

## Installation and Setup

Follow these steps to get the generator up and running.

### 1. Clone the Repository

Clone the official project repository from GitHub to your local machine.

```bash
git clone https://github.com/microsoft/AzDevOpsDemoGenerator
```

### 2. Update Configuration 

Navigate into the project's source directory. If needed, you can modify the `scope` property within the `appsettings.json` file to adjust the permissions the application will request.

```bash
cd AzDevOpsDemoGenerator/src/ADOGenerator
# Open appsettings.json and update the scope and add the suffix ./default at the end of subscription id
```

### 3. Install the .NET SDK

Use Homebrew to install the .NET SDK 

```bash
brew install --cask dotnet-sdk
```

### 4. Restore Dependencies

Navigate to the project's source directory (`src/ADOGenerator`) if you aren't already there, and run the restore command to download the necessary packages.

```bash
cd src/ADOGenerator
dotnet restore
```

### 5. Install .NET Runtime (If Necessary)

If you receive an error about a missing framework during the next steps, you may need to install the .NET runtime manually.

* **Download Link for macOS ARM64**: [Microsoft .NET 8.0.0 Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
* Download and run the installer to add the required runtime.

### 6. Build the Project

Compile the application by running the build command.

```bash
dotnet build ADOGenerator.csproj
```

### 7. Run the Application

Finally, run the project. The application will start, and you can provide the details such as org name, PAT token, project name etc

```bash
dotnet run --project ADOGenerator.csproj
```
