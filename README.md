# Exam Paper Auto Marker

这是一个基于 `pyautogui` 和 `keyboard` 的自动点击与按键脚本，适用于处理固定坐标的试卷批改或标注任务。脚本会依照预设的坐标和操作顺序自动进行点击和键盘输入，支持暂停与退出控制。

## 功能介绍

- 根据设定好的坐标序列自动点击试卷标注区域
- 模拟键盘输入分数或标识
- 每轮自动执行，可随时暂停与退出
- 支持点击 + 按键 + 等待时间的混合操作

## 使用说明

### 依赖安装

请确保使用 Python 3，且已安装以下依赖：

pip install pyautogui keyboard

## 运行脚本
将脚本运行后，请快速切换到目标批改界面（例如试卷批改系统），脚本将每轮自动执行点击与按键序列。

python your_script.py

## 控制方式
按下 P 键：暂停或继续执行

按下 Esc 键：退出程序

# 脚本逻辑说明
## 坐标定义
脚本使用一个字典 coords 来存储点击点的编号及其屏幕坐标。例如：
coords = {
    1: (476, 358),
    2: (534, 490),
    ...
}
这些坐标应基于你的屏幕分辨率和目标界面自行获取和调整。

# 操作序列
## 操作序列 sequence 是一组按顺序执行的操作，支持三种类型：

"click", 编号：点击 coords 中指定编号的坐标

"key", 键值：按下指定键盘键（如 "4"、"d"）

"wait", 秒数：等待指定秒数（如 4 秒）

## 运行流程
脚本启动后，将自动进入循环，每轮执行整个序列，并在每轮前等待 4 秒。可以随时通过按键控制：

按 P 暂停/恢复

按 Esc 立即退出

## 示例输出
程序启动，切换到目标程序，脚本每轮自动运行。
▶ 按 'P' 暂停/继续，按 'Esc' 退出。
点击坐标1
点击坐标2
按下键：4
等待 4 秒...
一遍执行完毕。

# 注意事项
本脚本仅适用于坐标固定的界面，请确保目标界面未发生位移或缩放

坐标应手动通过截图、定位工具获取，精度影响点击准确性

推荐将目标程序置于全屏状态，并关闭屏保、自动锁屏等功能

运行过程中请勿手动干预鼠标和键盘

坐标点提取见https://github.com/keing1209/Mouse-Click-Coordinate-Logger
