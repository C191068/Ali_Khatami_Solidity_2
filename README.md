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
      
      individuals.push(Individuals(_preferredNumber,_name)); //push Individual in our individual array ,we can also do in this way
  
  }


  
}

//0xd9145CCE52D386f254917e481eB44e9943F39138
```
