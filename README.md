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

### 一、所使用的的API
* 百度API[短语音识别](https://ai.baidu.com/tech/speech/asr)
* 百度API[在线语音合成](https://ai.baidu.com/tech/speech/tts)

### 一、使用水平 
1. 功能一：语音识别（百度AI）

* 输入代码：

```
# coding=utf-8

import sys
import json
import base64
import time

IS_PY3 = sys.version_info.major == 3

if IS_PY3:
    from urllib.request import urlopen
    from urllib.request import Request
    from urllib.error import URLError
    from urllib.parse import urlencode
    timer = time.perf_counter
else:
    from urllib2 import urlopen
    from urllib2 import Request
    from urllib2 import URLError
    from urllib import urlencode
    if sys.platform == "win32":
        timer = time.clock
    else:
        # On most other platforms the best timer is time.time()
        timer = time.time

API_KEY = 'kVcnfD9iW2XVZSMaLMrtLYIz'
SECRET_KEY = 'O9o1O213UgG5LFn0bDGNtoRN3VWl2du6'

# 需要识别的文件
AUDIO_FILE = './audio/16k.pcm'  # 只支持 pcm/wav/amr 格式，极速版额外支持m4a 格式
# 文件格式
FORMAT = AUDIO_FILE[-3:]  # 文件后缀只支持 pcm/wav/amr 格式，极速版额外支持m4a 格式

CUID = '123456PYTHON'
# 采样率
RATE = 16000  # 固定值

# 普通版

DEV_PID = 1536  # 1537 表示识别普通话，使用输入法模型。1536表示识别普通话，使用搜索模型。根据文档填写PID，选择语言及识别模型
ASR_URL = 'http://vop.baidu.com/server_api'
SCOPE = 'audio_voice_assistant_get'  # 有此scope表示有asr能力，没有请在网页里勾选，非常旧的应用可能没有

# 忽略scope检查，非常旧的应用可能没有
# SCOPE = False

class DemoError(Exception):
    pass


"""  TOKEN start """

TOKEN_URL = 'http://openapi.baidu.com/oauth/2.0/token'


def fetch_token():
    params = {'grant_type': 'client_credentials',
              'client_id': API_KEY,
              'client_secret': SECRET_KEY}
    post_data = urlencode(params)
    if (IS_PY3):
        post_data = post_data.encode( 'utf-8')
    req = Request(TOKEN_URL, post_data)
    try:
        f = urlopen(req)
        result_str = f.read()
    except URLError as err:
        print('token http response http code : ' + str(err.code))
        result_str = err.read()
    if (IS_PY3):
        result_str =  result_str.decode()

    print(result_str)
    result = json.loads(result_str)
    print(result)
    if ('access_token' in result.keys() and 'scope' in result.keys()):
        print(SCOPE)
        if SCOPE and (not SCOPE in result['scope'].split(' ')):  # SCOPE = False 忽略检查
            raise DemoError('scope is not correct')
        print('SUCCESS WITH TOKEN: %s  EXPIRES IN SECONDS: %s' % (result['access_token'], result['expires_in']))
        return result['access_token']
    else:
        raise DemoError('MAYBE API_KEY or SECRET_KEY not correct: access_token or scope not found in token response')

"""  TOKEN end """

if __name__ == '__main__':
    token = fetch_token()

    speech_data = []
    with open(AUDIO_FILE, 'rb') as speech_file:
        speech_data = speech_file.read()

    length = len(speech_data)
    if length == 0:
        raise DemoError('file %s length read 0 bytes' % AUDIO_FILE)
    speech = base64.b64encode(speech_data)
    if (IS_PY3):
        speech = str(speech, 'utf-8')
    params = {'dev_pid': DEV_PID,
             #"lm_id" : LM_ID,    #测试自训练平台开启此项
              'format': FORMAT,
              'rate': RATE,
              'token': token,
              'cuid': CUID,
              'channel': 1,
              'speech': speech,
              'len': length
              }
    post_data = json.dumps(params, sort_keys=False)
    # print post_data
    req = Request(ASR_URL, post_data.encode('utf-8'))
    req.add_header('Content-Type', 'application/json')
    try:
        begin = timer()
        f = urlopen(req)
        result_str = f.read()
        print ("Request time cost %f" % (timer() - begin))
    except URLError as err:
        print('asr http response http code : ' + str(err.code))
        result_str = err.read()

    if (IS_PY3):
        result_str = str(result_str, 'utf-8')
    print(result_str)
    with open("result.txt","w") as of:
        of.write(result_str)

```

* 输出：

```
{"corpus_no":"6595003755536106531","err_msg":"success.","err_no":0,"result":["北京科技馆，"],"sn":"611278720461535518969"}
```
2. 功能二：语音合成（百度AI）

* 输入代码：

```
# coding=utf-8
import sys
import json

IS_PY3 = sys.version_info.major == 3
if IS_PY3:
    from urllib.request import urlopen
    from urllib.request import Request
    from urllib.error import URLError
    from urllib.parse import urlencode
    from urllib.parse import quote_plus
else:
    import urllib2
    from urllib import quote_plus
    from urllib2 import urlopen
    from urllib2 import Request
    from urllib2 import URLError
    from urllib import urlencode

API_KEY = '4E1BG9lTnlSeIf1NQFlrSq6h'
SECRET_KEY = '544ca4657ba8002e3dea3ac2f5fdd241'

TEXT = "欢迎使用百度语音合成。"

# 发音人选择, 基础音库：0为度小美，1为度小宇，3为度逍遥，4为度丫丫，
# 精品音库：5为度小娇，103为度米朵，106为度博文，110为度小童，111为度小萌，默认为度小美 
PER = 4
# 语速，取值0-15，默认为5中语速
SPD = 5
# 音调，取值0-15，默认为5中语调
PIT = 5
# 音量，取值0-9，默认为5中音量
VOL = 5
# 下载的文件格式, 3：mp3(default) 4： pcm-16k 5： pcm-8k 6. wav
AUE = 3

FORMATS = {3: "mp3", 4: "pcm", 5: "pcm", 6: "wav"}
FORMAT = FORMATS[AUE]

CUID = "123456PYTHON"

TTS_URL = 'http://tsn.baidu.com/text2audio'


class DemoError(Exception):
    pass


"""  TOKEN start """

TOKEN_URL = 'http://openapi.baidu.com/oauth/2.0/token'
SCOPE = 'audio_tts_post'  # 有此scope表示有tts能力，没有请在网页里勾选


def fetch_token():
    print("fetch token begin")
    params = {'grant_type': 'client_credentials',
              'client_id': API_KEY,
              'client_secret': SECRET_KEY}
    post_data = urlencode(params)
    if (IS_PY3):
        post_data = post_data.encode('utf-8')
    req = Request(TOKEN_URL, post_data)
    try:
        f = urlopen(req, timeout=5)
        result_str = f.read()
    except URLError as err:
        print('token http response http code : ' + str(err.code))
        result_str = err.read()
    if (IS_PY3):
        result_str = result_str.decode()

    print(result_str)
    result = json.loads(result_str)
    print(result)
    if ('access_token' in result.keys() and 'scope' in result.keys()):
        if not SCOPE in result['scope'].split(' '):
            raise DemoError('scope is not correct')
        print('SUCCESS WITH TOKEN: %s ; EXPIRES IN SECONDS: %s' % (result['access_token'], result['expires_in']))
        return result['access_token']
    else:
        raise DemoError('MAYBE API_KEY or SECRET_KEY not correct: access_token or scope not found in token response')


"""  TOKEN end """

if __name__ == '__main__':
    token = fetch_token()
    tex = quote_plus(TEXT)  # 此处TEXT需要两次urlencode
    print(tex)
    params = {'tok': token, 'tex': tex, 'per': PER, 'spd': SPD, 'pit': PIT, 'vol': VOL, 'aue': AUE, 'cuid': CUID,
              'lan': 'zh', 'ctp': 1}  # lan ctp 固定参数

    data = urlencode(params)
    print('test on Web Browser' + TTS_URL + '?' + data)

    req = Request(TTS_URL, data.encode('utf-8'))
    has_error = False
    try:
        f = urlopen(req)
        result_str = f.read()

        headers = dict((name.lower(), value) for name, value in f.headers.items())

        has_error = ('content-type' not in headers.keys() or headers['content-type'].find('audio/') < 0)
    except  URLError as err:
        print('asr http response http code : ' + str(err.code))
        result_str = err.read()
        has_error = True

    save_file = "error.txt" if has_error else 'result.' + FORMAT
    with open(save_file, 'wb') as of:
        of.write(result_str)

    if has_error:
        if (IS_PY3):
            result_str = str(result_str, 'utf-8')
        print("tts api  error:" + result_str)

    print("result saved as :" + save_file)
```

 * 输出：
 
 ```
 result saved as :result.mp3
 ```



### 二、使用比较分析
* 语音识别api对比

|   对比项  |  百度AI   |  阿里云   |
| --- | --- | --- |
|   性价比  |  按调用量计费，前5万次调用免费。默认为限额为5QPS，开通付费后限额提升至50QPS   |   1.8元/小时  |
|   成熟度  |  中文普通话识别准确率达98%、多语言识别、批量音频快速识别、根据语音智能匹配合适的标点符号，。！？语音识别标准版可以将语音精准识别为文字，适用于手机语音输入、语音搜索、智能语音对话等场景。包含中文普通话输入法、中文普通话搜索、英语、粤语、四川话、远场6个识别模型。其中Android，iOS，Linux SDK支持唱过60秒的实时场语音识别   |   可以使用自学习平台等工具改善语音识别效果，而且提供了功能更丰富的管理控制台和更易用的SD  |

* 语音合成api对比

|   对比项  |  百度AI   |  阿里云   |
| --- | --- | --- |
|   性价比  |  有免费额度，企业认证基础音库100QPS   |   1.8元/小时  |
|   成熟度  |  语音合成可将文字信息转化为声音信息，适用于手机APP、儿童故事机、智能机器人等多种应用场景。基于业界领先的深度神经网络技术，提供高度拟人、流畅自然的语音合成服务，让您的应用、设备开口说话，更具个性。  |   语音合成提供将输入文本合成为语音二进制数据的功能。支持输出pcm、wav、mp3编码格式数据；支持设置语速，语调，音量。支持设置男声/女声；  |

### 三、使用后风险报告

|   风险性  |  解决方法   |
| --- | --- |
|   音频质量过差，杂音较多  |  保持手机离麦克风比较近，尽量在安静的环境下打电话   |
|   语音识别的延迟性  |  使用较快的网络   |
