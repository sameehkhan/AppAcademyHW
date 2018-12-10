## `users`
column name     | data type | details
----------------|-----------|-----------------------
`id`              | integer   | not null, primary key
`username`        | string    | not null, indexed, unique
`email`           | string    | not null, unique
`password_digest` | string    | not null
`session_token`   | string    | not null, indexed, unique
`created_at`      | string    | not null
`updated_at`      | string    | not null

---
+ index on: `username, unique: true`
+ index on: `session_token, unique: true`


## `posts`
column name     | data type | details
----------------|-----------|-----------------------
`id`              | integer   | not null, primary key
`user_id`         | integer    | not null, indexed, foreign key
`caption`         | text      | 
`created_at`      | string    | not null
`updated_at`      | string    | not null

---

+ index on `user_id`
+ `user_id` REFERENCES `users`


## `likes`
column name     | data type | details
----------------|-----------|-----------------------
`id`              | integer   | not null, primary key
`user_id`         | integer   | not null, indexed, foreign key
`post_id`         | integer   | not null, indexed, foreign key
`created_at`      | string    | not null
`updated_at`      | string    | not null

---
+ index on `user_id`
+ index on `post_id`
+ `user_id` REFERENCES `users`
+ `post_id` REFERENCES `posts`

## `comments`
column name     | data type | details
----------------|-----------|-----------------------
`id`              | integer   | not null, primary key
`user_id`         | integer   | not null, indexed, foreign key
`post_id`         | integer   | not null, indexed, foreign key
`comment`         | text      | not null
`created_at`      | string    | not null
`updated_at`      | string    | not null

---
+ index on `user_id`
+ index on `post_id`
+ `user_id` REFERENCES `users`
+ `post_id` REFERENCES `posts`

## `following`
column name     | data type | details
----------------|-----------|-----------------------
`id`              | integer   | not null, primary key
`user_id`         | integer   | not null, indexed, foreign key
`following_id`    | integer   | not null, indexed, foreign key
`follows`         | boolean   | not null
`created_at`      | string    | not null
`updated_at`      | string    | not null

+ index on `user_id`
+ index on `following_id`
+ `user_id` REFERENCES `users`
+ `following_id` REFERENCES `users`
