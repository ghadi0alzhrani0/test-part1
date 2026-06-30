# HBnB - Part 1 UML Documentation

This repository contains the UML documentation for the first part of the HBnB project.

The goal of this part is to explain the design of the application before starting the implementation.

## Contents

- Task 0: High-Level Package Diagram
- Task 1: Detailed Class Diagram for the Business Logic Layer

---

## Task 0 - High-Level Package Diagram

This diagram shows the general architecture of the HBnB application.

The application is divided into three main layers:

- Presentation Layer
- Business Logic Layer
- Persistence Layer

The `HBnBFacade` is used to connect the API with the internal logic of the application.

![Task 0 Package Diagram](images/task0_package_diagram.png)

### Explanation

The `Presentation Layer` receives requests from users and returns responses.

The `Business Logic Layer` contains the main models and rules of the application, such as `User`, `Place`, `Review`, and `Amenity`.

The `Persistence Layer` is responsible for saving and retrieving data.

The `HBnBFacade` acts as a simple interface between the API and the other layers. This keeps the communication clear and avoids making the API access the database directly.

The request flow is:

```text
Presentation Layer -> HBnBFacade -> Business Logic Layer -> Persistence Layer
```

---

## Task 1 - Detailed Class Diagram for Business Logic Layer

This diagram shows the main business classes used in the HBnB application.

The main classes are:

- `BaseModel`
- `User`
- `Place`
- `Review`
- `Amenity`

![Task 1 Class Diagram](images/task1_class_diagram.png)

### Explanation

`BaseModel` is the parent class. It contains fields shared by all main entities:

- `id`
- `created_at`
- `updated_at`

`User`, `Place`, `Review`, and `Amenity` inherit from `BaseModel`.

`User` represents a user of the application. A user can own places and write reviews.

`Place` represents a property listed in the application. Each place belongs to one owner.

`Review` represents feedback written by a user about a place. Each review is connected to one user and one place.

`Amenity` represents a feature that can be added to a place, such as WiFi, parking, or air conditioning.

### Relationship Summary

- One `User` can own many `Place` objects.
- One `User` can write many `Review` objects.
- One `Place` can contain many `Review` objects.
- One `Review` is written by one `User`.
- One `Review` is about one `Place`.
- `Place` and `Amenity` have a many-to-many relationship.

## Short Summary

Task 0 explains the big structure of the application.

Task 1 explains the business classes, their attributes, methods, and relationships.

Together, these diagrams give a simple first design for the HBnB application.
