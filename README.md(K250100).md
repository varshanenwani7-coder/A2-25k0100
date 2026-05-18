# Reasoning Document

Create separate header (`.h`) files for each abstract class to define the interfaces, and implement their functionality in corresponding source (`.cpp`) files.

Abstract classes contain pure functions only; they serve as interfaces, therefore they don’t have any substantial implementation. Their functionality is implemented through derived classes.

---

# Operator Overloading Reasoning

Operator overloading is done to make user-defined data types behave like built-in data types. It improves readability, usability, and allows operators to work on objects.

Instead of doing:

```cpp
v1.getPrice() > v2.getPrice()
```

we use:

```cpp
v1 > v2
```

## Example in my code

```cpp
bool operator>(const Vehicle& v1, const Vehicle& v2) {
    return v1.getPrice() > v2.getPrice();
}
```

This compares two vehicles based on price.

## Example 2

```cpp
double operator-(const Vehicle& v1, const Vehicle& v2) {
    return v1.getPrice() - v2.getPrice();
}
```

This gives the difference in price.

---

# Reasoning for Using Friend Functions and Friend Classes

They are used when a function needs access to the private attributes of a class.

This approach decreases the number of getter functions needed to access private data members.

A friend class is made when an entire class needs access to the private data members.

## Example from the code

```cpp
friend void showSecretListingInfo(Listing& l);
```

### Justification

This friend function accesses the private members of class `Listing`: `price` and `approved`.

## Example 2

```cpp
friend class MaintenanceTool;
```

### Justification

`MaintenanceTool` is declared as a friend class of `Listing` because it needs to modify private data members `price` and `approved`.

---

# Inheritance Relationships and Their Justification

## 1. User and Buyer

`Buyer` is also a `User`; they both share common attributes. However, the `Buyer` class adds extra functionality like wallet management.

## 2. User and Seller

`Seller` is also a `User` but with additional functionalities like earning tracking. It reuses authentication and profile features from `User`.

## 3. User and Admin

`Admin` is also a `User` with functionalities like system auditing and role management.

## 4. Seller and PremiumSeller

This is an advanced version of `Seller` with added functionality like rating.

## 5. Car and Vehicle

`Car` is a `Vehicle` with added features like number of doors; otherwise, it shares common attributes with `Vehicle`.

## 6. Vehicle and Bike

Similarly, `Bike` is a `Vehicle` with an added feature of sports mode.

## 7. Vehicle and Truck

`Truck` is a `Vehicle` with a load capacity attribute.

## 8. Vehicle and Bus

`Bus` is a `Vehicle` with an added seating capacity feature.

## 9. Car and LuxuryCar

`LuxuryCar` is a `Car` with premium features.

## 10. Listing and AbstractListing (Interface Inheritance)

`Listing` implements the `AbstractListing` interface, ensuring it has a standard structure like display and price retrieval.

---

# Note on Linking this Assignment with Assignment 1

This assignment is an extension of Assignment 1 using more advanced OOP topics to enhance the functionalities.

Polymorphism was used through overridden functions such as the `display()` function and `displayVehicle()`.

Abstraction was also implemented using abstract classes.

Some components from Assignment 1 were redesigned for better integration. For example, the message functionality was retained but improved for better communication.

---

# Some Snippets from the Code
