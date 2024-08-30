# Usage of Instant_ngp

## 数据准备
在以下目录下创建自己要重建物体的文件夹：
```
E:\03-project\Instant-NGP-for-RTX-3000-and-4000\external\colmap\COLMAP-3.7-windows-no-cuda
```
下面以 `cup1` 为例：

<img width="416" alt="image" src="https://github.com/user-attachments/assets/e69f0571-9b39-49ba-98aa-6576b8b4dd07">

- `cup1.db` 为自己新建的数据库文件
- `images` 为自己准备的照片集

## 新建工程项目

**启动COLMAP**

  双击 `COLOMAP.bat` 打开软件，`CLOMAP.bat` 与在步骤一创建的 `cup1` 文件夹在同一目录下
  <img width="416" alt="image" src="https://github.com/user-attachments/assets/d97d0bae-8b9f-47ff-9c72-fd5cac73ab1f">

**新建项目**
  
  <img width="416" alt="image" src="https://github.com/user-attachments/assets/d6b26a78-e1a8-4061-afea-787e42f34d67">
   
  - 选择项目位置和照片位置，点击save保存
  
  <img width="291" alt="image" src="https://github.com/user-attachments/assets/53d4a1a0-778e-4230-bc1e-ee12c9091733">

**特征提取、匹配及重建**

  - 点击 `Processing` -> `Feature Extraction` 进行特征提取
  - 点击 `Processing` -> `Feature Match` 进行特征匹配
  - 点击 `Reconstruction` -> `Start Reconstruction` 开始重建
    
  <img width="416" alt="image" src="https://github.com/user-attachments/assets/4a3ce8ca-0d0a-4571-9fd5-331efb6b5da3">

**导出**

  点击 `File` -> `Export model as text` 将结果保存为文本。在 `cup1` 目录下新建 `colmap_text` 文件夹，并将导出的文本保存在该目录下。保存后 `colmap_text` 目录下会生成以下四个文件
    
  <img width="416" alt="image" src="https://github.com/user-attachments/assets/27ee199c-a971-4970-a93e-f90b404df2b9">

**运行脚本**

  - 将 `colmap2nerf.py` 文件复制到 `cup1` 目录下
    
  <img width="416" alt="image" src="https://github.com/user-attachments/assets/8b7468b8-5638-4c83-907c-9b3609bfcdac">

  - 双击打开 `Anaconda Prompt`（在电脑左下角搜索 `ana` 即可找到）
    
  <img width="415" alt="image" src="https://github.com/user-attachments/assets/27c0cb29-f1a0-4a81-b512-36a537472e4f">

  - 运行 `colmap2nerf.py` 脚本之后，生成 `transforms.json` 文件，获得相机参数

  <img width="416" alt="image" src="https://github.com/user-attachments/assets/57139d96-9019-42af-8c49-5f231d6ce0bb">

**启动 Instant-NGP**

  - 在以下目录下新建 `cup1` 文件夹：
  ```
  E:\03-project\Instant-NGP-for-RTX-3000-and-4000\data\nerf
  ```
  - 将生成的 `transforms.json` 文件及 `images` 图片集复制到该目录下
    
  <img width="416" alt="image" src="https://github.com/user-attachments/assets/ec5317e5-0587-48a1-8513-f7f412681f8a">

  - 双击打开 `instant-ngp.exe`，会出现一个黑框框（instant-ngp 界面）
    
  <img width="416" alt="image" src="https://github.com/user-attachments/assets/4a1631a1-ba10-4da6-9ff5-d624dcc04e1e">
  
  - 将 `E:\03-project\Instant-NGP-for-RTX-3000-and-4000\data\nerf` 目录下的 `cup1` 文件夹直接拖到instant_ngp界面中即可

  <img width="416" alt="image" src="https://github.com/user-attachments/assets/3c610b95-f6cf-43d1-a569-16528dbbcc1c">

  - 通过调整界面参数即可看到重建的水杯

  <img width="416" alt="image" src="https://github.com/user-attachments/assets/c19b4630-56bc-4569-ba1c-228a08a14d53">

  ---
  - 金胜男（2024.08.30）

