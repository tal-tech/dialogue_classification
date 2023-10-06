# dialogue_classification

培优呼叫中心聊天记录分类


## 入参样例
```
"家长: 科学课有试课吗
客服: 您问的是否是以下问题，点击或回复序号即可得到对应问题的答案：<br/>1.了解在线课<br/>
家长: 科学课有试课吗
客服: 我帮您看下呢
家长: 好
客服: 您好家长
客服: 我这边帮您看了下目前暂时没有开设科学的单次试听科哦
客服: 您可以等寒假的时候进行下试听， 寒假的第一节课可以作为试听课   在第二节课开课前申请退费的话会退回全部的课程费用哦
客服: 您客气啦~
客服: 山雨欲来风满楼，遇到问题别发愁，欢迎进入人工咨询！很高兴为您服务~
客服: 您好
客服: 请您稍等一下，我需要一些时间帮您查询一下，您放心问题已经锁定，马上回来~~
家长: 好的，谢谢
客服: 请问还有什么可以帮您的呢~
客服: 家长如果没有问题的话，请您对我的服务做出评价，五星好评是我们追求的目标，感谢您ღ( ´･ᴗ･` )比心"
```

## 出参样例
```
{"data": [{"type": "咨询类_课程咨询_报名流程", "prob": "0.6"}, {"type": "财务类_退费类_退费操作方式", "prob": "0.1"}], "code": 0, "msg": "success"}
```

## 错误码
```
-1:input_json_error（输入json有误）
-2:model_predict_failed（模型预测失败）
0:succcess（正常返回）
```

## 接口调用样例

```
from main import classfier

in_text = "家长: 科学课有试课吗\n客服: 您问的是否是以下问题，点击或回复序号即可得到对应问题的答案：<br/>1.了解在线课<br/>\n家长: 科学课有试课吗\n客服: 我帮您看下呢\n家长: 好\n客服: 您好家长\n客服: 我这边帮您看了下目前暂时没有开设科学的单次试听科哦\n客服: 您可以等寒假的时候进行下试听， 寒假的第一节课可以作为试听课   在第二节课开课前申请退费的话会退回全部的课程费用哦\n客服: 您客气啦~\n客服: 山雨欲来风满楼，遇到问题别发愁，欢迎进入人工咨询！很高兴为您服务~\n客服: 您好\n客服: 请您稍等一下，我需要一些时间帮您查询一下，您放心问题已经锁定，马上回来~~\n家长: 好的，谢谢\n客服: 请问还有什么可以帮您的呢~\n客服: 家长如果没有问题的话，请您对我的服务做出评价，五星好评是我们追求的目标，感谢您ღ( ´･ᴗ･` )比心"

out_json = classfier.classify(in_text)
print(out_json)

"""
{'code': 0, 'msg': "success", 'data': [{'name': '咨询类_课程咨询_班次安排（非续报）', 'prob': 0.6040901078415057}]}
"""
```


## 环境及依赖

```

python version 3.6

scikit-learn==0.20.2


```

