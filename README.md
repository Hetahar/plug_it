![Plug It](./client/src/assets/images/logo.png)

### Overview

This project was developed as part of a Web Development course at Metropolia University of Applied Sciences. As the product owner and an electric vehicle (EV) user in Finland, I identified a need for a more efficient and visually appealing platform to locate EV charging stations. The idea for this project emerged in 2022 during a road trip in Norway, where EV infrastructure was already more advanced and widely supported compared to Finland.

#### Demo Link

The project is hosted online using [Render](https://render.com/). Please note that since it runs on a free-tier hosting plan, the initial request to the backend may take some time to respond. After this initial load, the site should perform smoothly.

**Client**: [https://web-project-group-6-client.onrender.com/](https://web-project-group-6-client.onrender.com/)
**Server**: [https://plugit-backend.onrender.com/](https://plugit-backend.onrender.com/)

For a quick video demo, follow this [link](https://drive.google.com/file/d/1nZfeoszwnqsxKQjOOVgXwzQ-AxhoO5uz/view?usp=sharing).

**API documentation UI**:
The Swagger UI for API documentation is available at: [https://plugit-backend.onrender.com/api-docs/](https://plugit-backend.onrender.com/api-docs/)

**Note**: API calls can only be tested locally at ``http://localhost:4000/api-docs`` while the backend server is running.

### **Features**  

- **Search EV Charging Stations** – Fetches data from the **Open Charge Map API** for up-to-date station information.  
- **User Authentication** – Secure login and signup with **JWT (JSON Web Tokens)**.  
- **Google Login/Signup** – Convenient authentication using **Google OAuth**.  
- **Interactive Map** – Displays EV charging stations across Finland with dynamic features.  
- **Mobile Responsiveness** – Fully responsive design implemented with **Tailwind CSS** for seamless use on all devices.  
- **Detailed Station Information** – Displays valid and up-to-date data, including:  
  - Connector types  
  - Provider (if available)  
  - Number of chargers  
  - Charging speeds  
  - Pricing (if available)  
  - **Plug It** user reviews  
  - Address  
- **Location Services** – Detects the user's current location.  
- **Contact Form** – Allows users to send inquiries or feedback directly through the app.  
- **Charger Reviews and Favorites** – Enables users to:  
  - Submit reviews for charging stations.  
  - Save favorite stations for quick access later.  

### Technologies Used

#### **Frontend (FE)**  
- **Core Libraries:**  
  - React (v18.3.1)  
  - React DOM (v18.3.1)  
  - React Router DOM (v6.28.0)  

- **Mapping and Geolocation:**  
  - Leaflet (v1.9.4)  
  - React-Leaflet (v4.2.1)  
  - React-Leaflet-Markercluster (v4.1.1)  
  - Mapbox GL (v3.8.0)  
  - React-Geolocated (v4.2.0)  

- **HTTP Requests:**  
  - Axios (v1.7.7)  

- **Environment Variables:**  
  - Dotenv (v16.4.5)  

- **Styling and Responsiveness:**  
  - Tailwind CSS (v3.4.14)  
  - PostCSS (v8.4.47)  
  - Autoprefixer (v10.4.20)  

- **Utilities:**  
  - Lodash (v4.17.21)  

- **Development Tools:**  
  - Vite (v5.4.10) – Frontend build tool  
  - ESLint (v9.13.0) – Linting and code quality  
  - Nodemon (v3.1.7) – Live server reloading  

---

#### **Backend (BE)**  
- **Core Framework:**  
  - Express (v4.21.1)  

- **Authentication and Security:**  
  - Bcryptjs (v2.4.3) – Password hashing  
  - JSON Web Tokens (JWT) (v9.0.2) – Token-based authentication  
  - Google Auth Library (v9.15.0) – OAuth authentication  
  - Helmet (v8.0.0) – HTTP security headers  

- **Database and ORM:**  
  - Mongoose (v8.8.4) – MongoDB ODM  

- **File Handling and Storage:**  
  - Multer (v1.4.5-lts.1) – File uploads  
  - Multer-S3 (v3.0.1) – AWS S3 integration  
  - AWS SDK (v2.1692.0) – AWS services  

- **API and Documentation:**  
  - Swagger UI Express (v5.0.1) – API documentation  

- **Testing:**  
  - Jest (v29.7.0)  
  - Supertest (v7.0.0)  

- **Utilities:**  
  - Axios (v1.7.7) – HTTP client  
  - Dotenv (v16.4.5) – Environment variables  
  - Cors (v2.8.5) – Cross-Origin Resource Sharing  

- **Development Tools:**  
  - Nodemon (v3.1.4) – Live server reloading  
  - Cross-env (v7.0.3) – Environment variable management 

#### More
- [Open Charge Map](https://openchargemap.org/site) (API)

### 🔧 Installation

#### Prerequisites

1. Node.js and npm installed.
2. MongoDB database set up.
3. AWS S3 Configuration.
4. Google OAuth Credentials.
5. Open Charge Map API Key.
6. MapTiler API Key.
7. Mapbox Credentials.

#### Steps

1. Clone the repository:
```
git clone https://github.com/Hetahar/plug_it.git <project-name>
cd project-name
```
2. Navigate in terminal to both server and client separately and install dependencies:
```
npm install
```
3. Set up environmental variables:
Create a new ``.env`` file in both the server and client folders. Include in the server ``.env``:
```
PORT=4000
MONGO_URI=<YOUR_MONGO_URI>
GOOGLE_CLIENT_ID=<YOUR_GOOGLE_CLIENT_ID>
JWT_SECRET=<YOUR_JWT_SECRET>
OPEN_CHARGE_MAP_API_KEY=<YOUR_OPEN_CHARGE_MAP_API_KEY>
AWS_ACCESS_KEY_ID=<YOUR_AWS_ACCESS_KEY_ID>
AWS_SECRET_ACCESS_KEY=<YOUR_AWS_SECRET_ACCESS_KEY>
AWS_REGION=<YOUR_AWS_REGION>
S3_BUCKET_NAME=<YOUR_S3_BUCKET_NAME>
```
And client ``.env``:
```
VITE_REACT_APP_MAPTILER_API_KEY=<YOUR_VITE_REACT_APP_MAPTILER_API_KEY>
VITE_REACT_APP_GOOGLE_CLIENT_ID=<YOUR_VITE_REACT_APP_GOOGLE_CLIENT_ID>
VITE_REACT_MAPBOX_USERNAME=<YOUR_VITE_REACT_MAPBOX_USERNAME>
VITE_REACT_MAPBOX_TOKEN=<YOUR_VITE_REACT_MAPBOX_TOKEN>
VITE_REACT_MAPBOX_STYLE_ID=<YOUR_VITE_REACT_MAPBOX_STYLE_ID>
```
**Notes**: Replace placeholder values ``(<YOUR_VALUE>)`` with your actual credentials.

4. Start the development server in both the client and server terminal:
```
npm run dev
```

### Usage

1. Navigate to the homepage.
2. Log in or sign up:
   - Locally
   - With a Google account.
3. Add a profile picture.
4. Use the map to find EV charging stations.
5. Save and review charging stations.
6. Contact support when needed.

### Team Contributions

This project was developed as a team using the Scrum framework. I would like to thank my team for their collaboration and dedication throughout this school project. Below, I have highlighted my specific contributions:
- Project planning.
- Maintaining the product backlog.
- Setting up [Trello](https://trello.com/), writing and prioritizing user stories.
- Developing models, controllers, routes, and middleware for the backend.
- Implementing frontend login and register components.
- Configuring admin rights with a ``useContext`` protected route.
- Handling the contact form integration between the frontend and backend.
- Designing landing pages for footer links and populating them with dummy AI data.
- Conducting API research and integrating the **Open Charge Map** API into the project.
- Testing endpoints and workflows using **Postman**.
- Integrating the **MongoDB** database.
- Performing server testing with **Jest** and **Supertest**.
- API documentation with [Swagger](https://swagger.io/) and styling it for usability and a cohesive look.

Thank you!