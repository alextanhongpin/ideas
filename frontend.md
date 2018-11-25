## Publish/subscribe on active components

Say we are designing a news feed with comment system like Facebook, how do we limit the interaction to those components that are in view? If every feed item has websocket event attached to it (e.g. to check if a user is typing), we will see too much noise on the screen (concurrent updates on multiple components). It is a better design to limit the interaction to the components that the user are selecting only (e.g. hovering the static video link will play the video, hovering the animation gif will play the gif). We can use a publish-subscribe model to implement this - only subscribe to those components in the view and selected by user. 


## Data-Flow
Updating data on the frontend

- E.g. users
- Create a new User object
- Add to collection.
- Detect create, update, delete
- View and model are separated through controller.

```
state = { users: [], $users: [] }

// Models
addUserModel(users, new User())
removeUserModel(users, user)
updateUserModel(users, user)

// View
addUserView($users, new UserView(user))
removeUserView($users, user)
updateUserView($users, user)

// Controller: a facade
addUser() 
- addUserModel()
- addUserView()
```
