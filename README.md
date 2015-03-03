# SSIDObserver

Wi-Fi network SSID observer. 

Usage:
```objc
    self.observer = [APSSIDInfoObserver new];

    __weak __typeof(self) weakSelf = self;
    [self.observer setSsidChangedBlock:^(APSSIDModel *model){
        if (model) {
            weakSelf.networkStatusLabel.text = [NSString stringWithFormat:@"Network is: %@", model.ssid];
        } else {
            weakSelf.networkStatusLabel.text = @"Cannot find wifi network";
        }
    }];
    [self.observer startObserving];
```

APSSIDModel properties:

```objc
/**
 *  Represents Basic Service Set Identification
 */
@property (nonatomic, copy, readonly) NSString *bssid;

/**
 *  Reprsents Service Set Identification a.k.a Wi-Fi Name
 */
@property (nonatomic, copy, readonly) NSString *ssid;

/**
 *  Represents HEX representation of SSID
 */
@property (nonatomic, copy, readonly) NSData *ssidData;
```

### Screenshot:
<img width=320 src="https://dl.dropboxusercontent.com/u/11819370/IMG_3333.PNG">

Feel free to open issues and pull requests. Or email me krivoblotsky@me.com
