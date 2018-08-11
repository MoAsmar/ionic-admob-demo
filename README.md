# ionic-admob-demo
A demo ionic app with Google AdMob Advertisements integrated.

## Getting Started

1. Download as zip or clone the project using:
```
git clone https://github.com/MoAsmar/ionic-admob-demo.git
```
2. cd to your project and run `npm install` .
3. add the platform for the app to run on your device: `ionic cordova platform add android` for android devices.
    Use `ionic cordova platform add ios` for ios devices.

### Prerequisites

-Ionic version 3.1.0 or higher (built with version 4.0.6).

-cordova (built with version 8.0.0).

### Installing

connect your device and run the command:
```
ionic cordova run android
```
then the app will start you will see two buttons.

Show Banner will popup the banner:

<img src="https://drive.google.com/uc?authuser=0&id=1cmosyyDQpjMPlsr2zyFl-8XWVO8KTVR2&export=download" width="300">


Show Interstitial will show the full screen interstital:

<img src="https://drive.google.com/uc?authuser=0&id=1vBWT85jygjN1x6ed5Sck8z0kJzgzQK_D&export=download" width="300">


### Prepare for production

set property **isTesting** to **false** and copy the banner Ad Unit ID from your admob and past it under **id** property as below example:

```
 showBanner() {

      let bannerConfig: AdMobFreeBannerConfig = {
          isTesting: false, // Remove in production
          autoShow: true,
          id: 'ca-app-pub-xxxxxxxxx'
      };

      this.admob.banner.config(bannerConfig);

      this.admob.banner.prepare().then(() => {
          // success
      }).catch(e => console.log(e));

  }
```

_note:_ for interstital ads do the same but copy the interstitial id from admob and add it under launchInterstitial() method.

**for more options and settings**, check the [admob free plugin documentation](https://ratson.github.io/cordova-plugin-admob-free/identifiers.html)

## Acknowledgments

* This demo is built on top of this article [Integrating Google AdMob Advertisements in Ionic](https://www.joshmorony.com/integrating-google-admob-advertisements-in-ionic) by joshmorony. this guy has a great website that every mobile developer should see it:
https://www.joshmorony.com
* [ratson](https://github.com/ratson), the owner of this plugin [cordova-plugin-admob-free](https://github.com/ratson/cordova-plugin-admob-free)
