```js
{
entities: {
  users: {
    1: {
      id: 1,
      username: 'sameehkhan',
      email: sameehkhan1@gmail.com,
      }
  },
  posts: {
    1: {
      id: 1,
      caption: 'Brand new whip got no keys!',
      userId: 3,
    }
  },
  likes: {
  	1: {
    	id: 1,
      userId: 3,
      postId: 4
    }
  },
  comments: {
  	1: {
    	id: 1,
      userId: 3,
      postId: 4,
      comment: 'Jag Portfolio'
    }
  },
  following: {
  	1: {
    	id: 1,
      userId: 3,
      following: 4,
      follows: 'false'
    }
  }
}
ui: {
    loading: true/false
},
errors: {
    signUpForm:["Username is taken"],
    signUpForm:["Email is already registered"],
    login: ["Incorrect username/password combination"],
    postForm: ["Post cannot be blank"],
    commentForm: ["Comment cannot be blank"]
},
session: { currentUserId: 25 }
}
```