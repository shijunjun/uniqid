# uniqid
生成唯一的ID(整形和62进制的字符串)

#### 用法

```bash
# 下载安装
composer require shijunjun/uniqid
或
git clone https://github.com/shijunjun/uniqid.git
```

```php
/*
 * 生成整数的uniqid
 * ex: 6581098968539725824
 */
echo ($number = \shijunjun\uniqid\Id::getUniqId()) . PHP_EOL;

/*
 * 生成62进制的uniqid
 * ex: 7Q9vbTWnK01
 */
echo ($str_uid = \shijunjun\uniqid\Id::getUniqIdTo62()) . PHP_EOL;

/*
 * 解析62进制字符串的uniqid
 * ex: 7Q9vbTWnK01 => 6581098968539725825 
 */
echo \shijunjun\uniqid\Id::parseUniqIdForm62ToNumber($str_uid) . PHP_EOL;

/*
 * 解析整数uniqid
 * ex : 
 * array (
 *  'date' => '2019-09-21 16:57:45', // 生成时间
 *  'sequence' => 0,                 // 毫秒内自增ID
 *  'time' => 1569056265.006,        // 生成时间戳
 *  'nodeid' => 0,                   // 机器节点ID
 * ) 
 */
var_export(\shijunjun\uniqid\Id::parseUniqId($number));

/*
 * 将62进制的uniqid转化位整数的uniqid
 * ex:
 * array (
 *  'date' => '2019-09-21 16:57:45', // 生成时间
 *  'sequence' => 1,                 // 毫秒内自增ID
 *  'time' => 1569056265.006,        // 生成时间戳
 *  'nodeid' => 0,                   // 机器节点ID
 * ) 
 */
var_export(\shijunjun\uniqid\Id::parseUniqIdForm62($str_uid));

```
