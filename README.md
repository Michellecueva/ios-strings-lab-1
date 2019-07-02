# Strings Lab 1

## Instructions for lab submission

1. Fork the assignment repo
1. Clone your Fork to your machine
1. Complete the lab
1. Push your changes to your Fork
1. Submit a Pull Request back to the assignment repo
1. Paste a link to of your Fork on Canvas and submit

## Question 1

Write code that prints out all the numbers from 1 to 10 as a single string.
(Hint: the `String()` function can convert an Int to a String)
``` swift
var num = 1...10

for i in num {
    print(String("\(i)"), terminator: " ")
}

```
***
## Question 2

Write code that prints out all the even numbers from 5 to 51 as a single string.

```swift 
var num = 5...51

for i in num where i % 2 == 0 {
    print(String("\(i)"), terminator: " ")
}


```

***
## Question 3

Write code that prints out every number ending in 4 between 1 and 60 as a single string.

``` swift

var num = 1...60

for i in num where i % 10 == 4 {
    print(String("\(i)"), terminator: " ")
}


```

***
## Question 4

Print each character in the string `"Hello world!"`
``` swift
var greeting = "Hello world!"

for letter in greeting {
    print(letter)
}

```

***
## Question 5

Print out the last character in the string below.  You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).
``` swift
`let myStringSeven = "Hello world!"`

let myStringSeven = "Hello world!"
let lastChar = (myStringSeven.last)!
print(lastChar)



```

***
## Question 6

Write code that switches on a string, given the following conditions:
- If the string's length is even, print out every character.
- If the string's length is odd, print out every other character.
``` swift

let string = "Cueva"

switch string.count % 2  {
case 0 :
    for letter in string {
        print(letter)
    }
default:
    for(index, element) in string.enumerated() {
        if index % 2 == 1 {
            print(element)
        }
    }
}
```
***
## Question 7

Initialize a String with a character. Show that it is a Character, and not another String, that you're using to initialize it.
```swift
let dogNameChar: [Character] = ["L", "u", "c", "k", "y"]

let dogNameString = String(dogNameChar)
```
***
## Question 8

Build five pairs of **canonically equivalent** strings, the first of each being a pre-composed character and the second being one that uses combinable unicode scalars. Show that they are equivalent.
```swift

var PreComposedCharacter1 = "\u{E1}"
var combinableUnicodeScalars1 = "\u{0061}\u{0301}"

print(PreComposedCharacter1  == combinableUnicodeScalars1)

var PreComposedCharacter2 = "\u{F1}"
var combinableUnicodeScalars2 = "\u{006e}\u{0303}"

print(PreComposedCharacter2  == combinableUnicodeScalars2)

var PreComposedCharacter3 = "\u{F6}"
var combinableUnicodeScalars3 = "\u{006f}\u{0308}"

print(PreComposedCharacter3  == combinableUnicodeScalars3)

var PreComposedCharacter4 = "\u{E7}"
var combinableUnicodeScalars4 = "\u{0063}\u{0327}"

print(PreComposedCharacter4  == combinableUnicodeScalars4)

var PreComposedCharacter5 = "\u{EA}"
var combinableUnicodeScalars5 = "\u{0065}\u{0302}"

print(PreComposedCharacter5  == combinableUnicodeScalars5)
```

***
## Question 9

**Using only Unicode**, print out `"HELLO WORLD!"`
```swift
var helloWorld = "\u{0048}\u{0045}\u{004C}\u{004C}\u{004f}\u{0020}\u{0057}\u{004f}\u{0052}\u{004c}\u{0044}\u{0021}"

print(helloWorld)
```

***
## Question 10

**Using only Unicode**, print out your name.
```swift

var name = "\u{004D}\u{0069}\u{0063}\u{0068}\u{0065}\u{006C}\u{006C}\u{0065}"

print(name)

```
***
## Question 11

**Using only Unicode**, print out `"HELLO WORLD!"` in another language.
```swift
var spanishHelloWorld = "\u{0048}\u{006f}\u{006C}\u{0061}\u{0020}\u{004D}\u{0075}\u{006E}\u{0064}\u{006f}\u{0021}"
print(spanishHelloWorld)
```

***
## Question 12

Print the below flower box using the following information.

- The unicode number for ⚘ is U-2698
- The top and bottom of the box are represented by dashes and the rows are |
- Use the terminator argument in your print statements to print on the same line.
- Hint: It may be useful to try printing out a box of just one character to start then work your way from there.

```swift
Flower Box:
- - - - - - - - - - -
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
- - - - - - - - - - -

var dash = "-"

var bar = "|"

var flower = "\u{2698}"

for _ in 0...10 {
    print(dash, terminator: " ")
}

print("")

for _ in 0...10 {
    for j in 0...10 {
        if j % 2 == 0 {
            print(bar, terminator: " ")
        } else {
            print(flower, terminator: " ")
        }
    }

print(" ")

}

for _ in 0...10 {
    print(dash, terminator: " ")
}

```

***
## Question 13

Write a program that sets up a chess board using Unicode.

```swift
Chess Board:
♖ ♘ ♗ ♕ ♔ ♗ ♘ ♖
♙ ♙ ♙ ♙ ♙ ♙ ♙ ♙




♟ ♟ ♟ ♟ ♟ ♟ ♟ ♟
♜ ♞ ♝ ♛ ♚ ♝ ♞ ♜

var rook = "\u{2656}"
var knight = "\u{2658}"
var bishop = "\u{2657}"
var queen = "\u{2655}"
var king = "\u{2654}"
var pawn = "\u{2659}"

var blRook = "\u{265C}"
var blKnight = "\u{265E}"
var blBishop = "\u{265D}"
var blQueen = "\u{265B}"
var blKing = "\u{265A}"
var blPawn = "\u{265F}"



var range = 0...7

for i in range {
    for j in range {
        if i == 1 {
            print(pawn, terminator: " ")
        } else if i == 6 {
            print(blPawn, terminator: " ")
        } else if i == 0 && (j == 0 || j == 7) {
            print(rook,terminator: " " )
        } else if i == 0 && (j == 1 || j == 6) {
            print(knight, terminator: " ")
        } else if i == 0 && (j == 2 || j == 5) {
            print(bishop, terminator: " ")
        } else if i == 0 && j == 4 {
            print(king, terminator: " ")
        } else if i == 0 && j == 3 {
            print(queen, terminator: " ")
        } else if i == 7 && (j == 0 || j == 7) {
            print(blRook,terminator: " " )
        } else if i == 7 && (j == 1 || j == 6) {
            print(blKnight, terminator: " ")
        } else if i == 7 && (j == 2 || j == 5) {
            print(blBishop, terminator: " ")
        } else if i == 7 && j == 4 {
            print(blKing, terminator: " ")
        } else if i == 7 && j == 3 {
            print(blQueen, terminator: " ")
        }

    }
    print(" ")
}

```

***
## Question 14

You are given a string stored in the variable `aString`. Create new string named `replacedString` that contains the characters of the original string with all the occurrences of the character `"e"` replaced by `"\*"`.

```swift
var aString = "Replace the letter e with \*"
// Your code here

var aString = "Replace the letter e with *"

var replacedString = aString.replacingOccurrences(of: "e", with: "*")

print(replacedString)

 ```

Example:

Input:
`var aString = "Replace the letter e with *"`

Expected values:
`replacedString = "R*plac* th* l*tt*r * with *"`

***
## Question 15

You are given a string stored in variable `aString`. Create a new string called `reverse` that contains the original string in reverse order. Print the reversed string.

```swift
var aString = "this string has 29 characters"
var reverse = ""

// Your code here

reverse += aString.reversed()

print(reverse)
```

Example:
Input:
`var aString = "Hello"`

Output:
`"olleH"`

***
## Question 16

You are given a string stored in variable `aString`. Print `true` if `aString` is a palindrome, and `false` otherwise. A **palindrome** is a string which reads the same backward or forward.

```swift
let aString = "anutforajaroftuna"

// Your code here

if (aString == String(aString.reversed())) {
    print(true)
} else {
    print(false)
}
```

Example 1:
Input:
`var aString = "anutforajaroftuna"`

Output:
`true`

Example 2:
Input:
`var aString = "Hello"`

Output:
`false`

***
## Question 17

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"

// Your code

let stringOfWords = problem.components(separatedBy: " ")

for word in stringOfWords {
    print(word)
}
```

Example:
Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```

***
## Question 18

You are given a string stored in variable `problem`. Write code that prints the longest word in the string.

```swift
var problem = "find the longest word in the problem description"

// Your code here

let stringOfWords = problem.components(separatedBy: " ")
var longestWord = ""

for word in stringOfWords {
    if word.count > longestWord.count {
        longestWord = word
    }
}

print(longestWord)
```

Example:
Input:
`var problem = "find the longest word in the problem description"`

Output:
`description`

Hint: Keep track of the longest word you encounter and also keep track of its length.

***
## Question 19

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"

var vowelCount = 0
var consonantsCount = 0


for char in input {
    if vowels.contains(char) {
        vowelCount += 1
    } else if consonants.contains(char) {
        consonantsCount += 1
    }

}

var bothCounts = (vowels:vowelCount,consonants:consonantsCount)

print(bothCounts)

```

***
## Question 20

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`


Output: `7`
``` swift 
var input = "How are you doing this Monday?"

let stringOfWords = input.components(separatedBy: " ")

if stringOfWords.count == 0 {
    print("No last word")
} else {
    let lastWord = stringOfWords[stringOfWords.count-1]
    print(lastWord.count)
}


```

***
