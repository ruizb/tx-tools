# tx-tools v0.2.0

A command-line script to perform some actions related to the Transifex platform.

## Resource files support

Currently, only **JSON (key, value)** resources are supported.

## Requirements

To run this script, you need to have **Node JS** installed on your machine.
In addition, the script needs your Transifex credentials. To provide them, make sure to export these 2 environment variables in your `~/.bash_profile` file:

```
export TX_USER=email
export TX_PASS=password
```

## Install

Put the `tx` script in `~/bin` folder. Make sure this folder is in your PATH variable. The script has 2 dependencies: [Q](https://github.com/kriskowal/q) and [restler](https://github.com/danwrong/restler).

One-shot command:
```
mkdir -p ~/bin &&
curl -o ~/bin/tx https://raw.githubusercontent.com/ruizb/tx-tools/master/tx &&
chmod +x ~/bin/tx &&
cd ~/bin/ &&
npm install q restler minimist &&
cd -
```

## Usage

Use the following command to add new words to a specific resource of a Transifex project from where you are a **maintainer**:

```
tx add project-slug resource-slug word1 word2 ... wordN
```

Use this command to remove words from a resource (again, you need to be a **maintainer** to edit the resource):

```
tx rm project-slug resource-slug word1 word2 ... wordN
```

Use the next command to set the comment of a word from a resource:

```
tx comment project-slug resource-slug word1 'This is the command for word1'
```

## Examples

```
tx add my-project homepage 'Welcome to my website!' 'Click here' Homepage
```

```
tx rm my-project contact required 'Email address'
```

```
tx comment my-project add-user-form 'Error, fields 1 and 3 are required' 'This error occurs when the user does not set a phone number or an email address'
```

## Changelog

**v0.2.0** (*2015-03-14*)

- Add `comment` action

**v0.1.0** (*2015-02-21*)

- Initial state with `add` and `rm` actions
