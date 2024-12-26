# todoweb-repo
# To-Do Web Application

This project is a simple and interactive To-Do web application designed to help users manage tasks efficiently. The application features a login interface and a to-do task management system with animations and responsive design.

## Features

- **Login Page**: A user authentication system to log in with predefined credentials.
- **To-Do List**: Allows users to add, mark tasks as done, or reset the task list.
- **Animations**: Smooth animations for transitions and task status updates.
- **Responsive Design**: Adapts to different screen sizes and devices.
- **Customizable Background**: Includes an image and color overlays for styling.

## Files

### 1. `index.html`

- Entry point for the web application.
- Contains the login form and links to stylesheets and scripts.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do Web</title>
    <link rel="stylesheet" href="todo.css">
</head>
<body>
    <div class="background">
        <div class="overlay">
            <div id="pad">
                <div id="box">
                    <div class="todoenter">To-Do Login</div>
                    <hr>
                    <div>
                        <button onclick="login()" class="button">Login</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <script>
        function login() {
            window.open('login.html', '_blank');
        }
    </script>
</body>
</html>
```

### 2. `login.html`

- Contains the login form for user authentication.
- Features an animation effect on form appearance.

### 3. `todolist.html`

- The main to-do list page where users can add, update, and manage tasks.

### 4. `todo.css`

- Defines the styles for the application, including the background, button styles, and animations.

```css
body {
    background: radial-gradient(circle, #0084ff, #000000);
    justify-content: center;
    padding: 50px;
    size: 200px;
}
.todoenter {
    text-align: center;
    font-size: large;
    font-family: 'Trebuchet MS', Arial, sans-serif;
    font-weight: bolder;
    color: #0d1b2a;
}
#box {
    background-color: #e0e1dd;
    display: grid;
    border-radius: 10px;
    padding: 20px;
    margin: 20px auto;
    width: fit-content;
    box-shadow: 0px 2px 10px 10px rgba(0, 0, 0, 0.2);
    animation: fadeIn 1s ease-in-out;
}
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: scale(0.9);
    }
    to {
        opacity: 1;
        transform: scale(1);
    }
}
```

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/pragathees03/todoweb-repo.git
   ```
2. Navigate to the project directory:
   ```bash
   cd todoweb-repo
   ```
3. Open `index.html` in your browser to start the application.

## Scripts

### Login Script

- Validates username and password.

```javascript
function handlelogin(event) {
    event.preventDefault();
    const Username = document.getElementById('Username').value;
    const password = document.getElementById('password').value;
    todolist(Username, password);
}
function todolist(Username, password) {
    if (Username === 'admin' && password === '1234') {
        window.open('todolist.html');
    } else {
        alert('Invalid username & Password');
    }
}
```

### To-Do List Script

- Manages task actions such as marking tasks as done, showing alerts, and resetting the form.

```javascript
function markasdone(event, buttonelement) {
    event.preventDefault();
    const taskelement = buttonelement.closest('.task');
    taskelement.remove();
}
function warnnotyet(event, taskname) {
    event.preventDefault();
    alert(`${taskname} is not yet completed`);
}
function reset() {
    const form = document.getElementById('todoform');
    form.reset();
}
```

## Future Enhancements

- Add user registration functionality.
- Implement a database for persistent task storage.
- Integrate task deadlines and notifications.

## License

This project is licensed under the MIT License.

