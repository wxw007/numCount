# numCount
获取验证码倒计时
说明: #getCode 为包裹倒计时数字的容器id
```function(){
  var n = 5;
    $("#getCode").click(function(event) {
        var text = $(this).text();
        if (text != '获取验证码') {
            return
        } else {
            var t = setInterval(numCount, 1000)
            function numCount() {
                if (n > 1) {
                    n = n - 1;
                    $("#getCode").text(n + 'S');
                } else {
                    clearInterval(t);
                    n = 5
                    $("#getCode").text('获取验证码');
                    return
                }
            }
        }
    });
}
