
In this project I have created a viewer for SVG files, which are scaleable image files that don't lose their quality no matter how far you zoom in or out. We'll save these files in a decentralized database using GUN, and pull the data back from a keyword alone. The structure is extremely simple to implement, and both teaches you how to create a project on the React framework, and how to implement GUN databases for easy data storage and retrieval.

The actual SVG is converted into a URI component via JavaScript's built-in encodeURIComponent() function. 
The default SVG is actually the Ethereum logo, and if you want to quickly run your project to verify that, you may. When the app starts up, this will be the first thing displayed. The SVG object is actually stored with a title and the actual object, so we modify the component in the return statement to include that SVG data pass-through.

Also, we wanted to create a form that handles some inputs of a new SVG, and will allow a user to put in a new SVG and toss it up to the Gun database.

We created a GUN object. This is our database, and it allows us to send and receive data on a whim.
Objects are stored based on their title, which is the key. As such, we could use gun.get(key) to get an object, as long as we knew its name.
We used gun.get().put() to update the object. If it currently doesn't exist in the database, GUN will create a new entry for us and populate it with the data passed in.
We used gun.get().on() to handle the data by retrieving the data and the key, and piping that into an anonymous function. In doing so, we could simply set our SVG states using this.
