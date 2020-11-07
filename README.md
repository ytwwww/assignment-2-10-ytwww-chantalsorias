# Instructions about Testing and Starting
Please have the following packages installed before starting: `flask`, `pytest`, `pytest-cov`, `requests`.  
- To run tests with coverage, type `pytest --cov-report term --cov=. tests/unit_tests.py`  
- To run the app:
  - First, run the main Flask module by running `python3 PizzaParlour.py`.
  - Then, run the Shell module by running `python3 Shell.py`  
# How to interact with Pizza Shell
- `?` or `help` list all commands

- `? <cmd>` or `help <cmd>` display guide about `<cmd>`
  - Examples: `? add`, `help menu`

- `new` starts a new order, will return `<order-number>`.

- `menu` shows full menu

- `menu <category>` shows menu by category. 
  - `<category>` is one of `pizza`, `topping`, `drink`.
  - Examples: `menu pizza`, `menu drink`, `menu topping`

- `menu <category> <name>` shows price for a specific item.
  - `<category>` is one of `pizza`, `topping`, `drink`.
  - Examples: `menu pizza neapolitan`, `menu drink juice`, `menu topping jalapenos`

- `cart <order-number>` shows the cart of the order with `<order-number>`.
  - Example: `cart 1`

- `add <order-number> <category> <name>` adds a drink or a predefined pizza to the order with `<order-number>`.
  - `<category>` is one of `pizza`, `drink`.
  - Examples: `add 1 drink coke`, `add 1 pizza neapolitan`

- `add <order-number> custompizza <size> <topping-1> <topping-2> ...` adds a custom pizza to the order with `<order-number>`.
  - `<size>` is one of `small`, `medium`, `large`.
  - `<topping-n>` is one of `olives`, `tomatoes`, `mushrooms`, `jalapenos`, `chicken`, `beef`, `pepperoni`.
  - Example: `add 1 custompizza large beef olives mushrooms`

- `remove <order-number> <category> <name>` removes a specified item from the cart of the order with `<order-number>`.
  - Examples: `remove 1 drink coke`, `remove 1 pizza neapolitan`

- `cancel <order-number>` cancels the order with `<order number>`
  - Example: `cancel 2`

- `q` exits the shell.

# Pair Programming

Pair programming has great benefits. It allows two minds to work together. This means that when working together, we can help each other out and brainstorm on getting a functionality to work. While pair programming there were times when one of us did not know how to do something and the other did and would help programming go faster. Other times when we both did not know something, we would both search it up and this allowed us to find an answer faster. Other times, the driver would continue coding until the navigator found an answer to something. Pair programming also allows one to learn things from the other programmer. We both use the same text editor and when Ya-Tzu started commiting and pushing from within the program, I learned something new. I always did it through the terminal. Other postives are few mistakes and bugs and increased code quality. Lastly, it improved team morale because we can talk to each other and help solve problems so that we would not be stuck on something for a long time.

Some negatives would be if the driver is perfectly capable of programming a feature by themselves and does not need feedback from the navigator then the navigator could be working on something else in the mean time.
This leads to the next problem of finishing a project on time. We would not be able to pair program for all features because it would take a longer amount of time compared to doing some individually.

Chantal was the driver for removing an item and cancelling an order. This involved working on the remove and cancel functions in Shell.py. Testing it and then working on the tests in unit_tests.py.

Ya-Tzu was the driver for adding items to the order. This involved working on the add function in Shell.py. Testing it and then working on the tests in unit_tests.py.

# Program design

We chose to respresent items using classes. MenuItem is a parent class with "name" and "price" attributes. Drink, Pizza, Topping, and CustomPizza are children classes of MenuItem. We decided this because we found that every item has a name and price. CustomPizza has more attributes such as "size" and "toppings". When a user adds a custom pizza to the other, we must also know the toppings they want included. Pizza which is predefined already has predefined toppings. For the "price" attribute, we needed to use a function to calculate it because every custom pizza could be different and therefore depends on its size and toppings.

# Code Craftsmanship
