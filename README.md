# RichLink-Preview
A Rich Link Preview Library for Android

[![Android Arsenal]( https://img.shields.io/badge/Android%20Arsenal-RichLinkPreview-green.svg?style=flat )]( https://android-arsenal.com/details/1/6702 )


> Sample Image
<img src="https://github.com/PonnamKarthik/RichLinkPreview/raw/master/screenshots/sample.png" width="300" alt="ScreenShot">

#### To implement existing layout using XML

Add below code in activity_main.xml

~~~xml
<io.github.ponnamkarthik.richlinkpreview.RichLinkView
    android:id="@+id/richLinkView"
    android:layout_width="match_parent"
    android:layout_height="wrap_content">
</io.github.ponnamkarthik.richlinkpreview.RichLinkView>
~~~

In your MainActivity.java add below code

~~~java
public class MainActivity extends AppCompatActivity {
    
    RichLinkView richLinkView; 
    
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        // ...
        // 
        richLinkView = (RichLinkView) findViewById(R.id.richLinkView);
        
        
        richLinkView.setLink("https://stackoverflow.com", new ViewListener() {
            
            @Override
            public void onSuccess(boolean status) {
                
            }
            
            @Override
            public void onError(Exception e) {
                
            }
        });
        
    }
}
~~~

> **OR**

#### If you want to implement your own layout.

~~~java
private MetaData data;

RichPreview richPreview = new RichPreview(new ResponseListener() {
    @Override
    public void onData(MetaData metaData) {
        data = metaData;
       
        //Implement your Layout
    }
    
    @Override
    public void onError(Exception e) {
        //handle error
    }
});
~~~

> MetaData

```java
metaData.getTitle();

metaData.getImageurl();

metaData.getDescription();

metaData.getSitename();

metaData.getUrl();

metaData.getMediatype();
```