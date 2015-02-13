# tx-tools
This is a command-line script to perform some actions related to Transifex.

## Requirements
To run this script, you need to have **NodeJS** installed on your machine.
In addition, the script needs your Transifex credentials. To provide them, make sure to export these 2 environment variables in your `~/.bash_profile` file:
```
export TX_USER=email
export TX_PASS=password
```

## Installation
Put the `tx` script in `~/bin` folder. Make sure this folder is in your PATH variable. The script has 2 dependencies: [Q](https://github.com/kriskowal/q) and [restler](https://github.com/danwrong/restler).

One-shot command:
```
curl -o ~/bin/tx https://raw.githubusercontent.com/ruizb/tx-tools/master/tx &&
chmod +x ~/bin/tx &&
cd ~/bin/ &&
npm install q restler &&
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

## Examples
```
tx add my-project homepage 'Welcome to my website!' 'Click here' Homepage
```

```
tx rm my-project contact required 'Email address'
```
