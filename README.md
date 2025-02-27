# Billsync Project

## Project Description

Billsync is a comprehensive solution for managing billing processes efficiently. It consists of three main repositories structured as submodules:

- **billsync_backend** (Backend - Java, Spring Boot)
- **billsync_frontend** (Frontend - Angular)
- **Dependencies** (Common dependencies for backend)

Each module functions independently and can also be cloned together using Git submodules.

## Clone the Repository

To clone the project along with its submodules, use:

```sh
git clone --recurse-submodules https://github.com/Callisto30/billsync_project.git
```

## Navigating to Submodules

After cloning, navigate to the respective directories:

```sh
cd billsync_project
cd backend    # Navigate to backend (billsync_backend)
cd frontend   # Navigate to frontend (billsync_frontend)
```

## Installation Instructions

### Java 17 Installation

Ensure Java 17 is installed. To check:

```sh
java -version
```

If not installed, download it from:
- [OpenJDK](https://openjdk.org/)

#### Set Java Environment Variables (Windows)

1. Open **Environment Variables**.
2. Under **System Variables**, add:
   - `JAVA_HOME` → Path to JDK installation.
   - Add `%JAVA_HOME%\bin` to `Path`.

### Maven 3.x Installation

Check Maven version:

```sh
mvn -version
```

If not installed, download it from:
- [Maven Download](https://maven.apache.org/download.cgi)

#### Set Maven Environment Variables (Windows)

1. Add `MAVEN_HOME` pointing to the Maven installation.
2. Add `%MAVEN_HOME%\bin` to `Path`.

### Node.js and Angular Installation (Required for billsync_frontend)

Install Node.js (LTS recommended, version 20.x recommended) from:
- [Node.js Official Website](https://nodejs.org/)

Check installation:

```sh
node -v   # Ensure it displays version 20.x
npm -v    # Ensure it displays a compatible version
```

#### Set Node.js Environment Variables (Windows)

1. Open **Environment Variables**.
2. Under **System Variables**, add:
   - `NODE_HOME` → Path to Node.js installation.
   - Add `%NODE_HOME%in` to `Path`.

### Angular Installation

Ensure Angular CLI is installed:

```sh
npm install -g @angular/cli@16
```

Check Angular version:

```sh
ng version
```
## Git Workflow for Submodules

### **Pulling Changes from Remote**
Before making changes, always **pull the latest updates**:

#### Pull all submodules and main repo:
```sh
git pull --recurse-submodules
```

#### Pull updates for a specific submodule:
```sh
cd backend  # or frontend, dependencies
git pull origin main  # Ensure you’re on the correct branch
```

### **Making Changes in a Submodule**
1. Navigate to the specific submodule:
   ```sh
   cd backend  # or frontend, dependencies
   ```
2. Make changes and commit:
   ```sh
   git add .
   git commit -m "Updated backend feature"
   ```
3. Push changes to the respective submodule:
   ```sh
   git push origin main
   ```

### **Updating Main Project (`billsync_project`) After Pushing to Submodules**
After pushing changes in a submodule (like backend), update the main project to ensure everything is in sync:

1. **Go back to the main project root:**
   ```sh
   cd ..  # Navigate back to billsync_project
   ```
2. **Check for changes in submodules:**
   ```sh
   git status
   ```
3. **Stage the updated submodule reference:**
   ```sh
   git add backend  # or frontend, dependencies
   ```
4. **Commit and push the changes in the main project:**
   ```sh
   git commit -m "Updated backend submodule reference"
   git push origin main
   ```

### **When to Pull Before Pushing in Backend**
- Always pull the latest changes **before making modifications** to avoid conflicts.
- If other team members have updated the **backend**, first run:
  ```sh
  cd backend
git pull origin main
  ```
- If there are merge conflicts, resolve them before pushing your changes.

## How to Build and Start Each Module

### Backend (billsync_backend)

Navigate to the backend directory and build the project using Maven:

```sh
cd backend
mvn clean install
```

Run the backend:

```sh
mvn spring-boot:run
```

### Frontend (billsync_frontend)

Navigate to the frontend directory:

```sh
cd frontend
```

Install dependencies:

```sh
npm install
```

Start the Angular project:

```sh
ng serve
```

Ensure Angular CLI is installed:

```sh
npm install -g @angular/cli
```

## Developers

- **Riya Patel**
- **Shubham Patel**
- **Khushi Shah**
- **Smith Chokshi**

## Additional Notes

- The backend and frontend can run independently.
- Ensure all dependencies are installed before running.
- Use the `--recurse-submodules` flag while cloning to ensure submodules are fetched.
