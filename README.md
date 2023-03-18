# Obsidian_Publish_MkDocs_Material_Vercel_template

如果你用 Obsidian 记笔记，想公开分享你的笔记库，可以使用这个模板实现。这里提供的方法，解决了以下问题：

1. Obsidian 官方的 publish 服务太贵了，而这个方法是免费的。
2. 解决了双链引用的问题，渲染为链接的形式。

## 极简步骤

1. 点击 `use this template`，生成你自己的 GitHub 仓库。
2. 在 [**Vercel**](https://vercel.com/) 部署这个仓库，框架选择 `other`，其他不用选，一路选默认直到部署完成。（如果还没注册 Vercel 账号，可以直接用 GitHub 账户创建一个）
3. 预览看看，如果没问题的话，就修改 `mkdocs.yml` 文件。
4. 下载 Obsidian 软件，打开库（Vault）的位置为根目录下的 `doc` 文件夹。
5. 每次更新后推到 GitHub，Vercel 就会自动拉取更新，并部署网站。

## 开发者区域

根目录下各文件属性：

- `requirements.txt`：Vercel 在部署的时候会查看这个文件，检查需要的 Python 依赖并下载它们。
- `package.json`：里面包含了 MkDocs 的构建命令、要使用的 MkDocs 的版本号（默认为最新），Vercel 会用这些参数进行部署。

## 参考与致谢

- [jobindj/obsidian-publish-mkdocs](https://github.com/jobindj/obsidian-publish-mkdocs)
- [MkDocs Material](https://squidfunk.github.io/mkdocs-material/)
