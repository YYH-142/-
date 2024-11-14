11.4-11.8完成特征查找项目的c++代码转化  

计划11.11完成项目debug与实验  
11.11计划施行情况：初步完成debug,依然存在极小一部分代码处于研究阶段(将k邻近点在循环内更新等)，已经可以可视化循环step1的结果，暂时使用rabbit.pcd作为实验素材（只写了.pcd文件的读取代码），后续去寻找更多模型  

计划11.12,11.13彻底完成debug任务与寻找更多实验案例，多余时间看论文  
11.12,11.13计划施行情况：代码已经跑通，经过实验，判断循环step1结果没有问题，但是循环step2和step3结果存在问题，初步判断代码有一部分写得有问题，论文暂时没时间看  

计划11.14继续寻找循环step2的结果为什么有问题，剩余时间看论文  
11.14计划施行情况：已经找到bug（可视化的坐标没有随循环更新），现在已经得到正确的实验结果。论文正在看。  
![image](https://github.com/user-attachments/assets/e3d76067-7b68-41ba-b1a0-582e5a84c0ce)  
实验数据 block-smooth-groundtruth.pcd      int  K = 10;// 使用 K 个最近邻点  
float normal_angle_stddevs_weight = 2000;//法线夹角标准差权重参数  
float dot_product_stddevs_weight = 2000;//k临近点最小二乘距离标准差权重参数  
float alpha = 0.15;float beta = 0.15;  
float alpha_step2 = 0.075;float beta_step2 = 0.15;  
float alpha_step3 = 0.075;float beta_step3 = 0.15;  
![image](https://github.com/user-attachments/assets/b0a11c76-8bf7-48e6-ba5e-1d21a18da2ab)  
实验数据 block-smooth-randomdirectionnoise0.35.pcd      int  K = 15;// 使用 K 个最近邻点  
float normal_angle_stddevs_weight = 1000;//法线夹角标准差权重参数  
float dot_product_stddevs_weight = 1000;//k临近点最小二乘距离标准差权重参数  
float alpha = 0.15;float beta = 0.15;  
float alpha_step2 = 0.075;float beta_step2 = 0.15;  
float alpha_step3 = 0.075;float beta_step3 = 0.15;  

