### jQuery性能优化指南

#### 一、总是从ID选择器开始继承
 ``` html
     <!-- 在jQuery中最快的选择器是ID选择器，因为它直接来自于JavaScript的getElementById()方法。-->
     <!-- 例如有一段HTML代码： -->
     
     <div id="content">
     <form method="post" action="#"> 
     <h2>交通信号灯</h2> 
     <ul id="traffic_light"> 
     <li><input type="radio" class="on" name="light" value="red" /> 红色</li> 
     <li><input type="radio" class="off" name="light" value="yellow" /> 黄色</li> 
     <li><input type="radio" class="off" name="light" value="green" /> 绿色</li> 
     </ul> 
     <input class="button" id="traffic_button" type="submit" value="Go" /> 
     </form>
     </div>
```

``` javascript
     //如果采用下面的选择器，那么效率是低效的。
     var traffic_button = $("#content .button");
     
     //因为button已经有ID了，我们可以直接使用ID选择器。如下所示：
     var traffic_button = $("#traffic_button");
     
     //当然 这只是对于单一的元素来讲。如果你需要选择多个元素，这必然会涉及到 DOM遍历和循环，
     //为了提高性能，建议从最近的ID开始继承。
     //如下所示：
     var traffic_lights = $("#traffic_light input");
```