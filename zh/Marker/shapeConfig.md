# shape参数详情

| 名称 | 类型 | 说明 |
| :--- | :--- | :--- |
| type | String | 可点击区域的类型，可选值：                  -circle:圆形 -poly 多边形 -rect:矩形 |
| coords | Array.&lt;Number&gt; | 可点击区域组成元素数组，存放图形的像素坐标等信息，该数组元素由type决定 |

备注：

coords取值说明：

* type：circle ——coords格式为 \[x1, y1, r\]，x1，y1为圆心像素坐标，r为圆半径

* type：poly ——coords格式为 \[x1, y1, x2, y2 … xn, yn\]，各x，y表示多边形边界像素坐标

* type：rect—— coords格式为 \[x1, y1, x2, y2\]，x1，y1为矩形左上角像素坐标，x2，y2为矩形右下角像素坐标



