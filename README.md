# static-_website_hosting_on_docker
host static website by running apache server inside docker

steps-
mkdir my-website
cd my-website

# Build Docker image
docker build -t my-static-site .

# Run container
docker run -d -p 8080:80 --name website my-static-site

# Optional: run with local folder mount
docker run -d -p 8080:80 --name website -v $(pwd)/my-website:/usr/local/apache2/htdocs/ httpd:2.4
