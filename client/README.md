# 客户端（控制端Client）说明

# 2021-08-09
当前结构为MVC框架结构：
    main.py         ——程序入口(C--控制器)
        ·在当前脚本初始化了显示窗口，以及与服务端的连接
        ·提供了由M到V的图像显示接口
        ·提供了有V到M的操作信息接口

    RemoteGUI.py    ——图形界面(V--视图)
        ·MainWindow类定义了一个主窗口，并初始化了一个显示窗口
        ·DisplayLabel类显示图像，并且可以通过重写父类方法来监听键鼠操作，在由C提供的接口发送到M。

    ClientTCP.py    ——数据模块(M--模式)
        ·clientTCP类初始化与服务端的连接
        ·将接受到的图像信息通过C提供的接口发送到V
        ·将来自C提供的接口的数据发送到服务端