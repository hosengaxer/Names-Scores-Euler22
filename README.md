# Names-Scores-Euler22
Modified version of the Euler problem #22

## Problem:
Nimm die ersten 50 Namen in ein neues Array. Sortiere das Array und gib es aus. Verschlüssle jeden Namen mit einer Rotationsverschlüssleung indem du die Verschiebung im Form eingibst. 

## My Solution:
```js
const array = ["MARY","PATRICIA","LINDA","BARBARA","ELIZABETH","JENNIFER","MARIA","SUSAN","MARGARET","DOROTHY","LISA","NANCY","KAREN","BETTY","HELEN","SANDRA","DONNA","CAROL","RUTH","SHARON","MICHELLE","LAURA","SARAH","KIMBERLY","DEBORAH","JESSICA","SHIRLEY","CYNTHIA","ANGELA","MELISSA","BRENDA","AMY","ANNA","REBECCA","VIRGINIA","KATHLEEN","PAMELA","MARTHA","DEBRA","AMANDA","STEPHANIE","CAROLYN","CHRISTINE","MARIE","JANET","CATHERINE","FRANCES","ANN","JOYCE","DIANE","ALICE","JULIE","HEATHER","TERESA","DORIS","GLORIA","EVELYN","JEAN","CHERYL","MILDRED","KATHERINE","JOAN","ASHLEY","JUDITH","ROSE","JANICE","KELLY","NICOLE","JUDY","CHRISTINA","KATHY","THERESA","BEVERLY","DENISE","TAMMY","IRENE","JANE","LORI","RACHEL"];
const lett = "abcdefghijklmnopqrstuvwxyz".toUpperCase();
const changedArray = [""];
    
document.getElementById("txt").value += "Unsorted: \n" + array;
array.sort();
document.getElementById("txt").value += "\n\nSorted: \n" + array;

for ( var i = 0; i < array.length; i++ ){
    console.log(array[i]);
    console.log(getNextChar(array[i]));
    changedArray.push(getNextChar(array[i]));
    console.log(" ");
    
}

let oupt = "\n\nGeänderter Array ( Jeder buchstabe um drei mehr ) :\n";
for ( var i = 1; i < changedArray.length; i++ ){
    oupt += changedArray[i] +", ";
}
document.getElementById("txt").value += oupt;

function getNextChar(name){
    const length = name.length;
    let finalName = "";
    for ( var i = 0; i < length; i++ ){
        if ( name.charAt(i) == 'Z' ){
            name.charAt(i) == 'A';
            finalName += String.fromCharCode(name.charCodeAt(i) + 2);
        } else if ( name.charAt(i) == 'Y' ){
            name.charAt(i) == 'A';
            finalName += String.fromCharCode(name.charCodeAt(i) + 1);
        } else if ( name.charAt(i) == 'X' ){
            finalName += 'A';
        } else {
            finalName += String.fromCharCode(name.charCodeAt(i) + 3);
        }
    }
    
    return finalName;
    
}


```
