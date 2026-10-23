---
layout: default
title: "MicroPython & Pico Examples — Documentation and Guides"
description: "Browse the Raspberry Pi Pico 2 W MicroPython example and its GPIO, timing and board setup instructions."
permalink: /documentation/
---

Browse the published guides, examples and reference pages for **MicroPython & Pico Examples**. Each guide has a readable web page; the Markdown sources remain available on GitHub.

## 🔎 Example index

| Resource | Purpose |
|---|---|
| [Repository overview](README.md) | Requirements, quick start, limitations and license |
| [Onboard LED guide](PiPico2W/FirstLed/readme.md) | Program explanation, transfer/run procedure and expected timing |
| [main.py](PiPico2W/FirstLed/main.py) | The complete MicroPython program |
| [MIT license](LICENSE) | Repository license terms |

## 🧪 Hardware verification reference

Use a Pico 2 W with matching MicroPython firmware. Check that the LED changes state approximately once per second and that execution can be interrupted from the REPL. The board is not connected or tested by this documentation review.

Desktop Python is unsuitable for this sample's machine module. The generated page/source navigation below is retained for the documentation site.

## Read online

<table>
<thead><tr><th>Guide</th><th>Markdown or HTML source</th></tr></thead>
<tbody>
{% assign guides = site.html_pages | sort: 'url' %}
{% for guide in guides %}{% if guide.sitemap != false and guide.url != page.url and guide.url != '/404.html' %}
<tr><td><a href="{{ guide.url | absolute_url }}">{{ guide.title | default: guide.name | escape }}</a></td><td><a href="https://github.com/{{ site.repository }}/blob/main/{{ guide.path | uri_escape }}">View source</a></td></tr>
{% endif %}{% endfor %}
{% for guide in site.static_files %}{% if guide.extname == '.html' and guide.sitemap != false %}
<tr><td><a href="{{ guide.path | uri_escape | absolute_url }}">{% if guide.path == '/Linux_Commands/index.html' %}Linux Command Reference{% elsif guide.path contains 'AI-Learning-Atlas' %}AI Learning Atlas{% elsif guide.path contains 'ai_coding_plugins_beginners_guide' %}AI Coding Add-ons: Beginner’s Guide{% elsif guide.path contains 'Wifi Radar' %}WiFi Radar — static interface preview{% else %}{{ guide.name | escape }} — {{ guide.path | escape }}{% endif %}</a></td><td><code>{{ guide.path | escape }}</code></td></tr>
{% endif %}{% endfor %}
</tbody>
</table>

## Markdown source library

[View this documentation index source](https://github.com/{{ site.repository }}/blob/main/documentation.md). These are the authored Markdown files. Some are package-specific documents or alternate source formats of the same guide.

{% assign sources = site.static_files | sort: 'path' %}
{% for source in sources %}{% if source.extname == '.md' %}
- [{{ source.path | escape }}](https://github.com/{{ site.repository }}/blob/main{{ source.path | uri_escape }})
{% endif %}{% endfor %}

## Explore more

[All developer projects](https://gcfernando.github.io/gcfernando/projects/) · [Repository on GitHub](https://github.com/gcfernando/microcontoller) · [XML sitemap](https://gcfernando.github.io/microcontoller/sitemap.xml)
