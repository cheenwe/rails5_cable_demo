## README
Rails 5 Demo of Action Cable https://www.youtube.com/watch?v=n0WUjGkDFS0&feature=youtu.be by DHH

## nginx with WebSocket
```ruby
server {
  listen       5000;
  server_name  cheenwe.cn;
  root  /home/ubuntu/rails5_cable_demo/public;
  location / {
      proxy_set_header Host $host;
      proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for; 
      proxy_redirect off;
      proxy_pass http://localhost:3000;
      #This is for WebSocket
      proxy_http_version 1.1;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Connection "Upgrade";
    }
}
```
