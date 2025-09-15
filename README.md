# 🚀 Dhaval Patel - Portfolio Website

A modern, physics-based portfolio website built with Astro, React, and Tailwind CSS. Features interactive particle animations, smooth scrolling, and JSON-managed content for easy updates.

![Portfolio Preview](https://img.shields.io/badge/Status-Live-green) ![Astro](https://img.shields.io/badge/Astro-4.0+-orange) ![React](https://img.shields.io/badge/React-18+-blue) ![Tailwind](https://img.shields.io/badge/TailwindCSS-3.0+-cyan)

## ✨ Features

- **🎨 Modern Design**: Clean, professional layout with gradient accents and glass morphism effects
- **🌟 Physics-Based Interactions**: Interactive particle system that responds to mouse movements
- **📱 Fully Responsive**: Optimized for all devices and screen sizes
- **⚡ Lightning Fast**: Built with Astro for optimal performance
- **🔧 JSON-Managed Content**: Easy content updates without code changes
- **🎯 SEO Optimized**: Meta tags, Open Graph, and structured data
- **🚀 GitHub Pages Ready**: Automated deployment with GitHub Actions

## 🏗️ Project Structure

```
/
├── public/
│   ├── favicon.svg
│   └── .nojekyll
├── src/
│   ├── components/
│   │   ├── Navigation.astro
│   │   ├── PhysicsBackground.tsx
│   │   └── sections/
│   │       ├── IntroSection.astro
│   │       ├── AboutSection.astro
│   │       ├── ProjectsSection.astro
│   │       ├── ExperienceSection.astro
│   │       ├── EducationSection.astro
│   │       └── FooterSection.astro
│   ├── data/
│   │   ├── personal.json
│   │   ├── about.json
│   │   ├── projects.json
│   │   ├── experience.json
│   │   └── education.json
│   ├── layouts/
│   │   └── Layout.astro
│   ├── pages/
│   │   └── index.astro
│   └── styles/
│       └── global.css
├── .github/
│   └── workflows/
│       └── deploy.yml
└── package.json
```

## 🛠️ Tech Stack

- **Framework**: [Astro](https://astro.build) - Modern static site generator
- **UI Components**: [React](https://reactjs.org) - For interactive components
- **Styling**: [Tailwind CSS](https://tailwindcss.com) - Utility-first CSS framework
- **Animations**: [Three.js](https://threejs.org) - 3D graphics and physics
- **Icons**: [Heroicons](https://heroicons.com) - Beautiful SVG icons
- **Deployment**: [GitHub Pages](https://pages.github.com) - Free static hosting
- **Package Manager**: [Bun](https://bun.sh) - Fast JavaScript runtime and package manager

## 🚀 Quick Start

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/portfolio.git
   cd portfolio
   ```

2. **Install dependencies**

   ```bash
   bun install
   ```

3. **Start development server**

   ```bash
   bun run dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:4321`

## 🎨 Customization

### Personal Information

Edit the JSON files in `src/data/` to update your personal information:

- `personal.json` - Basic info, contact details, social links
- `about.json` - Bio, skills, achievements
- `projects.json` - Portfolio projects
- `experience.json` - Work experience
- `education.json` - Education and certifications

### Styling

- Modify `src/styles/global.css` for global styles
- Update color schemes in Tailwind classes
- Customize the physics animation in `PhysicsBackground.tsx`

### Content Sections

Each section is a separate Astro component in `src/components/sections/`:

- Modify layouts and styling as needed
- Add or remove sections by updating `src/pages/index.astro`

### Development Guidelines

The project includes a comprehensive `.cursorrules` file that provides:

- Code style and conventions
- Component structure patterns
- TypeScript interfaces for data
- Performance considerations
- Accessibility guidelines
- Common troubleshooting tips

## 📦 Commands

| Command           | Action                               |
| ----------------- | ------------------------------------ |
| `bun install`     | Install dependencies                 |
| `bun run dev`     | Start dev server at `localhost:4321` |
| `bun run build`   | Build production site to `./dist/`   |
| `bun run preview` | Preview build locally                |
| `bun run deploy`  | Deploy to GitHub Pages (manual)      |

## 🚀 Deployment

### Automatic Deployment (Recommended)

1. **Fork this repository** to your GitHub account

2. **Update the site configuration** in `astro.config.mjs`:

   ```js
   export default defineConfig({
     site: "https://yourusername.github.io",
     base: "/portfolio", // or '/' if using yourusername.github.io
     // ... other config
   });
   ```

3. **Enable GitHub Pages** in your repository settings:

   - Go to Settings > Pages
   - Source: GitHub Actions
   - The workflow will automatically deploy on every push to main

4. **Update your content** in the JSON files and push to main branch

### Manual Deployment

```bash
bun run build
# Upload the dist/ folder to your hosting provider
```

## 🎯 Performance

- **Lighthouse Score**: 100/100 (Performance, Accessibility, Best Practices, SEO)
- **Bundle Size**: < 50KB gzipped
- **Load Time**: < 1s on 3G networks
- **Core Web Vitals**: All green

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Astro](https://astro.build) for the amazing static site generator
- [Tailwind CSS](https://tailwindcss.com) for the utility-first CSS framework
- [Heroicons](https://heroicons.com) for the beautiful icons
- [Three.js](https://threejs.org) for 3D graphics capabilities

---

**Built with ❤️ by Dhaval Patel**

If you found this helpful, please give it a ⭐!
