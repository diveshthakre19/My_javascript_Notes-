# promise

In the last article, we've witinessed the callback hell. Now promise comes in to the rescue.

What are promises? They are objects that either return the sucessfully fetch data, or the error.
Let's try to create one:

```javascript
// Creating of the promise
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    console.log("Got the User");

    resolve({ user: "Adiran" });
  }, 2000);
});
// getting the data from the promise
promise.then((user) => {
  console.log(user);
});
```

As you can see, This is much much easier to read.

Keep in mind that during the callback examole, we didn't even test for the errors, when making requests, sometimes, the data may not come back. The reason can be your internet connection, or maybe you're just fetching the data from the wrong database.
In any case, the fact is, tahat sometimes, you're not going to recive the data you were looking for. And we need to handel those cases. with promises, its's east
Well just replace the resolve with reject, and pass our error message.

```javascript
// creating a promise
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    console.log("Got the user");
    // resolve({user: 'Divesh'});
    reject("Error");
  }, 2000);
});

//getting the data from the promise
// .then gives us the result of the resolve
// and .catch gives us the result of the reject

promise
  .then((user) => {
    console.log(user);
  })
  .catch((error) => {
    console.log(error);
  });
```

In the last example, with callback function, we had a lot of functions.

How woud we do that with promises?

```javascript
console.log(1);

const fetchUser = (username) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Now we have the user");
      resolve(username);
    }, 2000);
  });
};

const fetchUserPhotos = (username) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Now we have the photos");
      resolve(["photo1", "photo2"]);
    }, 2000);
  });
};

const fetchPhotoDetails = (photo) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("Now we have the photo details");
      resolve("details...");
    }, 2000);
  });
};

//not this

const user = fetchUser("test", (username) => {
  console.log(username);

  fetchUserPhotos(username, (userPhotos) => {
    console.log(userPhotos);

    fetchPhotoDetails(userPhotos[0], (details) => {
      console.log(details);
    });
  });
});

// and finally, we woud call it like this:

fetchUser("Divesh")
  .then((user) => fetchUserPhotos(user))
  .then((photos) => fetchPhotoDetails(photo[0]))
  .then((detail) => console.log(detail));

console.log(2);
```

This is the same thing that we have above. But notice how much easier this is to both read and write. We never again have to use callbacks.

Promises are enabling us to write asynchronous code in a much easier way. Recently, there has been an addition to promise. it's called async await, we are going to check it out next.
