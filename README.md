# Volaris Documentation Site

Welcome to the Volaris Documentation site! This repository contains the code for the official documentation of the Volaris encryption tool, built with SvelteKit and styled using Tailwind CSS.

## Project Overview

The Volaris Documentation site provides users with detailed information about the Volaris encryption tool, including guides, FAQs, and getting started instructions. The site is designed to be minimalist and responsive, featuring smooth animations and a clean layout.

## File Structure

- `src/routes/`: Main homepage of the documentation.
- `src/lib/global.css`: Global CSS styles.
- `src/lib/style404.css`: 404 Page's CSS styles.
- `src/routes/docs/introduction`: Introduction to Volaris.
- `src/routes/docs/installing-building`: Guide to installing/building Volaris.
- `src/routes/faq/`: Frequently asked questions.

## Getting Started

To set up and run the project locally, follow these steps:

1. **Clone the Repository**

    ```sh
    git clone https://github.com/volar-is/volaris-docs.git
    cd volaris-docs
    ```

2. **Install Dependencies**

    ```sh
    pnpm install
    ```

3. **Start the Development Server**

    ```sh
    pnpm run dev
    ```

   The local development server will be available at `http://localhost:5173`.

## Contributing

We welcome contributions from the community. To contribute:

1. Fork the repository.
2. Create a new branch:
   `git checkout -b feature/YourFeature`
3. Make your changes and commit them:
   `git commit -m "feat: Add your feature"`
4. Push to the branch:
   `git push origin feature/YourFeature`
5. Open a pull request.

Please ensure your code adheres to our coding standards and includes appropriate tests.

**Note:** This repository uses conventional commits. Please follow the [conventional commits guidelines](https://www.conventionalcommits.org/en/v1.0.0/) for your commit messages.

## License

This project is licensed under the BSD 2-Clause License. See the [LICENSE](LICENSE) file for details.
