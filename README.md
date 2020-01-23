# CQL_web_map
Using CQL For Web_map
# openlayer_wms_map
A wms map created using  Openlayers and Geoserver
# Motive
The main motive of this program was to make the program as readable, easy and short as possible.
# requirements
# Geoserver
* download geoserver (you may download it any way you like), from the official link or from this [link](https://drive.google.com/file/d/1PkcyuIdH2vNFGb9rx1GofMHTDDhvzOx_/view?usp=sharing)(this is the custom setup made by me.
* Than, when you will install leave the default settings as it is. 
![s](https://github.com/pranayteaches/openlayer_wms_map/blob/master/process/Installation.PNG)
* after the installation go to the search bar of your operating system and search for "start geoserver"., if it is there click on it and your server will be started. Else, try reinstalling itand repeat the process mentioned.
* open your browser and type http://localhost:8080/geoserver/web/ a webportal of geo server will apear.
* Just login using    username:- admin     password:- geoserver
* a welcome screen of geoserver will open.
![asd](https://github.com/pranayteaches/openlayer_wms_map/blob/master/process/login.PNG)
* click on the "workspace" in the left corner and "add a new workspace" by giving it a name and any url(not needs to be real). fr ex: pranay
* after creating click on the "stores" above the "workspace" in the data panel(left side). and add a new shape file(first option).
![a](https://github.com/pranayteaches/openlayer_wms_map/blob/master/process/3.jpg)
* download any shape file like a file. For ex. indian states.
* in "stores" in the workspace choose the workspace you created.
* below give any name to it, you may leave the description empty.
* at last browse the directry of shapefiles, for ex ``` D:\india```, and than click on save.
* after click on the "layers" above "stores". than add new layer. than choose the name of shapefile you uploaded in add layers from.
![ds](https://github.com/pranayteaches/openlayer_wms_map/blob/master/process/stores.PNG)
* than click on publish.
* first of all give a name to your layer and than title, leave the other things as it is and than scroll down to "Bounding Boxes".
* After that you just need to click on "compute from data", for the "native bounding box" and than below for "lat/long bounding box", click on "compute from native bounds".
![asd](https://github.com/pranayteaches/openlayer_wms_map/blob/master/process/layers.PNG)
* than click on save, congratulations your WMS layer has been created.
# Open Layers
* download node.js and install openlayers by:-
``` npm intall ol ```
* download any ide (vs code) (personal prefrence).
* install VsCode plugins
* create a new html file.
* and just copy and paste the code I mentioned.
* congratulations you are all set.
# How to use the code?
* First you have to start your geoserver.
* Then you may just open the html file in the chrome or start it using VsCode.
* If you wnat to use it directly just copy and paste the link below.
 http://localhost:8080/geoserver/wms/reflect?format=application/openlayers&layers=pranay:IND_pj&CQL_FILTER=NAME_1+IN+(%27Uttaranchal%27)
# Why use my code?
As, it is very simple and updated, and also very small, which saves time.
# How is it so Small while other codes of same are verybig?
First of all every things not worked for me right, it took me 2 days to research about open layers and geoserver but nothing works for me. Then suddenly when I was just reading Geoserver's 2.17.x documentation I came to know about a new feature." WMS Reflector".
# WMS Reflector
What WMS reflector do is it creates an open layer's layer or just make its image file.
WMS reflector has a great advantage in some occasions., as Standard WMS requests can be quite long and verbose. Typing into a browser, or HTML editor, can be quite cumbersome and error prone. The WMS Reflector solves this problem nicely by using good default values for the options that you do not specify.
For instance the following, which returns an OpenLayers application with an 800x600 image set to display the feature for ```
Russia:Asia_Russia ```
```
<!DOCTYPE html>
<html lang="en">
    <a href="http://localhost:8080/geoserver/wms/reflect?format=application/openlayers&layers=pranay:IND_pj">
      <img src="http://localhost:8080/geoserver/wms/reflect?layers=pranay:IND_pj&width=400"/>
      </a>
 </html>
 ```
# Code Difference(WMS(Reflector) VS WMS(Standard)) 
Here I will just provide you the code with the same function but one with (WMS(Reflector)) and one with (WMS(Standard)) 
They Display the image set to display the feature for ``` pranay:IND_pj ```
(NOTE: Both code are made in a contribution to OSGeo)
### (REFRENCE: WMS(std) = WMS Standard, WMS(ref) = WMS Reflector)
### WMS Reflector 
WMS(ref) = (pros) small and simple code .With ease understand

WMS(ref) = (cons) as it is only used to preview, so only one layer can be shown i.e you may not show multiple layers and even base layer also can't be added
### WMS Standard
WMS(std) = (pros) you may add many layers and functionality

WMS(std) = (cons it is time consume and the code needs to be long and elongated

# Code Explaination
* First of all i described that it is a HTML file.
* ``` <p>Type the name of any Indian State</p> ``` Heading.
* in these lines 
``` <head>
   <form>
     <textarea id="name"></textarea>
     <input type="button" value="OK" onclick="myFunction();"></input>
   </form> 
```
*First we decribed a head file by ``` <head> ```
  Than we just described the ``` <form> ``` which contain the input i.e the state we want to look in.
 * Inside that we define ``` <textarea> ``` and its id this will check just temporarily stores the data we inputed.
 * at last we just define the input box and and the OK button, At lat we define the main function, this is one of the most important things in the code, so the ``` onclick="myFunction();" ``` describes what the program needs to do when the button is clicked. and than we ended the form
*  in these lines
* in the this line ``` <img src="http://localhost:8080/geoserver/wms/reflect?layers=pranay:IND_pj&width=400"/> ```
it just tells that we just have to take an image of the src(source code) which is the web link or the local server link.
```
<script>
function myFunction() {
  var input = document.getElementById("name").value;
  window.open("http://localhost:8080/geoserver/wms/reflect?format=application/openlayers&layers=pranay:IND_pj&CQL_FILTER=NAME_1+IN+(%27"+input+"%27)");
}
</script>
```
* At the beginning we describe that it's a script file i.e .js file
* ``` function myFunction(); ``` as we know that the button will return the value in the ``` myFunction(); ``` so we declare here that what will happen after we click the "OK" button
* ``` var input = document.getElementById("name").value; ``` here we are declare a variable "input" that will permanently store the value enter which is "name", which we have mentioned here, ``` <input type="button" value="OK" onclick="myFunction();"></input> ```
* in this line ``` <a href="http://localhost:8080/geoserver/wms/reflect?format=application/openlayers&layers=pranay:IND_pj&CQL_FILTER=NAME_1+IN+(%27"+input+"%27)" ```
* ``` <a href=""> ``` tells that it is a web link.
* ``` "http://localhost:8080/geoserver/wms/" ``` is the localserver address
* ``` reflect ``` returns it 
* ``` ?format=application/openlayers&layer ``` is to describe that it is openlayer based application format.
* ``` pranay:IND_pj ``` workspace and layer for diasplaying. Should be entered in following manner
                              ``` {workspace name}:{layer name"} ```
* ``` CQL_FILTER= ```now here the real work begins, this is the part where the CQL begins, we define that now the filter is going to be applied.
* ``` NAME_1+IN+ ``` here as my dbf file of the geoserver contains some parameters like NAME_1 which is the name of the state, so I just need to apply the filter to it, SO ``` NAME_1 ``` defines the parameter in which we need to apply the filter.
* here the ``` + ``` describes the space as when you edit it in the open layers we right it as ``` NAME_1 IN () ```
* ``` (%27"+input+"%27)" ``` this here is just adding the variable "input" containing the value entered by the user to mesh up in the URL and the ``` %27 ``` here stands for the quotes ``` ' ```as the open layers preview code for CQL is NAME_1 IN ('{any state}'), so we need to use the quotes also.
* Congrats you Geoserver layer can be opened in the open layer with CQL, in which the user will give input.
* just save the HTML file and open it(make sure your geoserver is not stopped)
* A image will appear of the shapefile you created and uploaded on Geoserver.
* click on it to view the "open layers view".
* You may also give a it a pre existing Height and width. by using {&, width, height)
for ex:- ```  <img src="http://localhost:8080/geoserver/wms/reflect?layers=pranay:IND_pj&width=400"height="169" width="400"/> ```
# Comparision
### Image Before Filter
![sa](https://github.com/pranayteaches/CQL_web_map/blob/master/CL_FILTER/Entering_state_name.PNG)

### Image after Filter
![ad](https://github.com/pranayteaches/CQL_web_map/blob/master/CL_FILTER/image.png)

Thank you, 
That's all for the tutorial
