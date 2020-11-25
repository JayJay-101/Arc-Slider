# Arc-Slider
Simple Arc Slider for recyclerview!  added double carousel effect

## usage
add library in gradle

```
build.gradle(project)
.......................
allprojects {
    repositories {
        google()
        jcenter()
        maven { url 'https://jitpack.io' }..
build.gradle(:app)
...................
dependencies {
    implementation 'com.github.JayJay-101:Arc-Slider:v1.0'
    implementation 'androidx.recyclerview:recyclerview:1.1.0'...
```        
make object of ArcSlider
```
       ArcSlider (context,              // provide a context
                  Gravity.START,        // from which direction should the list items orbit? 
                  Orientation.VERTICAL, // Is this a vertical or horizontal scroll?
                  radius,               // The radius of the item rotation
                  peek,                 // Extra offset distance
                  shouldRotate);        // should list items angle towards the center? true/false.
```
```
Gravity.START
Orientation.VERTICAL

┏─────────┓
┃ x       ┃
┃  x      ┃
┃   X     ┃
┃   X     ┃
┃   X     ┃
┃  x      ┃
┃ x       ┃
┗─────────┛

Gravity.END
Orientation.VERTICAL
┏─────────┓
┃       x ┃
┃      x  ┃
┃     X   ┃
┃     X   ┃
┃     X   ┃
┃      x  ┃
┃       x ┃
┗─────────┛
     

Gravity.START
Orientation.HORIZONTAL
┏───────────┓
┃x         x┃
┃ x       x ┃
┃   X X X   ┃
┃           ┃
┃           ┃
┃           ┃
┃           ┃
┗───────────┛

Gravity.END
Orientation.HORIZONTAL
┏──────────┓
┃          ┃
┃          ┃
┃          ┃
┃          ┃
┃   X X X  ┃
┃ x      x ┃
┃x        x┃
┗──────────┛

```
example
```java
 ArcSlider recycler_view = new ArcSlider(this, ArcSlider.Gravity.START, ArcSlider.Orientation.HORIZONTAL, 920, 500, false);
        SnapHelper snap = new LinearSnapHelper();
        snap.attachToRecyclerView(recyclerViewHorizontal);
        recyclerViewHorizontal.setLayoutManager(recycler_view);
        recyclerViewHorizontal.setAdapter(new HorizontalAdapter(categories, //some  data for adapter
                                                                R.layout.recyclerview_horizontal, 
                                                                Activity_Name.this));
``` 
