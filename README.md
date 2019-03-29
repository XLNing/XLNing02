# XLning02
应用js技术实现字符串长度的比较
<!DOCTYPE html>
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <script type="text/javascript">
        function compare()
        {
            var string1 = String(document.getElementById("first_string").value);
            var string2 = String(document.getElementById("second_string").value);
            var len1 = string1.length;
            var len2 = string2.length;
            while(1)
            {
                if(len1 == 0 && len2 == 0)
                {
                    document.getElementById("show_result").value = string1 + '=' + string2;
                    break;
                }
                if(len1 == 0 && len2 != 0 || len1 != 0 && len2 == 0)
                {
                    document.getElementById("show_result").value = string1 + '!=' + string2;
                    break;
                }
                if(len1 > 0&& len2 > 0)
                {
                    var char1,char2;
                    char1 = string1.charAt(0);
                    char2 = string2.charAt(0);
                    if(char1 != char2)
                    {
                        document.getElementById("show_result").value = string1 + '!=' + string2;
                        break;
                    }
                    else
                    {
                        string1 = string1.substring(0);
                        len1 = string1.length;
                        string2 = string2.substring(0);
                        len2 = string2.length;
                    }
                }
            }
        }

        function clean()
        {
            document.getElementById("first_string").value = '';
            document.getElementById("second_string").value = '';
            document.getElementById("show_result").value = '';
        }
    </script>
</head>
<body>
<table border="1" align="center">
    <tr>
        <td colspan="2" align="center">
            字符串比较
        </td>
    </tr>
    <tr>
        <td align="right">
            请输入第一个字符串：
        </td>
        <td>
            <input type="text" name="first" id="first_string"/>
        </td>
    </tr>
    <tr>
        <td align="right">
            请输入第二个字符串：
        </td>
        <td>
            <input type="text" name="second" id="second_string"/>
        </td>
    </tr>
    <tr>
        <td colspan="2" align="center">
            <input type="text" name="show" id="show_result" style="width: 320px"/>
        </td>
    </tr>
    <tr>
        <td colspan="2" align="center">
            <button type="button" id="compare_btn" onclick="compare();">比较</button>
            <input type="button" id="clean_btn" value="清空" onclick="clean()"/>
        </td>
    </tr>
</table>
</body>
</html>

