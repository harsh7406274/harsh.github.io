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
        </select>
    </div>
    <ul id="authorList">
        <li class="adiga">Aravind Adiga - The White Tiger</li>
        <li class="divakaruni">Chitra Banerjee Divakaruni - The Palace of Illusions</li>
        <li class="guha">Ramachandra Guha - India After Gandhi</li>
        <li class="chandra">Vikram Chandra - Sacred Games</li>
        <li class="tagore">Rabindranath Tagore - Gitanjali</li>
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
            <option value="2007">2007</option>
            <option value="2006">2006</option>
            <option value="1910">1910</option>
        </select>
    </div>
    <ul id="dateList">
        <li class="2008">2008 - The White Tiger</li>
        <li class="2009">2009 - The Palace of Illusions</li>
        <li class="2007">2007 - India After Gandhi</li>
        <li class="2006">2006 - Sacred Games</li>
        <li class="1910">1910 - Gitanjali</li>
    </ul>
</section>

<footer>
    <p>&copy; 2024 Library Collection. All rights reserved.</p>
</footer>

<script>
    function filterBooks(type) {
        const genreFilter = document.getElementById('genreFilter').value;
        const authorFilter = document.getElementById('authorFilter').value;
        const dateFilter = document.getElementById('dateFilter').value;

        const genreList = document.getElementById('genreList').children;
        const authorList = document.getElementById('authorList').children;
        const dateList = document.getElementById('dateList').children;

        for (let li of genreList) {
            li.style.display = (genreFilter === 'all' || li.classList.contains(genreFilter)) ? '' : 'none';
        }
        for (let li of authorList) {
            li.style.display = (authorFilter === 'all' || li.classList.contains(authorFilter)) ? '' : 'none';
        }
        for (let li of dateList) {
            li.style.display = (dateFilter === 'all' || li.classList.contains(dateFilter)) ? '' : 'none';
        }
    }
</script>

</body>
</html>
