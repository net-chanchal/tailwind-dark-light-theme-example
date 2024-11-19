# Implementing Dark and Light Themes with TailwindCSS

Here’s a simple example demonstrating how to implement a dark and light theme using Tailwind CSS CDN. Tailwind CSS's `dark` mode utility is used to toggle between light and dark themes.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tailwind CSS Dark & Light Theme</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    // Enable dark mode class for toggling themes
    tailwind.config = {
      darkMode: 'class',
    };
  </script>
</head>
<body class="bg-white text-black dark:bg-gray-900 dark:text-white transition duration-300">
  <!-- Theme Toggle Button -->
  <div class="flex justify-center items-center min-h-screen">
    <div class="text-center">
      <h1 class="text-4xl font-bold mb-4">Tailwind CSS Theme Switcher</h1>
      <p class="mb-6">Click the button to toggle between light and dark themes.</p>
      <button
        id="theme-toggle"
        class="px-6 py-3 bg-blue-500 text-white font-semibold rounded hover:bg-blue-600 dark:bg-yellow-400 dark:text-black dark:hover:bg-yellow-500 transition duration-300"
      >
        Toggle Theme
      </button>
    </div>
  </div>

  <script>
    // JavaScript to toggle dark mode class on the <html> element
    const themeToggle = document.getElementById('theme-toggle');
    themeToggle.addEventListener('click', () => {
      document.documentElement.classList.toggle('dark');
    });
  </script>
</body>
</html>
```

### Explanation with Best Comments:
1. **Dark Mode Configuration**  
   ```javascript
   tailwind.config = { darkMode: 'class' };
   ```
   - Configures Tailwind to use the `dark` mode class (`dark:bg-gray-900`).
   - The `dark` class can be added to the root HTML or body element for toggling themes.

2. **HTML Structure**  
   ```html
   <body class="bg-white text-black dark:bg-gray-900 dark:text-white transition duration-300">
   ```
   - `bg-white` and `text-black`: Default light mode styles.
   - `dark:bg-gray-900` and `dark:text-white`: Dark mode styles when the `dark` class is present.
   - `transition duration-300`: Smooth transitions when toggling themes.

3. **Theme Toggle Button**  
   ```html
   <button id="theme-toggle" class="...">Toggle Theme</button>
   ```
   - A button styled for both light (`bg-blue-500`) and dark (`dark:bg-yellow-400`) themes.
   - Includes hover effects for interactive feedback.

4. **JavaScript for Theme Toggle**  
   ```javascript
   document.documentElement.classList.toggle('dark');
   ```
   - Toggles the `dark` class on the `<html>` element.
   - Ensures immediate theme switch without reloading the page. 

This example provides a clean and easily understandable implementation of light and dark themes with smooth transitions and minimal configuration.