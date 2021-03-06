# chatctl

[![GoDoc](https://godoc.org/github.com/minimalchat/chatctl?status.svg)](https://godoc.org/github.com/minimalchat/chatctl)
[![Build Status](https://travis-ci.org/minimalchat/chatctl.svg?branch=master)](https://travis-ci.org/minimalchat/chatctl)
[![Coverage Status](https://coveralls.io/repos/github/minimalchat/chatctl/badge.svg?branch=master)](https://coveralls.io/github/minimalchat/chatctl?branch=master)

---

Minimal Chat is an open source live chat system providing live one on one messaging to a website visitor and an operator.

Minimal Chat is:
-   **minimal**: simple, lightweight, accessible
-   **extensible**: modular, pluggable, hookable, composable

---

Minimal Chat CLI tool for interacting with the [letschat-daemon](https://github.com/mihok/letschat-daemon).

### installation

Download the prebuilt binaries available in the [releases]() section or clone the repo and build using Go `>=1.6`.

```
> curl -L https://github.com/mihok/chatctl/releases/download/v1.0.0/chatctl.tar.gz
> tar -zxvf chatctl.tar.gz
> cd chatctl/bin
```

### Usage

Use the following syntax to run chatctl commands from your terminal window:

```
chatctl controls the Chat daemon

Find more information at https://github.com/letschat/chatctl

Usage:
	chatctl [flags] COMMAND
	chatctl COMMAND

Commands:
  get	Display one or many resources
  config	Modifies config files

Flags:
  -api-server address
    	The address of the API server (default "http://localhost:8000")
  -config file
    	Path to chat config file, specifying operator and how to authenticate to the API server (default "~/.chatrc")

```

See the current chats available

```
> chatctl get chats
CLIENT                  MESSAGES        STARTED         STATUS
bcMisjtP1PklnPEDZC3z    13 messages     2 hours ago     /catalog/product-1
```

Send a client a chat message

```
> chatctl send bcMisjtP1PklnPEDZC3z "Hey hour are you?"
```

Get or change your operator information

```
> chatctl config set first_name Foo
Update operator First Name to Foou

> chatctl config set avatar ~/pictures/avatar.png
Update operator avatar to ~/pictures/avatar.png

> chatctl config get name
Foo Bar
```
