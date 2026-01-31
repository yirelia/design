---
name: pencil-design
description: 通过pencil 绘制原型图时，UI框架选择为Element Plus。主题色采用统一的预制主题色，针对一些用户的业务需求可以通过同样的业务组件模板来进行绘制，便于后期生成Vue,react等前端代码。css样式类采用BEM等风格。
disable-model-invocation: true
---

# Element Plus 设计规范 (Skill 文档)

本文档定义了基于 Element Plus 组件库的设计规范，包含统一主题色、业务组件母版以及原型图设计指南。

---

## 1. 设计理念

### 1.1 核心原则

- **一致性**: 所有组件遵循统一的视觉语言和交互模式
- **可扩展性**: 业务组件母版支持用户自定义扩展
- **可访问性**: 符合 WCAG 2.1 AA 标准
- **响应式**: 适配桌面端和移动端

### 1.2 设计 DNA

- **简洁现代**: 扁平化设计，减少视觉噪音
- **专业可靠**: 企业级应用的稳重感
- **高效友好**: 清晰的信息层级，流畅的操作体验

---

## 2. 字体规范

### 2.1 字体家族

```css
--el-font-family: 'Helvetica Neue', Helvetica, 'PingFang SC',
                  'Hiragino Sans GB', 'Microsoft YaHei', '微软雅黑',
                  Arial, sans-serif;
```

### 2.2 字号规范

| 用途 | 字号 | 行高 | 字重 |
|------|------|------|------|
| 大标题 | 20px | 28px | 600 |
| 标题 | 18px | 26px | 600 |
| 小标题 | 16px | 24px | 600 |
| 正文(大) | 16px | 24px | 400 |
| 正文 | 14px | 22px | 400 |
| 正文(小) | 13px | 20px | 400 |
| 辅助文字 | 12px | 18px | 400 |
| 提示文字 | 12px | 18px | 400 |

---

## 4. 间距规范

### 4.1 基础间距

```css
--el-spacing-xs: 4px;
--el-spacing-sm: 8px;
--el-spacing-md: 12px;
--el-spacing-base: 16px;
--el-spacing-lg: 20px;
--el-spacing-xl: 24px;
--el-spacing-xxl: 32px;
```

### 4.2 组件间距

| 场景 | 间距值 |
|------|--------|
| 表单项间距 | 16px |
| 卡片内边距 | 20px |
| 页面边距 | 24px |
| 模块间距 | 24px |
| 区块间距 | 32px |

---

## 5. 圆角规范

```css
--el-border-radius-base: 4px;
--el-border-radius-small: 2px;
--el-border-radius-round: 20px;
--el-border-radius-circle: 100%;
```

---

## 6. 消息提醒规范

### 6.1 消息类型

| 类型 | 使用场景 | 图标 | 颜色 |
|------|----------|------|------|
| success | 操作成功 | SuccessFilled | #67C23A |
| warning | 警告提示 | WarningFilled | #E6A23C |
| error | 错误提示 | CircleCloseFilled | #F56C6C |
| info | 信息提示 | InfoFilled | #909399 |

### 6.2 消息组件选择

| 组件 | 使用场景 |
|------|----------|
| ElMessage | 轻量级全局提示，自动消失 |
| ElMessageBox | 需要用户确认的操作 |
| ElNotification | 系统通知，较长内容 |
| ElAlert | 页面内静态提示 |

### 6.3 消息文案规范

- **成功**: "XXX成功" (如：保存成功、提交成功)
- **失败**: "XXX失败，请重试" (如：保存失败，请重试)
- **确认**: "确定要XXX吗？" (如：确定要删除吗？)
- **警告**: "XXX，请注意" (如：数据未保存，请注意)

---

## 7. 交互规范

### 7.1 按钮规范

| 类型 | 使用场景 | 样式 |
|------|----------|------|
| Primary | 主要操作 | type="primary" |
| Default | 次要操作 | 默认 |
| Text | 文字链接操作 | type="text" |
| Danger | 危险操作 | type="danger" |

### 7.2 按钮位置

- **表单**: 右对齐，主按钮在右
- **弹窗**: 右对齐，取消在左，确定在右
- **表格操作列**: 左对齐
- **页面顶部**: 右对齐

### 7.3 加载状态

- 按钮操作时显示 loading 状态
- 表格加载时使用 v-loading 指令
- 页面加载时使用骨架屏或 loading 遮罩

---

## 8. 原型图设计指南

### 8.1 使用 Pencil 绘制原型

原型图应包含以下要素：

1. **页面结构**: 清晰的布局层级
2. **组件标注**: 使用的 Element Plus 组件
3. **交互说明**: 关键交互行为描述
4. **状态展示**: 不同状态的界面表现

### 8.2 原型校验清单

- [ ] 布局是否符合规范
- [ ] 颜色是否使用主题色
- [ ] 间距是否符合规范
- [ ] 组件使用是否正确
- [ ] 交互是否完整
- [ ] 响应式是否考虑

---

## 9. 扩展指南

### 9.1 自定义主题

```scss
// 覆盖 Element Plus 变量
@forward 'element-plus/theme-chalk/src/common/var.scss' with (
  $colors: (
    'primary': (
      'base': #your-primary-color,
    ),
  ),
);
```

### 9.2 扩展业务组件

1. 继承母版组件
2. 通过插槽扩展功能
3. 通过 props 配置行为
4. 保持与设计规范一致

---

## Additional resources

- [theme-colors.md](./theme-colors.md) - 统一主题色方案（品牌主色、功能色、中性色、阴影系统）
- [component-templates.md](./component-templates.md) - 业务组件模板（页面布局母版、基础组件母版、业务组件母版）
- [pencil-file-structure.md](./pencil-file-structure.md) - Pencil 文件归类与业务组件命名规范（目录结构、命名规则、组件ID规范）

---

## 附录

### A. 图标使用

推荐使用 `@element-plus/icons-vue` 图标库。

### B. 参考资源

- [Element Plus 官方文档](https://element-plus.org/)
- [Element Plus 设计资源](https://element-plus.org/zh-CN/resource/index.html)

---

*本文档版本: 1.0.0*
*最后更新: 2026-01-30*
