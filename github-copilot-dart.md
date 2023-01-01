---
marp: true
---

# How to write a User class in Dart with fields name and lastname

```dart
class User {
  String name;
  String lastname;
}
```

The widget to display the User could be
    
    ```dart
    class UserWidget extends StatelessWidget {
      final User user;
    
      UserWidget(this.user);
    
      @override
      Widget build(BuildContext context) {
        return Text('${user.name} ${user.lastname}');
      }
    }
    ```

If we add another Int field named badges
    
    ```dart
    class User {
      String name;
      String lastname;
      int badges;
    }
    ```

If we want to display to text on top of each other with the name and the badges
    
    ```dart
    class UserWidget extends StatelessWidget {
      final User user;
    
      UserWidget(this.user);
    
      @override
      Widget build(BuildContext context) {
        return Column(
          children: [
            Text('${user.name} ${user.lastname}'),
            Text('${user.badges}'),
          ],
        );
      }
    }
    ```

Let's assume badges can be null
    
    ```dart
    class User {
      String name;
      String lastname;
      int? badges;
    }
    ```

Then the widget will look like
        
        ```dart
        class UserWidget extends StatelessWidget {
        final User user;
        
        UserWidget(this.user);
        
        @override
        Widget build(BuildContext context) {
            return Column(
            children: [
                Text('${user.name} ${user.lastname}'),
                if (user.badges != null) Text('${user.badges}'),
            ],
            );
        }
        }
        ```