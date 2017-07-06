# Kotlin Validation

## Usage

```
class User(val name: String, val age: Int)
val validation = Validation<User> {
    be { name.length >= 5 } not "name: 5 characters or more"
    be { age >= 20 } not "age: Over 20 years old"
}

val errorMessages = validation.validate(User("kamedon", 30))
//errorMessages: emptylist

val errorMessages =validation.validate(User("", 0)) 
//errorMessages: 2 message
```

## Installation

```
repositories {
    maven { url 'http://kamedon.github.com/Validation/repository' }
}

dependencies {
    implementation 'com.kamedon:kotlin-validation:0.1.0'
}
```

## License
This software is released under the MIT License, see LICENSE.txt.