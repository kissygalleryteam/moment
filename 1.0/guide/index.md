## 综述

* Moment是[moment.js v2.5.1](http://momentjs.com/)的KISSY Gallery封装，进行了简单修改以符合KISSY规范，是非常强大的时间格式化、计算、转义、i18n的组件。
* MIT licence

* 版本：1.0
* 作者：承风
* demo：[http://gallery.kissyui.com/moment/1.0/demo/index.html](http://gallery.kissyui.com/moment/1.0/demo/index.html)

## 初始化组件

    S.use('gallery/moment/1.0/index', function (S, Moment) {
         var moment = new Moment();
    });

## API说明
* **时间**转换成**Moment对象**
    * new Moment(String) 传递字符串，常用格式都支持。
    * new Moment(String, FormatString) 传递字符串并告知其格式。
    * new Moment(String, FormatString, I18N) 传递字符串并告知格式和国际化
    * new Moment(Milliseconds) 使用毫秒数初始化
    * new Moment(Date) 使用日期初始化
    * new Moment() 使用当前时间初始化
    * [更多方法](http://momentjs.com/docs/#/parsing/)
* **Moment对象内部方法**
    * `转换为Date`
        * 范例：new Moment().toDate()。
        * 返回值为JavaScript的Date对象。
    * `get/set`
        * 范例：new Moment().`func`(value)。
        * 如果传递了value，为set方法，否则为get。例如new Moment().second()，获取秒数;
        * 如果传递的值超过`进位`，例如new Moment().second(60)，结果是Moment的当前时间增加了1小时。
        * 其中`func`包含如下方法
            * second：秒，低于2位（例如9秒），直接显示1位
            * seconds：秒，返回值强制变成2位（例如03秒）
            * millisecond & milliseconds：毫秒
            * hour & hours：小时
            * date & dates：日期
            * day & days：星期（返回值受i18n影响，慎用）
            * isoWeekday：标准的星期，从1开始，到7结束
            * [更多方法](http://momentjs.com/docs/#/get-set/)
    * `add/subtract/manipulate/subtract`数学计算
        * 范例：new Moment().`func`(String, Number);
        * 其中`func`包含如下方法
            * add：加法
            * subtract：减法
            * [更多方法](http://momentjs.com/docs/#/manipulating/)
    * `format`格式化
        * 范例：new Moment().format(String)。
        * 基本日期格式：
            * YYYY 年，4位
            * YY   年，2位
            * MMMM 月，完整（January February ... November December）
            * MMM  月，简写（Jan Feb ... Nov Dec）
            * MM   月，2位
            * M    月，1位
            * DDDD 日，001 002 ... 364 365
            * DDDo 日，1st 2nd ... 364th 365th
            * DDD  日，1 2 ... 364 365
            * DD   日，01 02 ... 30 31
            * Do   日，1st 2nd ... 30th 31st
            * D    日，1 2 ... 30 31
            * H    时
            * m    分
            * s    秒
            * S    毫秒
        * [完整支持的格式](http://momentjs.com/docs/#/displaying/format/)
    * `i18n`国际化
        * 在引入包后，直接赋值`Moment(i18n)`。
        * 本组件当前只支持`zh-cn`，`zh-tw`，`en`三种语言，默认为英文。
        * [添加更多语言和自定义语言](http://momentjs.com/docs/#/i18n/)

* 更多方法可以访问[moment.js官方文档](http://momentjs.com/docs/)
     
