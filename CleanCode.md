# General lean code rules

## 1. Avoid poor naming

### Short variable names

```c++
// BAD
std::string an;

// GOOD
std::string adminName;
```

We don't know what "an" stands for, only the original author.
This is unmaintainable, if somebody (even the author themselves or a collegue) comes across this in the future they will have no idea what this is about.

### Long variable names

```c++
// BAD
std::vector<Person> peopleFromIndiaWhoCanSpeakFrench;

// GOOD
std::vector<Person> frenchSpeakerIndians;
```

Need to shortern such names without losing the meaning.
Keep in mind when someone shorten the variable name, it should still be meaningful to others who read that code.

### Bad notations

NOTE: In C++ this is an exception!

```js
// BAD
const iSize = 32;
let szName = "Dude";

// GOOD
const size = 32;
let name = "Dude";
```

Modern programming does not use hungarian notation.
Well, except C++ world...
In short, the variables should be:
- Not too short, Not too long
- Meaningful
- Reveal Intention
- Chosen from the problem domain

## 2. Follow correct naming conventions

There are different naming conventions in different programming languages:
- camelCase
- PascalCase
- snake_case
- kebab-case

It’s important that you follow the correct naming convention to avoid being a chaotic coder.
A developer coming from a C# background would name a method in PascalCase while a JavaScript developer would name it in camelCase.
Always refer to good coding examples online if you are new to that language, also the documentations might help to find-out the best practices.

## 3. Create proper method signatures

```c++
// BAD
Laptop GetPerson(std::string ownerId)
{
    //do something
}

// GOOD
Laptop GetLaptopByOwnerId(std::string ownerId)
{
    //do something
}
```

Here you would call GetPerson method with an ownerId to fetch a person, but instead it would return you a Laptop. 
While that function might serve its’ purpose, it’s a terrible name which should be modified to a meaningful name so anyone who’s using it won’t be misguided.

## 4. Keep function parameter count to a minimum

```c++
// BAD
void myMethod(int param1, String param2, float param3, int param4, String param5) {}

// GOOD
void myMethod(int param1, String param2, float param3) {}
```

The best practice is to keep your method to 3 or less parameters.
While it can become hard sometimes, when you look closely there are situations where you can split the method to different functions.
Also if those parameters are actually related to same entity as attributes you would be able to create a new class and pass that object to you function.
This would ultimately improve reusability and readability in your code.

## 5. Declare variables at the place of use (*)

```c++
void MyMethod(Person person)
{
    std::string a, b, c;
    // after 25 lines...
    a = person.getName();
}
```

Where should the variables be declared?
Prefer it when variables are declared at the place where they are actually being used.
That way you won’t have to scroll back and forth to understand your code.

## 6. Avoid using confusing magic numbers

```c++
// BAD
player.x += 2;

Document GetDocument(int state)
{
    if (state == 1)
    {
        return new ActiveDocument();
    } else if (state == 2)
    {
        return new CanceledDocument();
    }
}

// GOOD
player.x += player.MovementSpeed;

// Can use defines
#define ACTIVE 1
#define CANCEL 2

// Can use enums
enum EDocumentState
{
    Active = 1,
    Cancel
};

Document GetDocument(int state)
{
    if (state == EDocumentState::Active)
    { 
        return new ActiveDocument();
    }
    else if (state == EDocumentState::Cancel)
    {
        return new CanceledDocument();
    }
}
```

## 7. Minimise extensive nested conditions

```c++
// BAD
if(a = true){
    if(b = true){
        state = "Active";
    } else {
      state = "Cancel";
    } 
} else if(c = true){
    if(b = true){
        state = "Active";
    } else {
      state = "Cancel";
    } 
} else {
    state = "Cancel";
}
```

Multiple nested conditions make it hard to read your code.
Always try to simplify them.
Above code can be simplified as below:

```c++
// GOOD
if(b = true && (a = true || c = true)) {
    state = "Active";
} else {
    state = "Cancel";
}
```

Also using ternary operators is a good practice:

```c++
// GOOD
state = (b = true && (a = true || c = true)) ? "Active" : "Cancel";
```

Keep in mind not to go overboard with combining conditions or ternary operators.

## 8. Don’t implement super long functions

Try to avoid creating long functions.
Just because you can read it and understand that doesn’t mean it’s a good practice.
Most of the time it’s hard to understand, to change and reuse.
Also it’s imported to manage cohesion in your code.
(related things should be together unrelated things should not be together).
A method should be short (preferably around 10 lines).
It should only do one thing and serve a single purpose.

```c++
// BAD
long long getAccountBalanceFromPersonId(std::string pid)
{
    //fetch person from id
    //get account from person account number
    //get account balance
}
```
This function is doing multiple things, it should be broken down to serve a single purpose.
Each functionality could be defined in separate methods.

## 9. Avoid code duplication

Another crucial factor is duplication in your code.
Do you find yourself copy pasting the same code to different places with small changes (may be only variable names or some values?), stop and think about creating a common function to be called.
Always stick to the DRY principle, Don’t Repeat Yourself!

## 10. Make necessary comments

It’s a common understanding that comments on codes are good.
I don’t find this to be very useful unless in specific situations.
It’s better to keep your code clean and understandable than making comments everywhere.
I follow below guideline when commenting on my code:

### Never state the obvious
If it’s obvious in code what you do your comment will be just a useless distraction.

```c++
// BAD
// A map to store employee id and the employee object
std::map<int, Employee> empIdToEmployeeMap;
```

### Never manage version history using comments
Managing version history changes through comments is not going to be useful in the long run.
This can easily be achieved through a versioning system like git.

```c++
// BAD

// v1.12
std::string GetName() {}
```

### Clarify through the code not comments
Instead of “pf” use a more clarifying name “payfrequency”.

```c++
// BAD
int pf; // payfrequency
```

### Dead code
Never leave commented out useless code.
Remove them completely.
If needed use version management to restore them but don’t comment and leave out dead code.

```c++
// BAD

/*void SetName(){
//do something
}*/
```

Don’t write comments to explain the code, try to change your code to be more understandable.
Use your comments to explain whys and hows.
Also you might have business reasons that might not be expressed through code that has to be mentioned as a comment.