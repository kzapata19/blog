---
layout: post
title:  "What is in a Name?"
date:   2018-01-01 18:30:12 -0700
categories: variables, functions, naming, labels, Clean Code
---

Chapter 2 of Clean Code emphasizes the importance of choosing a good name. It takes careful planning and time but the investment is well worth it because a good name will save time in the long run. Here are a few of the sensible and simple rules that stood out to me.

### Choose Descriptive and Unambiguous Names

Once a name is decided, if a better one reveals itself later, update the name. The name of the variable, function or class should answer questions about the purpose of its existance, its function, and how its used. If the name requires a comment, then it does not reveal its intent. For example, as I comb through my tic-tac-toe code, I see a method in my `GameSession` that can be renamed from `update_both_boards(location, player)` to `update_board(location, player_mark)`. This method takes the location provided by the current player and places that player's mark in the corresponding index location on the `Board`'s `grid` (aka array). Once this `@board.grid` is updated,  we call the `Display`'s `print_game_board(@board.grid)` method and pass the updated `@board.grid` to present the UI of the board on the terminal. I think that renaming the method to `update_board` communicates that there is one board (the board being displayed on the terminal) and no longer conflates the UI of the board (displayed in the terminal) with the board's grid (the data structure storing the source of truth - the current players' moves and the 'empty' labeled board spaces).

### Make Meaningful Distinctions

Create names that are distinguishable in a way that the reader will know what the differences offer. For example, Uncle Bob brings up how two classes `ProductInfo` and `ProductData` are two distinct names but the names when compared to each other and in the same context don't really mean anything different because `Info` and `Data` are unnecessary words.

### Use Pronounceable Names

If you can't pronounce it, you can't discuss it without sounding like a weirdo. The exmaples used in the book `Private Date genymdhms` is much harder to discuss in a conversation than `Private Date generationTimestamp`

### Class Names

Classes and objects should have noun or noun-phrase names such as `Customer`, `Account`, and `AddressParser`. A class should not be a verb.

### Method Names

Methods should have verb or verb-phrase names like `save` or `deletePage`.

### Pick One Word per Concept

Pick one word for each abstract concept and stick with it. For example, choose between `fetch`, `retrieve` and `get` but don't alternate among these.

### Don't Pun

Avoid re-using the same term where its semantic meaning in the code is different. For example using `add` for consistency in all classes even though in some classes `add` means pushing an element to the end of a collection and in other classes `add` means prepending an element to a collection.

### Don't Add Gratuitous Context

Shorter names are in general preferred over longer ones, as long as they are clear. Avoid adding more context to a name than necesssary. Some examples used include names like `accountAddress` and `customerAddress` for instances of the class `Address`. However these same names would be poor class names. `Address` is a perfectly fine name for a class.
