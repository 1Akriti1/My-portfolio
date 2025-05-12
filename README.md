# My-portfolio
# Create a zip file with basic HTML/CSS files for Akriti Bhagat's portfolio website

from pathlib import Path
from zipfile import ZipFile

# Create the necessary files and directories
base_dir = Path("/mnt/data/akriti_portfolio")
base_dir.mkdir(exist_ok=True)

# HTML content
index_html = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Akriti Bhagat | Content Writer</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Akriti Bhagat</h1>
        <p>Creative & Professional Content Writer</p>
    </header>

    <nav>
        <ul>
            <li><a href="#about">About Me</a></li>
            <li><a href="#portfolio">Portfolio</a></li>
            <li><a href="#resume">Resume</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section id="about">
        <h2>About Me</h2>
        <p>I am a passionate content writer with a flair for crafting compelling stories, articles, and digital content that engages and informs. With a strong grasp of SEO and audience-focused writing, I aim to create meaningful connections through words.</p>
    </section>

    <section id="portfolio">
        <h2>Portfolio</h2>
        <ul>
            <li><strong>Blog Post:</strong> <a href="#">"The Power of Content Marketing"</a></li>
            <li><strong>Website Copy:</strong> <a href="#">Landing Page for a Wellness Brand</a></li>
            <li><strong>Article:</strong> <a href="#">"Top 10 Tips for Freelance Writers"</a></li>
        </ul>
    </section>

    <section id="resume">
        <h2>Resume</h2>
        <p><strong>Experience:</strong><br>
        Freelance Content Writer (2021–Present)<br>
        Junior Copywriter at XYZ Agency (2020–2021)</p>
        <p><strong>Education:</strong><br>
        B.A. in English Literature</p>
    </section>

    <section id="contact">
        <h2>Contact Me</h2>
        <p>Email: <a href="mailto:akriti@example.com">akriti@example.com</a></p>
        <p>LinkedIn: <a href="#">linkedin.com/in/akritibhagat</a></p>
    </section>

    <footer>
        <p>© 2025 Akriti Bhagat</p>
    </footer>
</body>
</html>
"""

# CSS content
style_css = """
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
    color: #333;
    background-color: #f9f9f9;
}

header {
    background: #004080;
    color: #fff;
    padding: 20px;
    text-align: center;
}

nav {
    background: #e0e0e0;
    padding: 10px;
    text-align: center;
}

nav ul {
    list-style: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 15px;
}

nav ul li a {
    text-decoration: none;
    color: #004080;
}

section {
    padding: 20px;
    max-width: 800px;
    margin: auto;
}

footer {
    background: #004080;
    color: #fff;
    text-align: center;
    padding: 10px;
}
"""

# Save files
index_file = base_dir / "index.html"
css_file = base_dir / "style.css"

index_file.write_text(index_html)
css_file.write_text(style_css)

# Create zip file
zip_path = "/mnt/data/akriti_portfolio.zip"
with ZipFile(zip_path, "w") as zipf:
    zipf.write(index_file, arcname="index.html")
    zipf.write(css_file, arcname="style.css")

zip_path
