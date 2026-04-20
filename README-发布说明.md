# 夏休み攻略网页发布说明

这个文件夹已经是一个可以直接托管到公网的静态网站目录：

- `index.html`：网页入口
- `Attachment/`：网页引用到的图片资源

## 最省事的发布方式

### 方案 A：Netlify Drop

适合临时分享，操作最少。

1. 打开 [Netlify Drop](https://app.netlify.com/drop)
2. 把整个 `public-site` 文件夹压缩成 zip，或者直接把里面的内容拖进去
3. 等待上传完成
4. 系统会自动生成一个公网链接，可以直接发给别人

特点：

- 最快
- 不需要写代码
- 链接默认是随机域名

### 方案 B：GitHub Pages

适合长期保存和反复更新。

1. 新建一个 GitHub 仓库
2. 把 `public-site` 里的全部内容上传到仓库根目录
3. 打开仓库 `Settings -> Pages`
4. 选择从当前分支部署
5. 等待几分钟后，GitHub 会生成固定链接

链接通常会是：

`https://<GitHub 用户名>.github.io/<仓库名>/`

特点：

- 链接稳定
- 适合长期维护
- 后续更新只需要重新上传

### 方案 C：Cloudflare Pages

适合想要更稳定访问速度和更好域名管理时使用。

1. 打开 Cloudflare Pages
2. 选择上传静态站点
3. 上传 `public-site` 文件夹内容
4. 等待构建完成

特点：

- 免费额度足够
- 域名绑定方便
- 后续也适合接 Git 仓库自动更新

## 推荐选择

- 只想尽快发给朋友：`Netlify Drop`
- 想做长期固定链接：`GitHub Pages`
- 以后可能还想绑自己的域名：`Cloudflare Pages`

## 更新网页的方法

如果 `夏休み.md` 有更新，先重新生成网页，再重新发布：

1. 运行 `tools/build_public_site.ps1`
2. 确认 `public-site/index.html` 已更新
3. 重新上传到 Netlify / GitHub Pages / Cloudflare Pages

## 注意事项

- 网页里的图片依赖 `Attachment/` 文件夹，发布时不能漏掉
- 如果只上传 `index.html` 而没有上传 `Attachment/`，图片会显示不出来
- 如果后面继续修改文档，最好每次都重新生成一次再上传
