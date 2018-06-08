【转载】
各种数据类型(日期/时间、integer、floating point和numeric)转换成格式化的字符串以及反过来从格式化的字符串转换成指定的数据类型。下面列出了这些函数，它们都遵循一个公共的调用习 惯：第一个参数是待格式化的值，而第二个是定义输出或输出格式的模板。
函数返回类型描述例子
to_char(timestamp, text)
text
把时间戳转换成字串
to_char(current_timestamp, 'HH12:MI:SS')
to_char(interval, text)
text
把时间间隔转为字串
to_char(interval '15h 2m 12s', 'HH24:MI:SS')
to_char(int, text)
text
把整数转换成字串
to_char(125, '999')
to_char(double precision, text)
text
把实数/双精度数转换成字串
to_char(125.8::real, '999D9')
to_char(numeric, text)
text
把numeric转换成字串
to_char(-125.8, '999D99S')
to_date(text, text)
date
把字串转换成日期
to_date('05 Dec 2000', 'DD Mon YYYY')
to_timestamp(text, text)
timestamp
把字串转换成时间戳
to_timestamp('05 Dec 2000', 'DD Mon YYYY')
to_timestamp(double)
timestamp
把UNIX纪元转换成时间戳
to_timestamp(200120400)
to_number(text, text)
numeric
把字串转换成numeric
to_number('12,454.8-', '99G999D9S')
用于日期/时间格式化的模式：
模式描述
HH一天的小时数(01-12)
HH12一天的小时数(01-12)
HH24一天的小时数(00-23)
MI分钟(00-59)
SS秒(00-59)
MS毫秒(000-999)
US微秒(000000-999999)
AM正午标识(大写)
Y,YYY带逗号的年(4和更多位)
YYYY年(4和更多位)
YYY年的后三位
YY年的后两位
Y年的最后一位
MONTH全长大写月份名(空白填充为9字符)
Month全长混合大小写月份名(空白填充为9字符)
month全长小写月份名(空白填充为9字符)
MON大写缩写月份名(3字符)
Mon缩写混合大小写月份名(3字符)
mon小写缩写月份名(3字符)
MM月份号(01-12)
DAY全长大写日期名(空白填充为9字符)
Day全长混合大小写日期名(空白填充为9字符)
day全长小写日期名(空白填充为9字符)
DY缩写大写日期名(3字符)
Dy缩写混合大小写日期名(3字符)
dy缩写小写日期名(3字符)
DDD一年里的日子(001-366)
DD一个月里的日子(01-31)
D一周里的日子(1-7；周日是1)
W一个月里的周数(1-5)(第一周从该月第一天开始)
WW一年里的周数(1-53)(第一周从该年的第一天开始)
下面是PostgreSQL中支持的时间/日期操作符的列表：
操作符例子结果
+
date '2001-09-28' + integer '7'
date '2001-10-05'
+
date '2001-09-28' + interval '1 hour'
timestamp '2001-09-28 01:00'
+
date '2001-09-28' + time '03:00'
timestamp '2001-09-28 03:00'
+
interval '1 day' + interval '1 hour'
interval '1 day 01:00'
+
timestamp '2001-09-28 01:00' + interval '23 hours'
timestamp '2001-09-29 00:00'
+
time '01:00' + interval '3 hours'
time '04:00'
-
- interval '23 hours'
interval '-23:00'
-
date '2001-10-01' - date '2001-09-28'
integer '3'
-
date '2001-10-01' - integer '7'
date '2001-09-24'
-
date '2001-09-28' - interval '1 hour'
timestamp '2001-09-27 23:00'
-
time '05:00' - time '03:00'
interval '02:00'
-
time '05:00' - interval '2 hours'
time '03:00'
-
timestamp '2001-09-28 23:00' - interval '23 hours'
timestamp '2001-09-28 00:00'
-
interval '1 day' - interval '1 hour'
interval '23:00'
-
timestamp '2001-09-29 03:00' - timestamp '2001-09-27 12:00'
interval '1 day 15:00'
*
interval '1 hour' * double precision '3.5'
interval '03:30'
/
interval '1 hour' / double precision '1.5'
interval '00:40'

select  to_char(to_timestamp(ts),'yyyyMMdd') as day, to_char(to_timestamp(ts),'DDD') as yday from gp_game_result LIMIT 1
