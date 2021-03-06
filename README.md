# Linq Java
Iterate over a collection is a medieval way to filtering, mapping and ordering. And with Java we are used to work like that. 

[Download LINQ Java](dist/Linq.jar)

## How it works?

It's easy to use. Just add `import static com.nth.linq.Linq.*;` in your class and that's it!

## How to use this?

### 1 - Filter

First you need a Collection. Here we create a Animal List, and we called it animals.

```java
List<Animal> animals;
```

Later you goes add a lot of animals in this list.

Now, you want to take *all* cats, it's easy for Linq! In this case, name is a method (`animal.name()`).

```java
from(animals).where("name", eq("Cat")).all();
```

Or, would the *first* animal with 2 year old? Easy too!

```java
from(animals).where("age", eq(2)).first();
```

### 2 - Filter specification

You can be more specific in your query, adding more specifications, like *and* and *or*.

```java
from(animals).where("name", eq("Lion")).and("age", eq(2)).all();
from(animals).where("name", eq("Dog")).or("age", eq(5)).all();
```

### 3 - Matchers

There are other matchers to be precise!

```java
eq("Cat")
eqIgnoreCase("Cat")
contains("og")
greaterThan(3)
lessThan(10)
isNull()
```

Or a special matcher, called *not*.

```java
not(eq("Bird"))
not(contains("at"))
not(isNull())
```

### 4 - Order

Order is a very interesting feature to sort your collection.

```java
from(animals).where("name", eq("Cat")).orderBy("age").all();
from(animals).where("age", eq(5)).orderBy("name", Order.DESC).first();
```

You can use just order, without filter.

```java
from(animals).orderBy("name");
```


