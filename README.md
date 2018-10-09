# PHPUnit Tutorial
## Getting Started
1. Setup your vagrant environment
2. Clone this repository
3. Run `composer update`
4. Setup PHPStorm to run your unit tests:
    1. Under Languages & Frameworks > PHP, set the CLI interpreter to point to your vagrant instance
    2. Under Languages & Frameworks > PHP > Test Frameworks, set the CLI interpreter to the same interpreter you setup in 3.1. Under "PHPUnit library" select "Use Composer autoloader" and point the path to "autoload.php" in the vendor directory
## Kata
This Kata was taken from <http://osherove.com/tdd-kata-1/> and <http://codingdojo.org/kata/StringCalculator/>. For convenience the steps are replicated here:

### Step 1
* Create a simple string calculator with a method `int add(string $numbers)`
* The method can take 0, 1, or 2 numbers separated by a comma and return their sum
* An empty string will return 0
* Examples: 
    * "" should return `0`
    * `1` should return `1`
    * `1,1` should return `2`
    * `2,5` should return `7`

_Start with the simplest test case and them move to 1 and then 2 numbers. Solve things as simply as possible. Remember "red, green, refactor"_

### Step 2
* Allow the method to handle and unknown amount of numbers

### Step 3
* Allow the method to handle new lines as a separator
* Examples: 
    * `1\n2,3` should return `6`
    * `2\n5` should return `7`

### Step 4
* Add errors for invalid input
* Examples:
    * `2,\n5` should return `Number expected but "\n" found`
    * `1,2,` should return `Number expected but EOF found`
    
### Step 5
* Allow the add method to handle different delimiters
* To change the delimiter the beginning of the string will contain a separated line that looks like this `//[delimiter]\n[numbers]`
* If this line is not present the method should behave as before
* Examples:
    * `//;\n1;2` should return 3
    * `//|\n1|2|3` should return 6
    * `//sep\n2sep3` should return 5
    * `//|\n1|2,3` is invalid and return the message `'|' expected but ',' found`
    