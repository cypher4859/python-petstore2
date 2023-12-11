# python-petstore2

## Goals
- Learn how to use the 2 most commonly used collections: List and Dictionary.

## Instructions
In the last exercise we added a function to add a product to store. In this exercise, we're going to expand on that as well as add a new function to view our product list.

1. We're going to add a new class to handle all of our product functionality. Add a new class called `ProductLogic`.
1. In this new `ProductLogic` class, add your constructor by writing the `def __init__():`. For now just add the `pass` keyword inside the constructor.
1. In `ProductLogic` add a new private class variable called `_products` which will be a list. Remember to add an underscore _ before the name because it's a private variable. Set this equal to an empty list.
1. Create a new function/method in your `ProductLogic` class called `AddProduct()`. This will not return anything and it will accept one argument called `product` and it should be of type Product. So the method declaration/signature will look like this: `def AddProduct(product: Product) -> None:`
1. In that method, `AddProduct()`, use the `_product` variable's `.append()` method to add the method's argument (which should be `product`) to the list.
1. Next create another method in the class called `GetAllProducts()`. The method will return a type `list[Product]` and will have no arguments. This method will be really simple, all you have to do is return our private variable: `return _products`.
1. Back in our main "Program" class or wherever our main entry point is (which might be inside of `main()`), we're going to create an instance of our new ProductLogic. Make it a variable near or at the top of our class. Should look like:  `productLogic = ProductLogic()`
1. Replace the line where we are serializing via `json.dumps()` the product that the user is creating with the `AddProduct()` method and pass the product the user created into the method. In effect we want to take the product the User is creating and pass it to the `AddProduct()` which will add it to our total list of products.
1. After adding the product, add a nice message below it to let the user know that the product was added.
1. Our next major thing to add will be some dictionaries to hold our specific types of products. So back in `ProductLogic`, add 2 more private class variables. These two variables will be `dict`s and will hold a key/value mapping where the `key` is a string name of a dog product or cat product and the value is the corresponding object. You can choose what to name the variables that will contain the dog products and the cat products.
1. Now, in `AddProduct` add a conditional `if` statement. It's condition will check for the Type of object. If the type of object is a DogLeash it will be added to the dog product dictionary you created previously. If it's a CatFood object, it will be added to the cat products dictionary. The key will be the product's `name` value. So an if statement will look like this: if (isinstance(product, DogLeash)).
1. Inside the body of this conditional `if` statement, use the following technique to add the product to the appropriate dictionary: `dogproducts[product.name] = product`. Make sure the `.name` matches the casing (upper/lower) of the class property.
1. Add another conditional `if` block that does the same thing except for `CatFood` instead of `DogLeash`. As a result we should have two classes, `CatFood` and `DogLeash` that look similar.
1. Add another method called `GetDogLeashByName()`. It will return an object of type DogLeash and will have one argument of type string called "name".
1. Inside the body of the `GetDogLeashByName()` method you will need to use the `name` argument to access the `dogproducts` dictionary (or whatever you named this dictionary) in order to get back the `DogLeash` object. That would look like something this: `return dogproducts[name]`.
1. Back in the main program class, add a new option for the user. It will be option number 2 and will let them get a specific object out of the list. Since they're only adding a dog leash right now, we're going to just let them retrieve a dog leash.