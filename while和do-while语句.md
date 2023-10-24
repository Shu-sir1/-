# Solidity中的while和do-while循环

Solidity中的while和do-while循环是两种常见的迭代结构，用于重复执行一段代码块，直到满足退出条件。它们在循环开始之前检查条件，不同之处在于while循环在每次迭代之前检查条件，而do-while循环在每次迭代之后检查条件。以下是对Solidity中while循环和do-while循环的详细说明：

## while循环的语法

while循环由一个条件表达式和一个循环体组成。其语法如下：

```solidity
while (条件表达式) {
    // 循环体
}
```

- **条件表达式**：在每次循环迭代之前进行的条件检查。如果条件为真，则执行循环体；如果条件为假，则退出循环。

- **循环体**：在每次循环迭代时执行的代码块。

## while循环的执行流程

while循环的执行流程如下：

1. 检查条件表达式。如果条件为假，则跳出循环，继续执行下一个语句。

2. 执行循环体。

3. 返回步骤1，重复执行循环。

## do-while循环的语法

do-while循环由一个条件表达式、一个循环体和关键字`while`组成。其语法如下：

```solidity
do {
    // 循环体
} while (条件表达式);
```

- **循环体**：在每次循环迭代时执行的代码块。

- **条件表达式**：在每次循环迭代之后进行的条件检查。如果条件为真，则继续执行循环；如果条件为假，则退出循环。

## do-while循环的执行流程

do-while循环的执行流程如下：

1. 执行循环体。

2. 检查条件表达式。如果条件为真，则返回步骤1，继续执行循环；如果条件为假，则跳出循环，继续执行下一个语句。

## 示例

下面是一个使用while循环和do-while循环的示例，演示了如何在Solidity中计算数字之和：

```solidity
pragma solidity ^0.8.0;

contract LoopExample {
    function calculateSum(uint n) public pure returns (uint) {
        uint sum = 0;
        uint i = 1;

        while (i <= n) {
            sum += i;
            i++;
        }

        return sum;
    }

    function calculateSumDoWhile(uint n) public pure returns (uint) {
        uint sum = 0;
        uint i = 1;

        do {
            sum += i;
            i++;
        } while (i <= n);

        return sum;
    }
}
```

在上面的示例中，我们使用while循环和do-while循环计算从1到n的数字之和。在每次迭代中，我们将当前数字加到总和中，并递增计数器。当计数器达到n时，循环结束，返回计算得到的总和。
