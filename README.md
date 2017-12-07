# This
🌋 Powerful, Clean, Elegant Initialisation Sugar 🌋

# Description

This is a small syntactic extension to NSObject that makes it easier for you to initilialize your object in a very Swifty way.

## Simply

-   `this()` is an extension on all NSObject subclasses

    ```swift
    let fileManager = FileManager().this {
       $0.urls(for: .applicationDirectory, in: .userDomainMask)
    }
    ```
    
    Clean up your initialization Code
    
```swift
let tableView = UITableView().this {
    $0.backgroundColor = .white
    $0.register(UserCell.self, forCellReuseIdentifier: "CellID")
    $0.separatorStyle = .none
    $0.allowsSelection = false
}
```

Initialize in **this** way.

```swift
  let tableView : UITableView = {
      let table = UITableView()
      table.backgroundColor = .white
      table.register(UserCell.self, forCellReuseIdentifier: "CellID")
      table.separatorStyle = .none
      table.allowsSelection = false
      return table
  }()
```

### Easy Customization

- Use your own Types With a simple Extension

    ```swift
    extension CustomType: This {}
    
    let instance = CustomType().this {
      $0.color = .blue
      $0.label.text = "Custom Type"
    }
    ```


### A Real World Example
```swift
class LoginViewController : UIViewController {
    var loginButton = UIButton().this {
        $0.setTitle("Login", for: .normal)
        $0.backgroundColor = . yellow
        $0.layer.masksToBounds = true
        $0.layer.cornerRadius = 5
    }
    override func viewDidLoad() {
        super.viewDidLoad()
        view.addSubview(loginButton)
    }
}

```

### Installing

- **For iOS 8+ projects** with [CocoaPods](https://cocoapods.org):

    ```ruby
    pod 'This'


## Deployment

just `clone` the repo and run on Xcode


## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.


## Authors

* **Chris Karani** - 

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
