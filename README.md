# Pup - Lightweight Python Packaging Wrapper

Simple script which wraps the `pip` and `python` programs to install and manage dependencies locally.

## Usage

Put the `pup` script somewhere on your path e.g. `~/bin/` (plus, `export PATH="$HOME/bin:$PATH"` somewhere).

### Install a Package

Install a package locally by running:

    pup install <package>

For example:

    pup install awslogs

This will also take a text file of requirements:

    pup install -r requirements.txt

### Executing an Installed Program

You can run a program with:

    pup exec <script>

For example:

    pup exec awslogs get --aws-region=us-east-1 production myapp --watch


### Running a Local Program with its Dependencies

Install any required modules, write your code, then:

    pup run myapp.py

For example, put the Flask example into `myapp.py`:

    from flask import Flask
    app = Flask(__name__)

    @app.route("/")
    def hello():
        return "Hello World!"

    if __name__ == "__main__":
        app.run()

Install the `Flask` package, as per the example above, then run:

    pup run myapp.py 

    * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)

## Disclaimer

I wrote this as an experiment to see if it was possible. There are no tests, I'm not running it in production and I don't intend to support it.
