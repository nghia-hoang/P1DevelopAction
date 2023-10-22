FROM python:3.8
## Step 1:
# Create a working directory
WORKDIR /app
## Step 2:
# Copy source code to working directory
COPY . /app
# Ensure that the database is initialized with the pre-defined posts in the init_db.py file
COPY init_db.py ./
RUN python init_db.py
## Step 3:
# Install packages from requirements.txt
# hadolint ignore=DL3013
#RUN pip install -i https://pypi.org/simple flask
RUN pip install --no-cache-dir --trusted-host pypi.python.org -r requirements.txt
## Step 4:
# Expose port 80
EXPOSE 3111

## Step 5:
# Run app.py at container launch
CMD ["python", "app.py"]