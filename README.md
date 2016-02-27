# hci-homework
homework</br>
使用说明
</br>
pc端应用步骤：</br>
<1>font-face声明字体
@font-face {font-family: 'iconfont';
    src: url('iconfont.eot'); /* IE9*/
    src: url('iconfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
    url('iconfont.woff') format('woff'), /* chrome、firefox */
    url('iconfont.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/
    url('iconfont.svg#iconfont') format('svg'); /* iOS 4.1- */
}
</br>
<2>定义使用iconfont的样式
.iconfont{font-family:"iconfont";
font-size:16px;font-style:normal;}
</br>
<3>挑选相应图标并获取字体编码，应用于页面
<i class="iconfont">&#33</i>
</br>
在Android中使用iconfont
</br>
第一步：复制字体文件到项目 assets 目录；
</br>
第二步：打开 iconfont 目录中的 demo.html，找到图标相对应的 HTML 实体字符码；
</br>
第三步：打开 res/values/strings.xml，添加 string 值；
</br>
<string name="icons">&#x3605; &#x35ad; &#x35ae; &#x35af;</string>
</br>
第四步：打开 activity_main.xml，添加 string 值到 TextView：
</br>
<TextView
    android:id="@+id/like"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/icons" />
</br>    
第五步：为 TextView 指定文字：
</br>
import android.graphics.Typeface;
 
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
 
    Typeface iconfont = Typeface.createFromAsset(getAssets(), "iconfont/iconfont.ttf");
    TextView textview = (TextView)findViewById(R.id.like);
    textview.setTypeface(iconfont);
}
