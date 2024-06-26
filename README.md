## Write an app that will read data from this library, process it and display the result.

`DataProviderApi` will provide you with series of data sets. Each data set is a list of `n` non-negative integers representing an elevation map where the width of each bar is `1`. You need to compute how water will be trapped in each terrain after raining, and display it on the screen. 

## App should consist of 3 screens:

### 1. Main

A list of all the processed data sets. Each element should consist of name (included in the data set) and time it took to compute the result (milliseconds to 5 decimal places). For example:
```
    | Warsaw            0.00342 |
    | Prague            0.00411 |
```
Clicking on the item will open a detail screen.

Also include a button to open playground screen. Clicking this button should first open dialog to input dimensions for playground grid, and after submiting this dialog playground screen should open with selected dimensions.

### 2. Details

Display the elevation map and trapped water. Use the size of the screen to display data in full, without any scrolling. The representation doesnt need to be graphically advanced and can be as simple as black and blue squares representing terrain and water respectively. For example:

<img width="457" alt="image" src="https://github.com/pepperoni-digiteq/DigiteqAssigmentDataProvider/assets/165902639/2b5b99f5-52bc-410d-ad8e-3bd7c4bf48ae">

### 3. Playground

Represents an input grid. Should be empty by default. User input elevation data by touching the screen in the place where elevation level should be (drawing the elevation map). Trapped water level should be computed and displayed in realtime. The result should look simular to details screen. 
Dimensions for the input grid shuold be specified by the user before opening this screen.

## Testing
In order to test your algorithmic solution use `assertAmount { ... }` tool from DataProvider library. **You must have a unit test in your project that passes this assertion.**
Create a GitHub Actions workflow that will run all unit tests automatically with visible logs (`-i`), each time pull request accurs and can be triggered manually.


## DataProvider library

DataProvider library is equipt with `koinDPModule` and `DaggerDPModule`, to retrieve `DataProviderApi` using `koin`, `Dagger2` or `Hilt` at your choosing. Its essential to use DI, because its the only way to receive all the necessary data in your app.

**To add DataProvider library to your project you need to:**

1. In your project level `build.gradle` or `settings.gradle`:
   ```
   repositories {
       mavenCentral()
       maven {
           url = uri("https://jitpack.io")
       }
   }
   ```

2. In your app level `build.gradle`:
   ```
   implementation("com.github.pepperoni-digiteq:DigiteqAssigmentDataProvider:1.5")
   ```
