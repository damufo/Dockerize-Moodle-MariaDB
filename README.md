# Dockerize-Moodle-MariaDB
```
Start:

  1. docker-compose up -d
  2. Access on localhost:80
```

# Deploy behind Reverse Proxy
```
If you want to deploy behind Revere proxy (https://github.com/gilangvperdana/Multiple-Https-Nginx-withOneServer)
Please to change some configuration inside container :

/var/www/html/moodle/config.php :
$CFG->wwwroot   = 'https://your.domain.com';
$CFG->sslproxy = true;

and Comment 3-line on index.php (var/www/html/moodle/admin/index.php) :
Comment in line 753-755,

//        if ($adminuser->lastip !== getremoteaddr()) {
//           print_error('installhijacked', 'admin');
//        }
        
Refresh your web, and happy deploying!
```
