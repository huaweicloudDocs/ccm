# 创建用户并授权使用PCA<a name="ccm_01_0328"></a>

如果您需要对您所拥有的PCA进行精细的权限管理，您可以使用[统一身份认证服务](https://support.huaweicloud.com/usermanual-iam/iam_01_0001.html)（Identity and Access Management，简称IAM），通过IAM，您可以：

-   根据企业的业务组织，在您的华为云帐号中，给企业中不同职能部门的员工创建IAM用户，让员工拥有唯一安全凭证，并使用PCA资源。
-   根据企业用户的职能，设置不同的访问权限，以达到用户之间的权限隔离。
-   将PCA资源委托给更专业、高效的其他华为云帐号或者云服务，这些帐号或者云服务可以根据权限进行代运维。

如果华为云帐号已经能满足您的要求，不需要创建独立的IAM用户，您可以跳过本章节，不影响您使用PCA服务的其它功能。

本章节为您介绍对用户授权的方法，操作流程如[图 给用户授权PCA权限流程](#zh-cn_topic_0000001124401651_fig673713328586)所示。

## 前提条件<a name="zh-cn_topic_0000001124401651_section121325115513"></a>

给用户组授权之前，请您了解用户组可以添加的PCA权限，并结合实际需求进行选择，PCA支持的系统权限，请参见[CCM系统权限](https://support.huaweicloud.com/productdesc-ccm/ccm_01_0007.html)。若您需要对除CCM之外的其它服务授权，IAM支持服务的所有策略请参见[系统权限](https://support.huaweicloud.com/permissions/policy_list.html?product=ccm)。

## 示例流程<a name="zh-cn_topic_0000001124401651_section1354851316146"></a>

**图 1**  给用户授权PCA权限流程<a name="zh-cn_topic_0000001124401651_fig673713328586"></a>  
![](figures/给用户授权PCA权限流程.png "给用户授权PCA权限流程")

1.  <a name="zh-cn_topic_0000001124401651_li8135822590"></a>[创建用户组并授权](https://support.huaweicloud.com/usermanual-iam/iam_03_0001.html)

    在IAM控制台创建用户组，并授予私有证书管理服务管理员权限“PCA FullAccess“。

2.  [创建用户并加入用户组](https://support.huaweicloud.com/usermanual-iam/iam_02_0001.html)

    在IAM控制台创建用户，并将其加入[1](#zh-cn_topic_0000001124401651_li8135822590)中创建的用户组。

3.  [用户登录](https://support.huaweicloud.com/usermanual-iam/iam_01_0552.html)并验证权限

    新创建的用户登录控制台，切换至授权区域，验证权限：

    在“服务列表”中选择云证书管理服务，若未提示权限不足，表示“PCA FullAccess“已生效。

