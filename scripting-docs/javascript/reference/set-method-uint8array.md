---
title: "set Method (Uint8Array) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 6b0b48d5-e419-4c3c-98ed-d94cbe56e95d
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# set Method (Uint8Array)
Sets a value or an array of values.  
  
## Syntax  
  
```JavaScript  
uint8Array.set(index, value);  
uint8Array.set(array, offset);  
  
```  
  
## Parameters  
 `index`  
 The index of the location to set.  
  
 `value`  
 The value to set.  
  
 `array`  
 A typed or untyped array of values to set.  
  
 `offset`  
 The index in the current array at which the values are to be written.  
  
## Remarks  
 If the input array is a TypedArray, the two arrays may use the same underlying ArrayBuffer. In this situation, setting the values takes place as if all the data is first copied into a temporary buffer that does not overlap either of the arrays, and then the data from the temporary buffer is copied into the current array.  
  
 If the offset plus the length of the given array is out of range for the current TypedArray, an exception is raised.  
  
## Example  
 The following example shows how to set the first element of the array.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Uint8Array(buffer.byteLength);  
            intArr.set(0, 9);  
        }  
    }  
  
```  
  
## Requirements  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]