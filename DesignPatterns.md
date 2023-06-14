# Software Design Patterns
Software design pattern is a general, reusable solution to a commonly occurring problem within a given context in software design.
it is a description or template for how to solve a problem that can be used in many different situations. Design patterns are formalized best practices that the programmer can use to solve common problems when designing an application or system.

#### Examples are in C++ and TypeScript languages

## Creational Patterns
How object are created

### Builder
Separate the construction of a complex object from its representation,
allowing the same construction process to create various representations.

```c++
// Definitions
class Burger
{
public:
  Burger();
  void SetBuns(std::string Bun) { mBun = Bun; }
  void SetPatty(std::string Patty) { mPatty = Patty; }
  void SetChese(std::string Cheese) { mCheese = Cheese; }

private
  std::string mBun;
  std::string mPatty;
  std::string mCheese;
};

class BurgerBuilder
{
public:
  BurgerBuilder();

  BurgerBuilder* AddBuns(std::string Bun)
  {
    mBurger->SetBuns(Bun);
    return this;
  }

  BurgerBuilder* AddPatty(std::string Patty)
  {
    mBurger->SetPatty(Patty);
    return this;
  }

  BurgerBuilder* AddCheese(std::string Cheese)
  {
    mBurger->SetChese(Cheese);
    return this;
  }

  Burger* Build()
  {
    return mBurger;
  }

private:
  Burger mBurger = new Burger(); // Heap allocated
  // Burger mBurger(); // Stack allocated
};
```
```c++
// Usage
Burger* burger = BurgerBuilder()
  .AddBuns("Sesame")
  .AddPatty("Spicy Beef")
  .addCheese("Cheddar")
  .Build();
```

### Dependency Injection
A class accepts the objects it requires from an injector instead of
creating the objects directly.

```ts
  
```

### Object pool
Avoid expensive acquisition and release of resources by recycling
objects that are no longer in use.

```c++
  
```

### Singleton
Ensure a class has only one instance,
and provide a global point of access to it.

```c++
// Definition
class Random
{
public:
  Random(const Random&) = delete;

  static Random& Get()
  {
    static Random sInstance;
    return sInstance;
  }

  // Return a member
  float GetSeed() { return Get().mSeed; }

  // Call a private function
  float RandomFloat() { return Get().PrivateRandomFloat(); }

  int RandomInt() { return 3; }

private:
  Random() {}
  PrivateRandomFloat() { return 6.7f; }
  float mSeed = 0.5f;
};
```
```c++
// Usage
float Seed = Random::GetSeed();
float ItemDropChance = Random::RandomFloat();
float ItemPrice = Random::RandomInt();
```

---

## Structural patterns
How objects relate to another

### Adapter
Convert the interface of a class into another interface clients expect.
An adapter lets classes work together that could not otherwise because
of incompatible interfaces.
```c++
// Definition
class USBCable
{
public:
  void PlugUSB()
  {
    bmIsPlugged = true;
  }

private:
  bmIsPlugged = false;
};

class USBPort
{
public:
  void Plug(USBCable& Cable)
  {
    if (bmIsAvailable)
    {
      Cable.PlugUSB();
      bmIsAvailable = false;
    }
  }

private:
  bmIsAvailable = false;
};

class MicroUSBCable
{
public:
  void PlugMicroUSB()
  {
    bmIsPlugged = true;
  }

private:
  bmIsPlugged = false;
};

class MicroToUSBAdapter //: public USBCable
{
public:
  MicroToUSBAdapter(MicroUSBCable MicroUsbCable)
  {
    mMicroUsbCable = MicroUsbCable;
    mMicroUsbCable.PlugMicroUSB();
  }

  // can override USBCable::PlugUSB()

private:
  MicroUSBCable mMicroUsbCable;
};
```
```c++
// Usage

// Usb can plug into usb...
USBCable UsbCable();
USBPort UsbPort();
UsbPort.Plug(UsbCable);

// MicroUsbCables can plug into Usb ports via an adapter
MicroToUSBAdapter MicroToUsbAdapter(MicroUSBCable());
UsbPort2 = USBPort();
UsbPort2.Plug(MicroToUsbAdapter);
```

### Bridge
Decouple an abstraction from its implementation allowing the two to
vary independently.

### Decorator
Attach additional responsibilities to an object dynamically keeping
the same interface. Decorators provide a flexible alternative to
subclassing for extending functionality.

### Facade
Provide a unified interface to a set of interfaces in a subsystem.
Facade defines a higher-level interface that makes the subsystem easier
to use.

```c++
// Definition
class ElectricCar
{
public:
  // Provides a simple interface to use externaly
  bool StartEngine() { /* Code */ }
  bool StopEngine() { /* Code */ }
  bool EnableAutoPilot() { /* Code */ }
  bool DisableAutoPilot() { /* Code */ }

private:
  /*
  Bunch of other complicated methods
  Instances of other classes
  And a bunch of class members
  ...
  */
};
```
```c++
// Usage
ElectricCar Car();
if (Car.StartEngine())
  Car.EnableAutoPilot();
```

---

## Behavioral patterns
How objects communicate with eachother

### Command
Encapsulate a request as an object, thereby allowing for the
parameterization of clients with different requests, and the queuing
or logging of requests.

### Observer
Define a one-to-many dependency between objects where a state change
in one object results in all its dependents being notified and updated
automatically.

```ts
// Definition
class YoutubeChannel {
  name: string;
  private subscribers: Array<YoutubeSubscriber>;

  constructor(name: string) {
    this.name = name;
    this.subscribers = [];
  }

  void subscribe(func: Function) {
    this.subscribers.push(func);
  }

  void trigger(msg: string) {
    this.subscribers.forEach(sub => sub.getNotification(this.name, msg))
  }
}

class YoutubeSubscriber {
  name: string

  constructor(name: string) {
    this.name = name
  }

  void getNotification(channelName: string, videoName: string) {
    console.log(`${this.name} received ${videoName} from ${channelName}`);
  }
}
```
```ts
// Usage
const channel = new YoutubeChannel("T Scott");
channel.subscribe(new YoutubeSubscriber("Dan"));
channel.subscribe(new YoutubeSubscriber("Yan"));
channel.subscribe(new YoutubeSubscriber("Wan"));

channel.trigger("This bus transforms into a train");
```

### State
Allow an object to alter its behavior when its internal state changes.
The object will appear to change its class.

### Strategy
Define a family of algorithms, encapsulate each one,
and make them interchangeable. Strategy lets the algorithm vary
independently from clients that use it.

```c++
class IFilterStrategy
{
public:
  virtual bool RemoveValue(int Value);
};

class RemoveNegativeStrategy : public IFilterStrategy
{
public:
  bool RemoveValue(int Value) { return Value < 0; }
}

class RemoveOddStrategy : public IFilterStrategy
{
public:
  bool RemoveValue(int Value) { return Value % 0; }
}

class IntArray8
{
public:
  IntArray8(std::array<int, 8> Values) : mValues(Values) {}
  FilterMutate(IFilterStrategy Strategy)
  {
    for (int& Item : mValues)
    {
      if (!Strategy.RemoveValue(item)) Item = 0;
    }
  }

private:
  std::array<int, 8> mValues;
};
```
```c++
IntArray8 Arr({1, 2, 3, 4, 5, 6, 7, 8});
Arr.FilterMutate(RemoveOddStrategy());
// Arr is {2, 4, 6, 8};
```

---

## Concurrency patterns:
NOPE