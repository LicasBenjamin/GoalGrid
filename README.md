# GoalGrid

**GoalGrid** is a bingo-card style productivity web app designed to make goal tracking fun and interactive. Complete tasks, fill your bingo card, and boost your productivity one goal at a time!


### Features
- **Full account support** - sign up, log in, and keep your progress of cards across sessions.
- Create and manage your own goals.
- Track progress with a bingo-card style interface.
- Fun and motivating way to achieve daily, weekly, or personal goals.


GoalGrid is a full-stack app with a **Spring Boot (Java) backend** and a **React frontend**.

- **Backend**: Spring Boot + Spring Data JPA (MySQL)
- **Frontend**: Create React App

## Project structure

- `backend/` — Spring Boot API
- `goalgrid-app/` — React UI

## Prerequisites

You’ll need:

- **Java 17** (JDK)
- **Node.js + npm**
- **MySQL Server** (local install)

## Ports

- **Frontend**: `http://localhost:3000`
- **Backend**: `http://localhost:8080`

## Backend setup (Linux Mint)

### 1) Install and start MySQL

```bash
sudo apt update
sudo apt install -y mysql-server
sudo systemctl enable --now mysql
```
### 2) Create the database

```bash
sudo mysql
```
In the MySQL Prompt, paste the following in:
```SQL
CREATE DATABASE IF NOT EXISTS goalgrid;

CREATE USER IF NOT EXISTS 'goalgrid_user'@'localhost'
IDENTIFIED BY 'goalgrid_pass';

GRANT ALL PRIVILEGES ON goalgrid.* TO 'goalgrid_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

### 3) Run the backend
```bash
cd backend
./mvnw spring-boot:run
```

## Frontend setup (Linux Mint)
Open a second terminal:
```bash
cd goalgrid-app
npm install
npm start
```
## Using the App

1) Open the app at http://localhost:3000

2) Now you can sign up by creating a new user in the **"Sign Up"** Section
    - Note that the password **must contain**:
        - At least **8 characters**
        - One **number**
        - One **special character**
    - The username must also be **unique**

3) Type in a name for your new grid and click the "Add" button
4) Enter in your goals and click "Add Goal" To add it into your goal list
5) Once you have enough goals listed you can select the size you wish to generate
    - Note that there must be **at least** 9 goals for a 3x3 card, 16 for a 4x4 card, etc.
    - In the case you enter >9 goals but still generate a 3x3 card, it will **randomly select** goals and leave some out
6) Enjoy fun productivity!