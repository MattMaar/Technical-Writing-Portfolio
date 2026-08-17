# How to retrieve blog posts and user data using JSONPlaceholder

## Prerequisites:
* Browser
* No account or API key necessary

## How to access the site

Enter the site by using the link https://jsonplaceholder.typicode.com/ to arrive at the homepage. Adding specific endpoints to the link address gives you the ability to display blog posts by ID or by user, as well as giving information about the user associated with a certain userID.

## The following endpoints can be used:
Posts: by adding /posts/1 at the end of the link address, you will get the first blog post in the directory, with its associated userID, title and body:

```
{
"userId":  1,
"id": 1,
"title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
"body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
}
```

Changing the number in the endpoint retrieves the specific blog post associated with that number.
User: by adding /users/1  at the end of the link address, you will get the information about user associated with that ID, for example their name, username, mail address, as well as their contact details:

```
{
"id":  1,
"name": "Leanne Graham",
"username": "Bret",
"email": "Sincere@april.biz",
"address": {
"street": "Kulas Light",
"suite": "Apt. 556",
"city": "Gwenborough",
"zipcode": "92998-3874",
"geo": {
"lat": "-37.3159",
"lng": "81.1496"
}
},
"phone": "1-770-736-8031 x56442",
"website": "hildegard.org",
"company": {
"name": "Romaguera-Crona",
"catchPhrase": "Multi-layered client-server neural-net",
"bs": "harness real-time e-markets"
}
}
```

Using the endpoints without any numbers, e.g., /users/ or /posts lists all available users and blog posts in the directory.

## Combining endpoints

Endpoints can be combined to get more specific information, like a specific blog post by a specific user or all blog posts by multiple users. In order to do this, simply combine the endpoints, adding them after /posts and separating them from the main query with a ?, e.g., /posts?userId=1&userId=5 (gives you all posts by users 1 and 5) or /posts?userId=1&id=5 (gives you post 5 by user 1). Repeating the same parameter (e.g., userId twice) works as OR — matching either value. Combining different parameters (e.g., userId and id) works as AND — matching only entries that satisfy both.

## Common Errors
Putting /posts/userid/1 at the end of the link does not give any output (shows just a blank, black page). In order to get the specific posts for a specific userID, you will need to put /posts?userId=1&id=5 at the end of the link address (this example will give post 5 by user 1).
Separating the endpoints with an / when combining multiple endpoints instead of using a ?. This does not print any results.