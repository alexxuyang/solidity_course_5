合约文件是[ExtendedERC20.sol](https://github.com/alexxuyang/solidity_course_5/blob/main/contracts/ExtendedERC20.sol)

实现的功能：
- 合约创建者（owner）mint token
- 任何人都可以burn token
- 合约创建者（owner），可以设置
    - fee：transfer收取的手续费
    - burnAmount：在fee中，需要燃烧的数量（burn）
    - feeCollector：手续费收集账号

当用户A transfer token时，假设金额是amount，接收者是B。那么：
- A.balance = A.balance - amount - fee
- B.balance = B.balance + amount
- feeCollector.balance = feeCollector.balance + fee - burnAmount
- totalSupply = totalSupply - burnAmount

测试案例文件是[ExtendedERC20.js](https://github.com/alexxuyang/solidity_course_5/blob/main/test/ExtendedERC20.js)