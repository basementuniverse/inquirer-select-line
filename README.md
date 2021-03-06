# inquirer-select-line

select-line prompt for [inquirer](https://github.com/SBoudrias/Inquirer.js)

Forked from https://github.com/adam-golab/inquirer-select-line

## Changes in this fork

* Now accepts a `default` option (number or Function) so we can set the initially-selected line

## Installation

```
npm install --save inquirer-select-line
```

## Usage

### Register the prompt

```javascript
inquirer.registerPrompt('selectLine', require('inquirer-select-line'));

inquirer.prompt({
  type: 'selectLine',
  message: message,
  name: name,
  choices: choices,
  placeholder: placeholder,
})
```

Change `selectLine` to whatever you might prefer.

### Options
-**message** : (*String*|*Function*) The question to print. If defined as a function, the first parameter will be the current inquirer session answers.

-**name** : (*String*) The name to use when storing the answer in the answers hash. If the name contains periods, it will define a path in the answers hash.

-**choices**: (*Array*|*Function*) Choices array or a function returning a choices array. If defined as a function, the first parameter will be the current inquirer session answers. Array values have to be simple strings. The choices array can also contain [a Separator](https://github.com/SBoudrias/Inquirer.js/#separator).

-**placeholder** (*String*|*Function*) The name to display as a placeholder for chosen line. If defined as a function, the first parameter will be index of currently chosen answer. (optional) default: `INSERT HERE`.

-**default** (*number*|*Function*) The initially selected index in the choices array. If this is a function, the current answers hash will be passed in.

#### Example

```javascript
inquirer.registerPrompt('selectLine', require('inquirer-selectLine'));
inquirer.prompt([{
  type: 'selectLine',
  message: 'Where add line?',
  name: 'line',
  choices: ['first', 'second', 'third', 'fourth'],
}]).then(function(answers) {
    console.log('Chosen line: ' answers.line);
    /*
    OUTPUT :
    Chosen line: 2
    */
});
```

## License
MIT
