# README

## package.json

```json
{
  // 由于我们使用的是 sourceMap 和 declarationMap，因此我们还需要发布 src
  "files": ["dist", "src"]
  // ...
}
```

## tsconfig.json

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "strict": true,
    // 通过允许 ESM 样式的导入来提高兼容性
    "esModuleInterop": true,
    "rootDir": "./src",
    "outDir": "./dist",
    "sourceMap": true,
    // 这将生成声明文件
    "declaration": true,
    // 改善开发人员体验, 将生成源映射 （.d.ts.map）将我们的声明文件 （.d.ts） 映射到我们的原始 TypeScript 源代码
    "declarationMap": true
  }
}
```
