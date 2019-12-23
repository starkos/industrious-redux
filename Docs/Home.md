# Industrious.Redux

## Basic Concepts

The [idea behind Redux](https://redux.js.org/introduction/motivation) is simplifying modern application development by making application state changes predictable and easy to reason about. It does this by introducing [three rules](https://redux.js.org/introduction/three-principles) guiding how data can be stored and changed. The [core concepts](https://redux.js.org/introduction/core-concepts) can be easily implemented with basic language features and no special libraries.

**Industrious.Redux** adapts the original Redux concept to .NET idioms, and hopefully gives you a jumpstart on using those ideas in your own applications.

If you're new to Redux, you may want to start by skimming through [the original Javascript project documentation](https://redux.js.org/introduction/getting-started). At a minimum, be sure to check out [Motivation](https://redux.js.org/introduction/motivation), [Core Concepts](https://redux.js.org/introduction/core-concepts), and the [Three Principles](https://redux.js.org/introduction/three-principles).

## Getting Industrious.Redux

I'll be publishing a NuGet package in the near future, once I get collection support and another example or two online. In the meantime, the source code is [available on GitHub](https://github.com/industriousone/industrious-redux).


## A Simple Example

The "Hello, world!" of Redux is the Counter example: a simple application which allows a counter value to be incremented or decremented.

> TODO: screenshot showing just the main bits...link to README within Counter example with more screenshots**





A _store_ contains the One True Application State.

The application state is changed by sending an _action_ to the store.

The action is handled by a _reducer_, a [pure function](https://en.wikipedia.org/wiki/Pure_function) that receives the current state and the action and returns the new application state.


### Application State

Define your application state as a read-only, immutable object.

```csharp
public struct AppState
{
    public AppState(Int32 counterValue = 0)
    {
        CounterValue = counterValue;
    }

    public Int32 CounterValue { get; }
}
```

This state is changed by dispatching actions, which describe the change to be made. For our simple counter example there is only one way to change the state: by adding

```csharp
public struct AddToCounterAction
{
	public AddToCounterAction(Int32 amount)
	{
		Amount = amount;
	}

	public Int32 Amount { get; }
}
```

Finally, a _reducer_ takes the current application state and an action, and returns a new application state representing the result of the action.

```csharp
public static AppState Counter(AppState state, Object action)
{
	switch ()
}
```



Let's start with the application state. For our simple Counter example, all we need to store is the current value of the counter itself.

```csharp
public struct AppState
{
    public AppState(Int32 counterValue = 0)
    {
        CounterValue = counterValue;
    }

    public Int32 CounterValue { get; }
}
```

In the Redux model, all of your application state is stored in a single object tree (don't get too hung up on this; yes, of course you can have multiple state objects for specific purposes when that extra complexity is needed). For this simple application a single object is all we need; usually your state will be composed of a tree of smaller state objects, each responsible for support a specific feature of your application.

Another important feature of the state, perhaps _the_ most important, is that it is _immutable_: the only way to change it is to create a new instance of the state to hold the modified values. [This article by NDepend](https://blog.ndepend.com/c-sharp-immutable-types-understanding-attraction/) provides a good introduction to the idea.

I tend to use `struct` instead of `class` for my state objects as they are little more than lightweight data containers, and the built-in equality support is convenient for unit testing.

### Actions

Changes to the application state are triggered by sending an action

The collection of actions provides a nice catalog of all the things that can be changed in your application.
