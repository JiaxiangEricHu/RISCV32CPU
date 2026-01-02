# RISCV32CPU
这是一个基于RISV-V的CPU架构项目，是我的一次项目尝试。
This is the repo for a RISC-V ISA implemented CPU developing and its considered as a practical demo for CPU building example and some basic optimization and verification are also attached in this repo.
# Architecture
CPU并不是能够运行的最小单元，其正常的运行依赖于外接的**命令存储**以及**数据存储**。
- Instruction Fetch (IF)
这个过程本质上就是从**命令存储**中选取下一个周期的命令来放入下一个模块。
- Instruction Decode (ID
这个过程本质就是将命令进行拆分并放入下一个模块进行执行。
- Execution (EX)
这个过程本质上是CPU的核心模块，它将从ID解析出来的**数据存储**内容进行数据运算。
- Memorization (MEM)
这个过程本质上是EX中的延申，如果是关于Load/Store指令，则在此阶段进行；若是例如Add等指令，将在此阶段直接跳过。
- Write Back (WB)
这个过程本质上是将计算所得的内容写回到**数据存储**。
注：会有forwarding unit将MEM或EX的结果放回去。
