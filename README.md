# 🏡 Home Care

A simple phone app to help a family stay on top of house cleaning and home maintenance. It covers jobs from weekly to yearly, and each job reschedules itself when you tick it off.

It's a single web page, so there's nothing to install from an app store. Host it free on GitHub Pages, open it on your phone and add it to your home screen. It then opens full-screen like an app and works offline.

## Features

- **93 ready-made jobs** with short how-to tips, grouped as weekly, monthly, every 3 months, every 6 months, yearly cleaning and yearly maintenance for an established home
- **Today screen** showing overdue jobs, jobs due today and what's coming up this week
- **Robot vacuum days** with a checklist for before and after each run (choose your own days, or turn it off)
- **My jobs** for each person. Jobs can be assigned to Anyone, Adults, Kids, one person, or "Book a pro"
- **Pet-friendly:** dog bedding, bowls, yard clean-up, flea/tick reminders and fence checks
- **Undo**, "done on a different day", job history, search, and your own custom jobs
- **Adjustable schedule:** change how many days apart each group of jobs is
- **Excel export:** download every job with last done, done by, next due and status
- **Backup and restore** to move your list to another phone
- **Private:** all data stays in the browser on your phone. No account, no server, no tracking

The default tips suit Australian homes (termites, storm season, paralysis ticks, Queensland's 2027 smoke alarm rules), but the jobs apply almost anywhere. You can hide any job that doesn't fit your home.

## Put it online with GitHub Pages (free, about 5 minutes)

1. Sign in to [GitHub](https://github.com) (or create a free account).
2. Click **+** → **New repository**. Name it `home-care`, set it to **Public**, and click **Create repository**.
3. On the new repository page, click **uploading an existing file**. Select **all the files in this folder** (there are no subfolders), then click **Commit changes**. This works from a phone browser too.
   - `index.html` must be at the top level of the repository, not inside another folder.
4. Go to **Settings** → **Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select the **main** branch and the **/ (root)** folder, then click **Save**.
5. Wait a minute or two. Your app will be live at:
   `https://YOUR-USERNAME.github.io/home-care/`

Share that link with anyone who wants to use it. Each person or family gets their own private list on their own phone.

## Install it on a phone

**iPhone:** open the link in **Safari** → tap **Share** → **Add to Home Screen** → **Add**.

**Android:** open the link in **Chrome** → tap **⋮** → **Install app** (or **Add to Home screen**).

## Using it as a family

Each phone keeps its own list. To start everyone with the same setup, one person sets it up, goes to **Settings → Save backup**, and sends that file to the others. They open the app and choose **Settings → Restore backup**.

Ticks don't sync between phones automatically. (That would need a server, and this app deliberately doesn't use one.) The simplest approach is to keep one shared phone or tablet in the kitchen as the family's main list.

## Customise the jobs

All the built-in jobs are in `index.html`, in the list that starts with `var T = [`. Each job is one line:

```js
["w-toilets","w","Bathrooms","adults","Clean toilets, inside & out","Tip text…"],
//  id        how-often  area     who       name                       tip
```

- **how often:** `w` weekly · `m` monthly · `q` 3-monthly · `h` 6-monthly · `y` yearly clean · `ym` yearly maintenance
- **who:** `all` · `adults` · `teen` (kids) · `pro` (book a tradie)
- Add an optional number at the end to make a job first due that many days after setup (e.g. `,0` = due on day one).
- Keep each `id` unique and don't rename existing ones, or people will lose those jobs' history.

After changing files, also bump `VERSION` in `sw.js` (e.g. `home-care-v2`) so installed phones pick up the update.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app |
| `manifest.webmanifest` | App name, colours and icons for "Add to Home Screen" |
| `sw.js` | Service worker that lets the app open offline |
| `icon-*.png`, `apple-touch-icon.png` | App icons |

## Good to know

- Clearing your browser data, or using private browsing, erases the list. Save a backup now and then.
- On iPhone, data saved in Safari and data in the home-screen app are kept separately. Set it up from the home-screen icon.
- This is general guidance, not professional advice. Check local rules, and use licensed trades for electrical, gas, roofing and structural work.

## Licence

MIT. Free to use, change and share.
