## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`
```
var str = "Hello, there"
print(str.uppercased())
```
Output: `HELLO, THERE`

2. **Given a String, return a String alternating between uppercase and lowercase letters**

Input: `Hello, there`

```
var str = "Hello, there"
var newStr = Array(str)
var ansStr = ""

for (index, char) in newStr.enumerated() {
    if index % 2 == 0 {
       ansStr = ansStr + String(char.uppercased())
    } else {
        ansStr = ansStr + String(char)
    }
}

print(ansStr)
```

Output: `HeLlO, tHeRe`


3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`
```
var str = "Hello, there"
var newStr = Array(str)
var ansStr = ""
for (index, char) in newStr.enumerated() {
    if char != "e" {
       ansStr += String(char)
    }
}

print(ansStr)

```

Output: `Hllo, thr`


## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`
```
var input = [1,5,2,4,1,4]
var largestNum = 0

for num in 1...input.count {
    if input[0] > largestNum {
        largestNum = input[num]
    }
}
print(largestNum)
```

Output: `5`

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`
```
var input = [1,5,2,4,1,4]
var smallesNum = 0


```

Output: `1`

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`
```
var input = [1,5,2,4,1,4]
var sumOfInput = 0

for num in input {
    sumOfInput += num
}
print(sumOfInput)

```

Output: `17`

4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`
```
var Input = [3, 4.5, 7.5, 2, 1]
var avg = 0.0
var sum = 0.0

for (num) in Input {
    sum += num
    avg = (sum) / Double(Input.count)
}
print(avg)
```
Output: `3.6`

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`
```
var sum = 0.0 
for (num) in Input {
    if num > 3 {
    sum += num
}
}

print(sum)

```
Output: `12`


6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`
```
var product = 1.0
for num in Input {
    product *= Double(num)
}
print(product)
```

Output: `202.5`

7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`
```
var validString = [String]()

for word in input {
    if word == nil { continue }
    validString.append(word ?? "a")
}
print(validString)

```
Output: `["We", "come", "in", "peace"]`

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

```

```

Output: `[]`

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`
```
var input = [4, nil, 9, 5, nil]
var validNum = [Int]()

for thing in input {
    guard let thing = thing else {
        continue
    }
    validNum.append(thing)
}
print(validNum)
```

Output: `18`

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`
```
var sum = 0

for thing in input {
    guard let thing = thing else {
        continue
    }
    if thing > 1 {
    sum += thing
}
}

print(sum)
```

Output: `24`


## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`
```
var setInput = Set<String>(input)
print(setInput)
```

Output: `["apple", "banana", "cake"]`

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`
```
var freqChar: Character = "?"
var freqDict: [Character : Int] = [:]
var trimmedStr = ""

for word in input {
    if word.isPunctuation || word.isWhitespace { continue }
    trimmedStr += String(word)
}

for char in trimmedStr {
    if let count = freqDict[char] {
        freqDict[char] = count + 1
    } else {
        freqDict[char] = 1
    }
}

var largestKeyValue = 0
for (key, value) in freqDict {
    if value > largestKeyValue {
        largestKeyValue = value
        freqChar = key
    }
}

print(freqChar)
```

Output: `t`

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`
```
var ansArr = [Int]()
var twiceDict: [Int : Int] = [:]

for num in input {
    if let count = twiceDict[num] {
        twiceDict[num] = count + 1
    } else {
        twiceDict[num] = 1
    }
}
for (key, value) in twiceDict {
    if value >= 2 {
        ansArr.append(key)
    }
}
print(ansArr)
```


Output: `[1,3,6]`

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`


## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`
```
let ansInput = input.sorted {$0 < $1}
print(ansInput)
```
Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`
```
let ansInput = input.sorted { $0.count < $1.count }
print(ansInput)
```

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`
```
let ansInput = input.filter { $0.count >= 4 }
print(ansInput)

```
Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`


## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
    
    func evenOrOdd (_ input: [Int], _ num: NumberType) -> [Int] {
        var ansArr = [Int]()
        switch num {
        case.even:
            for number in input {
                if number % 2 == 0 {
                    ansArr.append(number)
                }
            }
        case.odd:
            for number in input {
            if number % 2 != 0 {
                ansArr.append(number)
            }
        }
    }
return ansArr
}
}

```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
    
    func upperOrLower (_ sentence: String, _ word: StringType) -> String {
        switch word {
        case.lowercase:
            return sentence.lowercased()
        case.uppercase:
            return sentence.uppercased()
        }
    }
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
