# mod_rewrite

### To run the container
`docker run -d -p 80:80 --name mod-rewrite-container -v "$PWD/src/":/var/www/html/ cesarhernandezgt/mod_rewrite`

* Server is available on host port 80.
* `src` is the host folder containing your `.htaccess` and `html` files.

### To inspect the container:
`docker exec -it mod-rewrite-container bash`
