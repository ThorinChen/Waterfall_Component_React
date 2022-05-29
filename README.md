# Waterfall_Component_React
 Waterfall component for mobile and App terminal Based on React

 
 IOS App Preview
 ========

![iOS](./preview/ios.gif)

 Android App Preview
 =========


![Android](./preview/android.gif)



### Getting started
#### 1.install
```
$ npm i react-native-waterfall-layout --save
```
#### 2.import
```
import Waterfall from 'react-native-waterfall-layout';
```

#### Properties  
|    Prop       |      Default   |  Type        |  Description             |
|:-----------------:|:--------------:|:-----------------:|:------------------------------:|
|    columns      |        2       |  Number      |  Number of columns of waterfall              |
|    space        |       10       |  Number      |  Interval between columns of waterfall        |
|    renderIte    |      null      |  Function    |  Used to customize the contents of each item in the waterfall  |
|keyExtractor   |  null             |  Function       |   Generate a non duplicate key for the given item. If this function is not specified, item is extracted by default Key as the key value. If item If the key does not exist, the array index is used|
|refresh         |    true      |         Boolean   |      Enable pull-down refresh|
|refreshing      |  (done) =>{}   | Function   |     Pull down refresh triggers this function and receives a done function to end the refresh|
|refreshConf     |                 |      Object | Drop down refresh parameters|
|infinite       |       true          |      Boolean  |      Enable rollover|
|infiniting   |       (done) => {}  |  Function    |    Scroll to the bottom of the list to trigger the function|
|hasMore    |       true          |     Boolean     |   Set to false to scroll to the bottom of the list without triggering infiniting|
|renderInfinite      |              |     Function  |     It is used to customize rolling load components and styles, and receive a loading to determine whether loading is in progress|



### Methods
##### addItems

Add items to the waterfall flow. The height of items is automatically calculated. Add items to the shortest column, so items will be rendered in turn
```
this.refs.waterfall.addItems([

    {name: 'Item1'}, 

    {name: 'Item2'}

])
```
##### addItemWithHeight

When you add items to the waterfall flow component, the height of the item will also be determined automatically. However, you need to add a height attribute to the data of each item object. This attribute is not the actual height of the item after rendering, but is used as the algorithm reference value of the item allocation column. Unlike additems, it is batch rendered
```
this.refs.waterfall.addItemsWithHeight([

      {name:"Item1", height: 210 },

      {name:"Item2", height: 150 }

]);
```
##### clear

Clear all items in the waterfall flow
```
this.refs.waterfall.clear();
```


#### Example
 **Demo source：[click](https://github.com/ThorinChen/Waterfall_Component_React/example/index.js)**
