Error 404 !








    Error 404 !








    P2 WRITE A SOLIDITY PROGRAM TO DEMONSTRATE LOOP STATEMENT.
  
    Source Code:
    // SPDX-License-Identifier: GPL-3.0
    
    pragma solidity <0.9.0;
    
    contract Loop {
        function loop() pure public returns(uint result) {
            for (uint i = 0; i < 10; i++){
                if (i == 3){
                    continue;
                }
                if ( i == 5) {
                    break;
                }
            }
    
            uint j;
            while( j < 10 ) {
                j++;
            }
            return j;
        }
    }
    Compile Contract:
    
     
    
    Deploy Contract: 
     
    
    
    Source Code:
    // SPDX-License-Identifier: GPL-3.0
    
    pragma solidity <0.9.0;
    
    contract IfElse {
        function foo(uint _x) public pure returns (uint) {
            if (_x < 10 ){
                return 0;
            } else if ( _x < 20 ) {
                return 1;
            } else {
                return 2;
            }
        }
        function ternary(uint _x ) public pure returns (uint) {
            return _x > 10 ? 1 : 2;
        }
    }
    
    
    Compile Contract:
     
    Deploy Contract: 
     
    Source Code:
    // SPDX-License-Identifier: GPL-3.0
    
    pragma solidity <0.9.0;
    
    contract ifelseif {
        uint i = 12;
        string result;
    
        function decision_making() public returns(string memory) {
            if(i < 10){
                result = "less than 10";
            }
            else if (i == 10){
                result = "Equal to 10";
            }
            else {
                result = "Greater than 10";
            }
            return result;
        }
    }
    
    Compile Contract:
     
    
    Deploy Contract: 
    
    
    P3 : Write a solidity program to demonstrate arrays and constructor.
    
  Array
  
  // SPDX-License-Identifier: MIT
  pragma solidity <0.9.0;
  
  
  contract Prac3_Array {
      uint[5] fixedArray = [1, 2, 3, 4, 5];
      uint[] dynamicArray;
  
  
      function pushElement(uint number) public returns(uint[] memory) {
          dynamicArray.push(number);
          return dynamicArray;
      }
  
  
      function popElement() public returns (uint[] memory) {
          dynamicArray.pop();
          return dynamicArray;
      }
  
  
      function removeIndex(uint index) public returns(uint[] memory) {
          require(dynamicArray.length > index, "Index out of bound");
          delete dynamicArray[index];
          return dynamicArray;
      }
  
  
      function getLength() public view returns (uint) {
          return dynamicArray.length;
      }
  
  
      function getDynamicArray() public view returns (uint[] memory) {
          return dynamicArray;
      }
  
  
      function getFixedArray() public view returns(uint[5] memory) {
          return fixedArray;
      }
  }
  
  
  Constructor and inheritance
  
  // SPDX-License-Identifier: MIT
  pragma solidity <0.9.0;
  
  
  contract Person {
    // Constructor to initialize name
    constructor(string memory _name)  {
      name = _name;
    }
  
  
    string public name;
  }
  
  
  contract Employee is Person{
      constructor(string memory _name, uint _salary) Person(_name) {
          salary = _salary;
      }
      uint public salary;
  }
  
  
  contract Manager is Employee{
      constructor(string memory _name, uint _salary, string memory _department) Employee(_name, _salary) {
          department = _department;
      }
      string public department;
  }
  
    
    
     
    P4 : Write a solidity program to demonstrate strings
  // SPDX-License-Identifier: MIT
  pragma solidity <0.9.0;
  contract Test {
      string store;
      event LogMessage(string message, string value);   
      function concatenateStrings(string memory s1, string memory s2) public pure returns (string memory) {
          return string.concat(s1, s2);
      }
      function getStore() public view returns (string memory) {
          return store;
      }
      function setStore(string memory inputStr) public returns (string memory) {
          store = inputStr;
          return store;
      }
      function logStore() public {
          emit LogMessage("Value of store is: ", store);
      }
  }
  
    
    P5  : Write a solidity program to demonstrate structure and enumerator
    
    Code:
    // SPDX-License-Identifier: GPL-3.0
    pragma solidity <0.9.0;
    
    contract Types{
        enum week_days{
            Monday,
            Tuesday,
            Wednesday,
            Thrusday,
            Friday,
            Saturday,
            Sunday
        }
        week_days week;
        week_days choice;
        week_days constant default_value = week_days.Sunday;
        function set_value() public {
            choice = week_days.Thrusday;
        }
        function get_choice() public view returns(week_days){
            return choice;
        }
        function getdefaultvalu() public pure returns(week_days) {
            return default_value;
        }
    }
    
    Compile contract:
     
    
    Deployed contract:
     
    
    2nd Program
    
    // SPDX-License-Identifier: GPL-3.0
    pragma solidity <0.9.0;
    
    contract test{
        struct Book{
            string name;
            string writer;
            uint id;
            bool available;
        }
        Book book1;
        Book book2 = Book("Building Etherium DApps", "Roberto Infante", 2, false);
        function set_book_detail() public{
            book1 = Book("Introducing Etherium & Solidity", "Chris Damen", 1, true);
        }
        function book_info() public view returns(string memory, string memory, uint, bool){
            return(book2.name, book2.writer, book2.id, book2.available);
        }
        function get_details() public view returns(string memory, uint) {
            return (book1.name, book1.id);
        }
    }
    
    
    
    
     P6  : Write the following programs for Blockchain in Python :
    i.	A Simple client class that generates the private and public keys by using the built in Python RSA algorithm and test it.
    ii.	A transaction class to send and receive money and test it.
    Code :- 
  
  
    # import libraries
    import hashlib
    import random
    import string
    import json
    import binascii
    import numpy as np
    import pandas as pd
    import pylab as pl
    import logging
    import datetime
    import collections
    
    pip install pycryptodome
    
    # following imports are required by PKI
    import Crypto
    import Crypto.Random
    from Crypto.Hash import SHA
    from Crypto.PublicKey import RSA
    from Crypto.Signature import PKCS1_v1_5
    
    import binascii
    
    class Client:
       def __init__(self):
          random = Crypto.Random.new().read
          self._private_key = RSA.generate(1024, random)
          self._public_key = self._private_key.publickey()
          self._signer = PKCS1_v1_5.new(self._private_key)
    
       @property
       def identity(self):
          return binascii.hexlify(self._public_key.exportKey(format='DER')).decode('ascii')
    
    class Transaction:
       def __init__(self, sender, recipient, value):
        self.sender = sender
        self.recipient = recipient
        self.value = value
        self.time = datetime.datetime.now()
       def to_dict(self):
        if self.sender == "Genesis":
          identity = "Genesis"
        else:
          identity = self.sender.identity
        return collections.OrderedDict({
          'sender': identity,
          'recipient': self.recipient,
          'value': self.value,
          'time' : self.time})
       def sign_transaction(self):
        private_key = self.sender._private_key
        signer = PKCS1_v1_5.new(private_key)
        h = SHA.new(str(self.to_dict()).encode('utf8'))
        return binascii.hexlify(signer.sign(h)).decode('ascii')
    Dinesh = Client()
    Ramesh = Client()
    t = Transaction(Dinesh,Ramesh.identity,5.0)
    signature = t.sign_transaction()
    print (signature)
    
    Output 
    
    
    Output Screenshot
    
    P7 Write the following programs for Blockchain in Python :
    i.	Create multiple transactions and display them.
    ii.	Create a blockchain, a genesis block and execute it.
    Code: -
    def display_transaction(transaction):
       #for transaction in transactions:
       dict = transaction.to_dict()
       print ("sender: " + dict['sender'])
       print ('-----')
       print ("recipient: " + dict['recipient'])
       print ('-----')
       print ("value: " + str(dict['value']))
       print ('-----')
       print ("time: " + str(dict['time']))
       print ('-----')
    
    transactions = []
    
    Dinesh = Client()
    Ramesh = Client()
    Seema = Client()
    Vijay = Client()
    
    t1 = Transaction(
       Dinesh,
       Ramesh.identity,
       15.0
    )
    
    t1.sign_transaction()
    transactions.append(t1)
    
    t2 = Transaction(
       Dinesh,
       Seema.identity,
       6.0
    )
    t2.sign_transaction()
    transactions.append(t2)
    t3 = Transaction(
       Ramesh,
       Vijay.identity,
       2.0
    )
    t3.sign_transaction()
    transactions.append(t3)
    t4 = Transaction(
       Seema,
       Ramesh.identity,
       4.0
    )
    t4.sign_transaction()
    transactions.append(t4)
    t5 = Transaction(
       Vijay,
       Seema.identity,
       7.0
    )
    t5.sign_transaction()
    transactions.append(t5)
    t6 = Transaction(
       Ramesh,
       Seema.identity,
       3.0
    )
    t6.sign_transaction()
    transactions.append(t6)
    t7 = Transaction(
       Seema,
       Dinesh.identity,
       8.0
    )
    t7.sign_transaction()
    transactions.append(t7)
    t8 = Transaction(
       Seema,
       Ramesh.identity,
       1.0
    )
    t8.sign_transaction()
    transactions.append(t8)
    t9 = Transaction(
       Vijay,
       Dinesh.identity,
       5.0
    )
    t9.sign_transaction()
    transactions.append(t9)
    t10 = Transaction(
       Vijay,
       Ramesh.identity,
       3.0
    )
    t10.sign_transaction()
    transactions.append(t10)
    
    for transaction in transactions:
       display_transaction (transaction)
       print ('--------------')
    
    class Block:
       def __init__(self):
          self.verified_transactions = []
          self.previous_block_hash = ""
          self.Nonce = ""
    
    last_block_hash = ""
    
    Dinesh = Client()
    
    t0 = Transaction (
       "Genesis",
       Dinesh.identity,
       500.0
    )
    
    block0 = Block()
    
    block0.previous_block_hash = None
    Nonce = None
    
    block0.verified_transactions.append (t0)
    
    digest = hash (block0)
    last_block_hash = digest
    
    TPCoins = []
    
    def dump_blockchain (self):
       print ("Number of blocks in the chain: " + str(len (self)))
       for x in range (len(TPCoins)):
          block_temp = TPCoins[x]
          print ("block # " + str(x))
          for transaction in block_temp.verified_transactions:
             display_transaction (transaction)
             print ('--------------')
          print ('=====================================')
    
    TPCoins.append (block0)
    dump_blockchain(TPCoins)
     
    
  
  
  
  
  
  
  
      
  
   
  







    
