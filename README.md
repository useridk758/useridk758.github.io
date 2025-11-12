<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>hey</title>
    <style>
        /* CSS for the fade-in animation */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        body {
            /* Set a background color for contrast (e.g., black) */
            background-color: #000; 
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: flex-start; /* Align at the top */
            height: 100vh;
            font-family: sans-serif; /* Use a clean font */
        }

        .fade-in-text {
            color: #fff; /* White text color */
            font-weight: bold; /* Bold text */
            font-size: 2em; /* Large text size */
            padding-top: 20px; /* Add some space from the very top */
            animation: fadeIn 2s ease-out forwards; /* Apply the animation */
            opacity: 0; /* Start with opacity 0, the animation handles the rest */
        }
    </style>
</head>
<body>
    <div class="fade-in-text">
        hello and welcome to useridk758's website!!
    </div>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>useridk758's Website</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Section 1: Hello and Welcome -->
    <div class="hero-section" id="section1">
        <h1 class="fade-in-text">HELLO AND WELCOME TO USERIDK758'S WEBSITE!!</h1>
    </div>

    <!-- Spacer div to allow scrolling -->
    <div class="spacer"></div>

    <!-- Section 2: GAMES -->
    <div class="hero-section" id="section2">
        <h1 class="fade-in-text">GAMES</h1>
    </div>

    <script src="script.js"></script>
</body>
</html>
