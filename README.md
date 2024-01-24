## Overview

A basic mkdocs server running the material theme and version control. A great place to get started with a mkdocs server

## Setup

### Linux Machine/VM
- Prerequisite
  `gcc, g++, python3 and python-pip`

- Create python virtualenv and activate virtualenv
  ```bash
  python3 -m venv venv
  source venv/bin/activate
  ```

-  Install dependencies
   ```bash
   pip install --upgrade pip
   pip install -r requirments.txt
   ```

- Ensure correct default branch being used by mike
  ```bash
  mike set-default latest
  ```

## Viewing Docs

If using python virtualenv, then source the environemnt.
  ```bash
  source venv/bin/activate
  ```

To view your WIP documentation locally simply use `mkdocs serve` which will update as docs are changed. 

To view the versioned documentation (managed by `mike`) run `mike serve` (note: this will not auto-update as docs are changed and requires redeploying).

## Writing Docs

It's worth familiarising with the [available markdown formatting](https://www.mkdocs.org/user-guide/writing-your-docs/#writing-with-markdown) supported by mkdocs. There are some specific plugins enabled/installed in `mkdocs.yml`, see that file for more info. 

## Deploying Docs

Using `mike` we can deploy documentation with version tagging

- Deploy WIP data to `staging` 
```
mike deploy --push --no-redirect --update-aliases 20XX.Y staging
```

- Deploy a new stable version of documentation
```
mike deploy --push --no-redirect --update-aliases 20XX.Y latest
```

- Removing staging tag upon release to latest 
```
# Set a different branch to `staging` tag, see previous deploy WIP step
```

- Resetting/removing a version 
```
mike delete --push 20XX.Y
```
