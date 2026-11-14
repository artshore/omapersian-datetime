# Shamsi Clock for Omarchy

A bar clock for [Omarchy](https://omarchy.org) that shows the Iranian **Shamsi
(Jalali) date** alongside the Gregorian date, the weekday and the time.

<!-- Drop a screenshot here before publishing:
![Shamsi Clock on the Omarchy bar](preview.png)
-->

Bar label:

```
Nov 14th, 2026 | Saturday 10:50 AM | ۲۳ آبان ۱۴۰۵
└── Gregorian ─┘   └── time ──┘   └─ Shamsi ─┘
```

---

## English

### Features

- **Shamsi (Jalali) date** with Persian digits and month names, e.g. `۲۳ آبان ۱۴۰۵`.
- **Gregorian date** with an English ordinal suffix, e.g. `Nov 14th, 2026`.
- **Weekday and 12-hour time**, e.g. `Saturday 10:50 AM`.
- Live refresh every minute.
- No external dependencies: the Jalali conversion is pure JavaScript in
  `Model.js`.
- Text is pinned left-to-right with an explicit RTL embedding around the
  Persian segment, so the three parts never reorder.

### Install

```bash
omarchy plugin add https://github.com/<you>/omarchy-shamsi-clock --enable
```

Or, by hand:

```bash
git clone https://github.com/<you>/omarchy-shamsi-clock \
  ~/.config/omarchy/plugins/artshore.clock
omarchy plugin enable artshore.clock
omarchy-shell shell rescanPlugins
```

Then add it to the bar (for example, the center section):

```bash
omarchy bar put artshore.clock center
```

Or edit `~/.config/omarchy/shell.json` directly:

```json
{
  "bar": {
    "centerAnchor": "artshore.clock",
    "layout": {
      "center": [
        { "id": "artshore.clock" }
      ]
    }
  }
}
```

The shell hot-reloads `shell.json` on save.

### Files

| File | Purpose |
|------|---------|
| `BarWidget.qml` | Bar widget and live clock binding |
| `Model.js` | Jalali conversion, Persian digits and month names, ordinals |
| `Panel.qml` | Calendar popup (Gregorian month grid) |
| `manifest.json` | Omarchy plugin manifest |

### License

MIT — see [LICENSE](LICENSE).

---

<div dir="rtl">

## فارسی

ساعت نوار وضعیت برای [اومارشی](https://omarchy.org) که تاریخ **شمسی** را در کنار
تاریخ میلادی، روز هفته و ساعت نشان می‌دهد.

### ویژگی‌ها

- **تاریخ شمسی** با اعداد و نام ماه فارسی، مثل `۲۳ آبان ۱۴۰۵`.
- **تاریخ میلادی** با پسوند ترتیبی انگلیسی، مثل `Nov 14th, 2026`.
- **روز هفته و ساعت ۱۲ ساعته**، مثل `Saturday 10:50 AM`.
- به‌روزرسانی خودکار هر دقیقه.
- بدون وابستگی بیرونی: تبدیل تاریخ شمسی به‌صورت جاوااسکریپت خالص در
  `Model.js` انجام می‌شود.
- جهت متن به‌صورت چپ‌به‌راست ثابت شده و بخش فارسی داخل یک جاسازی راست‌به‌چپ
  قرار می‌گیرد تا ترتیب سه بخش به‌هم نریزد.

### نصب

```bash
omarchy plugin add https://github.com/<you>/omarchy-shamsi-clock --enable
```

یا به‌صورت دستی:

```bash
git clone https://github.com/<you>/omarchy-shamsi-clock \
  ~/.config/omarchy/plugins/artshore.clock
omarchy plugin enable artshore.clock
omarchy-shell shell rescanPlugins
```

سپس آن را به نوار اضافه کنید (برای مثال بخش وسط):

```bash
omarchy bar put artshore.clock center
```

یا مستقیماً `~/.config/omarchy/shell.json` را ویرایش کنید:

```json
{
  "bar": {
    "centerAnchor": "artshore.clock",
    "layout": {
      "center": [
        { "id": "artshore.clock" }
      ]
    }
  }
}
```

پوسته هنگام ذخیره، `shell.json` را به‌صورت خودکار بارگذاری می‌کند.

### فایل‌ها

| فایل | کاربرد |
|------|--------|
| `BarWidget.qml` | ویجت نوار و اتصال ساعت زنده |
| `Model.js` | تبدیل تاریخ شمسی، اعداد و نام ماه فارسی، پسوند ترتیبی |
| `Panel.qml` | پنجره تقویم (شبکه ماه میلادی) |
| `manifest.json` | مانیفست افزونه اومارشی |

### مجوز

MIT — فایل [LICENSE](LICENSE) را ببینید.

</div>
