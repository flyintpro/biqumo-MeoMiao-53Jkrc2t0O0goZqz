
大家好，我是汤师爷\~


今天聊聊权限系统的应用服务设计。


![](https://img2024.cnblogs.com/other/2625446/202411/2625446-20241113195932246-257002628.png)


从业务需求的角度来看，权限系统需要解决两个核心问题：


**1、菜单渲染与动态展示**


当用户成功登录并接入系统后，系统需要动态获取并展示该用户有权限访问的菜单项。


这一过程涉及前端系统与权限系统的交互。前端系统会向权限系统发送请求，获取用户的权限信息，并根据这些信息动态渲染出用户可见的菜单项。


这种方式保证每个用户只能看到他们有权限访问的功能模块。


**2、后端接口鉴权**


当用户通过前端界面或其他方式请求系统后端接口时，系统需要严格验证用户的权限。


这一步骤能阻止用户访问超出其权限范围的接口。即使某些用户试图绕过前端限制，直接通过接口地址访问，系统仍能有效阻止未经授权的访问，确保安全性。


为了有效解决上述两个关键问题，权限系统需要提供两类核心应用服务：


**1、菜单权限管理**


菜单权限管理服务包含一系列细粒度的权限管理功能，例如角色管理、菜单管理、功能权限管理、API 权限管理、数据权限管理等。同时，还支持用户与角色的绑定，以及用户与特定数据权限的关联。


这些功能让管理员可以精确地为每个用户分配适当的权限，实现对系统资源的精细化控制。


**2、后端鉴权服务**


当用户尝试访问系统的 API 时，后端鉴权服务会实时检查用户的身份和权限信息，并将其与所请求的 API 所需的权限进行匹配。


通过这种实时鉴权机制，系统确保用户只能访问他们有权限使用的 API，有效防止了未经授权的访问和安全风险。



> 本文已收录于，我的技术网站：[tangshiye.cn](https://github.com) 里面有，算法Leetcode详解，面试八股文、BAT面试真题、简历模版、架构设计，等经验分享。


 本博客参考[楚门加速器](https://shexiangshi.org)。转载请注明出处！
