# AutoLabelImg 多功能自动标注工具

### 简介：

在[labelImg](https://github.com/tzutalin/labelImg)的基础上，增加了多种标注工具，放在**Annoatate-tools**和**Video-tools**两个菜单栏下面。具体功能包含如下：

- **`TOOL LIST`**：
- [x] **自动标注**：基于yolov5的模型自动标注
- [x] **追踪标注**：利用opencv的追踪功能，自动标注视频数据
- [x] **放大镜**：局部放大，对小目标的标注有帮助，可以关闭
- [x] **数据增强**：随机使用平移，翻转，缩放，亮度，gama，模糊等手段增强图片
- [x] **查询系统**：输入关键字获得详细说明信息
- [x] 其他批量处理功能：可以利用查询系统查看详细信息，欢迎体验

### Demo:

### 更新日志：

2022.01.14：自动标注去掉Retinanet，仅保留yolov5，并增加标签选择

2022.01.11：优化放大镜卡顿现象，增加放大镜可关闭选项

2020.12.28：增加视频追踪标注工具

2020.12.10：初步把所有工具加进labelimg，版本1.0

## 安装步骤：

1. 复制仓库：

   ```bash
   git clone https://github.com/wufan-tb/AutoLabelImg
   cd AutoLabelImg
   ```

2. 安装依赖：

   ```bash
   conda create -n {your_env_name} python=3.7.6
   conda activate {your_env_name}
   pip install requirements.txt
   ```

3. 源码编译：

   **Ubuntu用户:**
   
   ```
   sudo apt-get install pyqt5-dev-tools
   make qt5py3
   ```
   
   **Windows用户:**
   
   ```
   pyrcc5 -o libs/resources.py resources.qrc
   ```
   
4. 准备yolov5模型并放置在如下位置，官方模型获取参考[Yolov5](https://github.com/ultralytics/yolov5)

   ```bash
   mv {your_model_weight.pt} pytorch_yolov5/weights/
   ```

5. 打开软件，开始标注

   ```
   python labelImg.py
   ```

## 设置快捷方式[非必须]

**Windows:**

桌面创建labelImg.bat,右键用文本编辑器打开，键入下面内容(不一定是D盘，根据实际输入)：

```bash
D:
cd D:{path to your labelImg folder}
start python labelImg.py
exit
```

双击labelImg.bat即可打开标注软件。

**Ubuntu:**

打开环境变量文件：

```bash
vim ~/.bashrc
```

然后增加下面内容：

```bash
alias labelimg='cd {path to your labelImg folder} && python labelImg.py
```

使环境变量生效：

```bash
source ~/.bashrc
```

然后在任何地方输入指令labelimg即可打开编著软件。

## 引用

```
{   AutoLabelImg,
    author = {Wu Fan},
    year = {2022},
    url = {\url{https://https://github.com/wufan-tb/AutoLabelImg}}
}
```

