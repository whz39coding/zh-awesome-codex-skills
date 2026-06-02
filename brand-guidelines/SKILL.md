---
name: brand-guidelines
description: 将 OpenAI/Codex 品牌色、字体和视觉规范应用到文档、幻灯片、网页或其他 artifact。适用于需要品牌色、样式指南、视觉格式或公司设计标准的任务。Keywords: OpenAI brand, Codex style, visual formatting.
license: Complete terms in LICENSE.txt
---

# OpenAI Brand Styling

## Overview

Apply OpenAI's brand identity and style resources with this skill.

**Keywords**: branding, corporate identity, visual identity, post-processing, styling, brand colors, typography, OpenAI brand, Codex, visual formatting, visual design

## Brand Guidelines

### Colors

**Main Colors:**

- Charcoal: `#0E0F12` - Primary text and dark backgrounds
- Slate: `#202123` - Surface backgrounds
- Mist: `#F5F7FA` - Light backgrounds and text on dark
- Steel: `#9EA1AA` - Secondary elements and dividers

**Accent Colors:**

- OpenAI Green: `#10A37F` - Primary accent
- Azure: `#2B8FFF` - Secondary accent
- Graphite: `#40434A` - Neutral accent for icons or strokes

### Typography

- **Headings**: Inter, Semibold/Bold (with Arial fallback)
- **Body Text**: Inter, Regular (with Arial fallback)
- **Code/Monospace**: IBM Plex Mono (with Menlo/monospace fallback)
- **Note**: Fonts should be pre-installed in your environment for best results

## Features

### Smart Font Application

- Applies Inter Semibold/Bold to headings (24pt and larger)
- Applies Inter Regular to body text
- Applies IBM Plex Mono for code snippets or inline code
- Automatically falls back to Arial/Menlo if custom fonts unavailable
- Preserves readability across all systems

### Text Styling

- Headings (24pt+): Inter Semibold/Bold
- Body text: Inter Regular
- Smart color selection based on background (Charcoal or Mist as appropriate)
- Preserves text hierarchy and formatting

### Shape and Accent Colors

- Non-text shapes use accent colors
- Cycle accent usage: OpenAI Green → Azure → Graphite
- Maintains visual interest while staying on-brand

## Technical Details

### Font Management

- Uses system-installed Inter and IBM Plex Mono fonts when available
- Provides automatic fallback to Arial (headings/body) and Menlo/monospace (code)
- No font installation required - works with existing system fonts
- For best results, pre-install Inter and IBM Plex Mono fonts in your environment

### Color Application

- Uses RGB color values for precise brand matching
- Applied via python-pptx's RGBColor class
- Maintains color fidelity across different systems
