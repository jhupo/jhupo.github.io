---
title: Components Widget
date: 2022-03-30 16:37:06
tags:
- QtCreator
- Components
- Widget 
---

##    自定义标题栏

### 一、实现思路

隐藏系统标题栏，添加窗体作为标题栏。

### 二、实现流程

#### 	1.隐藏系统标题栏

#### 	2.添加控件，Layout布局

#### 	3.

#### 	

### 三、实现代码

```c++
	//TODO:控制窗口移动
	Q_D(QtComponentsWidget);
    if (event->type() == QEvent::HoverMove)
    {
        QHoverEvent *hoverEvent = (QHoverEvent *)event;
        QPoint point = hoverEvent->pos();
        //cur pos calculate move
        int offsetX = point.x() - d->_mousePoint.x();
        int offsetY = point.y() - d->_mousePoint.y();
        if (d->_mousePressed) 
        {
            this->move(this->x() + offsetX, this->y() + offsetY);
        }
    } 
    else if (event->type() == QEvent::MouseButtonPress)
    {
        QMouseEvent *mouseEvent = (QMouseEvent *)event;
        d->_mousePoint = mouseEvent->pos();
        d->_mousePressed = true;
        
    }
    else if (event->type() == QEvent::MouseButtonRelease)
    {
        d->_mousePressed = false;
    }
```



### 四、接口预留
