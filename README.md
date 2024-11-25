#初衷
创建微信公众号,对接淘宝联盟进行发券,用户可以发送商品连接,
后台接收商品连接后解析商品信息,然后到对应的平台查找商品优惠券,返回连接或者商品口令给用户

#问题
    使用ngrok内网穿透可以访问,但是微信发送验证请求时超时.
问题原因:新版的ngrok免费隧道访问时有一个visit验证页面,需要手动确认才可以访问.
解决方案:
    1.在请求头中拼接一个ngrok-skip-browser-warning 参数(因为无法设置微信接口发送请求的请求头,不适用此方式)
    2.使用natapp内网穿透,免费隧道没有验证页面,可以直接使用.(使用此方案解决)

#死路
用户关注后发送信息领券的行为被认定为违反微信公众号运营协议,
实测新创建的公众号用户发送商品链接消息后公众号会被封禁,需要人脸验证解封,
据了解,如果封禁多次将被永久封停,且没有成熟的账号进行测试,
目前想不到办法规避,项目搁浅.