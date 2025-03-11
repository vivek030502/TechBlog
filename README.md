### TechBlog Project

Welcome to the TechBlog project! This repository contains the source code and documentation for a technical blog platform developed using Java, JDBC, and MySQL. TechBlog allows users to create, manage, and share technical articles with a focus on providing an intuitive and feature-rich blogging experience.

---

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Introduction

TechBlog is a full-fledged blogging platform designed to help users publish and manage technical articles. The platform offers a clean and responsive UI, making it easy for users to read, write, and interact with blog posts. It also includes administrative features for managing users and content, ensuring a robust and scalable solution for technical blogging.

---

## Features

- **User Authentication:** Secure user registration and login system.
- **Post Management:** Create, edit, delete, and view blog posts.
- **Category Management:** Organize posts into categories for better navigation.
- **Comments:** Users can comment on posts to facilitate discussion.
- **Responsive Design:** Mobile-friendly layout for seamless browsing across devices.

---

## Technologies Used

  - Java
  - JDBC
  - MySQL

---

## Installation

Follow these steps to set up the TechBlog project on your local machine:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/vivek030502/TechBlog.git
   cd TechBlog
   ```

2. **Set up the database:**
   - Install MySQL and create a database named `techblog`.
   - Import the database schema from the `database/schema.sql` file.
   ---sql
    create table user(
	    Id int primary key not null auto_increment,
      Name varchar(500) not null,
      Email varchar(500) not null,
      Password varchar(500) not null,
      Gender varchar(20) not null,
      About varchar(1000) default "hey, I am using Tech Blog.",
      rdate timestamp
    );

    create table categories(
	    cid int primary key not null auto_increment,
      name varchar(200) not null,
      description varchar(500) not null
    );

    CREATE TABLE posts (
      pid INT PRIMARY KEY AUTO_INCREMENT,
      pTitle VARCHAR(150) NOT NULL,
      pContent LONGTEXT,
      pCode LONGTEXT,
      pPic VARCHAR(100),
      pDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
      catId INT,
      FOREIGN KEY (catId) REFERENCES categories(cid)
    );

    select * from user;
    select * from categories;
    select * from posts;
    select * from liked;

  ---
  
3. **Configure the application:**
   - Open the `src/main/resources/config.properties` file.
   - Update the database connection details:
     ```properties
     db.url=jdbc:mysql://localhost:3306/techblog
     db.username=your_username
     db.password=your_password
     ```

4. **Build the project:**
   - Use an IDE like IntelliJ IDEA or Eclipse to import the project and build it.
   - Alternatively, use Maven from the command line:
     ```bash
     mvn clean install
     ```

5. **Run the application:**
   - Deploy the application on a web server like Apache Tomcat.
   - Access the application in your web browser at `http://localhost:8080/TechBlog`.

---

## Usage

1. **User Registration and Login:**
   - Register a new account or log in with an existing account.

2. **Creating and Managing Posts:**
   - Navigate to the "New Post" section to create a new blog post.
   - Edit or delete existing posts from the "My Posts" section.

3. **Admin Panel:**
   - Access the admin panel to manage users, posts, and categories.

4. **Search and Comments:**
   - Use the search bar to find specific posts.
   - Comment on posts to engage with other users.

---

## Contributing

We welcome contributions to the TechBlog project! To contribute, follow these steps:

1. **Fork the repository:**
   Click the "Fork" button at the top right of this page to create a copy of this repository in your GitHub account.

2. **Clone the forked repository:**
   ```bash
   git clone https://github.com/vivek030502/TechBlog.git
   cd TechBlog
   ```

3. **Create a new branch:**
   ```bash
   git checkout -b feature-branch
   ```

4. **Make your changes and commit them:**
   ```bash
   git add .
   git commit -m "Describe your changes"
   ```

5. **Push to the branch:**
   ```bash
   git push origin feature-branch
   ```

6. **Create a pull request:**
   Open a pull request on the original repository to merge your changes.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

## Contact

For any questions or feedback, feel free to reach out:

- **Name:** Vivek Akhilesh Tiwari
- **Email:** vivektiwari4397@gmail.com
- **LinkedIn:** [Vivek Tiwari](https://www.linkedin.com/in/vivek-tiwari-290224283)

---

Thank you for using TechBlog! We hope you find it useful and enjoy contributing to its development.
