# 周报

   

#### A*算法与人工势场法的融合

![a55afa5b9ef4239be6c1db18c3de1d7](C:\Users\admin\Documents\WeChat Files\wxid_tr41g1c5qkgm22\FileStorage\Temp\a55afa5b9ef4239be6c1db18c3de1d7.png)

  结合a星算法，在a星算法搜索的过程中，使用人工势场法来评估节点代价，帮助决定搜索方向。可以解决人工势场法的局部最优和目标点不可达的问题。

#### 机器人建模

urdf文件语法

- robot 根标签，类似于 launch文件中的launch标签
- link 连杆标签
- joint 关节标签
- gazebo 集成gazebo需要使用的标签

- visual ---> 描述外观(对应的数据是可视的)
  - geometry 设置连杆的形状
    - 标签1: box(盒状)
      - 属性:size=长(x) 宽(y) 高(z)
    - 标签2: cylinder(圆柱)
      - 属性:radius=半径 length=高度
    - 标签3: sphere(球体)
      - 属性:radius=半径
    - 标签4: mesh(为连杆添加皮肤)
      - 属性: filename=资源路径(格式:**package://<packagename>/<path>/文件**)
  - origin 设置偏移量与倾斜弧度
    - 属性1: xyz=x偏移 y便宜 z偏移
    - 属性2: rpy=x翻滚 y俯仰 z偏航 (单位是弧度)
  - metrial 设置材料属性(颜色)
    - 属性: name
    - 标签: color
      - 属性: rgba=红绿蓝权重值与透明度 (每个权重值以及透明度取值[0,1])
- collision ---> 连杆的碰撞属性
- Inertial ---> 连杆的惯性矩阵



- name ---> 为关节命名
- type ---> 关节运动形式
  - continuous: 旋转关节，可以绕单轴无限旋转
  - revolute: 旋转关节，类似于 continues,但是有旋转角度限制
  - prismatic: 滑动关节，沿某一轴线移动的关节，有位置极限
  - planer: 平面关节，允许在平面正交方向上平移或旋转
  - floating: 浮动关节，允许进行平移、旋转运动
  - fixed: 固定关节，不允许运动的特殊关节
