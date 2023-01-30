# Async js and callback Hell

In this section we're going to cover a lot of advanced javascript concepts, some of which are: API data fetching, asynchronous code, callback functions, promises and asunc/await.

This section is going to teach you how you can first simulate or create that asynchronous source and then how we can properly deal with the data coming out of it.
Let's immediately dive in into a real example of asynchronous javascript, and that is: data from a range of diffrent Api's. API stands for Application Programing Interface and it id simpliy something that can access data from
Once we fetch the data, depanding on the size of the data we're fetching and our certain amount of time.
Opposed to the setTimeout, Where we always waited for 2 second, with real data fetching, we cannot be sure how long is it going to take.
Now we're going to simulate that data fetching.
Let's say that we're trying to fetch a user from the database.
This is the problem:

```javascript
const fetchUser = (username) => {
  setTimeout(() => {
    return { user: username };
  }, 2000);
};
const user = fetchUser("test");
console.log(user); // undefined
```

The reason because we got undefined is thet the data wasn't return from the function immediately. It waited 2 seconds. How can we fix this?

Here comes the concept of Callback Functions.
We can pass in a callback function that's going to run when the data is fetched.

```javascript
const fetchUser = (username, callback) => {
  setTimeout(() => {
    conslole.log("Now we have The user");
    callback({ user: username });
  }, 2000);
};

const user = fetchUser("test", (user) => {
  console.log(user);
});
```

Our fetch user function accepts a callback function as a parameter, and that's where we get the data.

This was just a simple example, but now, let's add more things onto it, bacause later on, we're going to exachange callback function for both promises and Async/Await.

To complicate it, we're gooing to imagine that we're working on a social media platform of sorts.
once the user profile is fetched, then we want to fetch his photos.
So let's create a function for that :

```javascript
const fetchUser = (username, callback) => {
  setTimeout(() => {
    console.log("Now we have the user");
    callback(username);
  }, 2000);
};

const fetchUserPhotos = (username, callback) => {
  setTimeout(() => {
    console.log("Now we have the photos");
  }, 2000);
};

const user = fetchUser("test", (username) => {
  console.log(username);

  fetchUserPhotos(username, (userPhotos) => {
    console.log(userPhotos);
  });
});
```

This is already getting messy.

Let's add just one more function, and you'll easily notice the problem.

```javascript
const fetchUser = (username, callback) => {
  setTimeout(() => {
    console.log("Now we have the user");

    callback(username);
  }, 2000);
};

const fetchUserPhotos = (username, callback) => {
  setTimeout(() => {
    console.log("Now we have photos");
    callback(["photo1", "photo2"]);
  }, 2000); // we dont know the time but let's say 2000
};

const fetchPhotoDetails = (photo, callback) => {
  setTimeout(() => {
    console.log("Now we have the photo details");
    callback("details...");
  }, 2000); // we dont know the time, but let's say 2000
};
const user = fetchUser("test", (username) => {
  console.log(username);

  fetchUserPhotos(username, (userPhotos) => {
    console.log(userPhotos);

    fetchPhotoDetails(userPhotos[0], (details) => {
      console.log(details);
    });
  });
});
```

As you can see, if we use callbacks, we get this wierd structure that just keeps moving to the right. if we added a few more callbacks, this is how it would look:

```javascript
//
```

This is called callback hell. It becomes unreadable.

In this code we can see on the left side, there is a traingle like structure to the indentation, this is infamously known as the CALLBACK HELL. So what callback include is:

**_In short, every function gets an argument which is another function that is called with a parameter that is responsible from the previous one._**

You will definitely get baffled with this sentence which describes CALLBACK HELL.

As in our case you can only imagine, to display several results how many callback function we will have to make. it's difficult to manage a lot of callback functions.

Even if you wrote them yourself, you're going to have hard time understanding them once you come back
to the code after some time!
This patern of coding(i.e callbacks) at a large scale is not maintainable and is confusing and also voilates the DRY principle and hence is a bad practice to follow.
So to resolve this issue, Javascript introduces the concept of promises. we will learn how promises work in next Article. Stay tuned!
