# Правки для index.html — инструкция для Claude Code

## 1. Favicon + Open Graph — вставить в <head> ПОСЛЕ строки <meta name="theme-color">

```html
  <!-- Favicon -->
  <link rel="icon" type="image/png" sizes="192x192" href="icons/icon-192.png" />
  <link rel="icon" type="image/png" sizes="512x512" href="icons/icon-512.png" />
  <!-- Open Graph (красивая карточка при отправке ссылки в мессенджеры) -->
  <meta property="og:title" content="Крептонит — Калькуляторы стройматериалов" />
  <meta property="og:description" content="Рассчитайте объём бетона, расход сухих смесей и количество инертных материалов. Завод ГК «Эдиль», г. Гусев, Калининградская обл." />
  <meta property="og:image" content="https://barakuda989.github.io/kreptonit-calc/icons/icon-512.png" />
  <meta property="og:url" content="https://barakuda989.github.io/kreptonit-calc/" />
  <meta property="og:type" content="website" />
  <meta property="og:locale" content="ru_RU" />
```

## 2. CSS для мессенджеров — вставить в <style> ПЕРЕД закрывающим </style>

```css
    /* ─── МЕССЕНДЖЕРЫ (плавающие кнопки) ─── */
    .messengers {
      position: fixed;
      bottom: 20px;
      right: 20px;
      display: flex;
      flex-direction: column;
      gap: 10px;
      z-index: 900;
    }
    .msg-btn {
      width: 56px;
      height: 56px;
      border-radius: 50%;
      border: none;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 4px 16px rgba(0,0,0,.25);
      transition: transform .2s, box-shadow .2s;
      text-decoration: none;
    }
    .msg-btn:hover {
      transform: scale(1.1);
      box-shadow: 0 6px 20px rgba(0,0,0,.35);
    }
    .msg-btn.wa { background: #25D366; }
    .msg-btn.tg { background: #2AABEE; }
    .msg-btn svg { width: 28px; height: 28px; fill: #fff; }
    @media (max-width: 600px) {
      .messengers { bottom: 14px; right: 14px; }
      .msg-btn { width: 50px; height: 50px; }
      .msg-btn svg { width: 24px; height: 24px; }
    }
```

## 3. HTML кнопок мессенджеров — вставить ПЕРЕД </body>

```html
<!-- Мессенджеры: WhatsApp + Telegram -->
<div class="messengers">
  <!-- WhatsApp -->
  <a class="msg-btn wa" href="https://wa.me/79216174920?text=%D0%97%D0%B4%D1%80%D0%B0%D0%B2%D1%81%D1%82%D0%B2%D1%83%D0%B9%D1%82%D0%B5!%20%D0%A5%D0%BE%D1%87%D1%83%20%D1%83%D0%B7%D0%BD%D0%B0%D1%82%D1%8C%20%D1%86%D0%B5%D0%BD%D1%83%20%D0%BD%D0%B0%20%D0%BC%D0%B0%D1%82%D0%B5%D1%80%D0%B8%D0%B0%D0%BB%D1%8B" target="_blank" rel="noopener" title="Написать в WhatsApp">
    <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
  </a>
  <!-- Telegram -->
  <a class="msg-btn tg" href="https://t.me/+79216174920" target="_blank" rel="noopener" title="Написать в Telegram">
    <svg viewBox="0 0 24 24"><path d="M11.944 0A12 12 0 000 12a12 12 0 0012 12 12 12 0 0012-12A12 12 0 0012 0h-.056zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 01.171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.479.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/></svg>
  </a>
</div>
```

## 4. Не забыть!

- Файлы robots.txt и sitemap.xml положить в корень папки kreptonit-calc-git
- Добавить их в sw.js в массив FILES_TO_CACHE (необязательно, но желательно)
- Инкрементировать версию кэша в sw.js: kreptonit-v25 → kreptonit-v26
- Деплой: git add . && git commit -m "favicon og messengers robots sitemap" && git push
