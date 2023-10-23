FROM python:3.8
## Step 1:
# Create a working directory
WORKDIR /app
## Step 2:
# Copy source code to working directory
COPY . /app

## Step 3:
#RUN pip install -i https://pypi.org/simple flask
#RUN pip install --no-cache-dir --trusted-host pypi.python.org -r ./techtrends/requirements.txt
RUN pip install --no-cache-dir --trusted-host pypi.python.org -r techtrends/requirements.txt
## Step 4:
# Ensure that the database is initialized with the pre-defined posts in the init_db.py file
#COPY ./techtrends/init_db.py ./
RUN echo "Current working directory:" && pwd && echo "Contents of the current directory:" && ls
RUN python techtrends/init_db.py

# Expose port 80
EXPOSE 3111

## Step 5:
# Run app.py at container launch
CMD ["python", "app.py"]