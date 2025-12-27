# Theme Quick Reference Guide

## 🎨 Color Palette

### Primary Colors
```
Cyan (Primary):    #00d9ff  |  hsl(188 100% 50%)  |  bg-primary, text-primary
Green (Secondary): #39ff14  |  hsl(123 100% 55%)  |  bg-secondary, text-secondary
```

### Background Colors
```
Background:        #0a0e1a  |  hsl(222 84% 5%)    |  bg-background
Card:              #0f1419  |  hsl(222 84% 8%)    |  bg-card
Muted:             #1a2332  |  hsl(217 33% 15%)   |  bg-muted
```

### Text Colors
```
Foreground:        #d9ffff  |  hsl(180 100% 90%)  |  text-foreground
Muted Text:        #8fa3b8  |  hsl(215 20% 60%)   |  text-muted-foreground
```

### Border & Effects
```
Border:            #00d9ff4d (30% opacity)         |  border-border
Ring:              #00d9ff                         |  ring-ring
```

---

## 🛠️ Utility Classes

### Gradients
```css
.gradient-hero      /* Hero section gradient background */
.gradient-card      /* Card gradient background */
.gradient-text      /* Gradient text effect */
```

### Shadows & Glows
```css
.shadow-elegant     /* Subtle cyan shadow */
.shadow-glow        /* Glowing cyan shadow */
.shadow-neon        /* Strong neon glow */
```

### Effects
```css
.grid-pattern       /* Futuristic grid overlay */
.radial-glow        /* Radial gradient glow */
.border-glow        /* Glowing border effect */
.card-futuristic    /* Complete futuristic card styling */
.transition-smooth  /* Smooth transitions (0.3s) */
```

---

## 📦 Component Examples

### Futuristic Card
```tsx
<Card className="card-futuristic shadow-elegant transition-smooth hover:shadow-glow">
  <CardContent className="p-6">
    <h2 className="text-2xl font-bold text-primary mb-4">Title</h2>
    <p className="text-foreground">Content goes here</p>
  </CardContent>
</Card>
```

### Primary Button with Glow
```tsx
<Button className="shadow-glow transition-smooth">
  Click Me
</Button>
```

### Secondary Button
```tsx
<Button 
  variant="outline" 
  className="border-2 border-secondary text-secondary hover:bg-secondary/10 transition-smooth"
>
  Secondary Action
</Button>
```

### Hero Section
```tsx
<section className="relative h-[600px] overflow-hidden">
  <div className="absolute inset-0 gradient-hero">
    <div className="absolute inset-0 radial-glow" />
    <div className="absolute inset-0 grid-pattern" />
  </div>
  <div className="relative z-10">
    {/* Content */}
  </div>
</section>
```

### Accent Border
```tsx
<div className="border-l-2 border-secondary pl-4">
  <h3 className="text-foreground font-semibold">Title</h3>
  <p className="text-muted-foreground">Description</p>
</div>
```

---

## 🎯 Common Patterns

### Page Container
```tsx
<div className="min-h-screen bg-background">
  {/* Page content */}
</div>
```

### Section with Background
```tsx
<section className="py-16 bg-background">
  <div className="container mx-auto px-4">
    {/* Section content */}
  </div>
</section>
```

### Card Grid
```tsx
<div className="grid grid-cols-1 xl:grid-cols-3 gap-8">
  <Card className="card-futuristic shadow-elegant">
    {/* Card content */}
  </Card>
</div>
```

### Interactive Element
```tsx
<div className="transition-smooth hover:shadow-glow cursor-pointer">
  {/* Interactive content */}
</div>
```

---

## 🎨 Typography

### Headings
```tsx
<h1 className="text-5xl font-bold text-foreground">Main Title</h1>
<h2 className="text-3xl font-bold text-primary">Section Title</h2>
<h3 className="text-xl font-semibold text-foreground">Subsection</h3>
```

### Body Text
```tsx
<p className="text-foreground">Main content text</p>
<p className="text-muted-foreground">Secondary text</p>
<p className="text-primary">Accent text</p>
```

### Links
```tsx
<Link className="text-primary hover:text-primary-glow transition-smooth">
  Link Text
</Link>
```

---

## 🔧 Do's and Don'ts

### ✅ DO
- Use semantic color tokens (`bg-primary`, `text-foreground`)
- Apply `.transition-smooth` to interactive elements
- Use `.card-futuristic` for consistent card styling
- Add hover effects with `.shadow-glow`
- Use `.border-border` for borders

### ❌ DON'T
- Use hardcoded colors (`bg-cyan-500`, `text-green-400`)
- Mix theme tokens with Tailwind color classes
- Forget transitions on interactive elements
- Overuse glow effects (use sparingly for emphasis)
- Use light backgrounds (breaks theme consistency)

---

## 🚀 Quick Start Checklist

When creating a new component:

1. ✅ Use `bg-background` or `bg-card` for backgrounds
2. ✅ Use `text-foreground` for main text
3. ✅ Use `text-primary` for accents
4. ✅ Add `border-border` for borders
5. ✅ Apply `.transition-smooth` to interactive elements
6. ✅ Use `.shadow-elegant` or `.shadow-glow` for depth
7. ✅ Test hover states
8. ✅ Verify contrast ratios

---

## 📱 Responsive Considerations

### Mobile
```tsx
<div className="text-lg xl:text-2xl">
  Responsive text
</div>
```

### Grid Layouts
```tsx
<div className="grid grid-cols-1 xl:grid-cols-3 gap-4 xl:gap-8">
  {/* Responsive grid */}
</div>
```

### Spacing
```tsx
<section className="py-8 xl:py-16">
  {/* Responsive padding */}
</section>
```

---

## 🎭 Animation Examples

### Hover Scale
```tsx
<div className="transition-smooth hover:scale-105">
  {/* Scales on hover */}
</div>
```

### Fade In
```tsx
<div className="opacity-60 hover:opacity-100 transition-smooth">
  {/* Fades in on hover */}
</div>
```

### Glow Effect
```tsx
<Button className="shadow-elegant hover:shadow-glow transition-smooth">
  Glowing Button
</Button>
```

---

## 🔍 Debugging Tips

### Color Not Showing?
- Check if using semantic token (e.g., `bg-primary` not `bg-cyan-500`)
- Verify token exists in `index.css`
- Check for conflicting classes

### Glow Effect Not Visible?
- Ensure element has proper background contrast
- Check if shadow is being overridden
- Verify element has sufficient padding

### Border Not Appearing?
- Confirm using `border-border` class
- Check if border width is set (`border`, `border-2`, etc.)
- Verify opacity is sufficient

---

## 📚 Additional Resources

- **Full Theme Guide**: `THEME_UPDATE_SUMMARY.md`
- **Customization Guide**: `SITE_CUSTOMIZATION_GUIDE.md`
- **Quick Start**: `QUICK_START_CUSTOMIZATION.md`
- **Changelog**: `CHANGELOG.md`

---

**Version**: 1.2.0  
**Last Updated**: 2025-12-02  
**Quick Reference for**: Developers & Designers
