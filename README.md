# DevTinder

- Created a Vite + React application
- Remove unecessary code and create a Hellow World app
- Install Tailwind css //npm install tailwindcss @tailwindcss/vite
- Install daisyUI
- Add NavBar component to App.jsx
- Create NavBar separate component file
- Install react-router-dom
- Craete BrowserRouter >Routes>Route=/Body>RouteChildren
- Craete an Outlet in your Body Component
- Create footer
- Create a login page
- Install axios
- CORS - install cors in backend=> add middleware to app with configurations: origin, creadentials: true
  -Whenever you're making API call so pass axios=> {withCredentials: true}
- Install react-redux + @reduxjs/toolkit-https://redux-toolkit.js.org/tutorials/quick-start
- configureStore=>Provider=>createSlice=>add reducer to store
- Add redux devtools in chrome
- Login and see if you data is coming properly in store
- NavBar should update as soon as user logs in
- Refactor our code to add constants files + create a components folder
- You shoud not be acces to other routes without login
- If token is not prasent, redirect user to login page
- Logout Feature
- Get the feed and the feed in the store
- Build the user card on feed
- Edit profile fetaure
- Show tost message on save of profile
- New page - See all my connections
- New page - See all my Connection Requests
- Feature - Accept/Reject Connection Request
- Send/ignore the user card from feed
- Sigup new user
- ETETesting

Body
Navbar
Route=/ => Feed
Route=/login => Login
Route=/connections => Connections
Route=/profile => Profile

# Deployment

- Sinup on AWS
- Launch instance
- chmod 400 <secret>.pem
- ssh -i "devTinder-secret.pem" ubuntu@ec2-13-207-185-115.ap-south-1.compute.amazonaws.com
- Install Node version 24.12.0
- Git clone
- Frontend
  - npm install -> dependencies install
  - npm run build
  - sudo apt update
  - sudo apt install nginx
  - sudo systemctl start nginx
  - sudo systemctl enable nginx
  - Copy code from dist(build files) to /var/www/html
  - sudo scp -r dist/\* /var/www/html/
  - Enable port :80 of instance

- Backend
  - allowed ec2 instance public IP on mongodb server
  - npm install pm2 -g
  - pm2 start npm --name "devtinder-backend" -- start - with custome name command
  - pm2 start npm -- start
  - pm2 logs -
  - pm2 list, pm2 flush <name>, pm2 stop, pm2 delete <name>
  - config nginx - sudo nano /etc/nginx/sites-available/default
  - restart nginx- sudo systemctl restart nginx
  - Modify the BASE_URL in frontend project to "/api"

  # Nginx config:

  Frontend: http://13.207.185.115/
  Backend: http://13.207.185.115:3000/

  Domain name = devTinder.com=> 13.207.185.115

  Frontend = devTinder.com
  Backend = devTinder.com:3000=>devTinder.com/api

  server_name 13.207.185.115;

  location /api/ {
  proxy_pass http://localhost:3000/;

        proxy_http_version 1.1;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;

        # WebSocket support (if needed)
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";

  }

# Adding a custome Domain name

- purchased domain name from godaddy
- signup on cloudflare & add new domain name
- change the name servers on godaddy and point it to cloudflare
- wait for some time till your name servers are updated ~15 min
- DNS record: A <DomainName> 13.207.185.115
- Enable SSL for website
