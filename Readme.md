# Pick-A-Random-Item

## Problem Statement

As a user, I want Deluge to randomly pick an item from a *list of things*.

The reason why we mentioned a *list of things* is because we could use this for other things. Like a list of emojis, email addresses, URLs for Giphys as a few example. This is a really short code to randomly pick a list if it does not require a sequence (the opposite of a [Round Robin](https://github.com/TheWorkflowAcademy/Round-Robin-Owner-Assignment-Deluge)).

Let’s assume we have a list of NBA players. And whenever the script runs, I want to see a different name to be returned.

---

## Solution

First, let’s retrieve a list of names. For this example, we will be hard coding a list of NBA players’ names.

```jsx
listOfNames = ["Kobe Bryant","Bill Russell","Klay Thompson","Michael Jordan","Scottie Pippen","Dennis Rodman","Shaquille O'N0eal"];
```

Then get the size of the list.

```jsx
sizeOfList = listOfNames.size(); //Returns 7
```

Use the `randomNumber()` function to produce a random number.

We will be selecting from the first element in the list, to the last element, we will be starting from 0, to the size of the list.

This returns us the position of the name we’re looking for in the list. You can also see this as an identifier. And let’s call this identifier `nameId`.

```jsx
nameId = randomNumber(0,sizeOfList); //This will return numbers from 0 to 6.
```

Once we have the `nameId`, then we use `.get()` to return the selected item.

```jsx
info listOfNames.get(nameId);
```

And that returns a result at random!

Give this code a shot at Deluge Tryout!

```jsx
listOfNames = ["Kobe Bryant","Bill Russell","Klay Thompson","Michael Jordan","Scottie Pippen","Dennis Rodman","Shaquille O'N0eal"];
sizeOfList = listOfNames.size();
nameId = randomNumber(0,sizeOfList);
info listOfNames.get(nameId);
```

---

## Notes on randomNumber()

ℹ️ The two arguments for the `randomNumber()` function mean:

- Argument 1: `Start Number` - Starting from a number..
- Argument 2 (optional): `End Limit` - The range of numbers this function can use.
    - Though the [Deluge Function Documentation](https://www.zoho.com/deluge/help/functions/number/randomnumber.html) states this is the end limit, we have observed this is not necessarily the case.
    - How this should work is:
        - The `End Limit` should always be greater than the `Start Number`.
        - **Important:** If you wanted to generate a random number between 2, and 4, then take the max of that number, and add it by 1, so you get 5.
            - As weird as it sounds - the number you provide (for this case, 5) will be ignored. But by doing so, you are able to get a result of 4.
        - Run the function, and you should get a set of results between 2, 3 and 4.

Give it a shot below with the sample code that will run a the `randomNumber()` function 51 times.

```jsx
// Create a dummy list to use for a loop.
//
// Learn more about this at:
// https://github.com/TheWorkflowAcademy/Create-List-Of-Sequential-Numbers
//
iterator = repeat(",",50);
results = list();
for each i in iterator{
	// Capture results
	results.add(randomNumber(2,5));
}
// Print unique results from the list. This should show numbers between 2 to 4
//   But no more or less.
info results.sort().distinct();
```