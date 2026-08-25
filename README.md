# DEVELOP A DJANGO-BASED CRUD APPLICATION

## AIM

To develop a Django-based web application that performs CRUD (Create, Read, Update, and Delete) operations on student records.

## ALGORITHM

1. Create a Django project and an application.
2. Define the `Student` model with the required fields (Name and Email).
3. Run migrations to create the database table.
4. Configure URL routing for Home, Add, Update, and Delete operations.
5. Create the `home()` view to retrieve and display all student records.
6. Create the `add()` view to insert a new student record into the database.
7. Create the `update()` view to modify an existing student record using its ID.
8. Create the `delete()` view to remove a student record using its ID.
9. Design the HTML page with separate forms/buttons for Add, View, Update, and Delete operations.
10. Run the Django development server and perform all CRUD operations through the web browser.

## PROGRAM
~~~
<html>
<head>
    <title>Student Management Portal</title>
</head>

<body>

    <h2>Student Database Operations</h2>

    <h4>Register a New Student</h4>

    <form action="/create/" method="POST">
        {% csrf_token %}

        <label>Student Full Name:</label>
        <input type="text" name="name" placeholder="Full name here" required>

        <br><br>

        <label>Email Address:</label>
        <input type="email" name="email" placeholder="name@example.com" required>

        <br><br>

        <button type="submit">Save Record</button>
    </form>

    <hr>

    <h4>Registered Students List</h4>

    <table border="1" cellpadding="5">
        <tr>
            <th>Roll No / ID</th>
            <th>Full Name</th>
            <th>Email Address</th>
        </tr>

        {% for i in result %}
        <tr>
            <td>{{ i.Idno }}</td>
            <td>{{ i.Name }}</td>
            <td>{{ i.Email }}</td>
        </tr>
        {% endfor %}
    </table>

    <br>

    <form action="{% url 'home' %}" method="GET">
        <button type="submit">Refresh Table</button>
    </form>

    <hr>

    <h4>Modify Student Details</h4>

    <form action="{% url 'up' %}" method="POST">
        {% csrf_token %}

        <label>Student ID:</label>
        <input type="text" name="id" placeholder="Enter existing ID" required>

        <br><br>

        <label>New Name:</label>
        <input type="text" name="name" placeholder="Updated name" required>

        <br><br>

        <label>New Email:</label>
        <input type="email" name="email" placeholder="Updated email" required>

        <br><br>

        <button type="submit">Save Changes</button>
    </form>

    <hr>

    <h4>Remove Student Record</h4>

    <form action="{% url 'del' %}" method="POST">
        {% csrf_token %}

        <label>Student ID:</label>
        <input type="text" name="id" placeholder="ID to delete" required>

        <br><br>

        <button type="submit" style="color: red;">Delete Record</button>
    </form>

</body>
</html>
~~~
## OUTPUT

### Add
<img width="1907" height="960" alt="image" src="https://github.com/user-attachments/assets/99293815-83b8-4113-83dc-baa7223d31c0" />

### Update
<img width="1917" height="947" alt="image" src="https://github.com/user-attachments/assets/4f79fbc0-5d79-464b-8c81-8a01ba06469c" />

### Delete

<img width="1913" height="957" alt="image" src="https://github.com/user-attachments/assets/bf24de4e-8d80-49e0-a223-5ee27f1b2e03" />

## RESULT

A Django-based CRUD web application was successfully developed to perform Create, Read, Update, and Delete operations on student records using SQLite as the backend database.


