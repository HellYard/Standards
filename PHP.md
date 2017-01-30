# CFH PHP Code Quality Standards
## Definitions
Software - The software that these standards are packaged with.

## Why?
The CFH PHP Code Quality Standards were created to establish code format rules for contributors to follow when making changes and/or additions to software created by creatorfromhell. These rules are in place to prevent the individual contributors from using their own development style and ultimately making the Software source a mess of different styles thrown together.

## Function & Variables names:
* Must have an underscore(_) between each word
  * Correct Example(s): $example_variable, $another_variable, example_function(), another_example()
  * Incorrect Example(s): $exampleVariable,  $examplevariable, ExampleFunction(), exampleFunction()
* Must be all lower-case characters unless using an abbreviation
  * Correct Example(s): $example_variable, $another_variable, correct_example(), correct_PHP()
  * Incorrect Example(s): $Example_Variable,  $EXAMPLE_VARIABLE, incorrect_Example()

## Arrays:
* When initializing/insert values of arrays that use a Key => Value pair, and you're initialize it with/inserting multiple values you must put each Key => Value pair on a separate line. If you're only inserting/initializing one value then the Key => Value pair may be placed on the same line you create the array or set the value.
  * Correct Example(s):
  ```php
  $example_array = array(
      'Key' => 'Value',
      'SecondKey' => 'SecondValue',
  );
  $example_array['example'] = array(
      'NewKey' => 'Example',
      'KeyTest' => 'Test',
  );
  $example_array = array('Key' => 'Value');
  $example_array['NewKey'] = array('Test' => 'Value');
  ```

## Files:
* Files must not contain any redundant closing tags

## Classes & Class Files:
* Class files must contain just one class per file

## Class & Class File names:
* Class files must use the same name as the class they contain
  * Correct Example(s): ExampleClass in ExampleClass.php, Group in Group.php, AnotherExampleClass in AnotherExampleClass.php
  * Incorrect Example(s): exampleClass in Example.php, group in Group.php, AnotherexampleClass in anotherexampleclass.php
* Class names must be in upper camel case.
  * Correct Example(s): ExampleClass, Group, AnotherExampleClass
  * Incorrect Example(s): exampleClass, group, AnotherexampleClass

## Methods/Operators to use
* When trying to obtain a value from a language file you should ALWAYS use the ```get_value``` method in the LanguageManager class.
  * Correct Example:
* Only use array_push when adding more than one value to an array.
  * Correct Example(s):
  ```php
  $example = array('test');
  array_push($example, 'test1', 'test2', 'test3');
  ```
  * Incorrect Example(s):
  ```php
  $example = array('test');
  array_push($example, 'test1');
  ```
* Do NOT use deprecated methods
* Always use instanceof instead of is_a()
  * Correct Example(s):
  ```php
  if($variable instanceof Class) {
      //Do something
  }
  if(!($variable instanceof Class)) {
      //Do something
  }
  ```
  * Incorrect Example(s):
  ```php
  if(is_a($variable, 'Class')) {
      //Do something
  }
  if(!is_a($variable, 'Class')) {
      //Do something
  }
  ```

## Database
* When storing user inputted information into SQL, you must escape the information before storing it.
* Always use prepared statements when possible.
* NEVER use non-secure practices when dealing with databases
* When performing any database operations PDO should be used over mysqli

## Unused & Deprecated Functions
* Any unused functions should be marked as deprecated using a PHPDoc Comment with the @deprecated tag.
* Deprecated methods shall be removed after being deprecated for no more and no less than one Software release.
* In the event that majority of the Software's users would like a deprecated method to stay;
  * It may be unmarked as deprecated,
  * or it may stay in the Software source longer than one release.
  * *The choice is entirely up to the discretion of the core Software developers.*

## General Style
* Indentation should be done with four spaces, not tabs.
* Do not  place spaces before or after the concatenation operator(".")
* Place a space before and after the concatenating assignment operator(".=")
* Always use the clean_input() method on user provided values
* Always use PHP_EOL instead of specifying a line separator
* Always use DIRECTORY_SEPARATOR instead of specifying a separator
* Never assume a variable is an instance of a class. Always check using instanceof before using variables/methods.

# Soft Standards
Standards located in this section are not organized in any particular fashion other than the fact they are currently not enforced, and are documented here for the sole purpose of allowing contributors to become informed of them before they are enforced.

## PHP 7 Specific
  * Use coalescing operator(??) where possible
  * Use Statements
    * Always group use statements together when possible
    * Use statements should be places at the top
## General

## Proposals
Addition proposals are accepted from anyone who feels that these standards don't adequately cover certain aspects of PHP that is able to be formatted various ways. Proposals must follow a specific format to provide the most clear, understandable proposal.

### Format
The format to be used for proposals is as follows:

```
Proposal Format

Section: The section this proposal corresponds to, or the name of the new section proposed.

Addresses: The PHP feature this addresses, and the various non-recommended formats and ways each format could impair code readability, and flow.

Proposed: The proposed recommended format for this particular PHP feature, and how it makes code more readable than the alternative formats.
```

## Modifications
The CFH PHP Code Quality Standards may change from time to time, because of this, it is the sole responsibility of each contributor to stay up-to-date on these standards when making modifications to the Software Source Code.

## Last Modified
The CFH PHP Code Quality Standards were last modified on January 30th, 2017.

## Proposed Additions
These are additions that have been proposed for the coding standards, but still have to be voted upon by the core Software developers. Addition proposals must follow the guidelines specified in Additions > Proposals section of these standards.