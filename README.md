# Keep It Simple, Stupid (KISS) in Programming 🚀

> **Keep It Simple, Stupid** — Don’t overcomplicate things unnecessarily.
In programming, this principle helps you write **cleaner, easier-to-maintain code** by keeping things simple, clear, and modular.


## Introduction

Overly complicated code is hard to read, debug, and maintain.  
KISS suggests that **simpler is better** whenever possible.

Below are three examples showing how to apply KISS in real-life scenarios.


## Example 1: JSON Handling In Flutter (Before vs After)

### ❌ Before: Manual JSON handling

```dart
class User {
  String name;
  int age;

  User(this.name, this.age);

  Map<String, dynamic> toJson() {
    return {
      'name': name,
      'age': age,
    };
  }

  static User fromJson(String jsonString) {
    final data = json.decode(jsonString);
    return User(data['name'], data['age']);
  }
}
```
### ✅ After: Using json_serializable

```dart
@JsonSerializable()
class User {
  String name;
  int age;

  User(this.name, this.age);

  factory User.fromJson(Map<String, dynamic> json) => _$UserFromJson(json);
  Map<String, dynamic> toJson() => _$UserToJson(this);
}
```
## Example 2:


### ❌ Before: Complicated & Confusing Class Names

```dart
class ClsA {}
class ClsB {}
class DmHndl {}
class PrcMgr {}
```

### ✅ After: Meaningful Names Without Noise

```dart
class AuthenticationService {}
class PaymentProcessor {}
class UserProfileManager {}
class NotificationHandler {}
```
