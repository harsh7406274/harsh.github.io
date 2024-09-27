<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Library Book Collection</title>
    <style>
        /* Add your existing CSS styles here */

        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            line-height: 1.6;
            background-color: #f9f9f9;
        }

        header {
            background-color: #4CAF50;
            color: white;
            text-align: center;
            padding: 1em 0;
        }

        nav a {
            margin: 0 15px;
            color: white;
            text-decoration: none;
            font-weight: bold;
        }

        .button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 15px;
            margin: 5px;
            cursor: pointer;
            border-radius: 4px;
        }

        .button:hover {
            background-color: #45a049;
        }

        section {
            padding: 20px;
            margin: 10px auto;
            max-width: 600px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        h2 {
            color: #4CAF50;
        }

        ul {
            list-style-type: none;
            padding: 0;
        }

        ul li {
            background-color: #f4f4f4;
            margin: 5px 0;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }

        footer {
            text-align: center;
            padding: 1em 0;
            background-color: #4CAF50;
            color: white;
            position: relative;
            bottom: 0;
            width: 100%;
        }

        .filter {
            margin-bottom: 20px;
        }

        .filter select {
            padding: 10px;
            border-radius: 4px;
            border: 1px solid #ddd;
        }

        .search-container {
            margin: 10px auto;
            max-width: 600px;
        }

        .search-container input {
            width: 70%;
            padding: 10px;
            border-radius: 4px;
            border: 1px solid #ddd;
        }

        .search-container button {
            padding: 10px 15px;
            border-radius: 4px;
            border: none;
            background-color: #4CAF50;
            color: white;
            cursor: pointer;
        }

        .search-container button:hover {
            background-color: #45a049;
        }

        .login-container {
            display: flex;
            justify-content: center;
            margin: 20px auto;
        }

        .login-container input {
            padding: 10px;
            margin-right: 10px;
            border-radius: 4px;
            border: 1px solid #ddd;
        }

        .login-container button {
            padding: 10px 15px;
            border-radius: 4px;
            border: none;
            background-color: #4CAF50;
            color: white;
            cursor: pointer;
        }
    </style>
</head>
<body>

<header>
    <h1>Library Book Collection</h1>
    <nav>
        <a href="#genres">Genres</a>
        <a href="#authors">Authors</a>
        <a href="#dates">Publication Dates</a>
    </nav>
</header>

<div class="login-container">
    <input type="text" id="username" placeholder="Username">
    <input type="password" id="password" placeholder="Password">
    <button onclick="login()">Login</button>
</div>

<div class="search-container">
    <input type="text" id="search" placeholder="Search for books..." oninput="searchBooks()">
    <button onclick="searchBooks()">Search</button>
</div>

<section id="genres">
    <h2>Books by Genre</h2>
    <div class="filter">
        <label for="genreFilter">Filter by Genre:</label>
        <select id="genreFilter" onchange="filterBooks('genre')">
            <option value="all">All</option>
            <option value="fiction">Fiction</option>
            <option value="historical">Historical Fiction</option>
            <option value="nonfiction">Non-Fiction</option>
            <option value="mystery">Mystery</option>
            <option value="poetry">Poetry</option>
        </select>
    </div>
    <ul id="genreList">
        <!-- Book List Here (Existing Content) -->
    </ul>
</section>

<section id="authors">
    <h2>Books by Author</h2>
    <div class="filter">
        <label for="authorFilter">Filter by Author:</label>
        <select id="authorFilter" onchange="filterBooks('author')">
            <option value="all">All</option>
            <option value="adiga">Aravind Adiga</option>
            <option value="divakaruni">Chitra Banerjee Divakaruni</option>
            <option value="guha">Ramachandra Guha</option>
            <option value="chandra">Vikram Chandra</option>
            <option value="tagore">Rabindranath Tagore</option>
            <option value="frost">Robert Frost</option>
            <option value="dickinson">Emily Dickinson</option>
            <option value="morrison">Toni Morrison</option>
            <option value="orwell">George Orwell</option>
            <option value="hemingway">Ernest Hemingway</option>
            <option value="austen">Jane Austen</option>
            <option value="shakespeare">William Shakespeare</option>
            <option value="chevalier">Tracy Chevalier</option>
            <option value="martel">Yann Martel</option>
            <option value="coelho">Paulo Coelho</option>
        </select>
    </div>
    <ul id="authorList">
        <!-- Book List Here (Existing Content) -->
    </ul>
</section>

<section id="dates">
    <h2>Books by Publication Date</h2>
    <div class="filter">
        <label for="dateFilter">Filter by Publication Year:</label>
        <select id="dateFilter" onchange="filterBooks('date')">
            <option value="all">All</option>
            <option value="2008">2008</option>
            <option value="2009">2009</option>
            <option value="2010">2010</option>
            <option value="2011">2011</option>
            <option value="2012">2012</option>
            <option value="2013">2013</option>
            <option value="2014">2014</option>
            <option value="2015">2015</option>
            <option value="2016">2016</option>
            <option value="2017">2017</option>
            <option value="2018">2018</option>
            <option value="2019">2019</option>
            <option value="2020">2020</option>
            <option value="2021">2021</option>
            <option value="2022">2022</option>
            <option value="2023">2023</option>
        </select>
    </div>
    <ul id="dateList">
        <!-- Book List Here (Existing Content) -->
    </ul>
</section>

<footer>
    <p>&copy; 2024 Library Book Collection</p>
</footer>

<script>
    // Existing JavaScript functions go here

    function searchBooks() {
        const query = document.getElementById('search').value.toLowerCase();
        const allBooks = document.querySelectorAll('ul li');

        allBooks.forEach(book => {
            if (book.textContent.toLowerCase().includes(query)) {
                book.style.display = 'block';
            } else {
                book.style.display = 'none';
            }
        });
    }

    function login() {
        const username = document.getElementById('username').value;
        const password = document.getElementById('password').value;

        // Replace with your backend login API
        fetch('/api/login', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({ username, password })
        })
        .then(response => response.json())
        .then(data => {
            if (data.success) {
                alert('Login successful!');
                // Optionally redirect or show user info
            } else {
                alert('Login failed. Please try again.');
            }
        });
    }
</
