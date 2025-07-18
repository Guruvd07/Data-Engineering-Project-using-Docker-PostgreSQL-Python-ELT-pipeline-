
🚀 Data Engineering Project using Docker, PostgreSQL & Python (ELT Pipeline)

This project demonstrates a basic ELT (Extract, Load, Transform) data pipeline using:

- Docker for containerization
- PostgreSQL as both source & destination databases
- Python for scripting the ELT logic using `pg_dump` and `psql`

--------------------------------------------------

🧠 Project Goal

Simulate real-world data engineering by:
- Extracting data from a PostgreSQL container (source)
- Loading the data into another PostgreSQL container (destination)
- (Optional) Transforming the data further

--------------------------------------------------

📂 Project Structure

custom-elt-project/
│
├── docker-compose.yml               # Defines all services
├── source_db_init/
│   └── init.sql                     # Initializes the source DB with tables and sample data
│
├── elt_script/
│   ├── Dockerfile                   # Python + PostgreSQL client tools
│   └── elt_script.py                # Python script to extract and load data
│
└── README.txt                       # Documentation file

--------------------------------------------------

🔗 Technologies Used

- Docker 🐳
- PostgreSQL 🐘
- Python 🐍
- ELT Tools: pg_dump, psql, subprocess

--------------------------------------------------

🧱 How ELT Works

Step 1: Extract - Using pg_dump to extract the entire source database into data_dump.sql.

Step 2: Load - Using psql to load the dumped .sql file into the destination database.

Step 3: (Optional) Transform - You can later perform analysis or data transformation.

--------------------------------------------------

⚙️ Setup & Run (Step-by-Step Commands)

Step 1: Clone the Repository
    git clone https://github.com/Guruvd07/Data-Engineering-Project-using-Docker-PostgreSQL-Python-ELT-pipeline-.git
    cd Data-Engineering-Project-using-Docker-PostgreSQL-Python-ELT-pipeline-

Step 2: Initialize Git Repo (if not already done)
    git init
    git add .
    git commit -m "Initial commit: ELT project with Docker, PostgreSQL, and Python"

Step 3: Push to GitHub
    git remote add origin https://github.com/Guruvd07/Data-Engineering-Project-using-Docker-PostgreSQL-Python-ELT-pipeline-.git
    git branch -M main
    git push -u origin main

Step 4: Run the Pipeline
    docker compose up --build

Step 5: Connect to Destination DB to Verify
    docker exec -it custom-elt-project-destination_postgres-1 psql -U postgres -d destination_db

In psql shell:
    \dt
    SELECT * FROM users;
    SELECT * FROM films;

--------------------------------------------------

🔍 Key Files Explained

init.sql - Sample realistic tables like users, films, film_category, actors

elt_script.py - Extract and load the data using pg_dump and psql

Dockerfile - Installs Python and PostgreSQL tools

docker-compose.yml - Defines source DB, destination DB, and Python ELT container

--------------------------------------------------

✅ Output Example

SELECT * FROM users;

Returns:
| id | first_name | last_name | email | date_of_birth |
|----|------------|-----------|-------|---------------|
| 1  | Guru       | Dahiphale       | guruprasaddahiphale7@gmail.com | 19-04-2004 |
| ... | ...        | ...       | ...   | ...           |

--------------------------------------------------

🎯 Learning Outcomes

- Docker Networking
- PostgreSQL Initialization & Backup
- Python-based ELT Logic
- Database Container Interaction
- Real-World Data Flow Simulation

--------------------------------------------------

✨ Future Scope

- Add transformations using SQL or pandas
- Schedule ELT using Airflow or cron
- Connect to Power BI for visualizations
- Build ML models on loaded data

--------------------------------------------------

