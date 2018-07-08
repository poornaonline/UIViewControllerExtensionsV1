# UIViewController Extensions

This Swift extension contains useful extension methods for UIViewController

#### Hide Keyboard when tap around


```sh
func hideKeyboardWhenTappedAround() {
        
        let tap: UITapGestureRecognizer = UITapGestureRecognizer(target: self, action:                                                  #selector(UIViewController.dismissKeyboard))
        tap.cancelsTouchesInView = false
        view.addGestureRecognizer(tap)
    }
    
    @objc func dismissKeyboard() {
        view.endEditing(true)
    }
}
```


#### Show Basic Alert using extension


```sh
func showBasicAlert(title: String, message: String) {
        
        let alert = UIAlertController(title: title, message: message, preferredStyle:                                                               UIAlertControllerStyle.alert)
        alert.addAction(UIAlertAction(title: "Okay", 
                                     style: UIAlertActionStyle.default, handler: nil))
        self.present(alert, animated: true, completion: nil)
        
}
```


#### Show Basic Alert and go back in Navigation View Controller (to Previous View Controller)


```sh
func showBasicAlertAndGoBackInNVC(title: String, message: String) {
        
        let alert = UIAlertController(title: title, message: message, preferredStyle:                                             UIAlertControllerStyle.alert)
        alert.addAction(UIAlertAction(title: "Okay", style: UIAlertActionStyle.default, 
        handler: {[weak self] (alert) in
            guard let strongSelf = self else { return }
            strongSelf.navigationController?.popViewController(animated: true)
        }))
        self.present(alert, animated: true, completion: nil)
}
```



#### Show Basic Alert and dismiss the Navigation View Controller


```sh
func showBasicAlertWithDismissNVC(title: String, message: String) {
        
        let alert = UIAlertController(title: title, message: message, preferredStyle:                                             UIAlertControllerStyle.alert)
        alert.addAction(UIAlertAction(title: "Okay", style: UIAlertActionStyle.default, 
        handler: {[weak self] (alert) in
            guard let strongSelf = self else { return }
            strongSelf.navigationController?.dismiss(animated: true, completion: nil)
        }))
        self.present(alert, animated: true, completion: nil)
}
```





