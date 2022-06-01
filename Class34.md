# API Deployment

## Managing Django Settings: Issuess

- Different environments. Usually, you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc). You need an approach that allows you to keep all these Django setting configurations.

- Sensitive data. You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.


## Setting Configuration: Different Approaches

- settings_local.py

This is the oldest method. I used it when I was configuring a Django project on a production server for the first time. I saw a lot of people use it back in the day, and I still see it now.

The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS. Here’s an example:

The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS. Here’s an example:

settings.py file:

```
ALLOWED_HOSTS = ['example.com']
DEBUG = False
```

settings_local.py file:

```
ALLOWED_HOSTS = ['localhost']
DEBUG = True
```

### Separate settings file for each environment

This is an extension of the previous approach. It allows you to keep all configurations in VCS and to share default settings between developers.

In this case, you make a settings package with the following file structure:

```
settings/
   ├── __init__.py
   ├── base.py
   ├── ci.py
   ├── local.py
   ├── staging.py
   ├── production.py
   └── qa.py
```

### django-environ

- Based on the above, we see that environment variables are the perfect place to store settings.

Now it’s time to talk about the toolkit.

Writing code using os.environ could be tricky sometimes and require additional effort to handle errors. It’s better to use django-environ instead.

Technically it’s a merge of:

- envparse
- honcho
- dj-database-url
- dj-search-url
- dj-config-url
- django-cache-url

# What Is SSH: Understanding Encryption, Ports and Connection


- SSH, or Secure Shell Protocol, is a remote administration protocol that allows users to access, control, and modify their remote servers over the internet.

- SSH service was created as a secure replacement for the unencrypted Telnet and uses cryptographic techniques to ensure that all communication to and from the remote server happens in an encrypted manner. It provides a mechanism for authenticating a remote user, transferring inputs from the client to the host, and relaying the output back to the client.

- The example below shows a typical SSH prompt. Any Linux or macOS user can SSH into their remote server directly from the terminal window. Windows users can take advantage of SSH clients like Putty.  You can execute shell commands in the same manner as you would if you were physically operating the remote computer.

![ssh](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/shell-snapshot.jpg)


