---
layout: null
---



<html lang="pl">
<head>
    <meta charset="UTF-8">
    <title>Blog Opcja 3</title>
    <style>
        /* Reset podstawowych marginesów strony */
        body { 
            margin: 0; 
            padding: 0; 
            width: 100%;
            overflow-x: hidden;
        }
        
        /* Style dla menu rozwijanego (Dropdown) */
        .dropdown { position: relative; display: inline-block; }
        .dropdown-content { display: none; position: absolute; background-color: #ffffff; min-width: 250px; box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2); z-index: 1; top: 100%; left: 0; }
        .dropdown-content a { color: #000000 !important; padding: 12px 16px; text-decoration: none; display: block; font-size: 30px; font-family: 'Courier New', Courier, monospace; }
        .dropdown-content a:hover { background-color: #f1f1f1; }
        .dropdown:hover .dropdown-content { display: block; }

        /* Kontener pętli bloga zapewniający, że tekst nie rozciąga się na boki */
        .blog-posts-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            font-family: 'Courier New', Courier, monospace;
            min-height: 60vh;
        }
    </style>
</head>
<body>

    <!-- Główny pasek nawigacji (Zabezpieczony przed skakaniem do pionu) -->
    <div class="container" style="display: flex; flex-direction: row; align-items: center; justify-content: space-between; padding: 10px 40px; box-sizing: border-box; width: 100%;">
        <img src="logo.jpeg" alt="Logo" style="width: 200px; height: 200px; object-fit: cover; border-radius: 50%; flex-shrink: 0;">
        
        <!-- Wszystkie linki w jednej równej linii po prawej stronie -->
        <div style="display: flex; flex-direction: row; gap: 30px; align-items: center; white-space: nowrap;">
            <a href="index.html" style="font-size: 50px; font-family: 'Courier New', Courier, monospace; text-decoration: none; color: #000000;">GŁÓWNA</a>
            <div class="dropdown">
                <a href="#" style="font-size: 50px; font-family: 'Courier New', Courier, monospace; text-decoration: none; color: #928f84;">BLOG</a>
                <div class="dropdown-content">
                    <a href="traneg.html">Traneg</a>
                    <a href="wieslawpiecigrod.html">Wiesław Pięcigród</a>
                    <a href="opcja3.html">Opcja 3</a>
                </div>
            </div>
            <a href="przyciski.html" style="font-size: 50px; font-family: 'Courier New', Courier, monospace; text-decoration: none; color: #000000;">PRZYCISKI</a>
            <a href="DRIVE" style="font-size: 50px; font-family: 'Courier New', Courier, monospace; text-decoration: none; color: #000000;">ZDJĘCIA</a>
            <a href="login.html" style="font-size: 50px; font-family: 'Courier New', Courier, monospace; text-decoration: none; color: #000000;">LOGIN</a>
        </div>
    </div>

    <!-- Nagłówki środkowe -->
    <h1 style="font-size: 80px; text-align: center; font-family: 'Comic Neue'; margin-top: 40px;">Blog Opcja 3</h1>
    <h2 style="font-size: 50px; text-align: center; font-family: 'Courier New', Courier, monospace; margin-bottom: 50px;">BLOG OPCJA 3</h2>

    <!-- Środkowa sekcja z wpisami blogera -->
<div class="blog-posts-container">
    <!-- Przeszukujemy wszystkie posty -->
    {% for post in site.posts %}
        <!-- Sprawdzamy, czy autor wpisu to dokładnie: opcja3 -->
        {% if post.author == "opcja3" %}
            <div class="post-item" style="border-bottom: 2px solid #7c7c7c; margin-bottom: 30px; padding-bottom: 20px;">
                <p style="font-size: 24px; color: #928f84; margin: 0;">{{ post.date | date: "%Y-%m-%d" }} | Autor: {{ post.author }}</p>
                <h2 style="font-size: 40px; margin: 10px 0;">
                    <a href="{{ post.url }}" style="color: #000000; text-decoration: none; font-weight: bold;">{{ post.title }}</a>
                </h2>
                <p style="font-size: 30px; color: #333;">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
                <a href="{{ post.url | relative_url }}" style="font-size: 26px; color: #928f84; text-decoration: underline;">Czytaj dalej...</a>

            </div>
        {% endif %}
    {% endfor %}
</div>


    <!-- Stopka rozciągnięta prawidłowo na 100% szerokości na samym dole -->
    <div class="container" style="background-color: #7c7c7c; width: 100%; left: 0; right: 0; box-sizing: border-box;">
        <p style="font-size: 50px; text-align: center; font-family: 'Comic Neue'; margin: 0; padding: 40px 0;">
            Trade mark. All rights reserved. Chora psychiatrycznie Pięćdziesięciocentówka
        </p>
    </div>

</body>
</html>
