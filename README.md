<h1>使用方法</h1>

1、引入文件

		<script src="js/jquery-1.12.1.js"></script>
		<script src="js/jquery.validate.js"></script>

1.1 扩展校验js文件

		<script src="js/validate-methods.js"></script>
		
		
	需要默认中文错误提示引入：

		<script src="js/jquery.validate.messages_cn.js"></script>

2 ， html

		<form id="myform" method="post" action="">
            <ul>
                <li>
                    <label for="zero14">数值类型，包括整数和浮点数：</label>
                    <input id="zero14" name="zero14" />
                </li>
                <li>
                    <label for="zero15">只能输入[0-9]数字：</label>
                    <input id="zero15" name="zero15" />
                </li>
                <li>
                    <label for="zero18">手机号码验证：</label>
                    <input id="zero18" name="zero18" />
                </li>
                <li>
                    <label for="zero19">电话号码验证：</label>
                    <input id="zero19" name="zero19" />
                </li>
                <li>
                    <label for="zero20">联系电话(手机/电话皆可)：</label>
                    <input id="zero20" name="zero20" />
                </li>
                <li>
                    <label for="zero21">匹配qq：</label>
                    <input id="zero21" name="zero21" />
                </li>
                <li>
                    <label for="zero22">邮政编码验证：</label>
                    <input id="zero22" name="zero22" />
                </li>
                <li>
                    <label for="zero23">匹配密码，以字母开头，长度在6-12之间，只能包含字符、数字和下划线：</label>
                    <input id="zero23" name="zero23" />
                </li>
                <li>
                    <label for="zero24">身份证号码验证：</label>
                    <input id="zero24" name="zero24" />
                </li>
                <li>
                    <label for="zero25">IP地址验证：</label>
                    <input id="zero25" name="zero25" />
                </li>
                <li>
                    <label for="zero26">字符验证，只能包含中文、英文、数字、下划线等字符：</label>
                    <input id="zero26" name="zero26" />
                </li>
                <li>
                    <label for="zero27">匹配english：</label>
                    <input id="zero27" name="zero27" />
                </li>
                <li>
                    <label for="zero28">匹配汉字：</label>
                    <input id="zero28" name="zero28" />
                </li>
                <li>
                    <label for="zero29">匹配中文(包括汉字和字符)：</label>
                    <input id="zero29" name="zero29" />
                </li>
                <li>
                    <label for="zero30">判断是否为合法字符(a-zA-Z0-9-_)：</label>
                    <input id="zero30" name="zero30" />
                </li>
                <li>
                    <label for="zero31">判断是否包含中英文特殊字符，除英文"-_"字符外：</label>
                    <input id="zero31" name="zero30" />
                </li>
            </ul>
        
		
3 , JS

		<script>
		$(function(){
        var validate = $("#myform").validate({
            rules:{
                zero0:{isIntEqZero:true}, // 判断整数value是否等于0
                zero1:{isIntGtZero:true},// 判断整数value是否大于0
                zero2:{isIntGteZero:true},// 判断整数value是否大于或等于0
                zero3:{isIntNEqZero:true},// 判断整数value是否不等于0
                zero4:{isIntLtZero:true},// 判断整数value是否小于0
                zero5:{isIntLteZero:true},// 判断整数value是否小于或等于0
                zero6:{isFloatEqZero:true},// 判断浮点数value是否等于0
                zero7:{isFloatGtZero:true},// 判断浮点数value是否大于0
                zero8:{isFloatGteZero:true},// 判断浮点数value是否大于或等于0
                zero9:{isFloatNEqZero:true},// 判断浮点数value是否不等于0
                zero10:{isFloatLtZero:true},// 判断浮点数value是否小于0
                zero11:{isFloatLteZero:true},// 判断浮点数value是否小于或等于0
                zero12:{isFloat:true},// 判断浮点型
                zero13:{isInteger:true},// 匹配integer
                zero14:{isNumber:true},// 判断数值类型，包括整数和浮点数
                zero15:{isDigits:true},// 只能输入[0-9]数字
                zero18:{isMobile:true},// 手机号码验证
                zero19:{isPhone:true},// 电话号码验证
                zero20:{isTel:true},// 联系电话(手机/电话皆可)验证
                zero21:{isQq:true},// 匹配qq
                zero22:{isZipCode:true}, // 邮政编码验证
                zero23:{isPwd:true},// 匹配密码，以字母开头，长度在6-12之间，只能包含字符、数字和下划线。
                zero24:{isIdCardNo:true},// 身份证号码验证
                zero25:{ip:true}, // IP地址验证
                zero26:{stringCheck:true}, // 字符验证，只能包含中文、英文、数字、下划线等字符。
                zero27:{isEnglish:true},// 匹配english
                zero28:{isChinese:true},//匹配汉字
                zero29:{isChineseChar:true},//匹配中文(包括汉字和字符)
                zero30:{isRightfulString:true},//判断是否为合法字符(a-zA-Z0-9-_)
                zero31:{isContainsSpecialChar:true} // 判断是否包含中英文特殊字符，除英文"-_"字符外
            },
            //如果验证控件没有message，将调用默认的信息
            messages:{
                zero:{
                    //isIntEqZero:"请输入0"
                    //isFloat:"请输入浮点数"
                    //isInteger:"请输入整数"
                }

            },
            submitHandler: function() {
                //$("#myform").ajaxsubmit();
            },
            showErrors : function(errorMap, element) {
                var msg = "";
                $.each(errorMap, function(sender, message) {
                    msg += (message + "\r\n");
                });
                /*console.log(msg);
                if (msg != ""){
                    alert(msg);
                }*/
                this.defaultShowErrors();
            },
        });
    });
    </script>

4 , 调用方法：

	        $(function(){
                $("#myform").validate({
                        rules:{
                            name:{//需要校验的元素的name
                                property:value
                            }
                        },
                        success:"valid", // 验证通过添加样式
                        messages:{
                            name:{
                                property:messageString //校验提示信息，如果不填，使用默认信息
                            }
                        }
                    });
                });