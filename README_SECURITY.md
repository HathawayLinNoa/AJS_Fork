# 🔒 安全配置指南

## 配置文件安全

### 1. 配置文件设置
- 复制 `config.template.yaml` 为 `config.yaml`
- 根据你的环境修改配置参数
- **重要**: `config.yaml` 已被 `.gitignore` 忽略，不会被提交到版本控制

### 2. 白名单域名配置
在 `config.yaml` 中的 `scanner_scope.whitelist_domains` 部分：
```yaml
scanner_scope:
  whitelist_domains: ["your-target-domain.com", "localhost", "127.0.0.1"]
```

### 3. 敏感信息保护
- 所有分析结果存储在 `encryption_analysis/` 目录
- 该目录已被 `.gitignore` 忽略
- 日志文件和临时文件不会被提交

## 最佳实践

1. **配置管理**: 使用环境变量或配置文件管理敏感信息
2. **访问控制**: 确保只有授权人员可以访问配置文件
3. **定期清理**: 定期清理分析结果和日志文件
4. **网络安全**: 在受控环境中运行扫描器

## 注意事项

⚠️ **警告**: 
- 不要将包含真实目标域名的配置文件提交到公共仓库
- 定期检查 `.gitignore` 文件确保敏感文件被正确忽略
- 在生产环境中使用时，请确保适当的访问控制和监控