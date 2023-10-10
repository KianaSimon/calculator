# Creating a Graphical Calculator - Using Python and Tkinter
GitHub link for this project:[](https://github.com/KianaSimon/calculator/tree/master)
## 1.Assignment Table

| The Link Your Class                        | https://bbs.csdn.net/forums/ssynkqtd-04       |
| --------------------------------------- | --------------------------------------------- |
| The Link of Requirement of This Assignment |             https://bbs.csdn.net/topics/617332156           |
| The Aim of This Assignment                 | Implement the basic functions of a Calculator |
| MU STU ID and FZU STU ID                   | 21125490_832101308                           |

## 2.PSP Table

|Personal Software Process Stages| Estimated Time（minutes）| Actual Time（minutes）|  
---|---|---  
Planning| 20| 20  
• Estimate| 20| 20  
Development| 480| 360  
• Analysis| 120| 90  
• Design Spec| 20| 20  
• Design Review| 20| 20  
• Coding Standard| 20| 20  
• Design| 60| 30  
• Coding| 120| 120  
• Code Review| 20| 20  
• Test| 100| 40  
Reporting| 240| 270  
• Test Repor| 180| 180  
• Size Measurement| 30| 10  
• Postmortem & Process Improvement Plan| 30| 80  
Sum| 740| 650  

## 3.Description of Problem-Solving Ideas

This article will implement  a graphical calculator program using Python that supports basic arithmetic operations.

##  4.Design and Implementation Process
### 4.1. Graphic Interface Design

We start by creating a Tkinter window with a title and a background color. Then, we use Tkinter's Frame to create a button layout area. In this layout area, we add buttons for digits, operators,an input field, and a result label. 
### 4.2. Calculation Logic

The core logic of the calculator is implemented in the evaluate_expression . The evaluate_expression function calculates basic arithmetic operations. It takes the user's input expression and uses Python's eval function for computation. 

### 4.3.mid map


![img](https://img-community.csdnimg.cn/images/c74ce24225ad4a9ca195c952fcbce1c5.png "#left")


## 5. Code Description
Here are key code snippets:

```python
import tkinter as tk

def on_button_click(event):
    text = event.widget.cget("text")
    if text == "=":
        try:
            result = str(eval(screen.get()))
            screen.set(result)
        except Exception as e:
            screen.set("Error")
    elif text == "C":
        screen.set("")
    else:
        screen.set(screen.get() + text)

root = tk.Tk()
root.geometry("300x400")
root.title("capulator")

screen = tk.StringVar()
entry = tk.Entry(root, textvar=screen, font="lucida 20 bold", bd=8, relief=tk.SUNKEN, justify=tk.RIGHT)
entry.pack(fill=tk.X, ipadx=8, pady=10, padx=10)

button_frame = tk.Frame(root)
button_frame.pack()

buttons = [
    '7', '8', '9', '+',
    '4', '5', '6', '-',
    '1', '2', '3', '*',
    'C', '0', '=', '/'
]

row, col = 1, 0
for button_text in buttons:
    button = tk.Button(button_frame, text=button_text, font="lucida 15 bold", padx=20, pady=20)
    button.grid(row=row, column=col, padx=5, pady=5)
    button.bind("<Button-1>", on_button_click)
    col += 1
    if col > 3:
        col = 0
        row += 1

root.mainloop()


```

## 6. Displaying Result Functions

![img](https://img-community.csdnimg.cn/images/b8e3f532a36a41e1bf7b168aee1b03cd.png "#left")

![img](https://img-community.csdnimg.cn/images/71f1e1fbecd240c0a306d7d6185ec7f7.png "#left")

![img](https://img-community.csdnimg.cn/images/c55ea9d74a044c63bcad6de6f0962238.png "#left")



## 7. Summary

Through this article, we've learned how to create a graphical calculator program using Python's Tkinter library. We've improved the user interface design, enhanced user-friendliness, and added support for basic arithmetic operations and trigonometric functions. This project not only enhances our programming skills but also provides us with a useful tool for everyday calculation tasks.

There's plenty of potential for further expansion and improvement in this project. 
