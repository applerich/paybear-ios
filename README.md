# 🐻 Paybear iOS

[![CI Status](http://img.shields.io/travis/imryan/paybear-ios.svg?style=flat)](https://travis-ci.org/imryan/paybear-ios)
[![Version](https://img.shields.io/cocoapods/v/paybear-ios.svg?style=flat)](http://cocoapods.org/pods/paybear-ios)
[![License](https://img.shields.io/cocoapods/l/paybear-ios.svg?style=flat)](http://cocoapods.org/pods/paybear-ios)
[![Platform](https://img.shields.io/cocoapods/p/paybear-ios.svg?style=flat)](http://cocoapods.org/pods/paybear-ios)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Usage

#### Set Paybear API key
```swift
Paybear.shared.setToken("your-api-key")
```

#### Get current market prices
```swift
Paybear.shared.getCurrencies(completion: { (currencies, error) in
    if let currencies = currencies, error == nil {
        // Array of currency. Nice
    }
})
```

#### Get market exchange rates for all cryptocurrencies
```swift
Paybear.shared.getMarketRates(fiat: .usd) { (rates, error) in
    if let rates = rates, error == nil {
        // ...
    }
}
```

#### Get single market exchange rate for cryptocurrency
```swift
Paybear.shared.getSingleMarketRate(fiat: .usd, crypto: .btc) { (rate, error) in
    if let rate = rate, error == nil {
        // ...
    }
}
```

#### Create payment request in given cryptocurrency
```swift
Paybear.shared.createPaymentRequest(crypto: .btc, callbackURL: "http://ryans.online") { (request, error) in
    if let request = request, error == nil {
        // ...
    }
}
```

## Requirements

* Alamofire

## Installation

paybear-ios is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'paybear-ios'
```

## Author

Ryan Cohen, notryancohen@gmail.com

## License

paybear-ios is available under the MIT license. See the LICENSE file for more info.
