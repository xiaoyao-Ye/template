# vscode extensions template

```json
  // 插件名称, 唯一的, 不展示
  "name": "name-id",
  // 插件显示名称, 可搜索, 展示
  "displayName": "search extensions by name",
  // 插件描述
  "description": "current extension description"
  "scripts": {
    "build": "tsup src/index.ts --external vscode",
    // 调试的时候会走这里
    "dev": "npm run build --watch",
    // 不使用 vsce package 打包直接发布
    "vscode:prepublish": "npm run test && npm run build",
    "publish": "bumpp && vsce publish --no-dependencies",
    // 打包插件, 用于本地安装测试或发布
    "pack": "npm run build && vsce package --no-dependencies",
    "test": "vitest run",
    "typecheck": "tsc --noEmit",
    // 发布 npm, 便于其他人通过npm安装使用这个包的功能
    "release": "bumpp && npm publish"
  },
```

## todo

- [ ] GitHub actions 待补充
  - [ ] 运行单元测试
  - [ ] 更新版本号, 并 git tag
  - [ ] 使用 pnpm 安装依赖
  - [ ] 配置发布 vscode 的 TOKEN (如果需要的话)
  - [ ] 生成发布日志? 参考 changelogithub
