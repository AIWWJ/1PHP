《PHP入门很简单》
第三章 实战练习-向世界说Hello World!（代码如下）
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Hello World!</title>
    <style>
        #msg
        {
            font-size: 500%;
            margin-left: 60px;
            width: 900px;
            height: 300px;
            line-height: 300px;
            text-align: center;
            overflow: hidden;
        }
        #lang
        {
            font-size: 150%;
            margin-left: 120px;
            height: 80px;
            line-height: 80px;
            text-align: right;
        }
    </style>
</head>
<body>
<div id="msg"></div>
<div id="lang"></div>
<?php
/**
 * Created by PhpStorm.
 * User: Administrator
 * Date: 2016/10/11
 * Time: 23:37
 */
$msgArray=array('fh',
    '世界，你好',
    '世界，妳好',
    'こんにちは',
    'Γεια σας κόσμο',
    'สวัสดีชาวโลก',
    'Сайн байна уу дэлхий',
    'Hallo Welt',
    'Привет мир');
$langArray=array('英语',
    '简体中文',
    '繁体中文',
    '日语',
    '希腊语',
    '泰语',
    '蒙古语',
    '德语',
    '俄语');
$idPrev=0;
for($i=0;$i<=10;$i++)
{
    $id=rand(0,8);
    if($idPrev===$id)
    {
        $id=$idPrev+1;
        if($id>8)
        {
            $id=8;
        }
    }
    $msg=$msgArray[$id];
    $lang=$langArray[$id];
    $idPrev=$id;
    echo '<script language="javascript">
document.getElementById("msg").innerHTML="'.$msg.'"</script>';
    echo '<script language="javascript">
document.getElementById("lang").innerHTML="'.$lang.'"</script>';
    echo str_repeat(' ',1024*64);
    flush();
    sleep(1);
}
?>
</body>
</html>


