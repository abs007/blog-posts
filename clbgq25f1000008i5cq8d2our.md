# Go structs

A struct is a data type that groups together values of different types. Structs are useful for organizing related data into a single entity, hence making it easy to work with. This is a great use of abstracting away data.

To define a struct, you use the `type` keyword followed by the name of the struct, the `struct` keyword and finally, the list of fields enclosed within curly braces (This method of using `type`, *name* and then the *variable type* is go's way of defining custom data types). Each field has a name and a type. For example, the following code defines a `person` struct with two fields:

```go
type person struct {
  name string
  age int
}
```

There are multiple ways of creating a variable of a particular struct type. To make one of the `person` type, you can use the following ways:

## By using the *struct* literal.

```go
p1 := person{                   // p1 = person{"Rajiv", 30}
  name: "Rajiv",
  age: 30,
}

// Adding an '&' creates a pointer of type person
p2 := &person{                  // p2 = &person{"Rajiv", 30}
  name: "Rajiv",
  age: 30,
}

// Make sure to pass the values in the correct order
// This avoids having to add the field name 
p3 := person{"Rajiv", 30}      // p3 = person{"Rajiv", 30}
```

## Without using the **struct** literal, via the ***new*** keyword.

*This returns a pointer to the created struct.*

```go
p := new(person)
p.name = "Rajiv"
p.age = 30                      // p = &person{"Rajiv", 30}
```

Once you have created a struct value, you can access its fields using the dot notation. For example, the following code accesses the `name` field of the `person` struct `p`:

```go
fmt.Println(p.Name)  // "Rajiv"
```

Along with accessing fields, you can also modify the values of fields using the dot notation. For example, the following code sets the `age` field of the `person` struct `p` to 35:

```go
p.Age = 35
fmt.Println(p.Age) // 35
```

One of the key advantages of using structs in Go is that they allow you to define custom data types that can be used throughout your program. This makes it easier to write modular and reusable code, as you can define a struct that encapsulates a particular set of data and then use that struct wherever you need to work with that data.

For example, the following code defines a `book` struct with fields for the book's title, author, and page count:

```go
type book struct {
  title string
  author string
  pages int
}
```

This `book` struct can be used to represent a book in your program. You can create a `book` struct value by providing values for each of the fields, as in the following example:

```go
bk := book{
  title: "Oliver Twist",
  author: "Charles Dickens",
  pages: 373,
}
```

Once you have created a `book` struct, you can access and manipulate its fields using the dot notation, as in the previous example. For instance, the following code prints the title and author of the `book` struct `bk`:

```go
fmt.Printf("%s by %s\n", bk.Title, bk.Author)  // Oliver Twist by Charles Dickens
```

*Sidenote:* Using *lowercase* letters to name a field (eg: `title` field in the `book` struct) makes it such that it can't be used outside the package the struct was defined in. This is similar to how methods and functions in go can't be used outside the package if they start with a lowercase letter.

## Methods

In addition to defining custom data types, structs also allow you to define methods that operate on the struct's data. A method is a function that is associated with a struct and has access to the struct's fields. This allows you to define behaviour that is specific to your struct and that can be easily invoked on any variable of the particular struct value.

For example, the following code defines a `book` struct with a `PrintInfo` method that prints the book's title, author, and page count:

```go
type book struct {
  title string
  author string
  pages int
}

func (b *book) PrintInfo() {
  fmt.Printf("%s by %s (%d pages)\n", b.Title, b.Author, b.Pages)
}
```

Here, the `PrintInfo` method is defined as a function that takes a pointer to the `book` struct (`*book`) as its receiver. This means that the `PrintInfo` method can be called on any variable of the type `book` struct using the dot notation as in the following example:

```go
bk := &book{"Oliver Twist", "Charles Dickens", 373}
bk.PrintInfo()  // Oliver Twist by Charles Dickens (373 pages)
```

In this example, the `PrintInfo` method is called on the `book` struct `bk`, and it prints the title, author, and page count of the book. This allows you to easily print out information about the book without having to manually construct the output string.

Well, I hope this blog gave you a fair overview of structs in go and I hope you liked it.