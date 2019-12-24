# APP:Keep Calling(保持通话)

## Product Requirement（产品说明文档）
|  Title   |  Content   |
| --- | --- |
|  Target release（发布日期）   |   2019-11-26  |
|   Epic（名称）  |   Keep Calling  |
|  Document status(文档状态)   |   进行中  |
|  Document owner(文件主人)   |  曾嘉悦   |
|   Designer(领头的设计师)  |  曾嘉悦   |
|   Developer(领头的开发者)  |  曾嘉悦   |    
|   QA(领头的测试者)  |  曾嘉悦   |


# PRD 价值主张设计

### 一、背景
随着高科技与智能手机逐渐在人们的生活中普及，它们方便了许多人的生活。但是对于一部分特殊人群来说，高科技对于他们而言反而让他们与身边的人的交流产生障碍。这个世界上有7000万失聪患者，他们基本上失去了百分之八十甚至百分之百的听力，对于他们来说唇语或者手语是唯一的交流方式。在老年人人群中，超过65岁的老人们基本都会有听力下降的问题。这时，一个能让聋哑人打电话的app似乎就能解决他们沟通困难的问题，让他们的交流成为可能。

### 二、加值宣言
本产品皆在通过使用阿里云人工智能的部分功能（语音识别、语音合成）使聋哑人以及听力衰退的老人也能像正常人用手机打电话，进行基本的社交活动。

* 语音合成API对本产品价值部分在于：高度拟人、流畅自然的语音合成，提供多场景音库；语速、音调可调节；支持多音字标注。（优先级）
* 语音识别API对本产品价值部分在于：将语音快速准确识别为文字，支持手机应用语音交互、语音内容分析。（优先级）


### 三、核心价值（最小可行性产品）
本产品主要面向聋哑人，听力受损的群体，调用语音识别、语音合成API，解决聋哑人难以打电话的问题，方便聋哑人进行基本的社交。

### 四、实现目标
1. 使聋哑人顺畅的与正常人进行交流。
2. 在遇到紧急情况下，让聋哑人也可以通过电话进行求救。

### 五、目标用户
* 聋哑人
* 听力受损的人群

### 六、核心价值与用户痛点 

|   加值  |  用户痛点   |
| --- | --- |
|   文字转语音功能可以让哑巴“开口说话”  |  遇到紧急情况的时候，电话就成了非常重要的联络的工具   |
|   实时语音转写功能可以增加他们的交流方式  |  对于聋哑人来说唇语或者手语是唯一的交流方式   |
|   语音转文字与文字合成语音的双向功能可以使他们正常交流 |  聋哑人无法通过手机打电话   |
|   实时语音转写功能可以使听力受损的人正常接收他人语音信息  |  老年人人群中，超过65岁的老人们基本都会有听力下降的问题   |

### 七、人工智能概率性与用户痛点
* 痛点
1. 语音太模糊，导致识别的准确率低
2. 可能存在部分聋哑人不识字的现象
3. 可能出现普通话不标准，讲方言的问题

* 百度AI中的语音识别api：
1. 采用国际领先的流式端到端语音语言一体化建模算法，将语音快速准确识别为文字，支持手机应用语音交互、语音内容分析、机器人对话等多个场景。
2. 基于Deep Peak2端到端建模，超过10万小时数据训练，多采样率多场景声学建模，近场中文普通话识别准确率达98%。
3. 支持普通话和略带口音的中文识别；支持粤语、四川话方言识别；支持英文识别。

* 百度AI中的语音合成api：
1. 语音合成api提供基础音库和精品音库共9种音库供您选择，适用于泛阅读、订单播报、智能硬件等应用场景，即将推出更多特色音库。
2. 支持多种参数配置，可根据场景需求对音库的语速、音调、音量进行灵活设置，满足个性化需求。


### 八、需求列表与人工智能API加值
#### 需求列表
|   用户案例  |  对应API   |  重要程度   |
| --- | --- | --- |
|   文字转语音  |  语音合成api   |   极其重要  |
|   实时语音转写  |  语音识别api   |   极其重要  |

#### 具体运用场景
1. 聋人A的妈妈给小明打电话，告诉小明今晚妈妈要加班，但是她无法听见妈妈的声音，于是他运用保持通话app中的实时语音转写功能,看到妈妈想要告知他的信息。
2. 哑巴B遇到了紧急的情况想打110求助，但是他不能像常人一样拨号说话，此时他打开保持通话app中的文字转语音功能，给警察打电话，告知具体情况。

# 原型
### 一、交互及界面设计
APP中的语音识别功能和语音合成功能，运用百度AI的语音识别api与语音合成api。

* 最近通话页面

![最近通话](https://images.gitee.com/uploads/images/2019/1224/204310_0c067a95_1648179.png "最近通话.png")

* 通讯录页面

![通讯录](https://images.gitee.com/uploads/images/2019/1224/204800_aad42d46_1648179.png "通讯录.png")

* 拨号页面

![拨号](https://images.gitee.com/uploads/images/2019/1224/204818_fdc783ab_1648179.png "拨号.png")
![通话中](https://images.gitee.com/uploads/images/2019/1224/204834_6276fece_1648179.png "通话中.png")

* 我的页面

![我](https://images.gitee.com/uploads/images/2019/1224/204848_bc469c80_1648179.png "我.png")

### 二、信息设计
* APP打电话中说出对话将语音转为文字功能运用实时语音转写API，输出文本，实现语音转文字功能
* APP打电话中将文字转为语音功能运用实时语音转写API，输入音频，输出文本，实现音频转文字功能

![架构图](https://images.gitee.com/uploads/images/2019/1224/205346_ffb5ae87_1648179.png "架构图.png")

### 三、原型文档
原型文档：多少程度上有提供MVP可交互的原型文档，供它人在Github上下载使用

### 四、口头操作说明
大家好，我们团队做的项目是一款让聋哑人也能打电话的app，app名字叫keep calling 保持通话。keep calling是一款方便聋哑人打电话的App,它具有语音转化成文字以及文字转化成语音的双向功能，使他们的交流成为可能。本产品通过使用百度AI的语音识别api、语音合成api使聋哑人以及听力衰退的老人也能像正常人用手机打电话，进行基本的社交活动。语音合成API对本产品价值部分在于：高度拟人、流畅自然的语音合成，提供多场景音库；语速、音调可调节；支持多音字标注。语音识别API对本产品价值部分在于：将语音快速准确识别为文字，支持手机应用语音交互、语音内容分析。用户只需用此app打电话，即可将接收到的语音转为文字呈现给用户，同时用户可以输入文字，即可合成语音自动发送给对方。

# 产品使用关键AI或机器学习之API的输出入展示
### 一、使用水平 
使用水平：输入
    ```
    # -*- coding: utf8 -*-
import json
import time
from aliyunsdkcore.acs_exception.exceptions import ClientException
from aliyunsdkcore.acs_exception.exceptions import ServerException
from aliyunsdkcore.client import AcsClient
from aliyunsdkcore.request import CommonRequest
def fileTrans(akId, akSecret, appKey, fileLink) :
    # 地域ID，常量内容，请勿改变
    REGION_ID = "cn-shanghai"
    PRODUCT = "nls-filetrans"
    DOMAIN = "filetrans.cn-shanghai.aliyuncs.com"
    API_VERSION = "2018-08-17"
    POST_REQUEST_ACTION = "SubmitTask"
    GET_REQUEST_ACTION = "GetTaskResult"
    # 请求参数key
    KEY_APP_KEY = "appkey"
    KEY_FILE_LINK = "file_link"
    KEY_VERSION = "version"
    KEY_ENABLE_WORDS = "enable_words"
    # 是否开启智能分轨
    KEY_AUTO_SPLIT = "auto_split"
    # 响应参数key
    KEY_TASK = "Task"
    KEY_TASK_ID = "TaskId"
    KEY_STATUS_TEXT = "StatusText"
    KEY_RESULT = "Result"
    # 状态值
    STATUS_SUCCESS = "SUCCESS"
    STATUS_RUNNING = "RUNNING"
    STATUS_QUEUEING = "QUEUEING"
    # 创建AcsClient实例
    client = AcsClient(akId, akSecret, REGION_ID)
    # 提交录音文件识别请求
    postRequest = CommonRequest()
    postRequest.set_domain(DOMAIN)
    postRequest.set_version(API_VERSION)
    postRequest.set_product(PRODUCT)
    postRequest.set_action_name(POST_REQUEST_ACTION)
    postRequest.set_method('POST')
    # 新接入请使用4.0版本，已接入(默认2.0)如需维持现状，请注释掉该参数设置
    # 设置是否输出词信息，默认为false，开启时需要设置version为4.0
    task = {KEY_APP_KEY : appKey, KEY_FILE_LINK : fileLink, KEY_VERSION : "4.0", KEY_ENABLE_WORDS : False}
    # 开启智能分轨，如果开启智能分轨 task中设置KEY_AUTO_SPLIT : True
    # task = {KEY_APP_KEY : appKey, KEY_FILE_LINK : fileLink, KEY_VERSION : "4.0", KEY_ENABLE_WORDS : False, KEY_AUTO_SPLIT : True}
    task = json.dumps(task)
    print(task)
    postRequest.add_body_params(KEY_TASK, task)
    taskId = ""
    try :
        postResponse = client.do_action_with_exception(postRequest)
        postResponse = json.loads(postResponse)
        print (postResponse)
        statusText = postResponse[KEY_STATUS_TEXT]
        if statusText == STATUS_SUCCESS :
            print ("录音文件识别请求成功响应！")
            taskId = postResponse[KEY_TASK_ID]
        else :
            print ("录音文件识别请求失败！")
            return
    except ServerException as e:
        print (e)
    except ClientException as e:
        print (e)
    # 创建CommonRequest，设置任务ID
    getRequest = CommonRequest()
    getRequest.set_domain(DOMAIN)
    getRequest.set_version(API_VERSION)
    getRequest.set_product(PRODUCT)
    getRequest.set_action_name(GET_REQUEST_ACTION)
    getRequest.set_method('GET')
    getRequest.add_query_param(KEY_TASK_ID, taskId)
    # 提交录音文件识别结果查询请求
    # 以轮询的方式进行识别结果的查询，直到服务端返回的状态描述符为"SUCCESS"、"SUCCESS_WITH_NO_VALID_FRAGMENT"，
    # 或者为错误描述，则结束轮询。
    statusText = ""
    while True :
        try :
            getResponse = client.do_action_with_exception(getRequest)
            getResponse = json.loads(getResponse)
            print (getResponse)
            statusText = getResponse[KEY_STATUS_TEXT]
            if statusText == STATUS_RUNNING or statusText == STATUS_QUEUEING :
                # 继续轮询
                time.sleep(3)
            else :
                # 退出轮询
                break
        except ServerException as e:
            print (e)
        except ClientException as e:
            print (e)
    if statusText == STATUS_SUCCESS :
        print ("录音文件识别成功！")
    else :
        print ("录音文件识别失败！")
    return
accessKeyId = "您的AccessKey Id"
accessKeySecret = "您的AccessKey Secret"
appKey = "您的appkey"
fileLink = "https://aliyun-nls.oss-cn-hangzhou.aliyuncs.com/asr/fileASR/examples/nls-sample-16k.wav"
fileTrans(accessKeyId, accessKeySecret, appKey, fileLink)
    ```

### 二、使用比较分析
使用比较分析：在PRD文件中是否有说明且提供连结证据，所使用的API是查找过最适用的（主要竞争者无或比较次），如考量其成熟度丶性价比丶等等

### 三、使用后风险报告
使用后风险报告：在PRD文件中是否有说明且提供连结证据，所使用的API类别的现在及未来发展性，如API市场竞争程度丶输入输出限制丶定价丶及可替代的程序库（改用自己开发的代码及数据库而不用API）等等


