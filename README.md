### jQuery�����Ż�ָ��

#### һ�����Ǵ�IDѡ������ʼ�̳�
 ``` html
     <!-- ��jQuery������ѡ������IDѡ��������Ϊ��ֱ��������JavaScript��getElementById()������-->
     <!-- ������һ��HTML���룺 -->
     
     <div id="content">
     <form method="post" action="#"> 
     <h2>��ͨ�źŵ�</h2> 
     <ul id="traffic_light"> 
     <li><input type="radio" class="on" name="light" value="red" /> ��ɫ</li> 
     <li><input type="radio" class="off" name="light" value="yellow" /> ��ɫ</li> 
     <li><input type="radio" class="off" name="light" value="green" /> ��ɫ</li> 
     </ul> 
     <input class="button" id="traffic_button" type="submit" value="Go" /> 
     </form>
     </div>
```

``` javascript
     //������������ѡ��������ôЧ���ǵ�Ч�ġ�
     var traffic_button = $("#content .button");
     
     //��Ϊbutton�Ѿ���ID�ˣ����ǿ���ֱ��ʹ��IDѡ������������ʾ��
     var traffic_button = $("#traffic_button");
     
     //��Ȼ ��ֻ�Ƕ��ڵ�һ��Ԫ���������������Ҫѡ����Ԫ�أ����Ȼ���漰�� DOM������ѭ����
     //Ϊ��������ܣ�����������ID��ʼ�̳С�
     //������ʾ��
     var traffic_lights = $("#traffic_light input");
```