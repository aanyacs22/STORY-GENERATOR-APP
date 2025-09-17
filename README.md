# STORY-GENERATOR-APP
“Python Flask app that generates dynamic stories from user inputs with a modular, scalable backend.”
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/", methods=["GET", "POST"])
def index():
    story = ""
    if request.method == "POST":
        character = request.form.get("character")
        place = request.form.get("place")
        story = f"Once upon a time, {character} went to {place} and had an amazing adventure!"
    return render_template("index.html", story=story)

if __name__ == "__main__":
    app.run(debug=True)
    <!DOCTYPE html>
<html>
<head>
    <title>Story Generator App</title>
</head>
<body>
    <h1>Story Generator</h1>
    <form method="POST">
        Character: <input type="text" name="character" required><br>
        Place: <input type="text" name="place" required><br>
        <input type="submit" value="Generate Story">
    </form>
    {% if story %}
    <h2>Your Story:</h2>
    <p>{{ story }}</p>
    {% endif %}
</body>
</html>
# 📖 Story Generator App

## Short Description
Python Flask app that generates dynamic stories from user inputs with a modular, scalable backend design.

## Extended Description
This Flask web application allows users to create interactive stories by entering a character and a place. The backend is modular, making it easy to add more story templates or features. Ideal for learning Flask, backend design, and interactive storytelling.

## Features
- Dynamic story generation based on user inputs
- Modular backend for scalability
- Interactive web interface
from flask import Flask, render_template, request

app = Flask(__name__)

# Route for homepage
@app.route("/", methods=["GET", "POST"])
def index():
    story = ""
    if request.method == "POST":
        # Get user inputs
        character = request.form.get("character")
        place = request.form.get("place")
        # Generate story
        story = f"Once upon a time, {character} went to {place} and had an amazing adventure!"
    return render_template("index.html", story=story)

if __name__ == "__main__":
    # Run the Flask app
    app.run(debug=True)

