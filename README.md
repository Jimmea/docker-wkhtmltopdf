# Wkhtmltopdf Docker image

docker build -t wkhtmltopdf-image .

docker run -d --name wkhtmltopdf_service -v $(pwd):/data wkhtmltopdf-image

docker run -d --name wkhtmltopdf_service \
  -v $(pwd):/data \
  -v /tmp:/tmp \
  wkhtmltopdf-image

# Run
docker exec wkhtmltopdf_service wkhtmltopdf --viewport-size 1280x1024 --page-size A4 /data/input.html /data/test.pdf
docker exec wkhtmltopdf_service wkhtmltopdf --viewport-size 1280x1024 --page-size A4 http://google.com/ /data/test.pdf