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
![image](https://github.com/user-attachments/assets/8927d12f-19f7-429e-94c8-799aaca2b9e4)  
实验数据 fandisk-groundtruth.pcd      int  K = 25;// 使用 K 个最近邻点  
float normal_angle_stddevs_weight = 500;//法线夹角标准差权重参数  
float dot_product_stddevs_weight = 100;//k临近点最小二乘距离标准差权重参数  
float alpha = 0.15;float beta = 0.15;  
float alpha_step2 = 0.075;float beta_step2 = 0.15;  
float alpha_step3 = 0.075;float beta_step3 = 0.15;  
![image](https://github.com/user-attachments/assets/02d02faf-2062-449b-8172-7ee32bebfe2b)  
实验数据 fandisk-normdirectionnoise0.25.pcd      int  K = 25;// 使用 K 个最近邻点  
float normal_angle_stddevs_weight = 500;//法线夹角标准差权重参数  
float dot_product_stddevs_weight = 100;//k临近点最小二乘距离标准差权重参数  
float alpha = 0.15;float beta = 0.15;  
float alpha_step2 = 0.075;float beta_step2 = 0.15;  
float alpha_step3 = 0.075;float beta_step3 = 0.15;  
注意！以上实验结果仅调整了几次，未必是最佳结果。  

计划11.15看论文，寻找创新点  
11.15计划施行情况：论文看了一部分，记录论文要点。  
4.1 Feature-edge identification  该部分通过计算二面角与边缘检测得到“特征线”（i.e.尖锐部分与边缘） 

4.2 Preliminary input-mesh optimization  利用[Hoppe et al. 1993]论文的策略重新构建三角网格，并在构建过程中保证“特征线”不变，然后在“特征线”周围自适应调整   Mesh Optimization. In Proceedings of the 20th Annual Conference on Computer Graphics and Interactive Techniques (Anaheim, CA)  

4.3 Cross-field definition  通过在每个三角形中分配一个与“特征线”对齐的切线方向，在输入表面上构造一个Cross-field。step1:将与多个“特征线”相邻的网格进行分割，直到最多相邻一个“特征线”。step2:将与“特征线”方向匹配的场值分配给相邻的任何面。step3:利用[Diamanti et al. 2014]策略扩散。Designing N-PolyVector Fields with Complex Polynomials  

11.16-11.24看论文，暂时未找到创新点，准备考试事宜  

计划11.25-11.28准备机考内容（11.28机考时间）
