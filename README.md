<<<<<<< HEAD
# LibraryJDBCProject (Console)

## What's included
- Java source code (package `com.library`)
- `build.bat` (Windows) and `build.sh` (Linux/Mac) scripts to compile and build a runnable jar
- `db-init.sql` - SQL to create the database and `books` table
- Note: **MySQL Connector/J** is NOT included (download instructions below)

## Default DB credentials used in code
- URL: `jdbc:mysql://localhost:3306/librarydb`
- USER: `root`
- PASSWORD: `root`

If your MySQL username/password differ, edit `src/com/library/DBConnection.java` before building.

## Steps to prepare database
1. Start MySQL server.
2. Run the SQL in `db-init.sql` (via `mysql` CLI or phpMyAdmin).

```sql
-- db-init.sql
CREATE DATABASE librarydb;
USE librarydb;
CREATE TABLE books (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(100),
    author VARCHAR(100),
    price DOUBLE
);
```

## Download MySQL Connector/J
1. Go to: https://dev.mysql.com/downloads/connector/j/
2. Download the platform-independent zip and extract the `mysql-connector-j-<version>.jar`
3. Place the jar into the `lib/` folder (create `lib/` if missing)
   and rename it to `mysql-connector-java.jar`

## Build and run (Windows)
1. Open Command Prompt in project root.
2. Ensure `javac` and `jar` are on PATH (JDK installed).
3. Place `lib/mysql-connector-java.jar` in the `lib` folder.
4. Run:
   ```
   build.bat
   ```
5. After successful build, run:
   ```
   java -jar dist/LibraryJDBCProject.jar
   ```

## Build and run (Linux / macOS)
1. Open terminal in project root.
2. Ensure `javac` and `jar` are available (JDK).
3. Place `lib/mysql-connector-java.jar` in the `lib` folder.
4. Run:
   ```
   chmod +x build.sh
   ./build.sh
   ```
5. Run:
   ```
   java -jar dist/LibraryJDBCProject.jar
   ```

## What the build scripts do
- compile `.java` files to `out/`
- create a fat jar (LibraryJDBCProject.jar) in `dist/` that includes compiled classes
  but **NOT** the MySQL driver. The driver jar must be on the classpath when running
  (the scripts add the `lib/mysql-connector-java.jar` to the classpath during compilation/run).

## If you want me to compile and include an executable jar and connector jar:
I can attempt to compile here, but I cannot download the MySQL connector jar automatically due to environment restrictions.
The safest approach is to download the connector locally and follow the `build` steps above.

## Troubleshooting
- `ClassNotFoundException: com.mysql.cj.jdbc.Driver` → You didn't place the connector jar in `lib/`.
- `Access denied` → Check MySQL user/password and update `DBConnection.java`.
- Port or bind errors → Ensure MySQL is running on default 3306 or adjust the URL.

---
Enjoy! If you want, I can now:
- Provide a GUI (Swing) version.
- Try to compile and produce a runnable jar here (I will need the connector jar uploaded by you).
=======
# Library-Management-System-JDBC-Project
A simple Java console-based Library Management System using JDBC and MySQL.
>>>>>>> 5f4ac7f0754169c0df5bae7aa7184d5b4244ad6c
