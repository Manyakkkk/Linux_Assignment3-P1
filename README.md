# LINUX ASSIGNMENT 3

## PART - 1

## Task 1 -> Create a system user ##

1. Create a user with the specified home directory and shell for a non-login user. Use the following command to the same:

```
sudo useradd -r -d /var/lib/webgen -s /usr/sbin/nologin webgen
```

Here; we useradd `useradd` to create a new user account on system.

- `-r`: specifies that this is a **system user**.
- `-d`: specifies the user's home directory.
- `-s`: sets the user login shell.

2. Create the necessary directories as specifd for which use:

```
sudo mkdir -p /var/lib/webgen/bin /var/lib/webgen/HTML
```

Here, `-p` will ensure that the parent directories are created if they dont really exists.For example, if `var/lib/webgen` doesn't exists, it will be created along with the subdirectories ( `bin` and `HTML` ).

3. Create the specified files.

```
sudo touch /var/lib/webgen/bin/generate_index /var/lib/webgen/HTML/index.html
```

4. Change the ownership of the above two files created to webgen user within the webgen group.

```
sudo chown -R webgen:webgen /var/lib/webgen
```

Here, 

- `-R`: recursively applies the ownership change to all the files and directories within the /var/lib/webgen .
- `webgen:webgen`: sets both, owner and group to the webgen user. This is to ensure that the user has full control over it's home directory and files.

---

## Task 2 -> Create the .service and .timer files. ##

