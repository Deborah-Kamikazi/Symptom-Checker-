# CarLens

**Where car details come into focus — helping you discover your dream car.**

CarLens is a modern, interactive web application designed to help users explore and discover detailed information about various vehicles. With a sleek, glassmorphism-inspired interface, users can search for specific cars or filter by make, year, drive type, transmission, and fuel type to find their perfect match.

## Features

*   **Advanced Filtering**: Narrow down your search by Make, Year, Drive Type, Transmission, and Fuel Type.
*   **Smart Search**: Quickly find cars by model name or keyword.
*   **Detailed Specs**: View comprehensive data including horsepower, torque, curb weight, and top features.
*   **Responsive Design**: A clean, grid-based layout that works seamlessly on desktop and mobile devices.
*   **Visual Experience**: High-quality background visuals and a polished UI using the 'Outfit' font family.

## Technologies Used

*   **HTML5**: Semantic structure.
*   **CSS3**: Custom styling with Flexbox, Grid, and Glassmorphism effects.
*   **JavaScript (ES6+)**: Core application logic, DOM manipulation, and API handling.
*   **Google Fonts**: Typography (Outfit).

## API Reference

This project is designed to consume vehicle data from the **Vehicle Database API** via RapidAPI.

*   **API Provider**: [Vehicle Database on RapidAPI](https://rapidapi.com/principalapis/api/vehicle-database)
*   **Endpoint Used**: `https://vehicle-database.p.rapidapi.com/evehicleapi/get-data`

**Note on Data Source**:
During the current development phase, the application uses a robust **Mock Data** system. This ensures the application is fully functional for demonstration and testing purposes without requiring an active API subscription or hitting rate limits. The architecture is set up to easily switch to the live API by toggling the `USE_MOCK_DATA` flag in `js/api/carApi.js` and providing a valid `RAPID_API_KEY`.

## Setup & Installation

To run CarLens locally on your machine:

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/Deborah-Kamikazi/Car_Lens.git
    cd CarLens
    ```

2.  **Open the project**:
    You can simply open `index.html` in your web browser.
    *   *Recommended*: Use a live server extension (like Live Server in VS Code) to ensure all assets and modules load correctly.

3.  **Configuration (Optional)**:
    To use live API data:
    *   Open `js/api/carApi.js`.
    *   Set `const USE_MOCK_DATA = false;`.
    *   Replace `'YOUR_RAPID_API_KEY_HERE'` with your actual RapidAPI key.

## Deployment

CarLens is a static web application, making it easy to deploy to various platforms.

### Deploying to GitHub Pages
1.  Push your code to a GitHub repository.
2.  Go to **Settings** > **Pages**.
3.  Select the `main` branch as the source and save.
4.  Your site will be live at `https://Deborah-Kamikazi.github.io/CarLens/`.

### Deploying to Netlify / Vercel
1.  Connect your GitHub repository to Netlify or Vercel.
2.  The build settings can be left default (no build command needed for this vanilla JS project).
3.  Click **Deploy**.

## Challenges & Solutions

### 1. Balancing Interactivity with Usability
*   **Challenge**: Initially, we experimented with a physics-based "gravity" interface where car cards would fall and bounce. While visually striking, it made browsing specific information difficult and cluttered the UI.
*   **Solution**: We pivoted to a structured **Grid Layout**. This maintained the modern aesthetic through glassmorphism and smooth hover effects but significantly improved readability and user experience, allowing for clearer presentation of car specs.

### 2. Handling Data Complexity
*   **Challenge**: Vehicle data can be deeply nested and inconsistent. Displaying technical specs like "255/45WR19 tires" or specific trim levels required a flexible UI component.
*   **Solution**: We created a modular `carCard.js` component that gracefully handles missing data and formats complex objects (like `powertrain` and `specs_and_dimension`) into readable tags and lists.

### 3. API Dependency during Development
*   **Challenge**: Relying solely on a live API during the UI build phase can be slow and consume quota.
*   **Solution**: We implemented a comprehensive mock data layer. This allowed us to rapidly iterate on the UI (adding filters for Transmission, Drive Type, etc.) and test edge cases without constantly fetching external data.

## Credits

*   **Vehicle Database API**: Thanks to the developers at [Principal APIs](https://rapidapi.com/user/principalapis) for the comprehensive vehicle data structure.
*   **Google Fonts**: For the [Outfit](https://fonts.google.com/specimen/Outfit) typeface.
*   **Icons**: UI elements inspired by modern design systems.

---
