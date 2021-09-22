# Read JSON file from js file
![img.png](img.png) <br>
# Coding
``` JavaScript
var obj;
fetch('名字.json') //Your JSON file name
    .then(response => response.json())
    .then(data => {
        obj = data; //Your JSON file data will save in 'obj'
        //Your function start
        //for example
        //compare data
        chrome.contextMenus.onClicked.addListener(function (params, tab) {
            for (var i = 0; i < obj.length; i++){
                if (obj[i].name == params.selectionText){
                    chrome.tabs.create({url: '网页' + obj[i].countryCode}); //if match, go website
                }
            }
        }); //Your function end
    }
    )
    .catch(error => console.log(error));
``` 