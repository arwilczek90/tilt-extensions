# tilt-extensions
a collection of useful tilt extensions I made

# 1Password
## onepassword_secret_value

Allows you to fetch a single password from a vault using the url for the password

```
onepasswordUrl = 'something.1password.com
v1alpha1.extension_repo(name='arwilczek90', url='https://github.com/arwilczek90/tilt-extensions')
v1alpha1.extension(name='one-password', repo_name='arwilczek90', repo_path='one-password')
load('ext://one-password', 'onepassword_secret_value')

test_password = onepassword_secret_value('op://Some Vault/test-password/password', onepasswordUrl)
print(test_password)

```
output:
```
test-password
```

## onepassword_secret_values

Allows you to fetch multiple secret values from one item in a 1 password vault. (not the notes field or the password field if type is password)

```
onepasswordUrl = 'something.1password.com
v1alpha1.extension_repo(name='arwilczek90', url='https://github.com/arwilczek90/tilt-extensions')
v1alpha1.extension(name='one-password', repo_name='arwilczek90', repo_path='one-password')
load('ext://one-password', 'onepassword_secret_values')


test_values = ['password','username']
test_passwords = onepassword_secret_values('secret_uid', onepasswordUrl)
print(test_passwords)
```

output: 
```
{
    'password': 'test-password',
    'username': 'test-username',
}
```