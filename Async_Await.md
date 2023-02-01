## What is Async-Await?

Async await is simply an addition to promises, it is an easier and cleaner way to work with promises.
The main advantage of asynchronous functions is that they look and behave more like synchronous functions we're all used to. Because of that, it's easier to work with them.

Let's take a look at a simple example

```javascript
const fetchNumber = async () => {
  return 25;
};

asyncOne().then((result) => {
  console.log(result); //Shoud log 25
});
```

Running teh above code logs 25 to the console. This means that the promise was fullfilled then returned. if it had not the .then( ) method could
not have worked.
Now we come to the special await keyword. The await waits for the promise to return a result.
The await keyword can only be used inside of an async function.

Further more usage of the await expression dose not stop the functions from running. Rather it only make the function block with the async keyword Wait until a promise is fulfilled.

To go back to our initial example wi
th callbacks and promises, let's do it with async/await. Async await still uses promises, but with a nicer syntax.

```javascript
const displayData = async () => {
  const user = await fetchUser("Divesh");
  const photos = await fetchUserPhotos(user);
  const datail = await fetchPhotoDetails(photos[0]);

  console.log(details);
};
```

Look how clean and simple it looks. Amazing!
