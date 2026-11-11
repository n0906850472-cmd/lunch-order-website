# 中餐訂購網站

這是一個免登入前台訂餐、管理員後台的靜態網站，資料庫使用 Supabase。

## 設定步驟

1. 在 Supabase 建立專案，打開 SQL Editor，執行 `supabase.sql`。
2. 到 Authentication > Users 建立第一位管理員。
3. 取得該使用者 UUID，在 SQL Editor 執行：

```sql
insert into profiles (id, email, role)
values ('使用者UUID', '管理員Email', 'super_admin');
```

4. 從 Supabase Project Settings > API 複製 Project URL 與 anon public key，填入 `config.js`。
5. 用任何靜態伺服器開啟網站；不可直接用 `file://` 開啟。部署到 GitHub Pages、Netlify 或 Vercel 都可以。

## 功能

- 前台免登入下單、預約未來日期、每個取餐日 11:30 截止
- 姓名、電話、部門、備註與訂單總金額
- 管理員登入、訂單狀態、日期／狀態篩選
- 餐點新增、編輯、上架／下架
- 超級管理者與一般管理員角色

`config.js` 只能放 Supabase anon public key，不要放 service_role key。
