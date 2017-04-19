Installation Instructions

Install composer dependencies : composer install
Copy .env.example content to .env file ( Do not delete the original example file) : cp .env.example .env
Install node dependencies using yarn : yarn install
Run gulp for frontend development and then gulp watch : gulp && gulp watch
Copy Homestead.yaml.example to Homestead.yaml : cp Homestead.yaml.example Homestead.yaml
Change /path/to/your/project/ to your project folder path
Get copy of vagrant box and place it in your ~/.vagrant.d/boxes/ or simply download homestead box version 0.5.0
Finally do vagrant up and log into it : vagrant up && vagrant ssh
Your server is up now lets migrate the database & seed some test data: php artisan migrate --seed
Packages Used

Laravel Packages

Vue.js Packages

vue-router
vue-resource
vue-head - Manager the meta information of the head tag, a simple and easy way
Common Issues

CORS issue on AWS CloudFront/S3

Need to add company-name header is allowed headers. Further reading: https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html#cors-allowed-methods

<?xml version="1.0" encoding="UTF-8"?>
<CORSConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">
    <CORSRule>
        <AllowedOrigin>*</AllowedOrigin>
        <AllowedMethod>GET</AllowedMethod>
        <MaxAgeSeconds>3000</MaxAgeSeconds>
        <AllowedHeader>Authorization</AllowedHeader>
        <AllowedHeader>company-name</AllowedHeader>
    </CORSRule>
</CORSConfiguration>

