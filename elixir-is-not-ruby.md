# Elixir is not Ruby

---

### Welcome Elixir |> Lille #2

* Slack http://lille-elixir.herokuapp.com
* Meetup https://www.meetup.com/Lille-Elixir/

---

### Thanks

* LilleFP
* Dernier Cri

---

## We've all seen this kind of things lately

---

![](http://take.ms/E2JZv)

---

![](http://take.ms/iEsvN)

"DEVISE LIKE" REALLY?

---

![](http://take.ms/GwJJi)

https://robots.thoughtbot.com/elixir-for-rubyists

---

## Phoenix vs Rails

guess who wins...

```
Phoenix:
  req/s: 2,691.03
  Stdev: 139.92ms
  Max latency: 1.39s

Rails:
  req/s: 301.36
  Stdev: 2.06s
  Max latency: 8.36s
```

---

### But the comparison should stop here

![](http://take.ms/PHyBI)

---

### Because the ONLY thing that Ruby and Elixir have in common...

---

### Is this guy

![](http://take.ms/fETm4)

José Valim

Creator of Elixir - Former Rails Core Developer

---

## This is a technical talk

But we won't show any code

---

## Why?

---

## Because they have a **very** similar syntax

---

## Which makes people make such statements

> Elixir is Ruby on steroïds

---

## Or even

> Elixir is just a natural evolution of Ruby

---

## Real life example

---

## 🇫🇷 vs 🇪🇸

* Latin Script `A-Z`
* Derived from Latin Language
* Sentences could be translated almost word for word

---

## but...

* Knowing French doesn't mean you know Spanish
* French is not Spanish on steroïds
* Or the other way round

---

# Quick Comparison

---

## Ruby

* has objects
* relies on mutation

---

## Elixir

* has no objects
* relies on transformation

---

### And we could stop here

![](http://take.ms/e5JvA)

---

## Elixir is not Object Oriented

---

## We have

* Modules
* Functions <small>(first class citizen)</small>
* Immutability of variables

---

### And a few other niceties

* Pattern Matching <3
* Protocols <small>(Java Interface)</small>
* Macros <small>(LISP like)</small>

---

## Breaking News

Elixir is a **Functionnal Language**

---

### But not only

---

### Elixir is Concurrent

---

### And it's not over

---

### Elixir is Distributed

---

## How does it work?

---

In Elixir, code is evaluated sequentially (as in Ruby).

---

So Business Logic is written **sequentially**

---

But we put our code in what we call a **Process**

---

## What is a Process?

---

* Not an OS Process but a **very** lightweight thread of execution
* Communicates through messages
* Fully Isolated (which means data they hold is not accessible from the outside)
* Run concurrently, at **very** large scale (`> 100k`)

---

## Moreover

* Each process has its own address <small>#PID</small>
* They can communicate between nodes accross the internet

---

Our Business Logic, written sequentially, is executed **concurrently** thanks to Processes

---

We have a **concurrent Business Workflow** based on the execution of multiple Processes

---

### How do we handle failure?

In Ruby, we just wrap everything in a `begin rescue` block to catch `Exceptions`

---

### This whole idea is crazy

> Something really exceptionnal happened but just keep going again and again

---

![](http://take.ms/Ti8o2)

> Insanity: doing the same thing over and over again and expecting different results.

> Albert Einstein

---

In Elixir, a Process can fail and it won't take the whole application down.

---

Instead, we will decide for each Process how it should behave in case of failure.

---

But if we keep doing all of this manually, it will quickly get out of hands.

---

### OTP (Open Telecom Plateform)

---

**BEAM** gives us the foundations (Processes/Nodes) but **OTP** gives us tools and patterns

---

* GenServer (Generic Server) stores state and defines functions to transform it
* Supervision Tree (organize your processes lifecycle and recovery policy in case of failure)
* Tools for persistance in the form of key value stores (in memory, local storage or even distributed accross nodes) that can contain Elixir Structs

---

So if you're not using all those OTP tools, something's wrong.

---

### Concurrency and Distribution with Ruby

---

Trying to achieve the same level of distribution and concurrency with Ruby can be a daunting task.

---

Without the ease of BEAM/OTP, we have to handle all of the following by ourselves.

---

### Threading

* you have to handle the state accessed by potentially all your threads concurrently without letting you know
* you have to handle a MUTEX

---

### Background Jobs

* Fire and forget (you can't wait for the response)
* Can become hell with recursive background calls
* Hard to debug and to recover from failures

---

Oh, and you'll need a <small>(very)</small> good Sysadmin

---

But if you succeed in doing all of this...

---

### You can contact this guy

![](http://take.ms/tHFPA)

> Matz, creator of Ruby

---

Ruby 3, which will come in at least 3 years is all about this...

---

![](http://take.ms/F3voY)

And by this, we only mean the **concurrency** aspects and not on the **distribution** ones.

---

## What we learned

---

To architecture an application in Elixir, thinking about Data Hierarchy is not enough.

---

You have to think about how your application should react to failure and where and how to store state.

---

OTP gives no easy path to design a distributed application.

---

You will have to spend some <small>(a lot of)</small> time thinking about your application design.

---

## Conclusion

---

We believe that Elixir is a technology for the next decade but you must accept to become a "noob" and rewire your brain on application design.

---

So jump into Elixir if you're ready for a new challenge.

---

But if you're looking for Ruby with concurrency, just wait for it ;)

---

![](http://take.ms/Imhjn)
