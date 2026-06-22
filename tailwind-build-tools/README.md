# Tailwind 靜態 CSS 重新編譯說明

此資料夾是給未來維護用。正式網站執行時只會使用：

- `index.html`
- `assets/tailwind-static.css`

## 重新編譯步驟

在 `tailwind-build-tools` 資料夾內執行：

```bash
npx tailwindcss -c ./tailwind.config.js -i ./input.css -o ../assets/tailwind-static.css --minify
```

## 注意事項

1. `tailwind.config.js` 的 `content` 已指向 `../index.html`。
2. 如果未來 HTML 裡新增 Tailwind class，重新執行上方指令即可。
3. 如果有用程式動態組合 class，例如 `bg-${color}-100`，Tailwind 可能掃不到，需加入 safelist。
4. GitHub Pages 上傳時，請保留 `assets/tailwind-static.css` 路徑。
