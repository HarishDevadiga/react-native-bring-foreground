
# react-native-bring-foreground (https://www.npmjs.com/package/react-native-bring-foreground)

this is a react-native library for launching the application when the application is in the background . 

## Getting started

`$ npm install react-native-bring-foreground --save`

### Mostly automatic installation

`$ react-native link react-native-bring-foreground`

### Manual installation


#### iOS

Not Available

#### Android

1. Open up `android/app/src/main/java/[...]/MainApplication.java`
  - Add `import com.reactlibrary.LaunchApplicationPackage;` to the imports at the top of the file
  - Add `new LaunchApplicationPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-bring-foreground'
  	project(':react-native-bring-foreground').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-bring-foreground/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-bring-foreground')
  	```


## Usage


```javascript
import LaunchApplication from 'react-native-bring-foreground';
import type {RemoteMessage} from 'react-native-firebase';


//PackageName Must Be String For example "com.domain.application"
export default async (message: RemoteMessage) => {
    LaunchApplication.open(PackageName);
}


