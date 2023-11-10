# 1、次元转换
- 说明：三次元转二次元，或相反。
- SD设置：文生图、按需要选择要改的checkpoint模型，Prompt中输入更改后的内容。
- Controlnet：Tile
   + 小幅度变化，选择ControlNet is more important, CFG<5，更改画风的同时，原图片的内容保留较多。
   + 大幅度变化，选择My prompt is more important，CFG<7，可按照prompt的内容，对画面内容进行修改。搭配Lora可以换人。
   + 如果画面中，脸部占比太小，需要用Lineart进行补充控制。

# 2、局部更换
- 说明：如保持脸部，换衣服；或保持衣着，换脸；或换画面风格
- SD设置：文生图、按需要选择要改的checkpoint模型，Prompt中输入更改后的内容。
- Controlnet：Tile + Inpaint global harmonious
   + 降低Tile的wight值，0.5左右
   + Inpaint涂抹画布中要修改的内容，不要选Inpaint only+lama。
   + 如想保持构图不变，可增加Lineart补充控制。
   + 如果涂抹的边缘过度不好，可以再跑一遍Tile，不使用Inpaint。
 
# 3、更换场景
- 说明：白天改成黑夜，夏天改成冬天、人物着火等
- SD设置：文生图、Prompt中输入Make it nighttime/winter/on fire等
- Controlnet：IP2P + Lineart
   + 小幅度变化，选择Balance，有利于场景保持不变，如房屋着火，结冰等；
   + 大幅度变化，不选择Balance，有利于创新场景，如夏天改成冬天，则出现雪地等元素。
   + Lineart用来保持人物换场景，Balance色调不好，My prompt is more important人物有变形，建议ControlNet is more important。

# 4、增加细节
- 说明：使用ControlNet增加图片细节
- SD设置：图生图、Prompt不变
- Controlnet：Tile
   + CFG>15的话，增加细节就不明显了，建议15。
   + Denoising Strength越高，增加细节越多，但是对原话改变越大。
