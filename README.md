# HongYan-homework
HongYan-homework

    <!DOCTYPE html>
    <html lang="en"  >  
    <head>  
        <meta http-equiv="Content-Type" content="text/html;charset=UTF-8"/>  
        <title>ajax</title>  
        
        <script type="text/javascript">  
            function getWeather(){  
                    var xhr = new XMLHttpRequest();  
                    var s = "";  
                    xhr.onreadystatechange = function(){  
                        if(xhr.readyState==4){  
                            alert(xhr.responseText);  
                        }  
                        document.getElementById("weather").innerHTML = s;  
                    }  
                     xhr.open('get','http://123.207.89.151/jrtt/forecast');  
  
                    xhr.send(null); 
                    return false;  
        }  
        </script>  

        
    </head>  
    <body>  
        <script type="text/javascript">
            function onClick(ooj){
                ooj.style.background = "blue";
                ooj.style.left = "500px";       
            }  
        </script>

        <h2>获取天气信息</h2>  
        <input type="submit" value="获取天气" onclick="getWeather()"></input>  
        <div id="weather"></div>  
        <hr/>  
        <iframe width="420" scrolling="no" height="60" frameborder="0" allowtransparency="true" src="http://i.tianqi.com/index.php?c=code&id=12&icon=1&num=5"></iframe>  

        <div style="width:500px;height:300px;border:2px solid #ccc; background: red; position:absolute; left: 10px;top:300px;" id="div">
            
        </div>

        <script type="text/javascript">
            var px;
            var py;
            var div = document.getElementById("div");
            div.onmousedown = function(e){
                if(!e) e = window.event;
                px = e.clientX - parseInt(div.style.left);
                py = e.clientY - parseInt(div.style.top);
                div.onmousemove = mousemove;
            }
            div.onmouseup = function()
            {
                div.onmousemove = null;
            }
            function mousemove(em){
                if(!em) em = window.event;
                div.style.left = (em.clientX-px)+'px';
                div.style.top = (em.clientY-py)+'px';
            }

        </script>
    </body>     
    </html>  
