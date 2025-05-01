# Ex.05 Design a Website for Server Side Processing
## Date:01.05.2025

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

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
```python
<html>
    <head>
        <center>
            <h1>POWER CALCULATION</h1>
            <hr color="black">
        </center>
        <style>
            /* Styling the container with a border and centering it */
            .container {
                border: 3px solid black; /* Border around the content */
                padding: 20px; /* Add padding inside the box */
                width: 300px; /* Set width for the box */
                margin: 50px auto; /* Center the container horizontally and add margin from the top */
                background-color: white; /* Background color of the box */
                border-radius: 10px; /* Rounded corners (optional) */
                text-align: left; /* Ensure text inside the container is aligned left */
            }
            input {
                width: 100%; /* Make inputs take full width inside the box */
                padding: 8px; /* Padding inside input fields */
                margin-bottom: 10px; /* Space between input fields */
                border-radius: 5px; /* Rounded corners for inputs */
                border: 1px solid #ccc; /* Border for input fields */
            }
            button {
                background-color: green;
                color: white;
                padding: 10px;
                border: none;
                border-radius: 5px;
                width: 100%; /* Make button full width */
                cursor: pointer;
            }
            button:hover {
                background-color: darkgreen; /* Darker green on hover */
            }
        </style>
        <script>
            function cal() {
                var x = document.getElementById("t1").value;
                var y = document.getElementById("t2").value;
                document.getElementById("t3").value = x * x * y;
            }
        </script>
    </head>
    <body bgcolor="blue">
        <div class="container">
            <label for="intensity">Enter Intensity: </label>
            <input type="text" id="t1"><br><br>
            <label for="resistance">Enter Resistance: </label>
            <input type="text" id="t2"><br><br>
            <button onclick="cal();">Calculate</button><br><br>
            <label for="output">The Output:</label>
            <input type="text" id="t3" disabled><br><br>
        </div>
    </body>
</html>

##views.py

from django.shortcuts import render

def powerlamp(request):
    context={}
    context['Power'] = ""
    context['I'] = ""
    context['R'] = ""
    if request.method == 'POST':
        print("POST method is used")
        I = request.POST.get('Intensity','')
        R = request.POST.get('Resistence','')
        print('request=',request)
        print('Intensity=',I)
        print('Resistence=',R)
        Power = int(I) * int(I) * int(R)
        context['Power'] = Power
        context['I'] = I
        context['R'] = R
        print('Power=',Power)
    return render(request,'mathapp/math.html',context)

##urls.py

from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('PowerOfLampFilamentInAnIncandescentBulb/',views.powerlamp,name="PowerOfLampFilamentInAnIncandescentBulb"),
    path('',views.powerlamp,name="PowerOfLampFilamentInAnIncandescentBulb"),
]

```


## SERVER SIDE PROCESSING:
![WhatsApp Image 2025-05-01 at 13 30 21_f5b6e273](https://github.com/user-attachments/assets/6cc2ce83-202b-42d0-9859-43c4880be6cc)


## HOMEPAGE:
![alt text](<WhatsApp Image 2025-05-01 at 13.31.12_9ed534a9.jpg>)


## RESULT:
The program for performing server side processing is completed successfully.
