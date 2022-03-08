### Languages
![node] ![javascript] ![typescript]
 

### What I do and why (maybe because i'm bored...) ?
##### NodeJS & JavaScript algorythm optimizing
>> For example this function sends several requests, but we make it fast by sending these requests in parallel and asynchronously ! Now imagine that you need 18,000 requets or a lot of complex mathematical equations ?
>
> ```js 
> async function slow_function (total_pages = 200)
> {
>     // Just doing minus one for each page
>     for ( let page = total_pages; page--; ) await (await fetch(`https://jsonplaceholder.typicode.com/todos/${page}`)).json();
> }
> ```
>> ![image](https://user-images.githubusercontent.com/58662225/157330597-68fde1cf-3893-446e-9564-ec9eeea8a901.png)
> ```js
> let parallel_requests = [];
> let x, y;
>
> async function fast_function (total_pages = 200)
> {
>    const requests = async (page) => { await (await fetch(`https://jsonplaceholder.typicode.com/todos/${page}`)).json() };
>
>
>    // The loop recreates several times the variable x with a new data, 
>    // to have the less allocation in the memory we create first the value and then we modify it.
>
>    // Pushing all async requets in parallel to be executed in the promise function.
>    
>    for ( x = totalPages; x--; ) parallel_requests.push(requests(x));
>    await Promise.all(parallel_requests);
>     
> }
> ```
>> ![image](https://user-images.githubusercontent.com/58662225/157330804-8cadf92b-f5bb-4a5a-b21a-930dae0a797a.png)
>



[node]: https://badges.aleen42.com/src/node.svg
[javascript]: https://badges.aleen42.com/src/javascript.svg
[typescript]: https://badges.aleen42.com/src/typescript.svg
