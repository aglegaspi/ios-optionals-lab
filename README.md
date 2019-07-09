# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1 √

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap
``` swift

if userName != nil {
    print(userName!)
    } 
} else {
    print("No name.")
}

```

- Method two: Optional binding
``` swift

if let user = userName {
    print("\(user)")
} else {
    print("no username")
}

```

- Method three: Nil coalescing
``` swift

let uName = userName ?? "player 1"
print(uName)

```


## Question 2 √

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

`var backgroundColor: String?`

```swift

var backgroundColor: String?

let bgColor = backgroundColor ?? "new navy blue"
print(bgColor)

```

## Question 3 √

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift

var width: Double?
var height: Double?

width = 7.00
height = 5.00

if let w = width, let h = height {
    print("The area is \(w * h)")
} else {
    print("need width and height to calculate area")
}

```


## Question 4 √

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?

if let n = name, let a = age, let h = height {
    print("\(n), \(a) and \(h)")
} else {
    print("error! name, age, height required!")
}
```


## Question 5 √

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"

middleName = "Vicious"

if let m = middleName {
    let fullName = String("\(firstName) \(m) \(lastName)")
    print(fullName)
} else {
    print("Middle name required!")
}

```


## Question 6 √

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.

`let myIntString = "35"`

```swift

var myInt = Int(myIntString)
if let newInt = myInt {
    print(newInt + 15)
}

```

## Question 7  √

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift

let testCaseOne: (Int?, Int?, Int?)? = (4, nil, 7)
let testCaseTwo: (Int?, Int?, Int?)? = (nil, nil, 9)
let testCaseThree: (Int?, Int?, Int?)? = (5, 10, 24)
    
let testCases = [testCaseOne, testCaseTwo, testCaseThree]

for testCase in testCases {
    var sum = Int()
    
    if let testCaseUnWrapped = testCase {
        
            if let num1 = testCaseUnWrapped.0 {
                sum += num1
            }
            
            if let num2 = testCaseUnWrapped.1 {
                sum += num2
            }
            
            if let num3 = testCaseUnWrapped.2 {
                sum += num3
            }
    }
    print("The sum is \(sum)")
}

```


## Question 8 √

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?

if Bool.random() {
    tuple = (5, 3)
    if let tuple = tuple {
        print(tuple.0)
        print(tuple.1)
        }
}

```


## Question 9 √

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
let myInt: Int?
if Bool.random() {
    myInt = 5
    if let myInt = myInt {
        print(myInt)
        print(myInt * myInt)
    }
}
```


## Question 10 √

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
    myDouble = 12
    if let myDouble = myDouble {
        print(myDouble * doubleTwo)
    }
} else {
    print("myDouble is nil-ly vanilli")
}
```


## Question 11 √

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
    isTheGreatest = true
    if isTheGreatest == true {
        print(true)
    }
} else {
    isTheGreatest = false
    if isTheGreatest == false {
        print(false)
    }
}

```


## Question 12 √

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
 
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
    myTuple.0 = 5
    myTuple.2 = 14
    
} else {
    myTuple.1 = 9
    myTuple.3 = 10
}

let a = myTuple.0 ?? 0
let b = myTuple.1 ?? 0
let c = myTuple.2 ?? 0
let d = myTuple.3 ?? 0
let sum = a + b + c + d
print(sum)

```


## Question 13 √

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()

if let pokemon = pokemon, let evolutionaryStone = evolutionaryStone {

    print(pokemon)
    print(evolutionaryStone)
   
    if pokemon == "Pikachu" && evolutionaryStone == "Electic" {
        print("💫 Pokemon Evolved")
    }
    
    if pokemon == "Bulbasaur" && evolutionaryStone == "Grass" {
            print("💫 Pokemon Evolved")
    }
    
    if pokemon == "Charmander" && evolutionaryStone == "Fire" {
        print("💫 Pokemon Evolved")
    }
    
    if pokemon == "Squirtle" && evolutionaryStone == "Water" {
        print("💫 Pokemon Evolved")
        
    } else {
    print("Sorry Your pokemon will not evolve at this time!")
}

}
```


## Question 14 √

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift

var numberOfPeople14: Int?

if Bool.random() {
    numberOfPeople14 = 108
    if let evenNumPpl = numberOfPeople14 {
        
        if evenNumPpl % 2 == 0 {
        print("\(evenNumPpl) is even!")
        }
    }
}
```


## Question 15 √

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift

var someNumbers: [Int?] = []
var result15: [Int] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}

for n in someNumbers {
    var product = 0
    
    if n != nil {
        product = n ?? 0
        result15.append(product)
    }
}

let finalProduct = result15.reduce(1,*)
print(finalProduct)

```


## Question 16  √

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift

let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]
var cFCN: [String] = []

for city in poorlyFormattedCityNames {
    
    if let city = city {
        if city != nil {
            cFCN.append(city)
        }
        
        for (index,value) in cFCN.enumerated() {
                cFCN[index] = value.capitalized
        }
    }
}
print(cFCN)

```


## Question 17 √

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift

var aBunchOfNumbers: [Int?] = []
for _ in 0..<20 {
    aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}

var evenNumbers: [Int] = []

for number in aBunchOfNumbers {
    
    if let number = number {
        if number != nil && number % 2 == 0 {
            evenNumbers.append(number)
        }
    }
}
print(evenNumbers)

```


## Question 18 √

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

```swift


let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]
var zipCodeInts: [Int] = []

for zipString in zipCodeStrings {

    if let converter = Int(zipString) {
        zipCodeInts.append(converter)
    }
    
}
print(zipCodeInts)


```

## Question 19 √

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`

```swift 

let studentInfo: [(String, String?, String?)] =
    [("Bill", "Burgers", "Blue"),
     ("Rita", nil, "Red"),
     ("Peter", "Pizza", "Purple"),
     ("Sarah", "Sandwiches", nil),
     ("Jeff", nil, nil),
     ("Lucy", "Leftovers", "Lilac"),
     ("Mike", "Meat", "Mauve"),
     ("Gemma", nil, "Green")]

var studentWFavFoodnColors: [(String, String, String, String)] = []
var studentsWFFAC = [String]()

for student in studentInfo {
    
    if student.2 == nil && student.1 == nil {
        print("\(student.0) has no favorite food or color")
    } else if student.2 == nil {
        print("\(student.0) has no favorite color")
    }
    
    if let _ = student.1, let _ = student.2 {
        let studentName = student.0
        studentsWFFAC.append(studentName)
    }

}
let studentsWFFACTuple = ("\(studentsWFFAC[0])","\(studentsWFFAC[1])","\(studentsWFFAC[2])","\(studentsWFFAC[3])")

studentWFavFoodnColors.append(studentsWFFACTuple)

print(studentWFavFoodnColors)

```


## Question 20 √

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`

```swift

let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? =
    [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]


if let possibleColors = possibleColors {
var counter = 0
    
    for rgbTuples in possibleColors {
        
        if rgbTuples == nil {
            counter += 1
        }
        
        if let rgbValue = rgbTuples {
            
            if let r = rgbValue.r {
                if let g = rgbValue.g {
                    if let b = rgbValue.b {
                        print("3 RGB values (\(r), \(g), \(b))")
                    }
                }
            }
            
        } else {
            counter += 1
        }
        
    }
    print("Found \(counter) nil values too!")
}

```


## Question 21 √

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.
```swift

let number: Int??? = 10
print(number!!!)

```

- Optionally bind and print number.
```swift

let numberNested: Int??? = 10

if let number1 = numberNested, let number2 = number1, let number3 = number2 {
print(number3)
}

```


## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes", nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`

```swift 

let monkeyingAround = ["orangutan", "apes", nil, "monkeys", "gorillas", "lemurs", nil]

let vowels = ["a","e","i","o","u"]
var counter = 0
var output = ""

for value in monkeyingAround {
    
    if let string = value {
        
        // loop through string to see WHERE it has vowels and increment counter
        for letter in string where vowels.contains(String(letter)) {
            counter += 1
        }
        
        // if the counter less than 3 concatenate the string to the output
        if counter < 3 {
            output += string
        }

        counter = 0
    }
}
print(output)

```

## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`
