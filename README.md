# 🌿 Massage Therapist Website - Раца Лилия

A beautiful, responsive Vue 3 website for personal massage therapy practice featuring modern design, smooth animations, and an elegant user experience.

## ✨ Features

### 🎨 Visual Design
- **Modern Glass Morphism Effects** - Subtle backdrop blur and transparency effects
- **Animated Gradients** - Dynamic background animations and color transitions
- **Floating Elements** - Subtle animated circles and visual enhancements
- **Smooth Hover Effects** - Enhanced interactions with scaling and shadow effects
- **Responsive Design** - Optimized for desktop, tablet, and mobile devices

### 🚀 User Experience
- **Smooth Scrolling Navigation** - Seamless section transitions
- **Full-Screen Mobile Menu** - Immersive mobile navigation experience
- **Scroll Progress Indicator** - Visual progress bar at the top
- **Back to Top Button** - Convenient floating navigation button
- **Optimized Russian Typography** - Enhanced readability for Cyrillic text

### 📱 Sections
- **Hero Section** - Eye-catching introduction with floating animations
- **About Me** - Personal story with qualifications and experience
- **Services** - Detailed massage therapy offerings with pricing
- **Package Deals** - Cost-effective massage therapy courses
- **Contact** - Multiple contact methods with interactive buttons

### 🛠 Technical Features
- **Vue 3 Composition API** - Modern reactive framework
- **CSS Custom Properties** - Consistent design system
- **Intersection Observer** - Smooth scroll-triggered animations
- **Responsive Grid Layouts** - Flexible content organization
- **Accessibility Features** - Proper focus states and ARIA labels

## 🚀 Getting Started

### Prerequisites
- Node.js (version 16 or higher)
- npm or yarn package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd massage
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

4. **Build for production**
   ```bash
   npm run build
   # or
   yarn build
   ```

## 📁 Project Structure

```
src/
├── components/
│   ├── Header.vue           # Navigation with mobile menu
│   ├── Hero.vue            # Landing section with animations
│   ├── About.vue           # Personal information and qualifications
│   ├── Services.vue        # Massage therapy services
│   ├── Packages.vue        # Package deals and courses
│   ├── Contact.vue         # Contact information and buttons
│   ├── Footer.vue          # Footer with essential info
│   ├── ScrollProgress.vue  # Top progress indicator
│   └── BackToTop.vue       # Floating navigation button
├── composables/
│   └── useScrollAnimation.js # Scroll-triggered animations
├── App.vue                 # Main application component
└── main.js                # Application entry point
```

## 🎨 Design System

### Color Palette
- **Primary**: Warm beige tones (#D2B48C)
- **Secondary**: Olive green (#6B8E23)
- **Backgrounds**: Clean whites and subtle grays
- **Gradients**: Smooth transitions between brand colors

### Typography
- **Headers**: Montserrat (bold, modern)
- **Body Text**: Open Sans (readable, clean)
- **Optimized for Russian**: Enhanced letter-spacing and line-height

### Animations
- **Floating Elements**: Subtle circular movements
- **Hover Effects**: Scale, shadow, and color transitions
- **Scroll Animations**: Fade-in effects triggered by viewport intersection
- **Background Effects**: Shimmer and gradient animations

## 📱 Responsive Breakpoints

- **Desktop**: 1024px and above
- **Tablet**: 768px - 1023px
- **Mobile**: 767px and below
- **Small Mobile**: 480px and below

## 🔧 Customization

### Contact Information
Update contact details in `src/components/Contact.vue`:
- Phone number
- Telegram handle
- WhatsApp link
- Schedule and location

### Services and Pricing
Modify services in `src/components/Services.vue`:
- Service descriptions
- Pricing
- Duration
- Features

### Package Deals
Adjust packages in `src/components/Packages.vue`:
- Package contents
- Pricing
- Savings percentages

### Personal Information
Update therapist details in `src/components/About.vue`:
- Name and bio
- Qualifications
- Experience statistics

## 🌐 Browser Support

- Chrome 88+
- Firefox 85+
- Safari 14+
- Edge 88+

## 📄 License

This project is created for personal use. Please respect the design and code when using for your own projects.

## 🤝 Contributing

This is a personal website project. For suggestions or improvements, please create an issue or contact the developer.

## 📞 Contact

For questions about this website or massage therapy services:
- **Phone**: +7 (900) 123-45-67
- **Telegram**: @lilia_massage
- **Location**: Moscow, Sokolniki District

---

*Built with ❤️ using Vue 3 and modern web technologies*