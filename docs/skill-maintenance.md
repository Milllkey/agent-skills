# Skill 维护

## 比较源码与安装版

```bash
python3 scripts/compare_installed_skills.py
python3 scripts/compare_installed_skills.py --local-root "$HOME/.agents/skills"
```

脚本按哈希比较 Git 跟踪的文件，不写入安装目录，也不读取凭据。插件位置通过参数单独指定。

## 修改与验证

1. 在仓库中修改源码，保留第三方许可证和依赖声明。
2. 运行受影响模块的离线测试；涉及外部程序时，另做对应环境的集成验证。
3. 剪映入口使用固定组件哈希。核心变更经验证后，同步核心仓库和独立 Skill 的入口。
4. 更新安装版前保留备份，再核对来源提交和文件差异。

API 密钥、Cookie、代理、账号配置和运行数据保存在仓库之外；更新时沿用各用户的本机配置。
