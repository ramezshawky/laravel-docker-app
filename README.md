# Laravel Application using Docker and Docker Compose

You need to have Docker and Docker Compose installed on your server to proceed using this PHP environment.

This is a PHP development environment used to run Laravel applications. The following three separate service containers will be used:

<ol>
  <li>An app service running PHP7.4-FPM.</li>
  <li>A DB service running MySQL:8.0.</li>
  <li>An nginx:1.17-alpine service.</li>
</ol>

# Running the application
<ul>
    <li>To get started, set up your application in the root directory.</li>
    <li>Set the environment variables, creating a `.env` file. See the MySQL service section below for more information.</li>
    <li>Build the app image with the following command:</li>
</ul>

     git clone git@github.com:ramezshawky/laravel-docker-app.git
      
     docker compose build -t travellist-app
    
<ul>
<li>When the build is finished, you can run the environment in background mode with:</li>
</ul>

      docker compose up -d
            
<ul>
<li>To show information about the state of your active services, run:</li>
</ul>

      docker compose ps

The environment is now up and running, but you still need to execute a couple commands to finish setting up the Laravel application. You can use the `docker compose exec` command to execute commands in the service containers, such as a `ls -l` to show detailed information about files in the application directory:

      docker compose exec app ls -l

Generate a unique application key with the Artisan Laravel command-line tool. This key is used to encrypt user sessions and other sensitive data:

      docker compose exec app php artisan key:generate

<ul><li>Now go to your browser and access your server’s domain name or IP address on port `8000`:</li></ul>

        http://localhost:8000

<ul><li>If you want to pause your Docker Compose environment while keeping the state of all its services, run:</li></ul>

       docker compose pause

<ul><li>You can then resume your services with:</li></ul>

        docker compose unpause
