###  Ex.05 Design a Website for Server Side Processing

### AIM:

To design a website to perform mathematical calculations in server side.

### DESIGN STEPS:

### Step 1:

Clone the repository from GitHub.

### Step 2:

Create Django Admin project.

### Step 3:

Create a New App under the Django Admin project.

### Step 4:

Create python programs for views and urls to perform server side processing.

### Step 5:

Create a HTML file to implement form based input and output.

### Step 6:

Publish the website in the given URL.

## PROGRAM :
```
math.html
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Area of Rectangle</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body 
{
background-color:aqua;
}
.edge {
width: 1250px;
margin-left: auto;
margin-right: auto;
padding-top: 240px;
padding-left: 100px;
}
.box {
display:block;
border: Thick dashed lime;
width: 500px;
min-height:350px;
font-size:20px;
background-color:yellow;
}
.formelt{
color:red;
text-align: center;
margin-top: 6px;
margin-bottom: 6px;
}
h1
{
color:brown;
text-align: center;
padding-top: 16px;
}
</style>
</head>
<body>
<div class="edge">
<div class="box">
<h1>Area of a Triangle</h1>
<form method="POST">
{% csrf_token %}
<div class="formelt">
Height : <input type="text" name="height" value="{{h}}"></input>(in m)<br/>
</div>
<div class="formelt">
Base : <input type="text" name="base" value="{{b}}"></input>(in m)<br/>
</div>
<div class="formelt">
<input type="submit" value="Calculate"></input><br/>
</div>
<div class="formelt">
Area : <input type="text" name="area" value="{{area}}"></input>m<sup>2</sup><br/>
</div>
</form>
</div>
</div>
</body>
</html>

views.py
from django.shortcuts import render
def trianglearea(request):
    context={}
    context['area'] = "0"
    context['h'] = "0"
    context['b'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        h = request.POST.get('height','0')
        b = request.POST.get('base','0')
        print('request=',request)
        print('Height=',g)
        print('Base=',s)
        area = (int(h) * int(b))/2
        context['area'] = area
        context['a'] = a
        context['b'] = b
        print('Area=',area)
    return render(request,'myapp/math.html',context)

urls.py
from django.contrib import admin
from django.urls import path
from myapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaoftriangle/',views.trianglearea,name="area of triangle"),
    path('',views.triangle area,name="area of triangle root")
]
```

### SERVER SIDE PROCESSING:

![image](https://github.com/Anandanaruvi/mathserver/assets/120443233/f4de7d6c-14c7-4e71-9f41-c5cbcd266790)

### HOME PAGE:

![image](https://github.com/Anandanaruvi/mathserver/assets/120443233/8145737f-c675-488e-ab05-ec8acabfe68d)

### RESULT:

The program for performing server side processing is completed successfully.
