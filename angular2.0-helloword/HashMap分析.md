---
date: 2018-08-17 10:41
status: public
title: HashMap分析
---

#HashMap
  ```xml
      <select id="findByErpAndPin" resultType="com.jd.dictionary.rbac.domain.User">
        SELECT <include refid="user_filed_sql"/>
        from system_permission_user spu
        where
            spu.is_delete = 0
            and (
            <choose>
                <when  test="erp != null and ''!= erp and (pin == null or pin == '')">
                    spu.erp = #{erp}
                </when>
                <when  test="pin != null and ''!= pin and (erp == null or erp == '')">
                    spu.pin = #{pin}
                </when>
                <when test="erp != null and ''!= erp and pin != null and pin != ''">
                     spu.erp = #{erp} or spu.pin = #{pin}
                </when>
            </choose>
            )
    </select>
  ```
  ```java
public class DdDataServiceCommons {
    
    // 成都jsf接口
    public static final String ddAppVersion = "4.3";

    public static final String ddGetGroupChatSessionLogReqType = "getGroupChatSessionLog";

    //成功获取ACCESS_TOKEN的code码
    public static final Integer DD_MSG_SIGN_SUCCESS = 230031;

    //成功获取消息体内容的code码
    public static final Integer DD_MSG_DATA_REQ_SUC = 230100;


}
```