# Odera: a premium esthetic dental studio site with a Formgong form

**Live demo:** https://odera.formgong.com · Download: the [latest release](https://github.com/formgong/odera-template/releases/latest) zip.

[![Deploy to Cloudflare](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/formgong/odera-template) [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fformgong%2Fodera-template&project-name=odera&repository-name=odera)

Each button copies the site to your GitHub and publishes it. Then replace `fk_your_access_key` in `index.html` of your copy with your Formgong access key (free at https://formgong.com/new) and commit: the host republishes on its own.

Сайт преміальної естетичної стоматології з формою Формгонг

A one-page site for an esthetic dental studio, in a single `index.html` plus an `img/` folder. The demo studio, Odera, its doctors, address, reviews and prices are fictional sample content.

- **Header.** The wordmark and links on the left, the phone and two slanted buttons (Call, Book a visit) on the right. It is transparent over the hero, hides when you scroll down and comes back with a solid background when you scroll up. Below 1200 px it becomes a menu button.
- **Hero.** The page is split down the middle: warm ivory on the left, a framed studio photo on the right, and one large headline across both, dark on the ivory and white on the photo. As you scroll, the photo grows to full width, the headline turns white with it, and a line of treatment names slides across.
- **Approach.** A short note with the team's faces, then a large sentence that fills in word by word as you scroll, next to a square photo.
- **Treatments and prices.** Five treatments (veneers, implants, aligners, whitening, hygiene). On wide screens the section stays in place while each new photo wipes up over the last one; the big title, the description, visits, time, starting price and the list of treatments change with it. An index on the left jumps to any treatment. A click on a treatment fills in the topic of the form. On phones and tablets they are stacked.
- **Banner.** A full-width studio photo and a four-line heading whose lines slide in from both sides.
- **How a visit works.** Three framed cards (talk and scan, plan, treatment and aftercare) that stack on top of each other as you scroll, each with a slanted label in the corner. The last one is solid blue.
- **Team.** A giant blue line with three black-and-white portraits rising behind it, then names, roles and a line about each person. On phones the portraits scroll sideways.
- **Reviews.** A blue section with four sample reviews in a framed box, with square dots and arrows.
- **FAQ.** Six questions that open and close.
- **Book a visit.** A large heading, the address, hours, phone and email, and the Formgong form.
- **Footer.** Address, hours and contacts, and the studio name across the full width.

Headings rise line by line and blocks fade in as they scroll into view. Without JavaScript, or with `prefers-reduced-motion: reduce`, nothing moves or stays pinned and all content is visible.

## English

**Set up the form**

1. Create a form in the Formgong dashboard and copy its access key.
2. In `index.html`, replace `fk_your_access_key` with that key.
3. The form sends `name`, `email`, `phone`, `preferred_time`, `service`, `message`, a hidden `subject` and the empty spam trap `botcheck`. Name and email are required; phone, preferred time and the note are optional. It shows thanks only when Formgong answers `success: true`. If the answer is anything else, it shows the error and keeps what was typed.

**Health data.** This form is for appointment requests. Don't use it to collect diagnoses, medical history, prescriptions or insurance numbers; keep those in your clinic's own patient system. The note field carries a hint asking visitors not to include medical details.

**Edit**

- Colours and fonts are at the top of the styles: `--ivory` for the page, `--ink` for text and the dark sections, `--blue` for the accent (buttons, the reviews section, the last visit card) and `--blue-lt` for the accent on dark backgrounds. The fonts are Bodoni Moda and Hanken Grotesk from Google Fonts.
- The hero headline is written twice (`.hero-h.ink` and `.hero-h.lite`); change both. The sliding line of treatment names is `.hero-run`.
- Each treatment is an `<article class="tx-item">` with a photo, a title, a description, a `<dl class="spec">` with visits, time and price, and a list of links. Their `data-pick` value must match one of the `service` choices in the form. If you add or remove a treatment, also change the buttons in `.tx-index` and the `/ 05` counter.
- The visit cards are `<article class="vs-card">`; the card with the class `solid` is the blue one.
- Reviews are `<figure class="rv-slide">`; keep one square dot button per review.
- Address, hours, phone and email appear in the contact section, the footer and the menu.
- Replace the photos in `img/`, keeping the file names, or change the paths in `index.html`. `img-prompts.json` lists every photo with its ratio, alt text and the prompt used.

**Images.** The twelve photos were generated for this template with ChatGPT image generation (OpenAI) and saved as WebP, about 1.2 MB in all. The people and places are fictional. You may use them in your own site, but replace them with photos of your own studio and team before launch. Until the files are in `img/`, each photo shows as a plain colour block of the same size.

**Sample content.** The doctors, reviews, prices, address, phone number and opening hours are examples. Replace them with your own before publishing.

The "Powered by Formgong" links point to `https://formgong.com/review-page/fk_your_access_key`, so the same find and replace covers them. Once your key is in, the first click from your published site makes your own public review page on Formgong, where clients read and leave reviews, and every later click opens it. Switch the page off in Formgong (Reviews → your site → Settings) or change those links.

## Українська

Односторінковий сайт для естетичної стоматології: один файл `index.html` і папка `img/`. Студія Odera, лікарі, адреса, відгуки й ціни вигадані, це приклад наповнення.

На сторінці:

- шапка з логотипом, телефоном і двома скошеними кнопками; над першим екраном вона прозора, під час прокрутки вниз ховається, а вгору повертається;
- перший екран, поділений навпіл: світлий фон ліворуч, фото студії в рамці праворуч і великий заголовок на обидві половини; під час прокрутки фото розширюється на весь екран і через нього пропливає рядок із назвами процедур;
- короткий опис підходу з обличчями команди і велике речення, що проявляється слово за словом;
- п'ять процедур із цінами (вініри, імпланти, елайнери, відбілювання, гігієна): на широкому екрані блок зупиняється, а фото змінюються знизу вгору; клік на процедуру вписує тему у форму;
- широкий банер із заголовком, рядки якого з'їжджаються з боків;
- три картки «як проходить візит», що накладаються одна на одну;
- команда: великий синій рядок і три чорно-білі портрети, що піднімаються з-за нього;
- синій блок із відгуками;
- шість частих питань;
- контакти і форма запису;
- футер із назвою студії на всю ширину.

Без JavaScript або з `prefers-reduced-motion: reduce` нічого не рухається і не закріплюється, увесь вміст видно.

**Налаштування форми.** Створіть форму в кабінеті Formgong і замініть `fk_your_access_key` у `index.html` на свій ключ. Форма надсилає `name`, `email`, `phone`, `preferred_time`, `service`, `message`, прихований `subject` і порожнє поле-пастку `botcheck`. Ім'я та email обов'язкові, телефон, зручний час і коментар — ні. Подяка з'являється лише тоді, коли Formgong відповідає `success: true`; інакше форма показує помилку і зберігає введене.

**Медичні дані.** Ця форма лише для запитів на запис. Не збирайте через неї діагнози, історію хвороби, рецепти чи номери страховок; зберігайте це у власній системі клініки. Під полем коментаря є підказка не писати медичних подробиць.

**Редагування.** Кольори й шрифти задані на початку стилів: `--ivory` — фон, `--ink` — текст і темні блоки, `--blue` — акцент, `--blue-lt` — акцент на темному фоні. Шрифти: Bodoni Moda і Hanken Grotesk з Google Fonts. Заголовок першого екрана записаний двічі (`.hero-h.ink` і `.hero-h.lite`), змінюйте обидва. Кожна процедура — це `<article class="tx-item">`; значення `data-pick` має збігатися з одним із варіантів `service` у формі.

**Зображення:** дванадцять фото згенеровано для цього шаблону в ChatGPT (OpenAI) і збережено у WebP, разом близько 1,2 МБ. Люди й місця вигадані. Їх можна використовувати, але перед запуском замініть їх фото власної студії та команди. Поки файлів немає в `img/`, на місці кожного фото видно кольоровий блок того ж розміру. Список фото з пропорціями, підписами й промптами — у `img-prompts.json`.

**Приклад наповнення.** Лікарі, відгуки, ціни, адреса, телефон і години роботи — приклади. Замініть їх своїми перед публікацією.

MIT license.

Посилання «Powered by Formgong» ведуть на `https://formgong.com/review-page/fk_your_access_key`, тож та сама заміна ключа оновить і їх. Коли ключ стоїть, перший перехід з вашого опублікованого сайту створює вашу публічну сторінку відгуків на Formgong, де клієнти читають і залишають відгуки; далі посилання відкриває її. Вимкнути сторінку можна у Formgong (Відгуки → ваш сайт → Налаштування) або змінити ці посилання.
