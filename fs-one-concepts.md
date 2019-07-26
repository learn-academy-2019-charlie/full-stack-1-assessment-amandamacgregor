# Full Stack 1 Assessment

Try your best to answer each question on your own before looking up the answer online. Once you're done writing your first answer, you can google the question and write the best answer you find.


#### 1. What is Enzyme and what are some of the methods that it provides?
Testing in react. Red-Green-Refactor still applies as best practice.

Google:
Both Jest and Enzyme are specifically designed to test React applications, Jest can be used with any other Javascript app but Enzyme only works with React.
Jest can be used without Enzyme to render components and test with snapshots, Enzyme simply adds additional functionality.
Enzyme can be used without Jest, however Enzyme must be paired with another test runner if Jest is not used.

Enzyme is another library commonly used with either Jest or Mocha and Chai. With Enzyme we can create a mock DOM to test whether components are rendered correctly, and whether they behave correctly when acted upon. Enzyme’s mock rendering can either be done through shallow rendering or full DOM rendering. 
Shallow rendering is used when doing unit testing of a component. This allows for tests to focus only on that component and how it functions, without caring about other components it might interact with.
Full DOM rendering involves rendering your component and all children components. The allows for more in-depth testing to see how your components on the DOM interact with each other.


#### 2. What is the difference between dynamic and a static routes?

A static route is something that would have to manually navigated to; /aboutus.

We used dynamic routes with the Recipes project; one component for all recipes;
 < Link to={`/recipe/${recipe.id}`}>

Google:
In the Static routing, the table is set up and modified manually whereas in the Dynamic routing the table is built automatically with the help of the routing protocols. 
Dynamic routing is preferred over static routing because of the major issue in static routing where in case of link/node failure the system cannot recover. The dynamic routing overcomes from the static routing limitations.


#### 3. What is a JSON API?
A bunch of JSON objects that we can access/store to somehow.

Google:
JSON (JavaScript Object Notation) is most widely used data format for data interchange on the web. This data interchange can happen between two computers applications at different geographical locations or running within same hardware machine.

The good thing is that JSON is a human and machine readable format. So while applications/libraries can parse the JSON data – humans can also look at data and derive meaning from it.

A JSON document may contains text, curly braces, square brackets, colons, commas, double quotes, and maybe a few other characters.

Primarily, JSON is built on two structures:

A collection of name/value pairs. In various languages, this is realized as an object, record, struct, dictionary, hash table, keyed list, or associative array.
An ordered list of values. In most languages, this is realized as an array, vector, list, or sequence.


#### 4. What is a migration and why would you use one?
Migration is how we update the schema; we need to run it when certain things change in rails (column types, etc).  We don't want to edit the Schema file manually ever, so this is how we do that.  This provides us with a time-stamped file name for us to track versions, as well.

Google:
Requirements change all the time, and those changes often lead to database changes. Migrations give you a way to modify your database schema within your Rails application. So you use Ruby code instead of SQL. Using Rails migrations instead of SQL has several advantages.

Rails applications that can stay within the Active Record model are database-independent. If you have to write SQL to change your schema, you lose this independence. Migrations avoid this since you make the modifications in platform-independent Ruby.

Migrations keep your database schema changes with your application code. They’re written in Ruby and versioned with the rest of your app. Sure, you can (and should) version your SQL files, but do they belong in the same place? Not everyone feels the same way about that question. But it’s not an issue with Rails.

#### 5. Explain how to set up a route in React.
Import certain things (react-router-dom), place the paths in the render of the app.js within Routes>Switches, link to those addresses above Switches but still within Routes.

Lots of moving parts - listing the info from our syllabus (with some edits) below:

 import React, { Component } from "react";
 import ReactDOM from 'react-dom'
 import {
   BrowserRouter as Router,
   Route,
   Link
 } from "react-router-dom";
 import AboutUs from './pages/AboutUs'
 import Home from './pages/Home'
 import Tomato from './pages/Tomato'

 class App extends Component {
   render() {
     return(
       <Router>
         <div>
           <nav>
             <ul>
               <li>
                 <Link to="/">Home</Link>
               </li>
               <li>
                 <Link to="/about/">About</Link>
               </li>
               <li>
                 <Link to="/tomato/">Tomato</Link>
               </li>
             </ul>
           </nav>
       <Switch>
           <Route path="/" exact component={Home} />
           <Route path="/about/" component={AboutUs} />
           <Route path="/tomato/" component={Tomato} />
            <Route component={NotFound} />
        <Switch>
         </div>
       </Router>
     )
   }
 }

export default App


#### 6. When would you use a generate resource over a generate controller?

When you want to build a pretty much pre-built Rails template- building Model, Migration, controller, etc all at once, resource does it all.
Model creates one step down from that - migration and models.

Google:
The most commonly used generators are Controller, Model, Resource, and Scaffold. 
Controller is unique in that you don’t put table column names and types after the controller name, but you put the methods you want included in the new controller. The downside to creating controllers this way is that it creates unnecessary views because it creates a view for each method you enter. 
Model and Resource are very similar generators. 
Model creates a migration, model , and tests for the files that were generated. 
Resource command does everything Model command does, but also creates a controller, empty views folder, and resource routes. 


#### 7. Explain the difference between a controller spec and a request spec.
Google - I have no idea how ot answer this myself:
Controller specs - A controller spec is an RSpec wrapper for a Rails functional test. It allows you to simulate a single http request in each example, and then specify expected outcomes

Request specs - Request specs provide a thin wrapper around Rails' integration tests, and are designed to drive behavior through the full stack, including routing (provided by Rails) and without stubbing (that's up to you).

#### 8. Describe the React component lifecycle. What are some of the lifecycle methods?
Google - I didn't have a grasp on this besides componentDidMount being something in our code:
Mounting – Birth of your component
Update – Growth of your component
Unmount – Death of your component

Each component has several “lifecycle methods” that you can override to run code at particular times in the process.

Mounting
These methods are called in the following order when an instance of a component is being created and inserted into the DOM:

constructor()
static getDerivedStateFromProps()
render()
componentDidMount()

Updating
An update can be caused by changes to props or state. These methods are called in the following order when a component is being re-rendered:

static getDerivedStateFromProps()
shouldComponentUpdate()
render()
getSnapshotBeforeUpdate()
componentDidUpdate()

Unmounting
This method is called when a component is being removed from the DOM:

componentWillUnmount()

Additional Notes:
render()
The render() method is the most used lifecycle method. You will see it in all React classes. This is because render() is the only required method within a class component in React.
componentDidMount()
Now your component has been mounted and ready, that’s when the next React lifecycle method componentDidMount() comes in play.

componentDidMount() is called as soon as the component is mounted and ready. This is a good place to initiate API calls, if you need to load data from a remote endpoint.

Unlike the render() method, componentDidMount() allows the use of setState(). Calling the setState() here will update state and cause another rendering but it will happen before the browser updates the UI. This is to ensure that the user will not see any UI updates with the double rendering.


#### 9. At this point in the program, what technologies/languages do you find yourself gravitating to?
Really, I'm spending my free time trying to get a deeper understanding of all.  JavaScript is still my comfort zone, something I can rely on - but many brain teaser coding challenges are way easier in Ruby.  I like Active Record a lot!