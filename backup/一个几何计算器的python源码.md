要在 Python 中下载 `tkinter` 库，并且使用中国镜像源来加速下载，可以通过配置 `pip` 使用中国镜像源来完成。`tkinter` 是 Python 的标准库之一，通常在 Python 的标准安装包中已经包含，但如果需要安装或重新安装它，可以按以下步骤操作：

### 使用中国镜像源安装 Python 包（包括 `tkinter`）

1. **配置镜像源**：
   可以通过修改 `pip` 配置文件或在命令中直接指定镜像源来使用中国的镜像源。

   **临时使用镜像源**：
   ```bash
   pip install tkinter -i https://pypi.tuna.tsinghua.edu.cn/simple
   ```

   **永久配置镜像源**：
   在 `pip` 配置文件中添加镜像源。配置文件位置如下：
   - **Windows**: `C:\Users\<用户名>\pip\pip.ini`
   - **macOS/Linux**: `~/.pip/pip.conf`

   在配置文件中添加以下内容：
   ```ini
   [global]
   index-url = https://pypi.tuna.tsinghua.edu.cn/simple
   ```

2. **安装 `tkinter`**：
   对于大多数用户，`tkinter` 是 Python 的一部分，通常不需要单独安装。如果在使用 `tkinter` 时遇到问题，可能是因为 Python 安装包没有包括 `tkinter`。

   在大多数 Linux 发行版中，你可以使用以下命令来安装 `tkinter`：
   ```bash
   sudo apt-get install python3-tk
   ```

   对于 Windows 和 macOS 用户，通常只需要安装 Python 的标准发行版（如从 [Python 官方网站](https://www.python.org/) 下载的版本），`tkinter` 应该是默认包含的。

### 验证安装

安装完成后，你可以运行以下 Python 代码来验证 `tkinter` 是否正确安装：

```python
import tkinter as tk

root = tk.Tk()
root.title("Tkinter Test")
root.geometry("200x100")

label = tk.Label(root, text="Hello, Tkinter!")
label.pack()

root.mainloop()
```

如果上面的代码成功运行并弹出一个包含 "Hello, Tkinter!" 的窗口，那么 `tkinter` 已经成功安装并且可以正常使用。

如果你安装了，代码如下：
```
import` tkinter as tk
from tkinter import ttk
import math

# 定义常量
PI = 3.14

# 定义计算函数
def calculate():
    shape = shape_var.get()
    if shape == "长方形":
        length = float(entry1.get())
        width = float(entry2.get())
        area = length * width
        result.set(f"长方形的面积为: {area:.2f}")
    elif shape == "长方体":
        length = float(entry1.get())
        width = float(entry2.get())
        height = float(entry3.get())
        surface_area = 2 * (length * width + width * height + length * height)
        volume = length * width * height
        result.set(f"长方体的表面积为: {surface_area:.2f}, 体积为: {volume:.2f}")
    elif shape == "圆形":
        radius = float(entry1.get())
        area = PI * radius * radius
        result.set(f"圆形的面积为: {area:.2f}")
    elif shape == "球":
        radius = float(entry1.get())
        surface_area = 4 * PI * radius * radius
        volume = 4 / 3 * PI * radius * radius * radius
        result.set(f"球的表面积为: {surface_area:.2f}, 体积为: {volume:.2f}")
    elif shape == "圆柱体":
        radius = float(entry1.get())
        height = float(entry2.get())
        surface_area = 2 * PI * radius * (radius + height)
        volume = PI * radius * radius * height
        result.set(f"圆柱体的表面积为: {surface_area:.2f}, 体积为: {volume:.2f}")
    elif shape == "圆锥":
        radius = float(entry1.get())
        height = float(entry2.get())
        surface_area = PI * radius * (radius + math.sqrt(height**2 + radius**2))
        volume = 1 / 3 * PI * radius * radius * height
        result.set(f"圆锥的表面积为: {surface_area:.2f}, 体积为: {volume:.2f}")

# 更新输入框和标签
def update_inputs(event):
    shape = shape_var.get()
    if shape == "长方形":
        label1.config(text="长度:")
        label2.config(text="宽度:")
        label1.grid(row=1, column=0)
        entry1.grid(row=1, column=1)
        label2.grid(row=2, column=0)
        entry2.grid(row=2, column=1)
        label3.grid_forget()
        entry3.grid_forget()
    elif shape == "长方体":
        label1.config(text="长度:")
        label2.config(text="宽度:")
        label3.config(text="高度:")
        label1.grid(row=1, column=0)
        entry1.grid(row=1, column=1)
        label2.grid(row=2, column=0)
        entry2.grid(row=2, column=1)
        label3.grid(row=3, column=0)
        entry3.grid(row=3, column=1)
    elif shape == "圆形":
        label1.config(text="半径:")
        label1.grid(row=1, column=0)
        entry1.grid(row=1, column=1)
        label2.grid_forget()
        entry2.grid_forget()
        label3.grid_forget()
        entry3.grid_forget()
    elif shape == "球":
        label1.config(text="半径:")
        label1.grid(row=1, column=0)
        entry1.grid(row=1, column=1)
        label2.grid_forget()
        entry2.grid_forget()
        label3.grid_forget()
        entry3.grid_forget()
    elif shape == "圆柱体":
        label1.config(text="半径:")
        label2.config(text="高度:")
        label1.grid(row=1, column=0)
        entry1.grid(row=1, column=1)
        label2.grid(row=2, column=0)
        entry2.grid(row=2, column=1)
        label3.grid_forget()
        entry3.grid_forget()
    elif shape == "圆锥":
        label1.config(text="半径:")
        label2.config(text="高度:")
        label1.grid(row=1, column=0)
        entry1.grid(row=1, column=1)
        label2.grid(row=2, column=0)
        entry2.grid(row=2, column=1)
        label3.grid_forget()
        entry3.grid_forget()

# 创建主窗口
root = tk.Tk()
root.title("几何图形计算器")

# 创建下拉框
shape_var = tk.StringVar()
shapes = ["长方形", "长方体", "圆形", "球", "圆柱体", "圆锥"]
shape_menu = ttk.Combobox(root, textvariable=shape_var, values=shapes)
shape_menu.grid(row=0, column=1)
shape_menu.bind("<<ComboboxSelected>>", update_inputs)

# 创建标签和输入框
label1 = tk.Label(root, text="参数1:")
label1.grid(row=1, column=0)
entry1 = tk.Entry(root)
entry1.grid(row=1, column=1)

label2 = tk.Label(root, text="参数2:")
label2.grid(row=2, column=0)
entry2 = tk.Entry(root)
entry2.grid(row=2, column=1)

label3 = tk.Label(root, text="参数3:")
label3.grid(row=3, column=0)
entry3 = tk.Entry(root)
entry3.grid(row=3, column=1)

# 创建结果显示框
result = tk.StringVar()
result_label = tk.Label(root, textvariable=result)
result_label.grid(row=4, columnspan=2)

# 创建计算按钮
calculate_button = tk.Button(root, text="计算", command=calculate)
calculate_button.grid(row=5, columnspan=2)

# 运行主循环
root.mainloop()
```
