# Provider Data Cleaner

A modern, AI-powered React application for cleaning and validating healthcare provider data with automated phone number standardization, email validation, address quality analysis, and Google Maps integration.

![Provider Data Cleaner](https://img.shields.io/badge/React-18.2.0-blue)
![Vite](https://img.shields.io/badge/Vite-7.1.10-646CFF)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.1.14-38B2AC)

## 🌟 Features

### Data Cleaning & Validation
- **Phone Number Standardization**: Automatically formats phone numbers to Indian standard (+91 format)
  - Handles 10-digit, 11-digit (with 0), and 12-digit formats
  - Validates and flags invalid numbers
- **Email Validation**: Cleans and validates email addresses
  - Removes whitespace
  - Fixes multiple @ symbols
  - Removes consecutive dots
  - Validates against RFC standards
- **Address Quality Analysis**: Intelligent address scoring system
  - Checks for street numbers, street types, ZIP codes, and city names
  - Rates addresses: Excellent, Good, Fair, Poor, or Invalid
  - Generates approximate coordinates for valid addresses (India bounds)
  - Identifies specific issues in incomplete addresses

### Integration & Export
- **Google Maps Integration**: One-click address verification in Google Maps
- **Multiple Export Formats**: Download cleaned data as CSV or JSON
- **Audit Trail**: Complete decision logs showing all data transformations
- **Real-time Processing**: Visual feedback during data cleaning operations

### User Experience
- **Drag & Drop Interface**: Intuitive file upload with drag-and-drop support
- **Visual Statistics**: Real-time dashboard showing cleaning metrics
- **Data Preview**: Interactive table view with quality indicators
- **Modern UI**: Gradient designs with smooth animations and transitions

## 📋 Prerequisites

- Node.js (v16 or higher)
- npm or yarn package manager

## 🚀 Getting Started

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd ai-agentic-2
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and navigate to `http://localhost:5173`

### Building for Production

```bash
npm run build
```

The optimized production build will be created in the `dist` directory.

### Preview Production Build

```bash
npm run preview
```

## 📁 Project Structure

```
ai-agentic-2/
├── src/
│   ├── AI-AGENTIC.jsx      # Main application component
│   ├── main.jsx             # Application entry point
│   └── index.css            # Global styles and Tailwind imports
├── index.html               # HTML template
├── package.json             # Dependencies and scripts
├── vite.config.js           # Vite configuration with JSX support
├── tailwind.config.js       # Tailwind CSS configuration
└── postcss.config.js        # PostCSS configuration
```

## 💻 Usage

### Expected CSV Format

Upload a CSV file with the following columns (all optional, but recommended):
- `name`: Provider name
- `phone`: Phone number (any format)
- `email`: Email address
- `address`: Physical address
- `license`: License number
- `specialty`: Medical specialty
- `network`: Insurance network

### Data Transformations

**Phone Numbers:**
- Input: `9876543210` → Output: `+919876543210`
- Input: `09876543210` → Output: `+919876543210`
- Input: `919876543210` → Output: `+919876543210`

**Email Addresses:**
- Removes spaces: `test @email.com` → `test@email.com`
- Fixes multiple @: `test@@email.com` → `test@email.com`
- Removes consecutive dots: `test..name@email.com` → `test.name@email.com`

**Address Analysis:**
The system scores addresses based on:
- Street number presence (25 points)
- Street type identification (25 points)
- ZIP code format (20 points)
- City information (30 points)

### Output Fields

The cleaned CSV/JSON includes these additional fields:
- `phone_valid`: Boolean indicating valid phone number
- `email_valid`: Boolean indicating valid email address
- `address_rating`: Quality rating (Excellent/Good/Fair/Poor/Invalid)
- `approximate_latitude`: Generated coordinate for valid addresses
- `approximate_longitude`: Generated coordinate for valid addresses
- `validation_status`: Overall validation status (Validated/Pending)
- `last_updated`: Date of last validation

## 🛠️ Technology Stack

- **React 18.2.0**: Modern UI library with hooks
- **Vite 7.1.10**: Next-generation frontend tooling
- **Tailwind CSS 4.1.14**: Utility-first CSS framework
- **PapaParse 5.5.3**: CSV parsing and generation
- **Lucide React 0.545.0**: Beautiful icon library
- **PostCSS & Autoprefixer**: CSS processing

## 🎨 UI Components

- Gradient backgrounds and cards
- Animated hover effects
- Responsive design for all screen sizes
- Visual validation indicators (checkmarks, color-coded ratings)
- Interactive data tables
- Modal loading states

## 🔧 Configuration

### Vite Configuration
The project uses custom Vite configuration to support `.JSX` file extensions:
```javascript
esbuild: {
  loader: 'jsx',
  include: /src\/.*\.[jt]sx?$/,
}
```

### Tailwind CSS
Configured with modern Tailwind v4 using PostCSS plugin architecture.

## 📊 Features in Detail

### Address Quality Rating System
- **Excellent (90+ points)**: Complete address with all components
- **Good (70-89 points)**: Most components present
- **Fair (50-69 points)**: Basic address information
- **Poor (30-49 points)**: Minimal address details
- **Invalid (0-29 points)**: Incomplete or missing address

### Coordinate Generation
For addresses scoring 50+ points, the system generates approximate coordinates:
- Latitude range: 8°N to 35°N (India)
- Longitude range: 68°E to 97°E (India)
- Uses deterministic hash-based generation for consistency

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is open source and available under the MIT License.

## 🐛 Known Issues

- Coordinate generation is approximate and for visualization only
- Address analysis optimized for Indian addresses
- Large CSV files (>10MB) may experience slower processing

## 🔮 Future Enhancements

- [ ] Real geocoding API integration
- [ ] Support for international phone formats
- [ ] Batch processing for multiple files
- [ ] Advanced duplicate detection
- [ ] Database export options
- [ ] Undo/redo functionality
- [ ] Custom validation rules

## 📞 Support

For issues, questions, or contributions, please open an issue on the GitHub repository.

---

Built with ❤️ using React and Vite
