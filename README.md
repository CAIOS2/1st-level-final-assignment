# CodeAcademy
1st level final assignment

# Task description
You will need to create a simple app, where you can transfer balance between users. It should consist of 2 scenes - registration/login scene and home scene, where you can make transfers. Although we did registration/login a few times already, you should not blindly copy it from previous applications - we will ask questions during our 1 on 1 discussions about the implementation, so you need to understand why is it the way it is

There are no strict requirements about styling/structure for this assignment, since we are begginners and we are already overwhelmed about all the different stuff, but we should have that in mind and we will definitely take that into account when we will be reviewing your applications (in other words, we will not penalise you for missing cleanliness, but will give you a plus if you do it right)

Before sending your application to us, please try to test it as thoroughly as possible, check if there are no crashes, strange things or something like that

Your functions and variables naming should be easily understandable and readable. Also, think if you can use helper classes to handle all the validation logic etc. - take a look into our manager classes that we did in lectures. Do not forget about accessibility modifiers too (private). Use vars and lets appropriately

# Functionality
1. User should be able to register and login
2. When user sucessfully registers/logins - he is moved to home scene
3. In home scene, user is greeted with a label at the top of the screen **"Hello, username!"**
4. In home scene we can see user balance (in a label), two input fields, transfer button and logout button (in total, 5 UI elements)
5. In those input fields user can enter how much money he is going to transfer and for which user
6. Transfer button is for initiating transfer action (it takes values from input fields, validates them and shows a success or error alert)
7. After transfer, show a generic alert with information that transfer was sucessful. If any errors occured (for example, tried to transfer more than you have) - show same alert but with error message
8. When transfer is done, transferred amount should reflect in both sender and receiver accounts
9. If user presses on logout button, he should be routed back to login screen

Keyboard should be without auto-correct and auto-capitalisation (you can select that in *Interface Builder*, try to google if you cannot find it). You can have hardcoded user list (like we had with questions in the lectures), so you would not to need to register them everytime

# Validation
## Registration
1. Username should be at least 8 symbols and must not be already registered
2. Password should be at least 8 symbols
  
## Transfers
1. You cannot transfer negative (or zero) amount
2. You cannot transfer more than you have
3. Keyboard for amount textfield should be numeric
4. You cannot transfer to a user that does not exist

# Evaluation
For this assignment, we will basically only check if all functionality is fulfilled. We will give you comments about all the other things that are not mandatory for this task, but we will not take them into account when giving you a grade

# Deadline
The work needs to be sent as an archive to Romas or Tadas via Teams private message until 2022-12-06 (Tuesday 00:00)

---

# Cheatsheet

<br><br>
When creating a new view in Interface Builder:<br>
(do not forget to create your class that subclasses from `UIViewController`, before setting it as file owner)
<img width="1162" alt="1" src="https://user-images.githubusercontent.com/48261482/166254980-613694c1-9fe4-48ea-a4fd-f7e380dcd478.png">
![2](https://user-images.githubusercontent.com/48261482/166254932-14e3dd9e-dc59-487b-8b8f-3115c86c50c7.jpg)
<br><br>
If you need to present your view controller:<br>
`let yourViewController = YourViewController()`<br>
`present(yourViewController, animated: true)`
<br><br>
If you need to dismiss your view controller:<br>`
dismiss(animated: true)
`
<br>
Both of these commands (present and dismiss) needs to be called from `UIViewController` subclass (your view controller)
<br><br>
If you want your new screen to open in full screen after present is called, you should have:<br>
`yourViewController.modalPresentationStyle = .fullScreen` before calling present on `yourViewController`
<br><br>
When you will be ready to present your first screen, you need to make these changes if you changed your view controller name:
- In `AppDelegate.swift`: `window?.rootViewController = HomeViewController()` should become `window?.rootViewController = YourNewViewController()`
- In `SceneDelegate.swift`: `window.rootViewController = HomeViewController()` to `window.rootViewController = YourNewViewController()`
