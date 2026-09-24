<a href="https://aleksainsajder.rs/"><img src="media/cover.jpg" alt="Aleksa Insajder, home page on a laptop and a phone" width="100%"></a>

# Aleksa Insajder

Brand site for a sports creator, with a stream page he fills from his phone and first-party visit stats that use no cookies.

**[aleksainsajder.rs](https://aleksainsajder.rs/)** · [Case study (in Serbian)](https://svilenkovic.com/radovi/aleksa-insajder) · [Srpski](README.sr.md)

> [!NOTE]
> Client project. The source code belongs to the client and stays in a private repository. This page describes what I built and how.

<table>
  <tr><td><b>Client</b></td><td>Aleksa Insajder</td></tr>
  <tr><td><b>Industry</b></td><td>Sports video content</td></tr>
  <tr><td><b>Location</b></td><td>Serbia</td></tr>
  <tr><td><b>Type</b></td><td>One-page brand site with a stream page (PWA)</td></tr>
  <tr><td><b>My role</b></td><td>Design, development, SEO, hosting and maintenance</td></tr>
  <tr><td><b>Stack</b></td><td>PHP 8.3, SQLite, PWA, nginx</td></tr>
</table>

## About the project

Aleksa Insajder is a sports creator who tells athletes' stories on TikTok and YouTube, with a Discord community around the brand. He needed one page that explains the brand in a single scroll for people arriving from a profile link, and a second page he could fill himself, from his phone, while a match is on. Everything he publishes had to be editable from a panel, without touching the code.

The stream page shows the events he picks, up to ten cards, in a layout that adapts to how many there are. Until a visitor clicks, a card is only a poster from the site itself, and a network check confirmed that nothing is requested from third parties before that click. The server stores only a link, a title and a timestamp. It never fetches, keeps or re-streams the video itself: I decided that at the start, so the server would not end up distributing other people's material.

## What I built

- A panel installed as an app on his phone's home screen, with a login attempt limit that now holds under parallel requests
- Cookieless stats in SQLite: visitors hashed with a monthly salt, an endpoint that accepts only known paths, and viewing time counted per stream
- A service worker fix: the cached stylesheet never matched its versioned URL, so one hiccup in a mobile connection could leave the page unstyled
- Sessions moved out of a shared folder the system cleaned every half hour, which had been logging him out in the middle of a match
- Card age shown in the panel, turning yellow after twelve hours so that old matches get checked
- A privacy policy and terms written for this site, covering the stats and the note on embedded streams

## Results

| | Performance | Accessibility | Best practices | SEO |
| :-- | :-: | :-: | :-: | :-: |
| Mobile | 93 | 100 | 100 | 100 |
| Desktop | 100 | 100 | 100 | 100 |

PageSpeed Insights, lab test of the live site, September 2026. Security headers: 6 of 6. HTML validator: no errors. axe accessibility check: no violations. Structured data: `Organization`, `Person`.

## Screenshots

<table>
  <tr>
    <td width="68%" valign="top"><img src="media/desktop.webp" alt="Aleksa Insajder, home page on a 1440 px screen"></td>
    <td width="32%" valign="top"><img src="media/mobile.webp" alt="Aleksa Insajder, home page on a phone"></td>
  </tr>
</table>

<img src="media/inner-1.webp" alt="&quot;Moja priča&quot; (My story), then four principles: authenticity, verification, emotion and consistency">
<sub>"Moja priča" (My story), then four principles: authenticity, verification, emotion and consistency</sub>

<img src="media/inner-2.webp" alt="&quot;Moj fokus&quot; (My focus), then a Viktor Frankl quote as a pause before the contact section">
<sub>"Moj fokus" (My focus), then a Viktor Frankl quote as a pause before the contact section</sub>

---

<sub>Built by [D. Svilenković](https://svilenkovic.com).</sub>
