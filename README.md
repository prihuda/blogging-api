FORMAT: 1A
HOST: https://private-310d96-bloggingapi1.apiary-mock.com

# Blogging API

Simple API allowing consumers to view blogging authors, their posts and comments.

## Authors [/author]

### List All Authors [GET]

List all authors.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "username": "Mia Huljanah",
                "password": "************",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "mia_huljanah@email.com",
                "profile": "Profile"
            },
            {
                "id": "2",
                "username": "Rashif Ilmi Nurzaman",
                "password": "************",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "rashif_ilmi@email.com",
                "profile": "Profile"
            },
            {
                "id": "3",
                "username": "Hardo Fernando Silalahi",
                "password": "************",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "hardo_fernando@email.com",
                "profile": "Profile"
            }
        ]

### Create New Author [POST]

Create new author.

+ Request (application/json)

        {
            "username": "Rangga Dwipangga",
            "password": "************",
            "email": "rapangga@email.com",
            "profile": "Profile"
        }

+ Response 201 (application/json)

    + Headers

            Location: /author/4

    + Body

            {
                "id": "4",
                "username": "Rangga Dwipangga",
                "password": "************",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "rapangga@email.com",
                "profile": "Profile"
            }
            
## Authors Resource [/author/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Author with ID [GET]

List specific author using its ID.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "username": "Mia Huljanah",
                "password": "************",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "mia_huljanah@email.com",
                "profile": "Profile"
            }
        ]

### Edit an Author [PATCH]

Edit specific author using its ID.

+ Request (application/json)

        {
            "email": "mia_huljah@email.com"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "username": "Mia Huljanah",
                "password": "************",
                "salt": "AkasnASNF121anSKNfaknfa",
                "email": "mia_huljah@email.com",
                "profile": "Profile"
            }
        ]
        
### Delete an Author [DELETE]

Delete an author.

+ Response 204


## Posts [/post]

### List All Posts [GET]

List all posts.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "title": "Title 1",
                "content": "content 1",
                "tags": "tags1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "update_time": "2020-03-11T07:28:52.754Z",
                "author_id": "1"
            },
            {
                "id": "2",
                "title": "Title 2",
                "content": "content 2",
                "tags": "tags2",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "update_time": "2020-03-11T07:28:52.754Z",
                "author_id": "2"
            },
            {
                "id": "3",
                "title": "Title 3",
                "content": "content 3",
                "tags": "tags3",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "update_time": "2020-03-11T07:28:52.754Z",
                "author_id": "3"
            }
        ]

### Create New Post [POST]

Create new post.

+ Request (application/json)

        {
            "title": "Title 4",
            "content": "content 4",
            "tags": "tags4",
            "author_id": "1"
        }

+ Response 201 (application/json)

    + Headers

            Location: /post/4

    + Body

            {
                "id": "4",
                "title": "Title 4",
                "content": "content 4",
                "tags": "tags4",
                "status": "Created",
                "create_time": "2020-03-11T07:21:52.754Z",
                "update_time": "",
                "author_id": "1"
            }
            
## Posts Resource [/post/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Post with ID [GET]

List specific post using its ID.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "title": "Title 1",
                "content": "content 1",
                "tags": "tags1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "update_time": "2020-03-11T07:28:52.754Z",
                "author_id": "1"
            }
        ]

### Edit a Post [PATCH]

Edit specific post using its ID.

+ Request (application/json)

        {
            "content": "content 1a"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "title": "Title 1",
                "content": "content 1a",
                "tags": "tags1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "update_time": "2020-03-11T07:28:52.754Z",
                "author_id": "1"
            }
        ]
        
### Delete a Post [DELETE]

Delete a post.

+ Response 204


## Comments [/comment]

### List All Comments [GET]

List all comments.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "content": "content 1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "1",
                "email": "mia_huljah@email.com",
                "url": "miahuljah.com",
                "post_id": "2"
            },
            {
                "id": "2",
                "content": "content 2",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "2",
                "email": "rashif_ilmi@email.com",
                "url": "rashif_ilmi.com",
                "post_id": "3"
            },
            {
                "id": "3",
                "content": "content 3",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "3",
                "email": "hardo_fernando@email.com",
                "url": "hardo_fernando.com",
                "post_id": "1"
            }
        ]

### Create New Comment [POST]

Create new comment.

+ Request (application/json)

        {
            "content": "content 3",
            "author_id": "2",
            "email": "rashif_ilmi@email.com",
            "url": "rashif_ilmi.com",
            "post_id": "1"
        }

+ Response 201 (application/json)

    + Headers

            Location: /comment/4

    + Body

            {
                "id": "4",
                "content": "content 4",
                "status": "Created",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "2",
                "email": "rashif_ilmi@email.com",
                "url": "rashif_ilmi.com",
                "post_id": "1"
            }
            
## Posts Resource [/comment/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Post with ID [GET]

List specific comment using its ID.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "content": "content 1",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "1",
                "email": "mia_huljah@email.com",
                "url": "miahuljah.com",
                "post_id": "2"
            }
        ]

### Edit a Post [PATCH]

Edit specific post using its ID.

+ Request (application/json)

        {
            "content": "content 1a"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "content": "content 1a",
                "status": "Updated",
                "create_time": "2020-03-11T07:21:52.754Z",
                "author_id": "1",
                "email": "mia_huljah@email.com",
                "url": "miahuljah.com",
                "post_id": "2"
            }
        ]
        
### Delete a Post [DELETE]

Delete a post.

+ Response 204
