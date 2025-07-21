# Social Media Analytics Dashboard

## 1. Project Purpose and Overview

This project is a **Java-based Social Media Analytics Dashboard**. Its main goal is to allow a user to log in, select a social media platform (YouTube, Facebook, or Instagram), and visualize analytics data (like engagement rates and audience demographics) using interactive charts. It also generates a PDF report summarizing the analytics.

---

## 2. Main Features and Flow

### A. User Authentication
- The program starts by prompting the user for a username, password, and a unique ID.
- It checks the credentials using the `UserAuthentication` class.
- If authentication fails, a custom `AuthenticationException` is thrown and handled.

### B. Social Media User Modeling
- The system models three types of social media users:
  - **YouTube**
  - **Facebook**
  - **Instagram**
- Each platform is represented by a class (`Youtube`, `Facebook`, `Instagram`) that extends an abstract `User` class.
- These classes store data such as:
  - Number of followers
  - Engagement metrics (likes, comments, shares, etc.)
  - Regional audience breakdown (Asia, Europe, etc.)

### C. Data Visualization
- **Bar Chart:**  
  - Shows user engagement rates and total number of users for the selected platform.
  - Implemented using the `BarChart` class (uses JFreeChart).
- **Pie Chart:**  
  - Shows audience demographics (distribution by region) for the selected platform.
  - Implemented using the `PieChart` class (uses JFreeChart).

### D. PDF Report Generation
- After displaying the charts, the program generates a PDF report using the `report` class and Apache PDFBox.
- The report includes:
  - Title, date range, and datasets used
  - Analytics data for Facebook, Instagram, and YouTube (posts, likes, comments, etc.)

---

## 3. OOP Concepts in Depth

- **Abstraction:**  
  - The `User` class is abstract, defining methods like `userEngagement()` and `getfollowers()` that must be implemented by subclasses.
- **Inheritance:**  
  - `Youtube`, `Facebook`, and `Instagram` inherit from `User` and provide their own implementations for engagement calculations.
- **Polymorphism:**  
  - The program can treat all social media users as `User` objects, but calls to `userEngagement()` or `getfollowers()` will use the correct subclass logic.
- **Encapsulation:**  
  - Each class manages its own data and exposes only necessary methods.
- **Exception Handling:**  
  - Custom exceptions are used for authentication errors.
- **Modularity:**  
  - Code is organized into packages: `user`, `authentication`, `Bar`, `Pie`, etc.

---

## 4. Project Structure

```
src/
  authentication/
    AuthenticationException.java
    UserAuthentication.java
  Bar/
    BarChart.java
  Pie/
    PieChart.java
  user/
    User.java
    Facebook.java
    Instagram.java
    Youtube.java
  FacebookData.java
  InstagramData.java
  YoutubeData.java
  report.java
  SocialMediaAnalytics.java   <-- Main entry point
```

---

## 5. How the Program Works (Step-by-Step)

1. **Start the Program:**  
   - The main class is `SocialMediaAnalytics.java`.
2. **User Login:**  
   - Prompts for username, password, and unique ID(y-youtube,f-facebook,i-instagram).
   - Authenticates using `UserAuthentication`.
3. **User Creation:**  
   - Creates three user objects: one each for YouTube, Facebook, and Instagram, with sample data.
4. **Chart Display:**  
   - Depending on the unique ID, displays a bar chart and a pie chart for the selected platform.
   - Charts are shown in a GUI window (using Swing and JFreeChart).
5. **PDF Report:**  
   - Generates a PDF report with analytics data for all platforms and saves it to disk as `my_doc.pdf` in the project directory.

---

## 6. How to Run the Project

### A. Prerequisites
- **Java JDK** (version 8 or above)
- **JFreeChart** and **Apache PDFBox** libraries 
- **Font file**: `times-ro.ttf` 

### B. Steps to Run(important)

1. **Compile the Source Code**
   - Open a terminal/command prompt in the project root directory.
   - Compile all Java files, including the external JARs:
     ```sh
     javac -cp ".;jfreechart-1.0.19.jar;jcommon-1.0.23.jar;pdfbox-2.0.31.jar;fontbox-2.0.31.jar;pdfbox-app-3.0.2.jar;pdfbox-tools-2.0.31.jar;preflight-2.0.31.jar;xmpbox-2.0.31.jar" src\authentication\*.java src\Bar\*.java src\Pie\*.java src\user\*.java src\*.java
     ```

2. **Run the Main Program**
   - Run the main class, specifying the classpath:
     ```sh
     java -cp ".;src;jfreechart-1.0.19.jar;jcommon-1.0.23.jar;pdfbox-2.0.31.jar;fontbox-2.0.31.jar;pdfbox-app-3.0.2.jar;pdfbox-tools-2.0.31.jar;preflight-2.0.31.jar;xmpbox-2.0.31.jar" SocialMediaAnalytics
     ```
   - The program will prompt for username, password, and unique ID.

3. **Interact with the Program**
   - Enter the credentials (e.g., user1/password1 or user2/password2).
   - Enter a unique ID ending with `y` (YouTube), `f` (Facebook), or `i` (Instagram) to select the platform.
   - The program will display the relevant charts and generate a PDF report.

4. **View the PDF Report**
   - The PDF will be saved as `my_doc.pdf` in your project directory.

---

## 7. Things to observe

- **OOP Mastery:** Abstract classes, inheritance, polymorphism, encapsulation, and exception handling.
- **Data Visualization:** Integration with JFreeChart for real-time analytics.
- **Report Automation:** PDF generation with Apache PDFBox.
- **Authentication:** Custom user authentication system.
- **Modular Design:** Clean package structure and separation of concerns.
- **GUI Programming:** Use of Java Swing for interactive charts.

---

## 8. Possible Improvements

- Make the data dynamic (e.g., read from files or a database).
- Add more user interactivity (e.g., allow users to input their own analytics data).
- Improve error handling and user feedback.


---
