# 使用CPU假负载检查CPU插座电压步骤

------



| **步骤**          | **操作内容**                                                 | **说明**                                                     |
| ----------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **1. 准备工具**   | 确保所需工具齐全：CPU 假负载、数字万用表、主板电源连接器（24-pin 和 8-pin）。 | - CPU 假负载用于模拟 CPU 的工作状态。<br>- 数字万用表用于测量电压。 |
| **2. 安装假负载** | 将 CPU 假负载正确插入主板上的 CPU 插槽中。                   | - 确保假负载与插槽完全对齐并安装牢固。<br>- 避免弯曲或损坏针脚。 |
| **3. 连接电源**   | 将 ATX 电源连接到主板（24-pin 主电源和 8-pin CPU 供电接口）。 | - 确保所有电源线缆正确连接。<br>- 不要漏接任何必要的电源接口。 |
| **4. 开启电源**   | 打开 ATX 电源开关，为主板供电。                              | - 使用跳线帽短接主板上的电源开关引脚（通常标记为 PWR_SW），或者直接按机箱电源按钮。 |
| **5. 测量电压**   | 打开万用表电源，调至直流 2V 档位。黑表笔插入 COM 口并接地，红表笔插入 V/Ω 口并接触假负载测试点。 | - 根据需要选择合适量程（如 2V 或 20V）。<br>- 记录各测试点的电压值并与标准值对比。 |
