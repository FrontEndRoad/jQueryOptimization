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


#### ������classǰʹ��tag(��ǩ��)

``` html
<!-- ��jQuery�еڶ����ѡ������tag(��ǩ)ѡ����( ���磺$("head") )�� -->
<!-- ��IDѡ������ʱ����Ϊ������ԭ����getElementsByTagName() ������-->
<!-- �������ղ��Ƕ�HTML���룺-->

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
//������Ҫѡ�� ���� ��ѡ��
//��ô����ʹ��һ��tag name������(����)class ��������ʾ��
var active_light = $("input.on");

//��ȻҲ���Խ�� �ͽ���ID��������ʾ��
var active_light = $("#traffic_light input.on");

//��ʹ��tag������class��ʱ��������Ҫע�����¼��㣺
//��1�� ��Ҫʹ��tag������ID��������ʾ��
  var content = $("div#content");
  
//����һ����ѡ�������ȱ������е�divԪ�أ�Ȼ��ƥ��#content��
//������jQuery��1.3.1��ʼ�ı���ѡ�������ĺ󣬲�������������ˡ���ʱ�޷���֤����

//��2����Ҫ���������ʹ��ID������ID��������ʾ��
  var traffic_light = $("#content #traffic_light");
 
//ע�����ʹ������ѡ������Ҳ�뾡��ʹ��tag�����Σ�������ʾ��
$('p[row="c3221"]').html();������������$('[row="c3221"]').html();

//�ر���ʾ��
//tag.class �ķ�ʽ ��IE�µ�����  ���� .class ��ʽ��
//����Firefox��  ȴ���� ֱ�� .class��ʽ��
//Google����������ֶ���ࡣ
//��ҳ������300��Ԫ�أ����ǵ����ܲ�඼��50�������ڡ�
```


#### ������jQuery���󻺴�����

``` javascript
//��jQuery���󻺴����� ����Ҫ�������� Ҫ���ɽ�jQuery���󻺴��������ϰ�ߡ�
//������һ��jQuery����д��һ�δ��룺
$("#traffic_light input.on").bind("click", function(){ ... }); 
$("#traffic_light input.on").css("border", "1px dashed yellow"); 
$("#traffic_light input.on").css("background-color", "orange"); 
$("#traffic_light input.on").fadeIn("slow");

//���мǲ�Ҫ��ô��������Ӧ���Ƚ����󻺴��һ������Ȼ���ٲ�����������ʾ��
var $active_light = $("#traffic_light input.on"); 
$active_light.bind("click", function(){ ... }); 
$active_light.css("border", "1px dashed yellow");
$active_light.css("background-color", "orange"); 
$active_light.fadeIn("slow");

//��ס����Զ��Ҫ����ͬ��ѡ��������Ĵ�������ֶ��.

//ע����1��Ϊ��������ͨ��JavaScript�����jQuery���󣬿����ڱ�������ĸǰ���� $ ���š�
//��2������������ʹ��jQuery����ʽ�������Ը��ơ�������ʾ��
var $active_light = $("#traffic_light input.on");
$active_light.bind("click", function(){ ... }) 
                    .css("border", "1px dashed yellow") 
                    .css("background-color", "orange")
                    .fadeIn("slow");  

//��������������������ʹ��jQuery������ô���������ǻ��浽ȫ�ֻ����С����´�����ʾ��
// ��ȫ�ַ�Χ����һ������ (����: window����)
window.$my = { 
    head : $("head"), 
    traffic_light : $("#traffic_light"), 
    traffic_button : $("#traffic_button")
};

function do_something(){ 
    // ������������ô洢�Ľ������������
    var script = document.createElement("script");
    $my.head.append(script);
    
    // �����ں����ڲ�������, ���Լ�������ѯ����ȫ�ֶ�����ȥ. 
    $my.cool_results = $("#some_ul li");
    $my.other_results = $("#some_table td");
    
     // ��ȫ�ֺ�����Ϊһ����ͨ��jquery����ȥʹ��.
    $my.other_results.css("border-color", "red");
    $my.traffic_light.css("border-color", "green");
} 

//��Ҳ���������������� ʹ���� 

```


#### �ġ���ֱ�ӵ�DOM������������

``` javascript
//����Ļ���˼�������ڴ��н�����ȷʵ��Ҫ�Ķ�����Ȼ�����DOM ��
//�Ⲣ����һ��jQuery���ʵ���������������Ч��JavaScript���� ��ֱ�ӵ�DOM�����ٶȺ�����
//���磬���붯̬�Ĵ���һ���б�Ԫ�أ�ǧ��Ҫ������,������ʾ��
var top_100_list = [...], // ����������100����һ�޶����ַ��� 
$mylist = $("#mylist"); // jQuery ѡ�� <ul> Ԫ��
for (var i=0, l=top_100_list.length; i<l; i++){ 
  $mylist.append("<li>" + top_100_list[i] + "</li>");
}

//����Ӧ�ý�����Ԫ���ַ����ڲ����dom��֮ǰ��ȫ�������ã�������ʾ��
var top_100_list = [...],$mylist = $("#mylist"), top_100_li = ""; // ��������������洢���ǵ��б�Ԫ�� 
for (var i=0, l=top_100_list.length; i<l; i++){ 
   top_100_li += "<li>" + top_100_list[i] + "</li>";
} 
$mylist.html(top_100_li);

//ע���ǵ���ǰ������һ����д�������Ĵ��룺
for (i = 0; i < 1000; i++) { 
    var $myList = $('#myList'); 
    $myList.append('This is list item ' + i); 
} 

//�Ǻǣ���Ӧ���Ѿ��������������ˡ���Ȼ��#mylistѭ����ȡ��1000�Σ�����
```


#### �塢ð��

``` javascript
//���������������, ����ÿһ��js�¼�(����:click, mouseover��.)����ð�ݵ������ڵ㡣��������Ҫ�����Ԫ�ص���ͬ������ʱ��������á���������Ч�ʺܲ�Ķ�Ԫ���¼������ķ�������, ��ֻ�������ǵĸ��ڵ��һ�Ρ�����, ����ҪΪһ��ӵ�кܶ������ı�����������Ϊ: �������ѡ��ʱΪ�����һ��class����ͳ�������ǣ�ֱ��ѡ��input��Ȼ���focus�ȣ�������ʾ��
$("#entryform input").bind("focus", function(){ 
    $(this).addClass("selected");
}).bind("blur", function(){ 
    $(this).removeClass("selected");
});

//��Ȼ��������ܰ����������Ӧ�����񣬵������ҪѰ�����Ч�ķ�������ʹ�����´��룺
$("#entryform").bind("focus", function(e){ 
    var $cell = $(e.target); // e.target ��׽��������Ŀ��Ԫ�� 
    $cell.addClass("selected"); 
}).bind("blur", function(e){ 
    var $cell = $(e.target);
    $cell.removeClass("selected");
});

//ͨ���ڸ���������ȡ�����ʧȥ������¼�����Ŀ��Ԫ�ؽ��в���������������У�����Ԫ�ذ�����һ������Ա�Ľ�ɫ, �����Ի���Ŀ��Ԫ�ذ��¼�������㷢������ܶ�Ԫ�ذ���ͬһ���¼�����, ��ô���ڵ���϶�֪�����������ˡ�ͬ����Table����ʱ������Ҳ����ʹ�����ַ�ʽ���ԸĽ����룺��ͨ�ķ�ʽ��
$('#myTable td').click(function(){ 
    $(this).css('background', 'red'); 
}); 

//�Ľ���ʽ�� 
$('#myTable').click(function(e) {
     var $clicked = $(e.target); 
     $clicked.css('background', 'red'); 
}); 

//������100��td����ʹ����ͨ�ķ�ʽ��ʱ�������100���¼����ڸĽ���ʽ�У���ֻΪһ��Ԫ�ذ���1���¼���������100���¼���Ч�ʸߣ�����1���¼���Ч�ʸߣ�������Ҳ�����зֱ��ˡ�
```


#### �����Ƴٵ� $(window).load

``` javascript
//jQuery���ڿ�������˵��һ�������˵Ķ���, ���԰��κζ����ҵ�$(document).ready�¡�����$(document).ready ȷʵ�����ã� ��������ҳ����Ⱦʱ������Ԫ�ػ�û������ɾ�ִ�С�����㷢�����ҳ��һֱ�������е�״̬�����п��ܾ���$(document).ready��������ġ�����ͨ����jQuery�����󶨵�$(window).load �¼��ķ���������ҳ������ʱ��cpuʹ���ʡ����������е�html(����<iframe>)��������ɺ�ִ�С�
$(window).load(function(){
    // ҳ����ȫ�����ų�ʼ����jQuery����. 
});

//һЩ��Ч�Ĺ��ܣ������Ϸ�, �Ӿ���Ч�Ͷ���, Ԥ��������ͼ��ȵȣ������ʺ����ּ����ĳ��ϡ�
```


#### �ߡ�ѹ��JavaScript

ѹ������С�����JavaScript�ļ��� 
����ѹ����ַ: http://dean.edwards.name/packer/
ѹ��֮ǰ���뱣֤��Ĵ���Ĺ淶�ԣ��������ʧ�ܣ�����Js����


#### �ˡ�����ʹ��ID����Class

``` javascript
//ǰ�������Ż��Ѿ�˵����IDѡ�������ٶ������ġ�������HTML�����У���ʹ��ID�ľ���ʹ��ID������class���������һ�����ӣ�
// ����һ��list
var $myList = $('#myList'); 
var myListItems = '<ul>'; 
for (i = 0; i < 1000; i++) {
     myListItems += '<li class="listItem' + i + '">This is a list item</li>'; //����ʹ�õ���class
 } 
myListItems += '</ul>'; 
$myList.html(myListItems); 

// ѡ��ÿһ�� li
 for (i = 0; i < 1000; i++) { 
    var selectedItem = $('.listItem' + i); 
} 

//�ڴ������ѡ��ÿ��li�Ĺ����У��ܹ�����5066���룬����5���ˡ�����������һ���Աȣ���ID����class��
 

// ����һ��list
var $myList = $('#myList'); 
var myListItems = '<ul>'; 
for (i = 0; i < 1000; i++) { 
    myListItems += '<li id="listItem' + i + '">This is a list item</li>'; //����ʹ�õ���id 
} 
myListItems += '</ul>'; 
$myList.html(myListItems);
// ѡ��ÿһ�� li 
for (i = 0; i < 1000; i++) {
     var selectedItem = $('#listItem' + i); 
} 

//���϶δ����У�ѡ��ÿ��li�ܹ�ֻ����61���룬���class�ķ�ʽ����������100����
```


#### �š���ѡ����һ��������

``` javascript
//jQueryѡ��������һ��������ѡ����������ָ�������ġ�
//jQuery( expression, context );

//ͨ����������Сѡ������DOM�������ķ�Χ���ﵽ��ʡʱ�䣬���Ч�ʡ�
//��ͨ��ʽ��
$('.myDiv')
//�Ľ���ʽ��
$('.myDiv' , $("#listItem") )
```


#### ʮ������ .live()������Ӧ��˵������Ҫʹ�ã�

����jQuery1.3.1�汾֮�����ӵķ�������������Ĺ��ܾ���Ϊ ������DOMԪ�� ��̬���¼���
������Ч����˵����������Ƚ�ռ����Դ�������뾡����Ҫʹ������
��������ôһ�δ���:

``` javascript
$(function(){
 $("p").click(function(){
     alert( $(this).text() );
 }); 
$("button").click(function(){ 
    $("<p>this is second p</p>").appendTo("body"); 
});
})
```

``` html
<body>
<p>this is first p</p> <button>add</button>
</body>
```

���к���ᷢ�� ���� �� pԪ�أ���û�ñ���click�¼�������Ըĳ�.live("click")��ʽ��������⣬�������£�
$(function(){ 
$("p").live("click",function(){ //�ĳ�live��ʽ
     alert( $(this).text() );
 }); 
$("button").click(function(){ $("<p>this is second p</p>").appendTo("body"); });})
���Ҳ�����������ô������������һ�ַ�ʽȥ���������⣬�������£�

``` javascript
$(function(){ 
$("p").click(function(){ 
    alert( $(this).text() ); 
}); 
$("button").click(function(){ 
    $("<p>this is second p</p>").click(function(){  //Ϊ������Ԫ�����°�һ��
            alert( $(this).text() ); 
    }).appendTo("body"); 
});
})
```
��Ȼ�ҰѰ��¼�����д��һ�Σ�������˵㣬�����ַ�ʽ��Ч�����Ը���live()��ʽ���ر�����Ƶ����DOM�����У����ǳ����ԡ�



#### ʮһ����ѡ�����ͺ��ѡ����

���ѡ���������õ������磺$("#list  p");
���ѡ������ȡ����Ԫ���ڲ�����Ԫ�ء�

����ʱ��ʵ��ֻҪ��ȡ ��Ԫ�أ���ô�Ͳ�Ӧ��ʹ�ú��ѡ������
Ӧ��ʹ����ѡ�������������£�
$("#list > p");



#### ʮ����ʹ��data()�����洢��ʱ����

������һ�ηǳ��򵥵Ĵ��룬

``` javascript
$(function(){
    var flag = false;
    $("button").click(function(){ 
        if(flag){
            $("p").text("true");
            flag=false;
        }else{
            $("p").text("false");
            flag=true;
        } 
    });
})

```

����data()��ʽ�󣬴������£�

``` javascript
$(function(){ 

    $("button").click(function(){ 

        if( $("p").data("flag") ){ 

            $("p").text("true"); 

            $("p").data("flag",false); 

        }else{

             $("p").text("false");

             $("p").data("flag",true); 

        } 

    }); 

})
```
