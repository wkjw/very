有不懂的可以联系我，一起互相学习 (仅供学习)
## 联系方式 QQ：请添加好友 536469947
## 联系方式1：请下载Letstalk 请添加好友 t283141315
## 联系方式2：飞机Telegram 请添加好友 mogu667

1.  即将上线演示环境  <br>
体验地址:https://distribute.zbbino.com/mq/31/html/index.html<br>
账户17777777777 密码123456

#### 截图   全是一体化


### 手机移动端,页面自适应
![image](https://ppm-pics-res.s3.ap-southeast-1.amazonaws.com/bandicam-2023-06-04-15-43-41-935_1.gif)
![image](https://ppm-pics-res.s3.ap-southeast-1.amazonaws.com/cms/002228054fd65a2552a1cdc2e9a970e5.png)

### 后台端,页面自适应
![输入图片说明](https://ppm-pics-res.s3.ap-southeast-1.amazonaws.com/bandicam-2023-06-04-15-48-38-071.gif)

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
