# note
just test

//数组里面循环关键字
foreach($array as $k => $v){
    if(strstr($k, $keyword, true)){
        return $k;
    }
}
//XSS
function clean_xss($string, $low = false)
{
	if (!is_array ($string))
	{
		$string = trim ( $string );
		$string = strip_tags ( $string );
		$string = htmlspecialchars ( $string );
		if ($low)
		{
			return $string;
		}
		$string = str_replace ( array ('"', "\\", "'", "/", "..", "../", "./", "//" ), '', $string );
		$no = '/%0[0-8bcef]/';
		$string = preg_replace ( $no, '', $string );
		$no = '/%1[0-9a-f]/';
		$string = preg_replace ( $no, '', $string );
		$no = '/[\x00-\x08\x0B\x0C\x0E-\x1F\x7F]+/S';
		$string = preg_replace ( $no, '', $string );
		return $string;
	}
}
//变量
$str ='aaa';
$$aaa = 1;

//记录日志
self::logFile($str);
public static function logFile($msg)
{
	$fn = '/tmp/czc_debug.log';
	$fd = @fopen($fn,"a");
	@fwrite($fd, $msg."\r\n");
	@fclose($fd);
}
//strtotime
strtotime('Sunday -6 day',time());本周一
strtotime('last Monday');上周一
strtotime("next Monday");下周一
strtotime("last Sunday");上周日
strtotime("next Sunday");下周日

//rand中去重复值
public function randnum($num){
	$list = array(
		1=>1,
		2=>2,
		3=>3,
		4=>4,
		5=>5,
		6=>6,
		7=>7,
		8=>8,
		9=>9
	);

	unset($list[$num]);
	shuffle($list);

	return $list[1];
}

//unserialize 反序列化失败  因为有引号
public static function mb_unserialize($serial_str) { 
  $serial_str= preg_replace('!s:(\d+):"(.*?)";!se', "'s:'.strlen('$2').':\"$2\";'", $serial_str ); 
  $serial_str= str_replace("\r", "", $serial_str); 
  return unserialize($serial_str); 
} 


//JQ 变量拼接 libaozt
var num1 = 0;
var id = $(this).attr('data-id');
var pnum = eval('num'+id);
eval('num'+id+'++');

//JQ变量转int 进行运算
var nextid = parseInt(id) +1;

//JQ 获取redio值
$("input[name='redioname"+i+"']:checked").val();

//JQ 平滑位移
function go_to(div,top,ms){
	ms = ms || 1000;
	if ( div == 'body' ) {
		div = $('body')
	}
	var o = div.offset();
	var t = parseInt(o.top) - (top || 0);
	//$("html,body").animate({scrollTop:t},ms);
	$("html,body").scrollTop(t);
	return false;
}
//JQ改变宽百分比
$('.j-gamerate').css("width",data.rate+"%");
//radio 不要return

//js 循环
$.each(data.follow, function(key, val) {
	if(val) {
		$('.diy-guanzhu-cl-'+key).addClass('no').text('已关注');
	}
});	
//轮播样式
http://www.h5edu.cn/htm/step/h5edu_893.html
