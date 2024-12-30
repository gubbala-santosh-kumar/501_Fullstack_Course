### Postgres Setup
To set up Postgres, you can follow these steps:
- Install Postgres on your system. You can download the installer from the official Postgres website
- Once installed, open a terminal and run the command `psql -U postgres` to
open the Postgres shell
- Create a new database by running the command `CREATE DATABASE mydatabase;`
- Create a new user by running the command `CREATE ROLE myuser WITH PASSWORD 'mypassword';`
- Grant all privileges to the new user by running the command `GRANT ALL PRIVILEGES ON DATABASE mydatabase TO myuser;`
- Connect to the new database by running the command `\c mydatabase;`
- Create a new table by running the command `CREATE TABLE mytable (id SERIAL PRIMARY KEY , name VARCHAR(255));`
- Insert some data into the table by running the command `INSERT INTO mytable (name)
VALUES ('John Doe');`
- Commit the changes by running the command `COMMIT;`
- Close the Postgres shell by running the command `\q;`

Youtube Video link for the installation and setup process:
<a href='https://www.youtube.com/watch?v=F99TVfE7daM'>Video</a>