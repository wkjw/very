竞彩足球，竞彩篮球，北京单场，排列3,排列5，任选九,足球14场,七星彩,大乐透,足球比赛，足球数据，足球算法，足球下单,体彩

为了巩固自己的算法，自己写了一套如下的竞彩官网的计算注数，预测金额，赔率，开奖的算法

郑重申明，不要用于用户商业用途，如执意进行违法操作，与本人无任何关系
## 联系方式1：请下载Letstalk 请添加好友 t283141315
## 联系方式2：飞机Telegram 请添加好友 mogu667

1.  即将上线演示环境  <br>
APP体验地址:https://uns.dfg145.cfd/dg/app/html/index.html<br>
账户17777777777 密码123456 <br>
手机端后台体验地址:https://uns.dfg145.cfd/dg/admin/html/index.html<br>
账户admin 密码123456 <br>
PC端电脑后台体验地址: https://udm.dfg145.cfd<br>
账户admin 密码123456 <br>

<br>

#### 最近发现一个拿我以前开源很多bug的老版本在低价进行售卖，通过小号QQ进行诱骗，请大家注意了，已经骗了很多人。
#### 骗子gitee地址:  https://gitee.com/sports-lottery-source-code
#### 骗子github地址: https://github.com/lottery-code
#### 骗子用的小号QQ: 419367301
#### 这是被骗的人反馈给我的
[https://ppm-pics-res.s3.ap-southeast-1.amazonaws.com/cms/44249FFF746346F4B8628EECE641D0D1.png](https://ppm-pics-res.s3.ap-southeast-1.amazonaws.com/cms/44249FFF746346F4B8628EECE641D0D1.png)

<br>

#### 截图   全是一体化


### 搭建教程
[搭建教程](https://youtu.be/7BIIAtqUiUI)


## 足球竞赛
足球竞赛投注有两种模式，*单关* 和 *串关*。

单关投注计算方式是从投注比赛中每场选一个投注项和其它场次组合成一个最终投注单。形式简单不多介绍。

### 串关玩法介绍
共有6种玩法，*胜平负*，*让球胜平负*，*比分*，*半全场*，*总进球*，*混合过关*。不同玩法规则下每场比赛的投注选项不一样：
+ 胜平负

    每场比赛有三个投注选项。

        ['胜'，'平'，'负']
+ 让球胜平负

    每场比赛有三个投注选项。

        ['让胜'，'让平'，'让负']
+ 比分

    每场比赛有31个投注选项。
    
        [
            '1:0', '2:0', '2:1', '3:0', '3:1', '3:2', '4:0', '4:1', '4:2', '5:0', '5:1', '5:2', '胜其他',
            '0:0', '1:1', '2:2', '3:3', '平其他',
            '0:1', '0:2', '1:2', '0:3', '1:3', '2:3', '0:4', '1:4', '2:4', '0:5', '1:5', '2:5', '负其他'
        ]
+ 半全场

    每场比赛有9个投注选项。

        ['胜胜', '胜平', '胜负', '平胜', '平平', '平负', '负胜', '负平', '负负']
+ 总进球

    每场比赛有8个投注选项。

        ['0', '1', '2', '3', '4', '5', '6', '7+']
+ 混合

    每场比赛投注选项由以上选项混合而成。

### 串关过关方式
足球竞彩投注，用户至少选择两场比赛，最多选10-15场进行投注，每场比赛可选多个投注项。串关是对所选比赛场数进行组合搭配的一种快捷方法，`M串N` 计作 `MxN`。最多8串。

串关模式下过关方式分为两种：
1. 自由过关

    自由选择过关的场数组合，可选2场、3场...8场。分别组成串关组合，如2串1，3串1...8串1。投注时可多选。
2. 多串过关

    按照固定的模式对场数组合，至少3场，如3串3，3串4...8串247。投注时不可多选。
    
    *固定模式的一般解释*：对投注比赛场次先按照过关场数进行分组，然后对每组按照过关分组数区间进行分组，最终对分组后每组内的比赛每场选一个投注项进行组合。
    
    例如：有投注比赛`['A','B','C','D']`（ABCD分别代表一场比赛的投注内容，每场比赛可选多个内容），选择模式`3串3`，则过关场数是3，对该投注结果先按照3场一组进行组合得到
        
        [ 
            [ 'A' , 'B' , 'C' ],
            [ 'A' , 'B' , 'D' ],
            [ 'A' , 'C' , 'D' ],
            [ 'B' , 'C' , 'D' ]
        ]
    又`3串3`的过关分组数区间为2，然后对分组后的每组按照2场一组进行组合得到

        [ 
            [ 'A', 'B' ],
            [ 'A', 'C' ],
            [ 'B', 'C' ],
            [ 'A', 'B' ],
            [ 'A', 'D' ],
            [ 'B', 'D' ],
            [ 'A', 'C' ],
            [ 'A', 'D' ],
            [ 'C', 'D' ],
            [ 'B', 'C' ],
            [ 'B', 'D' ],
            [ 'C', 'D' ] 
        ] 
    再然后对每一组的投注内容进行交叉组合，最后形成多个投注项。假设比赛'A'投注内容为`['胜','平']`，'B'投注内容为`['让平','让负']`，则以上分组['A','B']形成投注项为
    
        [
            ['胜', '让平'],
            ['胜', '让负'],
            ['平', '让平'],
            ['平', '让负'],
        ]
以此类推，遍历计算每组比赛投注内容的组合，得出最后的投注组合。
