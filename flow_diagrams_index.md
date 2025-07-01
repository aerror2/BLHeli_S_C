# BLHeli_S 流程图索引

本文档列出了所有为 BLHeli_S.asm 创建的流程图文件及其描述。这些流程图使用 DOT 语言编写，可以使用 Graphviz 工具或在线 DOT 可视化工具（如 [GraphvizOnline](https://dreampuf.github.io/GraphvizOnline/)）进行可视化。

## 流程图文件列表

1. **主流程图** - `main_flow.dot`
   - 描述：BLHeli_S 固件的主要流程，包括初始化、信号检测、武装、等待加电和电机运行等主要阶段。
   - 内容：系统初始化、信号检测、武装流程、等待加电、电机启动和运行的主要状态转换。

2. **启动和初始化流程图** - `startup_flow.dot`
   - 描述：详细展示系统启动和初始化过程，包括参数读取、信号类型检测和校准等。
   - 内容：系统初始化、参数读取、信号类型自动检测、油门校准和编程模式等流程。

3. **零交叉检测和换向流程图** - `zc_comm_flow.dot`
   - 描述：详细展示零交叉检测和电机换向的处理流程。
   - 内容：零交叉扫描、比较器检测、换向时序调整和换向执行等关键步骤。

4. **运行阶段流程图** - `run_phase_flow.dot`
   - 描述：详细展示电机正常运行时的六步换向和状态检查流程。
   - 内容：六个运行阶段、启动阶段检查、初始运行阶段检查、双向模式处理和方向变化处理等。

5. **中断处理流程图** - `interrupt_flow.dot`
   - 描述：详细展示各种中断的处理逻辑，包括定时器中断和外部中断。
   - 内容：Timer0-3中断、外部中断0和PCA中断的处理流程，包括RC脉冲捕获、DShot解码、换向和零交叉检测等。

6. **DShot命令处理流程图** - `dshot_flow.dot`
   - 描述：详细展示DShot命令的处理逻辑，包括蜂鸣、方向控制和保存设置等命令。
   - 内容：DShot命令解析、命令计数器处理、蜂鸣命令、方向命令和保存设置命令的处理流程。

7. **换相时序计算流程图** - `timing_flow.dot`
   - 描述：详细展示calc_next_comm_timing函数的逻辑，说明如何计算换相时序和零交叉检测时间。
   - 内容：换相时间存储、平均时间计算、电角度时间计算、零交叉扫描延时设置、提前换相定时设置等。

## 使用方法

1. 安装 Graphviz：
   ```
   # macOS
   brew install graphviz
   
   # Linux
   sudo apt-get install graphviz
   ```

2. 使用 Graphviz 生成图像：
   ```
   dot -Tpng main_flow.dot -o main_flow.png
   ```

3. 或者使用在线工具：
   - 访问 [GraphvizOnline](https://dreampuf.github.io/GraphvizOnline/)
   - 复制 .dot 文件内容并粘贴到编辑器中
   - 查看生成的图像

## 流程图之间的关系

- **主流程图**（main_flow.dot）提供了整个系统的高级概览。
- **启动和初始化流程图**（startup_flow.dot）详细展示了主流程图中初始化和信号检测部分。
- **零交叉检测和换向流程图**（zc_comm_flow.dot）详细展示了电机控制的核心算法。
- **运行阶段流程图**（run_phase_flow.dot）详细展示了电机正常运行时的状态转换。
- **中断处理流程图**（interrupt_flow.dot）展示了各种中断如何支持主流程的执行。
- **DShot命令处理流程图**（dshot_flow.dot）详细展示了DShot数字信号的命令处理逻辑。
- **换相时序计算流程图**（timing_flow.dot）详细展示了换相时序计算的核心算法，包括电角度时间计算和零交叉检测时序。