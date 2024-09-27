<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Library Book Collection</title>
    <style>
        body {
            font-family: 'Helvetica Neue', Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f1f3f5;
            color: #333;
            line-height: 1.6;
        }

        header {
            background-color: #2C3E50;
            color: white;
            text-align: center;
            padding: 1.5em 0;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        nav a {
            margin: 0 20px;
            color: white;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s;
        }

        nav a:hover {
            color: #18BC9C;
        }

        section {
            padding: 30px;
            margin: 20px auto;
            max-width: 700px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        h2 {
            color: #2C3E50;
            margin-bottom: 20px;
            font-size: 1.8em;
            border-bottom: 2px solid #18BC9C;
            padding-bottom: 10px;
        }

        ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }

        ul li {
            background-color: #f9f9f9;
            margin: 10px 0;
            padding: 15px;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1.1em;
            transition: background-color 0.3s;
        }

        ul li:hover {
            background-color: #f0f4f8;
        }

        footer {
            text-align: center;
            padding: 20px 0;
            background-color: #2C3E50;
            color: white;
            position: relative;
            bottom: 0;
            width: 100%;
            box-shadow: 0 -4px 6px rgba(0, 0, 0, 0.1);
        }

        .filter {
            margin-bottom: 20px;
            display: flex;
            flex-direction: column;
        }

        .filter label {
            margin-bottom: 8px;
            font-weight: bold;
            color: #2C3E50;
        }

        .filter select {
            padding: 12px;
            border-radius: 6px;
            border: 1px solid #ccc;
            font-size: 1em;
            transition: border-color 0.3s;
        }

        .filter select:focus {
            border-color: #18BC9C;
            outline: none;
        }

        @media (max-width: 768px) {
            section {
                margin: 10px;
                padding: 20px;
            }

            nav a {
                margin: 0 10px;
            }
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
        <li class="fiction">Fiction - The Great Gatsby</li>
        <li class="fiction">Fiction - To Kill a Mockingbird</li>
        <li class="fiction">Fiction - 1984</li>
        <li class="fiction">Fiction - Pride and Prejudice</li>
        <li class="fiction">Fiction - The Catcher in the Rye</li>
        <li class="fiction">Fiction - The Road</li>
        <li class="fiction">Fiction - Life of Pi</li>
        <li class="fiction">Fiction - The Kite Runner</li>
        <li class="fiction">Fiction - The Alchemist</li>
        <li class="historical">Historical Fiction - The Palace of Illusions</li>
        <li class="historical">Historical Fiction - The Book Thief</li>
        <li class="historical">Historical Fiction - The Nightingale</li>
        <li class="historical">Historical Fiction - All the Light We Cannot See</li>
        <li class="historical">Historical Fiction - Atonement</li>
        <li class="historical">Historical Fiction - The Pillars of the Earth</li>
        <li class="historical">Historical Fiction - The Help</li>
        <li class="historical">Historical Fiction - The Other Boleyn Girl</li>
        <li class="historical">Historical Fiction - Water for Elephants</li>
        <li class="historical">Historical Fiction - Outlander</li>
        <li class="nonfiction">Non-Fiction - India After Gandhi</li>
        <li class="nonfiction">Non-Fiction - Sapiens: A Brief History of Humankind</li>
        <li class="nonfiction">Non-Fiction - The Immortal Life of Henrietta Lacks</li>
        <li class="nonfiction">Non-Fiction - Educated</li>
        <li class="nonfiction">Non-Fiction - Becoming</li>
        <li class="nonfiction">Non-Fiction - The Wright Brothers</li>
        <li class="nonfiction">Non-Fiction - The Glass Castle</li>
        <li class="nonfiction">Non-Fiction - Unbroken</li>
        <li class="nonfiction">Non-Fiction - The Soul of America</li>
        <li class="nonfiction">Non-Fiction - Quiet: The Power of Introverts</li>
        <li class="mystery">Mystery - Sacred Games</li>
        <li class="mystery">Mystery - The Girl with the Dragon Tattoo</li>
        <li class="mystery">Mystery - Gone Girl</li>
        <li class="mystery">Mystery - The Da Vinci Code</li>
        <li class="mystery">Mystery - And Then There Were None</li>
        <li class="mystery">Mystery - The Cuckoo's Calling</li>
        <li class="mystery">Mystery - In the Woods</li>
        <li class="mystery">Mystery - The No. 1 Ladies' Detective Agency</li>
        <li class="mystery">Mystery - The Secret History</li>
        <li class="mystery">Mystery - The Woman in White</li>
        <li class="poetry">Poetry - Gitanjali</li>
        <li class="poetry">Poetry - The Sun and Her Flowers</li>
        <li class="poetry">Poetry - Milk and Honey</li>
        <li class="poetry">Poetry - Leaves of Grass</li>
        <li class="poetry">Poetry - The Waste Land</li>
        <li class="poetry">Poetry - The Love Song of J. Alfred Prufrock</li>
        <li class="poetry">Poetry - The Raven</li>
        <li class="poetry">Poetry - A Street in Bronzeville</li>
        <li class="poetry">Poetry - The Collected Poems of W.B. Yeats</li>
        <li class="poetry">Poetry - Ariel</li>
        <li class="fiction">Fiction - The Time Traveler's Wife</li>
        <li class="fiction">Fiction - The Picture of Dorian Gray</li>
        <li class="fiction">Fiction - The Brief Wondrous Life of Oscar Wao</li>
        <li class="fiction">Fiction - A Thousand Splendid Suns</li>
        <li class="fiction">Fiction - The Fault in Our Stars</li>
        <li class="fiction">Fiction - Little Fires Everywhere</li>
        <li class="fiction">Fiction - The Night Circus</li>
        <li class="historical">Historical Fiction - The Other Einstein</li>
        <li class="historical">Historical Fiction - The Tea Girl of Hummingbird Lane</li>
        <li class="historical">Historical Fiction - The Night Watchman</li>
        <li class="historical">Historical Fiction - The Tattooist of Auschwitz</li>
        <li class="historical">Historical Fiction - The Alice Network</li>
        <li class="historical">Historical Fiction - The Girl Who Lived</li>
        <li class="nonfiction">Non-Fiction - Thinking, Fast and Slow</li>
        <li class="nonfiction">Non-Fiction - Freakonomics</li>
        <li class="nonfiction">Non-Fiction - The Body Keeps the Score</li>
        <li class="nonfiction">Non-Fiction - The Subtle Art of Not Giving a F*ck</li>
        <li class="nonfiction">Non-Fiction - Atomic Habits</li>
        <li class="nonfiction">Non-Fiction - Outliers</li>
        <li class="mystery">Mystery - The Woman in Cabin 10</li>
        <li class="mystery">Mystery - The Couple Next Door</li>
        <li class="mystery">Mystery - Behind Closed Doors</li>
        <li class="mystery">Mystery - The Family Upstairs</li>
        <li class="mystery">Mystery - The Silent Patient</li>
        <li class="mystery">Mystery - Big Little Lies</li>
        <li class="poetry">Poetry - The Essential Rumi</li>
        <li class="poetry">Poetry - The Complete Poems of Emily Dickinson</li>
        <li class="poetry">Poetry - The Poetry of Pablo Neruda</li>
        <li class="poetry">Poetry - The Collected Poems of Langston Hughes</li>
        <li class="poetry">Poetry - The Complete Poems of John Keats</li>
        <li class="poetry">Poetry - The Moon and Sixpence</li>
        <li class="fiction">Fiction - The Girl on the Train</li>
        <li class="fiction">Fiction - The Underground Railroad</li>
        <li class="fiction">Fiction - An American Marriage</li>
        <li class="fiction">Fiction - The Road Back</li>
        <li class="fiction">Fiction - Where the Crawdads Sing</li>
        <li class="fiction">Fiction - The Help</li>
        <li class="historical">Historical Fiction - The Night Watchman</li>
        <li class="historical">Historical Fiction - Homegoing</li>
        <li class="historical">Historical Fiction - The Good Lord Bird</li>
        <li class="historical">Historical Fiction - The Book of Longings</li>
        <li class="historical">Historical Fiction - The Great Alone</li>
        <li class="historical">Historical Fiction - The Last Train to London</li>
        <li class="nonfiction">Non-Fiction - Bad Blood: Secrets and Lies in a Silicon Valley Startup</li>
        <li class="nonfiction">Non-Fiction - The Devil's Chessboard</li>
        <li class="nonfiction">Non-Fiction - A People’s History of the United States</li>
        <li class="nonfiction">Non-Fiction - Just Mercy</li>
        <li class="nonfiction">Non-Fiction - The New Jim Crow</li>
        <li class="nonfiction">Non-Fiction - I Am Malala</li>
        <li class="mystery">Mystery - The 7 1/2 Deaths of Evelyn Hardcastle</li>
        <li class="mystery">Mystery - The Wife Between Us</li>
        <li class="mystery">Mystery - The Lying Game</li>
        <li class="mystery">Mystery - Then She Was Gone</li>
        <li class="mystery">Mystery - The Chain</li>
        <li class="mystery">Mystery - The Last Mrs. Parrish</li>
        <li class="poetry">Poetry - The Complete Poems of Anna Akhmatova</li>
        <li class="poetry">Poetry - The Poetry of Robert Frost</li>
        <li class="poetry">Poetry - The Poetry of William Carlos Williams</li>
        <li class="poetry">Poetry - The Collected Poems of Ted Hughes</li>
        <li class="poetry">Poetry - The Poetry of John Keats</li>
        <li class="poetry">Poetry - The Sunflower</li>
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
        <li class="adiga">Aravind Adiga - Amnesty</li>
        <li class="divakaruni">Chitra Banerjee Divakaruni - The Palace of Illusions</li>
        <li class="divakaruni">Chitra Banerjee Divakaruni - One Amazing Thing</li>
        <li class="guha">Ramachandra Guha - India After Gandhi</li>
        <li class="guha">Ramachandra Guha - Makers of Modern India</li>
        <li class="chandra">Vikram Chandra - Sacred Games</li>
        <li class="chandra">Vikram Chandra - Red Earth and Pouring Rain</li>
        <li class="tagore">Rabindranath Tagore - Gitanjali</li>
        <li class="frost">Robert Frost - The Road Not Taken</li>
        <li class="dickinson">Emily Dickinson - The Complete Poems</li>
        <li class="morrison">Toni Morrison - Beloved</li>
        <li class="orwell">George Orwell - 1984</li>
        <li class="hemingway">Ernest Hemingway - The Old Man and the Sea</li>
        <li class="austen">Jane Austen - Pride and Prejudice</li>
        <li class="shakespeare">William Shakespeare - Hamlet</li>
        <li class="chevalier">Tracy Chevalier - Girl with a Pearl Earring</li>
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
        <li class="date2008">2008 - The White Tiger</li>
        <li class="date2009">2009 - The Palace of Illusions</li>
        <li class="date2010">2010 - Freedom Song</li>
        <li class="date2011">2011 - The Night Circus</li>
        <li class="date2012">2012 - The Fault in Our Stars</li>
        <li class="date2013">2013 - The Goldfinch</li>
        <li class="date2014">2014 - All the Light We Cannot See</li>
        <li class="date2015">2015 - A Little Life</li>
        <li class="date2016">2016 - The Underground Railroad</li>
        <li class="date2017">2017 - The Handmaid's Tale</li>
        <li class="date2018">2018 - Where the Crawdads Sing</li>
        <li class="date2019">2019 - The Testaments</li>
        <li class="date2020">2020 - The Invisible Life of Addie LaRue</li>
        <li class="date2021">2021 - Klara and the Sun</li>
        <li class="date2022">2022 - The Lincoln Highway</li>
        <li class="date2023">2023 - The Island of Missing Trees</li>
    </ul>
</section>

<footer>
    <p>&copy; 2024 Library Book Collection</p>
</footer>

<script>
    function filterBooks(filterType) {
        const genreFilter = document.getElementById('genreFilter').value;
        const authorFilter = document.getElementById('authorFilter').value;
        const dateFilter = document.getElementById('dateFilter').value;

        const allBooks = document.querySelectorAll('ul li');

        allBooks.forEach(book => {
            let show = true;

            if (filterType === 'genre' && genreFilter !== 'all') {
                show = book.classList.contains(genreFilter);
            }
            if (filterType === 'author' && authorFilter !== 'all') {
                show = book.classList.contains(authorFilter);
            }
            if (filterType === 'date' && dateFilter !== 'all') {
                show = book.classList.contains(`date${dateFilter}`);
            }

            book.style.display = show ? 'block' : 'none';
        });
    }
</script>

</body>
</html>
