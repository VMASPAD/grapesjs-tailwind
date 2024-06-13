# Next.js GrapesJS TailwindCss Integration

This project demonstrates how to integrate GrapesJS, a free and open-source web builder framework, with a Next.js application. The provided code sets up a basic environment where you can use GrapesJS to drag-and-drop HTML elements and build web pages dynamically.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Dependencies](#dependencies)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/yourusername/nextjs-grapesjs-integration.git
   cd nextjs-grapesjs-integration
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Run the development server:**

   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Usage

The main component in this project initializes GrapesJS and sets up a basic block manager with a few predefined blocks. The blocks include a section, a text block, and an image block. These can be dragged and dropped onto the canvas.

### Code Overview

Here's a brief explanation of the key parts of the code:

- **Initialization of GrapesJS:**
  ```javascript
  const editor = grapesjs.init({
    container: '#editorjs',
    fromElement: true,
    height: '800px',
    width: 'auto',
    storageManager: false,
    panels: { defaults: [] },
    canvas: {
      styles: ["/tailwind.css", "/globals.css"]
    },
    blockManager: {
      appendTo: '#blocks',
      blocks: [
        {
          id: 'section',
          label: '<p class="font-bold text-red-500">Section</p>',
          attributes: { class:'gjs-block-section' },
          content: `<section>
            <h1 class="text-5xl font-bold">This is a simple title</h1>
            <div>This is just a Lorem text: Lorem ipsum dolor sit amet</div>
          </section>`,
        },
        {
          id: 'text',
          label: 'Text',
          content: '<div data-gjs-type="text">Insert your text here</div>',
        },
        {
          id: 'image',
          label: 'Image',
          select: true,
          content: { type: 'image' },
          activate: true,
        }
      ]
    },
  });
  ```

- **Custom Styles:**
  The editor uses custom styles from `tailwind.css` and `globals.css` to style the elements on the canvas.

- **Block Manager:**
  The block manager is configured to append blocks to the element with the ID `blocks`. It defines three blocks: a section, a text block, and an image block.

## Project Structure

- **pages/index.js:** The main page where GrapesJS is initialized.
- **public/tailwind.css:** Custom Tailwind CSS styles.
- **public/globals.css:** Global CSS styles.

## Dependencies

- **Next.js:** React framework for server-side rendering and static site generation.
- **GrapesJS:** Web builder framework for building HTML templates.
- **Tailwind CSS:** Utility-first CSS framework for styling.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a pull request

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
