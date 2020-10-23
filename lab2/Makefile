all: install test run deploy

install:
	@echo "Setting up pipenv environment..."
	pip install pipenv
	pipenv --python 3.8 
	pipenv install requests
	pipenv install ntplib
	pipenv install pytest

test:
	@echo "Running tests..."
	pipenv run python3 app.py >> results.txt

run:
	@echo "Running app..."
	pipenv run pytest tests/tests.py >> results.txt

deploy:
	@echo "Deploying"
	git add results.txt
	git commit -m "додаємо results.txt"
	git push
