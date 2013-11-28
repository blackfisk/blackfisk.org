---
layout: site
title: Pond spec

---

# POND SPECIFICATION 0.0.1

![](/img/pond.jpg)

## Pond client

### send

A pretty wrapper for gpg encrpyted message. The use of --armor and -R is recomended
to use anonymous recipient (use -R insted of -r to especify the email) and send
it to a given pond.

### fetch

Fetches the message from a given pond and tries to decrypt it with the user key.
Only shows the messages that are correctly decrypted.

## Pond server

Attempts to solve the possible metadata exchange in mail communications. Instead
of using mail protocols each message is sent to a pond server which will
broadcast the same GPG encrypted message to the other ponds.

The message can only be decrypted when it reaches their destination hoping for
an unknown amount of ponds.

### Message

A message is a plain text GPG encrypted text.
It's recommended to use anonymous recipient (use -R insted of -r to especify the
email)

### Read Messages

#### GET /

* Returns an json array of the stored GPG encrypted message. Each message shall live 2 days
  until is purged.

### Write Messages

#### POST /

* Adds the body of the request a message to be broadcasted to the other ponds
  and stored for reading. The server must handle message duplication applying
  a salt to the message for future checking.

### Friends

A friend is another pond server. Normally just an IP or a hostname. The
exact message will be POST'ed to that friend once for each friend.
