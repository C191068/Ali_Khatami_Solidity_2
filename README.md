## Ali_Khatami_Solidity_2
### Array and structure

Here we have created Array and structure<br>
Structure means we are creating new data type.<br>
Array is a data structure that will store large amount of data of same type.<br>


```
//SPDX-License-Identifier: MIT
pragma solidity ^0.8.7;

contract akrkSimplestorage {
  // basic data types: boolean, uint,int,address,bytes
  //uint(unsigned integer only positive),int both pos and neg
  //address is the address of the account
  //string are secretly byte objects only for text
  //bytes32 is a bytes objects whre 32 represent how many bytes we want them to be,max size is 32
  //byte objects look like 0xsdsysydggt
  //unint256 here 256 is bit (8,16,32 upto 256 we can use)
  uint256 preferredNumber;//remove public so that we don't get duplicate functions at the moment we will just get the retrieve function
   //if we have whole bunch of variables inside the contract akrkSimplestorage those actually get indexed
   //here 'uint256 preferredNumber' will get index to 'zero'
  
//Below we have created a new type in our solidity that holds both preferred number and name 
  struct Individuals{
    uint256 preferredNumber;//this get indexed to 0
    string name;// this get indexexd to 1
//whenever we have list of variables inside an object they automatically get indexed

}

  // here below we create an array of uint256 and now preferred number can be a list or array
  //uint256[] public preferredNumbersList;

//here below we want an array of Individuals we give it visibility of public and variable name individuals
  Individuals[] public individuals; //it is automatically giving a view function and it will give nothing if it is empty and in it's button the value that it wants is gonna be the index of the object
// array above is a dynamic array because size of the array is not given at it's initialization if we don't add any size it can be any size and here we gonna work with dynamic array

//pasing parameter of type uint256 and made the function public
  function store(uint256 _preferredNumber) public{
      preferredNumber = _preferredNumber;
    
  }

  function retrieve() public view returns(uint256){
    return preferredNumber;
  }

  //now we will create a function that is going to add individuals to Individual array
  function addCitizen(string memory _name, uint256 _preferredNumber) public {
      
      individuals.push(Individuals(_preferredNumber,_name));//Here we have created a push function which is available in our Individuals object
      //Here in the above inside the push function we have created a new Individual object that will take preferred number and name. 
  //push Individual in our individual array ,we can also do in this way
  }


  
}

//0xd9145CCE52D386f254917e481eB44e9943F39138
```

In our deploy and run transactions tab we get the following after compiling the above code :
![d1](https://user-images.githubusercontent.com/89090776/226176285-2ec73425-b364-4e32-aae6-ff06af8c592f.jpg)
Figure:1

Here,<br>
In the figure 1 we can see that blue color button ```individuals``` , instead of having a single button where the value shows up ,it is giving us a form to fill up<br>
If our array individuals[] is empty we can get nothing by clicking the blue color button ```individuals```.<br>
One think we must notice that capital word ```Individuals``` refers to struct or the new data type created.<br>
```individuals``` refers to array created<br>

![d2](https://user-images.githubusercontent.com/89090776/226181083-701ffd73-4d5a-4ebb-aaa8-8499c1cd0a50.jpg)
Figure2: Here when we typed ```Khatami,68``` and click ```addCitizen``` button then transaction occurs and then in form of ```individuals``` button <br>
when we typed ```0``` it means ```Khatami,68``` is stored at index ```0``` of individuals array<br>

![d3](https://user-images.githubusercontent.com/89090776/226181154-04690157-27b8-413b-b641-743e9d8a2766.jpg)
Figure3:Here when we typed ```Rokib,53``` and click ```addCitizen``` button then transaction occurs and then in form of ```individuals``` button <br>
when we typed ```1``` it means ```Rokib,53``` is stored at index ```1``` of individuals array<br>
![d4](https://user-images.githubusercontent.com/89090776/226181168-639bb228-0427-400f-bbec-221186ed9fc4.jpg)
Figure4:Here when we typed ```Rafi,65``` and click ```addCitizen``` button then transaction occurs and then in form of ```individuals``` button <br>
when we typed ```2``` it means ```Rafi,65``` is stored at index ```2``` of individuals array<br>

<br><br>





