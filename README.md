
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>QuizHive - Responsive Grid Layout</title>

    <style>

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f4f1ff;
        }

        /* Header */
        header {
            background-color: #291653;
            color: white;
            text-align: center;
            padding: 25px;
        }

        header h1 {
            color: #ffcc4d;
            font-size: 35px;
        }

        header p {
            margin-top: 10px;
        }

        /* Navigation */
        nav {
            background-color: #493078;
            display: flex;
            justify-content: center;
            gap: 30px;
            padding: 15px;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
        }

        nav a:hover {
            color: #ffcc4d;
        }

        /* Main Heading */
        .container {
            text-align: center;
            padding: 30px 20px;
        }

        .container h2 {
            color: #493078;
            margin-bottom: 10px;
        }

        .container p {
            margin-bottom: 25px;
        }

        /* Responsive Grid */
        .gallery {
            display: grid;
            grid-template-columns:
                repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
            padding: 20px;
            max-width: 1100px;
            margin: auto;
        }

        /* Gallery Cards */
        .card {
            background-color: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            cursor: pointer;
            display: block;
        }

        .card h3 {
            color: #493078;
            padding: 15px;
        }

        .card p {
            padding: 0 15px 15px;
            color: #555;
        }

        /* Lightbox */
        .lightbox {
            display: none;
            position: fixed;
            z-index: 100;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.9);
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .lightbox img {
            max-width: 90%;
            max-height: 80%;
            border-radius: 10px;
        }

        .close {
            position: absolute;
            top: 20px;
            right: 35px;
            color: white;
            font-size: 35px;
            cursor: pointer;
            background: none;
            border: none;
        }

        /* Footer */
        footer {
            background-color: #291653;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 30px;
        }

        /* Responsive Design */
        @media (max-width: 600px) {

            nav {
                flex-wrap: wrap;
                gap: 15px;
            }

            .gallery {
                grid-template-columns: 1fr;
            }

            header h1 {
                font-size: 28px;
            }
        }

        @media (min-width: 601px) and (max-width: 900px) {

            .gallery {
                grid-template-columns: repeat(2, 1fr);
            }
        }

    </style>
</head>

<body>

    <!-- Header -->
    <header>
        <h1>QuizHive 🐝</h1>
        <p>Gamified Quizzes for Interactive Learning</p>
    </header>

    <!-- Navigation -->
    <nav>
        <a href="#home">Home</a>
        <a href="#gallery">Gallery</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
    </nav>

    <!-- Main Section -->
    <div class="container" id="home">

        <h2>Welcome to QuizHive!</h2>

        <p>
            Learn new things through fun
            and interactive quizzes.
        </p>

    </div>

    <!-- Image Gallery -->
    <div class="gallery" id="gallery">

        <div class="card">
            <img
            src="https://images.unsplash.com/photo-1434030216411-0b793f4b4173?w=600"
            alt="Students studying"
            tabindex="0"
            onclick="openImage(this.src)">
            <h3>General Knowledge</h3>
            <p>Improve your general knowledge.</p>
        </div>

        <div class="card">
            <img
            src="https://images.unsplash.com/photo-1509062522246-3755977927d7?w=600"
            alt="Classroom learning"
            tabindex="0"
            onclick="openImage(this.src)">
            <h3>Education Quiz</h3>
            <p>Learn different subjects easily.</p>
        </div>

        <div class="card">
            <img
            src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?w=600"
            alt="Online learning"
            tabindex="0"
            onclick="openImage(this.src)">
            <h3>Technology Quiz</h3>
            <p>Test your technology knowledge.</p>
        </div>

        <div class="card">
            <img
            src="https://images.unsplash.com/photo-1503676260728-1c00da094a0b?w=600"
            alt="Books and learning"
            tabindex="0"
            onclick="openImage(this.src)">
            <h3>Science Quiz</h3>
            <p>Explore the world of science.</p>
        </div>

        <div class="card">
            <img
            src="https://images.unsplash.com/photo-1513258496099-48168024aec0?w=600"
            alt="Student writing"
            tabindex="0"
            onclick="openImage(this.src)">
            <h3>English Quiz</h3>
            <p>Improve your English skills.</p>
        </div>

        <div class="card">
            <img
            src="https://images.unsplash.com/photo-1509228468518-180dd4864904?w=600"
            alt="Mathematics learning"
            tabindex="0"
            onclick="openImage(this.src)">
            <h3>Maths Quiz</h3>
            <p>Practice mathematics questions.</p>
        </div>

    </div>

    <!-- Lightbox -->
    <div class="lightbox" id="lightbox"
         onclick="closeImage()">

        <button class="close"
                aria-label="Close image"
                onclick="closeImage()">
            &times;
        </button>

        <img id="largeImage" alt="Enlarged gallery image">

    </div>

    <!-- Footer -->
    <footer id="contact">
        <p>© 2026 QuizHive. All Rights Reserved.</p>
        <p>Learn • Play • Grow</p>
    </footer>

    <!-- JavaScript -->
    <script>

        function openImage(imageSrc) {

            document.getElementById("lightbox")
                .style.display = "flex";

            document.getElementById("largeImage")
                .src = imageSrc;
        }

        function closeImage() {

            document.getElementById("lightbox")
                .style.display = "none";
        }

        document.addEventListener("keydown", function(event) {
            if (event.key === "Escape") {
                closeImage();
            }
        });

        document.querySelectorAll(".card img").forEach(function(img) {
            img.addEventListener("keydown", function(event) {
                if (event.key === "Enter" || event.key === " ") {
                    event.preventDefault();
                    openImage(this.src);
                }
            });
        });

    </script>

</body>
</html>

