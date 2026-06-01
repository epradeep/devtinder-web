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
- See all my connections

Body
Navbar
Route=/ => Feed
Route=/login => Login
Route=/connections => Connections
Route=/profile => Profile
