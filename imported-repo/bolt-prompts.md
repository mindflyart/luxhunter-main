# LuxHunter Bolt AI Prompts

## Prompt 1: Airtable Integration

```
在 LuxHunter 网站添加 Airtable CRM 集成功能：

1. 创建文件 src/utils/airtable.js：
   - 使用 Airtable API Token: YOUR_AIRTABLE_TOKEN_HERE
   - Base ID: appOtJp0W9w7w7Jqw
   - Table: Leads
   - 函数 saveLeadToAirtable(leadData) - 保存线索
   - 函数 getLeadsFromAirtable() - 获取所有线索

2. 修改 Calculator 组件：
   - 在表单提交时，除了保存到 Supabase，同时调用 saveLeadToAirtable
   - 添加字段：Full Name, Email, Phone（必填）
   - 映射字段：
     * Name → leadData.name
     * Email → leadData.email  
     * Phone → leadData.phone
     * Source → "Calculator"
     * Interest → [用户选择的interest]
     * Budget → propertyPrice
     * Landing Page → "/calculator"
     * Notes → 包含 buyingFor, state 等信息

3. 修改 Free Report Modal：
   - 同样集成 saveLeadToAirtable
   - Source → "Free Report"
   - 提交后显示："报告将发送到您的邮箱"

4. 测试：
   - 提交表单后检查 Airtable 是否有新记录
```

## Prompt 2: Landing Page

```
在 LuxHunter 网站添加新的 Landing Page：

1. 创建路由 /lead 或 /report

2. 页面设计（Kit 风格）：
   - 暖黄色背景 (#FEF3C7)
   - 单页滚动布局
   - Section 1: Hero - 大标题"澳洲房产投资首购者完整指南"
   - Section 2: 痛点 - "收入不够银行要求？" "担心多付数万利息？"
   - Section 3: 解决方案 - 房产顾问服务 + 贷款优化服务
   - Section 4: 故事 - 引用文案建立信任
   - Section 5: 表单 - 姓名、邮箱、电话、兴趣、预算

3. 表单功能：
   - 提交到 Airtable（使用 airtable.js）
   - 提交后显示感谢信息
   - 可选：添加 Calendly 预约按钮

4. 样式要求：
   - 响应式设计
   - 简洁专业
   - 与现有网站风格协调
```

## Prompt 3: Calendly Integration

```
在 LuxHunter 网站添加 Calendly 预约功能：

1. 注册 Calendly（用户已完成）
   - 邮箱: info@luxhunter.com
   - 设置可用时间

2. 添加预约按钮：
   - 在 Contact 页面添加"预约免费咨询"按钮
   - 在 Landing Page 表单后添加"或直接预约"选项
   - 点击弹出 Calendly 弹窗

3. 嵌入代码：
   - 使用 Calendly 提供的嵌入代码
   - 或弹出窗口方式

4. 样式：
   - 按钮使用品牌色（暖黄/黑色）
   - 与网站风格一致
```

## Prompt 4: Admin Dashboard Extension

```
扩展 LuxHunter Admin 后台功能：

1. 当前已有：Featured Properties CRUD

2. 添加新功能：
   - News/Blog 管理：标题、内容、日期、状态
   - Newsletter 内容管理：邮件标题、内容、发送状态
   - Loan Policy 数据：利率、银行、产品类型、更新日期

3. 每个功能需要：
   - 列表页（查看所有记录）
   - 创建页（添加新记录）
   - 编辑页（修改记录）
   - 删除功能

4. 数据存储：
   - 使用 Supabase（已有）
   - 或 Airtable（新表）

5. 权限：
   - 只有 admin 密码 (0309) 可访问
```

## Prompt 5: Newsletter Template

```
创建 HTML Email Newsletter 模板：

1. 模板结构：
   - Header: LuxHunter Logo
   - Hero: 本期主题/大图
   - Content: 新闻列表（3-5条）
   - CTA: 预约咨询按钮
   - Footer: 联系方式、退订链接

2. 样式要求：
   - 响应式（手机友好）
   - 品牌色：暖黄 + 黑色
   - 简洁专业

3. 动态内容：
   - 使用变量 {{title}}, {{content}}, {{date}}
   - 可从 Airtable 读取数据

4. 兼容性：
   - Gmail, Outlook, Apple Mail
   - 测试显示效果
```

## 执行顺序

1. 先做 Prompt 1 (Airtable Integration) - 核心功能
2. 然后 Prompt 2 (Landing Page) - 获客页面
3. 接着 Prompt 3 (Calendly) - 预约功能
4. 再做 Prompt 5 (Newsletter) - 邮件模板
5. 最后 Prompt 4 (Admin) - 后台管理

每个完成后测试再下一个！