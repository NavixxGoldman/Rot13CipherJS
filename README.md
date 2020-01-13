# Rot13CipherJS
One of the simplest and most widely known ciphers is a Caesar cipher, also known as a shift cipher. In a shift cipher the meanings of the letters are shifted by some set amount.  A common modern use is the ROT13 cipher, where the values of the letters are shifted by 13 places. Thus 'A' ↔ 'N', 'B' ↔ 'O' and so on.
```javascript
function rot13(str) { // LBH QVQ VG!
var rotArray=[];
  //Regex for non-aplhabetic character
  var regex=/[\W_]/g;
  //Place str in array
  var newArray=str.split("");
//Function CheckRot
 var checkRot=function(obj){
             if(obj>=65){
              obj+=13;
              if(obj>90){
                 return obj -=26;
              }
             return obj;
          }else if(obj>90){
              return obj -=26;
          }};
//loop

  for (var i=0; i<newArray.length;i++){
    //Pass non-alphabetic character
      if (!regex.test(newArray[i])){
        //Convert 
          var rot=String.charCodeAt(newArray[i]);   
          rot=checkRot(rot);
          rot=String.fromCharCode(rot);
          rotArray.push(rot);
      }else{
        rotArray.push(newArray[i]);
      }
      
  }

  return rotArray.join("");
}

// Change the inputs below to test
console.log(rot13("SERR PBQR PNZC"));
console.log(rot13("GUR DHVPX OEBJA SBK WHZCF BIRE GUR YNML QBT."));
```
