docker run -d --name ghost-app \
-e "VIRTUAL_HOST=jradd.com,www.jradd.com,blog.jradd.com" \
-e "LETSENCRYPT_HOST=jradd.com,www.jradd.com,blog.jradd.com" \
-e "LETSENCRYPT_EMAIL=jredd42@gmail.com" \
--volumes-from ghost-data \
-p 8080:2368 \
ghost
