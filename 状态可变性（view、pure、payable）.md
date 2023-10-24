当在Solidity语言中编写智能合约时，可以使用`view`、`pure`和`payable`关键字来声明函数的状态可变性。这些关键字用于明确函数对区块链状态的读取、修改和支付的能力。

1. `view`: `view`关键字用于声明一个函数为“只读”函数，表示该函数不会修改合约的状态。它只能读取合约中的数据，而不能修改任何状态变量。它可以被其他函数调用，而不会消耗任何Gas。例如：

   ````solidity
   function getValue() public view returns (uint) {
       return someValue;
   }
   ```

   在上面的例子中，`getValue`函数只返回一个状态变量`someValue`的值，而不会对合约状态进行任何修改。

2. `pure`: `pure`关键字用于声明一个函数为“纯函数”，表示该函数不仅不会修改合约的状态，而且也不会访问合约的任何状态变量。它只执行计算操作，并返回结果。与`view`函数不同，`pure`函数不会访问任何状态变量，包括`msg.sender`和`block.number`等。例如：

   ````solidity
   function add(uint a, uint b) public pure returns (uint) {
       return a + b;
   }
   ```

   在上面的例子中，`add`函数只执行简单的加法操作，而不会对合约状态进行任何修改或读取。

3. `payable`: `payable`关键字用于声明一个函数可以接收以太币（Ether）作为支付。这个关键字通常用于接收以太币的函数，如接收捐赠、接收支付等。例如：

   ````solidity
   function receivePayment() public payable {
       // 执行接收以太币的逻辑
   }
   ```

   在上面的例子中，`receivePayment`函数声明为`payable`，表示它可以接收以太币，并将以太币存入合约的余额。

需要注意的是，`view`和`pure`函数在调用其他普通函数时，只能调用其他`view`或`pure`函数，因为它们不能修改状态。而`payable`函数则可以调用任何类型的函数，包括修改状态的函数。

总结起来，`view`关键字用于声明只读函数，`pure`关键字用于声明纯函数，而`payable`关键字用于声明接收以太币的函数。这些关键字有助于编写更安全和清晰的智能合约，并提供了对合约状态的明确访问和修改方式。
