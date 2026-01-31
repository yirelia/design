# Element Plus 主题色规范

本文档定义了基于 Element Plus 组件库的统一主题色方案。

---

## 1. 品牌主色

```css
/* 主色 - Element Plus 默认蓝色系 */
--el-color-primary: #409EFF;
--el-color-primary-light-3: #79BBFF;
--el-color-primary-light-5: #A0CFFF;
--el-color-primary-light-7: #C6E2FF;
--el-color-primary-light-8: #D9ECFF;
--el-color-primary-light-9: #ECF5FF;
--el-color-primary-dark-2: #337ECC;
```

---

## 2. 功能色

### 2.1 成功色

```css
--el-color-success: #67C23A;
--el-color-success-light-3: #95D475;
--el-color-success-light-5: #B3E19D;
--el-color-success-light-7: #D1EDC4;
--el-color-success-light-8: #E1F3D8;
--el-color-success-light-9: #F0F9EB;
--el-color-success-dark-2: #529B2E;
```

### 2.2 警告色

```css
--el-color-warning: #E6A23C;
--el-color-warning-light-3: #EEBE77;
--el-color-warning-light-5: #F3D19E;
--el-color-warning-light-7: #F8E3C5;
--el-color-warning-light-8: #FAECD8;
--el-color-warning-light-9: #FDF6EC;
--el-color-warning-dark-2: #B88230;
```

### 2.3 危险色

```css
--el-color-danger: #F56C6C;
--el-color-danger-light-3: #F89898;
--el-color-danger-light-5: #FAB6B6;
--el-color-danger-light-7: #FCD3D3;
--el-color-danger-light-8: #FDE2E2;
--el-color-danger-light-9: #FEF0F0;
--el-color-danger-dark-2: #C45656;
```

### 2.4 信息色

```css
--el-color-info: #909399;
--el-color-info-light-3: #B1B3B8;
--el-color-info-light-5: #C8C9CC;
--el-color-info-light-7: #DEDFE0;
--el-color-info-light-8: #E9E9EB;
--el-color-info-light-9: #F4F4F5;
--el-color-info-dark-2: #73767A;
```

---

## 3. 中性色

### 3.1 文本颜色

```css
--el-text-color-primary: #303133;
--el-text-color-regular: #606266;
--el-text-color-secondary: #909399;
--el-text-color-placeholder: #A8ABB2;
--el-text-color-disabled: #C0C4CC;
```

### 3.2 边框颜色

```css
--el-border-color: #DCDFE6;
--el-border-color-light: #E4E7ED;
--el-border-color-lighter: #EBEEF5;
--el-border-color-extra-light: #F2F6FC;
--el-border-color-dark: #D4D7DE;
--el-border-color-darker: #CDD0D6;
```

### 3.3 填充颜色

```css
--el-fill-color: #F0F2F5;
--el-fill-color-light: #F5F7FA;
--el-fill-color-lighter: #FAFAFA;
--el-fill-color-extra-light: #FAFCFF;
--el-fill-color-dark: #EBEDF0;
--el-fill-color-darker: #E6E8EB;
--el-fill-color-blank: #FFFFFF;
```

### 3.4 背景颜色

```css
--el-bg-color: #FFFFFF;
--el-bg-color-page: #F2F3F5;
--el-bg-color-overlay: #FFFFFF;
```

---

## 4. 阴影系统

```css
--el-box-shadow: 0px 12px 32px 4px rgba(0, 0, 0, 0.04),
                 0px 8px 20px rgba(0, 0, 0, 0.08);
--el-box-shadow-light: 0px 0px 12px rgba(0, 0, 0, 0.12);
--el-box-shadow-lighter: 0px 0px 6px rgba(0, 0, 0, 0.12);
--el-box-shadow-dark: 0px 16px 48px 16px rgba(0, 0, 0, 0.08),
                      0px 12px 32px rgba(0, 0, 0, 0.12),
                      0px 8px 16px -8px rgba(0, 0, 0, 0.16);
```

---

## 5. 自定义主题

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

---

*本文档版本: 1.0.0*
