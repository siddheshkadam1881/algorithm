function addressBook() {

  var addressBookObjectArr = {};
  var key = -1;

  while(1) {
    var choice = parseInt(prompt("press 1 to add address || press 2 to delete \
                                  address || press 3 to show addresses || \
                                  press 4 to show addresses sort by phone \
                                  number || press 5 to edit address",""));
    switch(choice) {
      // add address
      case 1:
        var name = prompt("enter name","");
        var city = prompt("enter city","");
        var mobile = parseInt(prompt("enter mobile no",""));
        addressBookObjectArr["name"] = name;
        addressBookObjectArr["city"] = city;
        addressBookObjectArr["mobile"] = mobile;
        ++key;
        localStorage.setItem(key, JSON.stringify(addressBookObjectArr));
        break;

        // delete address
        case 2:
          var mobileNoToDeleteAddress = parseInt(prompt("enter mobile no to \
                                                         delete particular \
                                                         address",""));
          for(var i=0; i<=key; i++) {
            var tempObj = JSON.parse(localStorage.getItem(i));
            if(tempObj == null) continue;
            if(tempObj.mobile == mobileNoToDeleteAddress) {
              localStorage.removeItem(i);
            }
          }
          break;

        // show address book
        case 3:
          for(var i=0; i<=key; i++) {
            if(localStorage.getItem(i) == null) continue;
            document.write(localStorage.getItem(i));
          }
          break;

        // show address book sort by phone no
        case 4:
          var mobileArr = [];
          var index = -1;
          // store mobile nos in a array
          for(var i=0; i<=key; i++) {
            var tempObj = JSON.parse(localStorage.getItem(i));
            if(tempObj == null) continue;
            ++index;
            mobileArr[index] = tempObj.mobile;
          }
          //console.log(mobileArr);
          // sort mobile nos
          mobileArr.sort();
          for(var i=0; i<mobileArr.length; i++) {
            for(var j=0; j<=key; j++) {
              var tempObj = JSON.parse(localStorage.getItem(j));
              if(tempObj == null) continue; // if you remove any address
              if(tempObj.mobile == mobileArr[i]) {
                document.write(localStorage.getItem(j));
            }
          }
        }
       break;

       // edit address
       case 5:
         var mobileNoToEditAddress = parseInt(prompt("enter mobile no to \
                                                      edit particular    \
                                                      address",""));
         for(var i=0; i<=key; i++) {
           var tempObj = JSON.parse(localStorage.getItem(i));
           if(tempObj == null) continue;  // if you remove any address
           if(tempObj.mobile == mobileNoToEditAddress) {
             var name = prompt("enter name","");
             var city = prompt("enter city","");
             var mobile = parseInt(prompt("enter mobile no",""));
             addressBookObjectArr["name"] = name;
             addressBookObjectArr["city"] = city;
             addressBookObjectArr["mobile"] = mobile;
             localStorage.setItem(i, JSON.stringify(addressBookObjectArr));
             break;
           }
         }
         break;
  }
}
}
addressBook();
