# Bruvscord

#### https://bruvscord.herokuapp.com

## Get Messages

Get all of the messages that have been sent over Bruvscord. Users can choose to have messages sent in ascending or descending order, and can specify the number of messages they would like.

**URL** : `/messages`

**Parameters**: order, num

**Method** : `GET`

**Examples**

```bash
curl https://bruvscord.herokuapp.com/messages
curl https://bruvscord.herokuapp.com/messages?order=asc
curl https://bruvscord.herokuapp.com/messages?num=1
curl https://bruvscord.herokuapp.com/messages?order=desc&num=2
```

### Specify Order

To request the messages in a specific order (ascending or descending), use the `order` parameter.

| Value      | Impact |
| ----------- | ----------- |
| asc      | returns messages in ascending order       |
| desc   | returns messages in descending order        |

**Examples**

```bash
curl https://bruvscord.herokuapp.com/messages?order=asc
curl https://bruvscord.herokuapp.com/messages?order=desc
```

### Specify Number of Messages

To request a certain number of messages only, use the `num` parameter.

| Value      | Impact |
| ----------- | ----------- |
| num      | the number of messages you would like to be returned       |

**Examples**

```bash
curl https://bruvscord.herokuapp.com/messages?num=1 # first message sent
curl https://bruvscord.herokuapp.com/messages?num=10&order=desc # last 10 messages sent
```
  
<br></br>


## Send Message

Send a message by specifying message content and the sender.

**URL** : `/messages/add/:sender:`

**Parameters**: sender, message

**Method** : `POST`

**Examples**

```bash
### Send a message "Hi there." to the Bruvscord server from cooper ###
curl -X POST https://bruvscord.herokuapp.com/messages/add/cooper -d "message=Hi there."

### Send a message "bruv" to the Bruvscord server from gr3g ###
curl -X POST https://bruvscord.herokuapp.com/messages/add/gr3g -d "message=bruv"
```

<br><br/>

## Get Users

Get all users registered with Bruvscord.

**URL** : `/users`

**Method** : `GET`

**Examples**

```bash
curl https://bruvscord.herokuapp.com/users
```

<br></br>

## Get Specific User

Get a specific user by searching with their name.

**URL** : `/users/:user:`

**Parameters**: user

**Method** : `GET`

**Examples**

```bash
### Get user details for cooper ###
curl https://bruvscord.herokuapp.com/users/cooper

### Get user details for joe ###
curl https://bruvscord.herokuapp.com/users/joe
```

<br></br>

## Add User

Add a user to Bruvscord with a name and a color.

**URL** : `/users/add/:user:`

**Parameters** : user, color

**Method** : `POST`

**Examples**

```bash
### Add user 'johnny' with color 'blue' ###
curl -X POST https://bruvscord.herokuapp.com/users/add/johnny -d "color=blue"

### Add user 'wayne' with color '#345abe' ###
curl -X POST https://bruvscord.herokuapp.com/users/add/wayne -d "color=#345abe"
```
