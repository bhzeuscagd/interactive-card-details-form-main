# Frontend Mentor - Interactive card details form solution

This is a solution to the [Interactive card details form challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/interactive-card-details-form-XpS8cKZDWw). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- Fill in the form and see the card details update in real-time
- Receive error messages when the form is submitted if:
  - Any input field is empty
  - The card number, expiry date, or CVC fields are in the wrong format
- View the optimal layout depending on their device's screen size
- See hover, active, and focus states for interactive elements on the page

### Links

- Solution URL: [GitHub Repository](https://github.com/bhzeuscagd/interactive-card-details-form-main)
- Live Site URL: [https://interactive-card-details-form-main-blond.vercel.app](https://interactive-card-details-form-main-blond.vercel.app)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- [Astro](https://astro.build/) - The web framework for content-driven websites
- [Tailwind CSS](https://tailwindcss.com/) - For utility-first styling
- [TypeScript](https://www.typescriptlang.org/) - For type safety
- [Sharp](https://sharp.pixelplumbing.com/) - For high-performance image processing

### What I learned

This project was a great opportunity to practice building interactive forms with Astro. I learned how to:

- **Handle Form Reactivity**: implemented real-time validation and visual feedback using Vanilla JavaScript within Astro's `<script>` tags, ensuring immediate response to user input without heavy client-side frameworks.
- **Data Binding**: Created a custom data binding system to update the credit card preview in real-time as the user types in the form fields.
- **Regex Validation**: Used regular expressions to format the credit card number with spaces every four digits and to validate numeric inputs.
- **Astro Image Optimization**: Leveraged Astro's built-in image optimization tools with `sharp` to serve responsive and optimized images.

Here is a snippet of the interactive validation logic I implemented:

```typescript
const updateUI = () => {
    // CASO ESPECIAL: Si es el número de tarjeta, aplicamos formato
    if (inputId === "cardNumber") {
        const cleanValue = inputElement.value.replace(/\D/g, "");
        const formattedValue = cleanValue.replace(
            /(\d{4})(?=\d)/g,
            "$1 ",
        );
        inputElement.value = formattedValue;
        previewElement.textContent = formattedValue || defaultText || "";
    } else {
        previewElement.textContent = inputElement.value || defaultText || "";
    }
};
```

### Continued development

I plan to continue exploring Astro's advanced features, specifically its "Inslands Architecture" for more complex interactive components. I also want to dive deeper into accessibility (a11y) to ensure my forms are fully usable by everyone, including screen reader users.

### Useful resources

- [Astro Documentation](https://docs.astro.build/en/getting-started/) - essential for understanding the project structure and component system.
- [Tailwind CSS Documentation](https://tailwindcss.com/docs) - helped with quickly styling the responsive layout.
- [Regex101](https://regex101.com/) - Invaluable for testing and refining the regular expressions used for input validation.

## Author
- Portfolio - [bhzeuscagd](https://portfolio-cagd.vercel.app/)
- GitHub - [bhzeuscagd](https://github.com/bhzeuscagd)
- Frontend Mentor - [@bhzeuscagd](https://www.frontendmentor.io/profile/bhzeuscagd)

## Acknowledgments

Thanks to the Frontend Mentor community for the inspiration and the challenges that help developers sharpen their skills.
