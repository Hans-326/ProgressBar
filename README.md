# ProgressBar
#### vue自定义进度条
![样图](../pic/aa.jpg)
## 使用方法
### 在需要使用的vue文件中引入组件
```
import progressBar from '@/components/ProgressBar/ProgressBar';
components:{
			progressBar
		}
```
### 在 template 中使用组件
```
<progress-bar title="批改" :totalCost="item.assignCnt" :drugCost="item.correctCnt" /> 
```

## 属性说明
| 属性名        | 类型    |  必填  | 说明|
| --------   | -----:   | :----: |--------|
| title        | string     |   是    |title为ProgressBar显示名称 |
| totalCost        | number     |   是    |totalCost为ProgressBar显示总量 |
| drugCost        | number     |   是    |drugCost为ProgressBar显示当前量 |
