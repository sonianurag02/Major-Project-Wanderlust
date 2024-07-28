Model: Listing

- title
- description
- image 
- price 
- location 
- country


Form Validations:

When we enter data in the form, the browser and/or the web server will check to see that the 
data is in the correct format and within thhe constraints set by the application.

- Client side Validation
- server side Validation


Validations for schema:

joi.dev tool


Handling Deletion:
using Mongoose Middleware

We can use 2 middlewares:
- Pre = run before the query is executed
- Post = run after the query is executed


Deleting Reviews:

Mongo $pull operator

$pull = This operator removes from an existing array all instances of a value or values 
that match a specified condition.


Miscellaneous:

- Express Router
    Express router are a way to organize your Express application such that our 
    primary app.js file does not become bloated.

    const router = express.Router() // creates new router object 

- Cookies (Web cookies) (Express Package)
    HTTP cookies are small blocks of data created by a web server while a user is 
    browsing a website and placed on the user's computer or other device by the user's 
    web browser.


What is State?

Stateful Protocol:

- Stateful Protocol require serve to save the status and session information.
eg - ftp

Stateless Protocol:

- Stateless Protocol does not require the server to retain the server information 

eg - http


Express Sessions: (Express Package)
An attempt to make our session stateful.


connect-flash: (express package)
- The flash is a special area of the session used for storing messages. Messages are
    written to the flash and cleared after being displayed to the user.


Let's understand:

Authentication  Authentication is a process of verifying who someone is (signup/login)

Authorization = Authorization is the process of verifying what specific applications,
    files, and data a user has access to.


Storing Passwords:

Hashing

We NEVER store the passwords as it is. We store their hashed form.

password            Hashing             how it is stored
"Hello world"       Function            "936ah3j54g2h34jv5234hjv62h5432v6hj23v62h3jv6j"

- For every input, there is a fixed output.
- There are one-way functions, we can't get input from output.
- For a different input, there is a different output but of same length.
- Small changes in input should bring large changes in output.


Salting: 

Password salting is a technique to protect passwords stored in databases by adding
string of 32 or more characters and then hashing them.


Passport:

npm i passport
npm i passport-local
npm i passport-local-mongoose 

Configuration Strategy:

passport.initialize()
A Middleware that initializes passport.

passport.session()
A web application needs the ability to identify users as they browse from page to page.
This series of requests and responses, each associated with the same user, is known as session.

passport.use(new LocalStrategy(User,authenticate()))


MVC: Model, View, Controller Framework (Mention in resume)


User Model:
user: username, password, email 


Cloud Setup:
Cloudinary and .env file
- npm i cloudinary
- npm i multer-storage-cloudinary


Geocoding:

Geocoding is the process of converting addresses (like a street address) into geographical
coordinates (like latitude and longitute), which you can use to place markers on a map, 
or postion the map.


Mongo Atlas:

Cloud Database Service
- Database. Deploy a multi-cloud database;

Username: thedungeontraveller
Pass: Dungeon@1970
mongodb+srv://thedungeontraveller:<password>@cluster0.y29aleo.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0
mongodb+srv://thedungeontraveller:<Dungeon@1970>@cluster0.y29aleo.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0
mongodb+srv://thedungeontraveller:Dungeon@1970@cluster0.y29aleo.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0


Deployment:

- render
- netlify
- cyclic






// Trash

// const { listingSchema, reviewSchema } = require("./schema.js");
// const wrapAsync = require("./utils/wrapAsync.js");
// const Listing = require("./models/listing.js");

// app.get("/testListing", async (req, res) => {
//   let sampleListing = new Listing({
//     title: "My New Villa",
//     description: "By the beach",
//     price: 1200,
//     location: "Calangute, Goa",
//     country: "India",
//   });

//   await sampleListing.save();
//   console.log("Sample was saved");
//   res.send("successfull testing");
// });

From listing schema
type: String,
    default:
      "https://images.unsplash.com/photo-1625505826533-5c80aca7d157?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTJ8fGdvYXxlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=800&q=60",
    set: (v) =>
      v === ""
        ? "https://images.unsplash.com/photo-1625505826533-5c80aca7d157?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTJ8fGdvYXxlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=800&q=60"
        : v,

"mysupersecretcode"