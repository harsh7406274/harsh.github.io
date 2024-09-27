const express = require('express');
const bodyParser = require('body-parser');
const cors = require('cors');

const app = express();
const PORT = 3000;

app.use(cors());
app.use(bodyParser.json());

// Sample users for login
const users = [
    { username: 'user1', password: 'password1' },
    { username: 'user2', password: 'password2' }
];

app.post('/api/login', (req, res) => {
    const { username, password } = req.body;
    const user = users.find(u => u.username === username && u.password === password);
    
    if (user) {
        res.json({ success: true });
    } else {
        res.json({ success: false });
    }
});

app.get('/', (req, res) => {
    res.send(`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Library Book Collection</title>
    <style>
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
        <li class="fiction">Fiction - The White Tiger</li>
        <li class="historical">Historical Fiction - The Palace of Illusions</li>
        <li class="nonfiction">Non-Fiction - India After Gandhi</li>
        <li class="mystery">Mystery - Sacred Games</li>
        <li class="poetry">Poetry - Gitanjali</li>
        <li class="fiction">Fiction - The Night Circus</li>
        <li class="fiction">Fiction - A Little Life</li>
        <li class="historical">Historical Fiction - The Book Thief</li>
        <li class="mystery">Mystery - The Girl with the Dragon Tattoo</li>
        <li class="poetry">Poetry - Leaves of Grass</li>
        <li class="nonfiction">Non-Fiction - Sapiens: A Brief History of Humankind</li>
        <li class="fiction">Fiction - The Great Gatsby</li>
        <li class="historical">Historical Fiction - All the Light We Cannot See</li>
        <li class="nonfiction">Non-Fiction - Educated</li>
        <li class="mystery">Mystery - Gone Girl</li>
        <li class="poetry">Poetry - The Waste Land</li>
        <li class="fiction">Fiction - The Kite Runner</li>
        <li class="historical">Historical Fiction - The Other Boleyn Girl</li>
        <li class="nonfiction">Non-Fiction - Becoming</li>
        <li class="mystery">Mystery - Big Little Lies</li>
        <li class="poetry">Poetry - The Sun and Her Flowers</li>
        <li class="fiction">Fiction - Life of Pi</li>
        <li class="historical">Historical Fiction - The Nightingale</li>
        <li class="nonfiction">Non-Fiction - The Immortal Life of Henrietta Lacks</li>
        <li class="mystery">Mystery - The Da Vinci Code</li>
        <li class="poetry">Poetry - Milk and Honey</li>
        <li class="fiction">Fiction - The Road</li>
        <li class="historical">Historical Fiction - The Help</li>
        <li class="nonfiction">Non-Fiction - The Wright Brothers</li>
        <li class="mystery">Mystery - In the Woods</li>
        <li class="poetry">Poetry - The Collected Poems of W.B. Yeats</li>
        <li class="fiction">Fiction - The Goldfinch</li>
        <li class="historical">Historical Fiction - The Book Thief</li>
        <li class="nonfiction">Non-Fiction - The Glass Castle</li>
        <li class="mystery">Mystery - The Woman in the Window</li>
        <li class="poetry">Poetry - Ariel</li>
        <li class="fiction">Fiction - Where the Crawdads Sing</li>
        <li class="historical">Historical Fiction - The Paris Library</li>
        <li class="nonfiction">Non-Fiction - Hillbilly Elegy</li>
        <li class="mystery">Mystery - The Silent Patient</li>
        <li class="poetry">Poetry - The Essential Rumi</li>
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
        <li class="adiga">Aravind Adiga - The White Tiger</li>
        <li class="divakaruni">Chitra Banerjee Divakaruni - The Palace of Illusions</li>
        <li class="guha">Ramachandra Guha - India After Gandhi</li>
        <li class="chandra">Vikram Chandra - Sacred Games</li>
        <li class="tagore">Rabindranath Tagore - Gitanjali</li>
        <li class="frost">Robert Frost - The Collected Poems</li>
        <li class="dickinson">Emily Dickinson - The Complete Poems</li>
        <li class="morrison">Toni Morrison - Beloved</li>
        <li class="orwell">George Orwell - 1984</li>
        <li class="hemingway">Ernest Hemingway - The Old Man and the Sea</li>
        <li class="austen">Jane Austen - Pride and Prejudice</li>
        <li class="shakespeare">William Shakespeare - Hamlet</li>
        <li class="chevalier">Tracy Chevalier - The Girl with a Pearl Earring</li>
        <li class="martel">Yann Martel - Life of Pi</li>
        <li class="coelho">Paulo Coelho - The Alchemist</li>
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
        <li class="2008">2008 - The White Tiger</li>
        <li class="2009">2009 - The Palace of Illusions</li>
        <li class="2010">2010 - India After Gandhi</li>
        <li class="2011">2011 - Sacred Games</li>
        <li class="2012">2012 - Gitanjali</li>
        <li class="2013">2013 - The Night Circus</li>
        <li class="2014">2014 - A Little Life</li>
        <li class="2015">2015 - The Book Thief</li>
        <li class="2016">2016 - The Girl with the Dragon Tattoo</li>
        <li class="2017">2017 - Sapiens: A Brief History of Humankind</li>
        <li class="2018">2018 - The Great Gatsby</li>
        <li class="2019">2019 - All the Light We Cannot See</li>
        <li class="2020">2020 - Educated</li>
        <li class="2021">2021 - Gone Girl</li>
        <li class="2022">2022 - The Road</li>
        <li class="2023">2023 - The Nightingale</li>
    </ul>
</section>

<footer>
    <p>&copy; 2024 Library Book Collection</p>
</footer>

<script>
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
            } else {
                alert('Login failed. Please try again.');
            }
        });
    }

    function filterBooks(filterType) {
        const selectedValue = document.getElementById(filterType + 'Filter').value;
        const allBooks = document.querySelectorAll(`ul#${filterType}List li`);

        allBooks.forEach(book => {
            if (selectedValue === 'all' || book.classList.contains(selectedValue)) {
                book.style.display = 'block';
            } else {
                book.style.display = 'none';
            }
        });
    }
</script>
</body>
</html>
    `);
});

app.listen(PORT, () => {
    console.log(`Server is running on http://localhost:${PORT}`);
});
