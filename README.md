# PerkPal

PerkPal is a community-focused deals and discounts platform built with HTML, CSS, and JavaScript. The project helps users discover offers tailored to their profile, including students, senior citizens, Black community members, and LGBTQ+ community members.

The application includes a public landing experience, authentication pages, personalized offer views, category-specific deal pages, a wishlist page, and an about page with FAQ, testimonials, and contact content.

## Overview

PerkPal is designed to make relevant savings easier to find. Users can explore deals by audience and category, register or log in, and view personalized offers based on their saved profile information.

The current repository is primarily a static frontend. Some pages also expect a backend service running locally on port `8080` for user registration, login, and personalized offer retrieval.

## Key Features

- Responsive landing page with featured deals and category filtering.
- Audience-based deal navigation for students, senior citizens, Black community members, and LGBTQ+ community members.
- Deal categories including clothing, entertainment, education, transport, food, electronics, and travel.
- Login and registration pages with client-side validation.
- Personalized welcome page that loads offers from a local API.
- Wishlist page for saved deals.
- Dark mode toggles across multiple pages.
- Scroll progress indicators, animated UI elements, and interactive deal cards.
- About page with mission statement, FAQ accordion, testimonials, and contact form.

## Tech Stack

- HTML5
- CSS3
- JavaScript
- Google Fonts
- Material Design Icons
- particles.js

## Project Structure

```text
PerkPal/
|-- About us page/
|   `-- aboutuspage.html
|-- Black/
|   |-- Black Clothing Page/
|   |-- Black Education Page/
|   |-- Black Electronics Page/
|   |-- Black Entertainment Page/
|   |-- Black Food Page/
|   `-- Black Transport Page/
|-- LGBTQ/
|   |-- LGBTQ Clothing Page/
|   |-- LGBTQ Education Page/
|   |-- LGBTQ Entertainment Page/
|   |-- LGBTQ Food Page/
|   `-- LGBTQ Travel/
|-- LogIn Page/
|   `-- loginpage.html
|-- Registration Page/
|   `-- registrationform.html
|-- Sr Citizen/
|   |-- Sr Citizen Clothing/
|   |-- Sr Citizen Education Page/
|   |-- Sr Citizen Electronics Page/
|   |-- Sr Citizen Entertainment Page/
|   |-- Sr Citizen Food page/
|   `-- Sr Citizen Travel Page/
|-- Student/
|   |-- Student Clothing Page/
|   |-- Student Education Page/
|   |-- Student Electronics Page/
|   |-- Student Entertainment page/
|   |-- Student Food page/
|   `-- Students Transport page/
|-- Wishlist Page/
|   `-- wishlist.html
|-- index.html
|-- welcomepage.html
|-- styles.css
`-- README.md
```

## Main Pages

- `index.html`: Public homepage with navigation, featured deals, filtering, dark mode, and claim buttons.
- `welcomepage.html`: Personalized post-login page that fetches eligible offers for the logged-in user.
- `Registration Page/registrationform.html`: User registration form with validation and profile fields.
- `LogIn Page/loginpage.html`: Login form with validation and local storage setup.
- `Wishlist Page/wishlist.html`: Wishlist interface for saved deals.
- `About us page/aboutuspage.html`: Project information, FAQ, testimonials, and contact form.

## Getting Started

### Prerequisites

You only need a modern web browser to view the static pages. For the personalized login and offer flow, you also need a backend API running on `http://localhost:8080`.

### Run Locally

Clone the repository:

```bash
git clone https://github.com/Tarunk1109/PerkPal.git
cd PerkPal
```

Open `index.html` directly in a browser, or serve the project with a lightweight local server:

```bash
python3 -m http.server 5500
```

Then visit:

```text
http://localhost:5500
```

## Backend API Expectations

The frontend currently references these local API endpoints:

```text
POST http://localhost:8080/api/users/register
POST http://localhost:8080/api/users/login
GET  http://localhost:8080/api/offers/user/{email}
GET  http://localhost:8080/api/offers/user/{email}/category/{category}
```

Expected user login response fields include:

```json
{
  "name": "User Name",
  "email": "user@example.com",
  "userGroups": ["Student"]
}
```

Expected offer response fields include:

```json
[
  {
    "title": "Offer title",
    "description": "Offer description",
    "discount": "50% off",
    "category": "Education",
    "imageLink": "https://example.com/image.jpg",
    "link": "https://example.com"
  }
]
```

## User Flow

1. Visit the homepage through `index.html`.
2. Browse deals by audience or category.
3. Register through `Registration Page/registrationform.html`.
4. Log in through `LogIn Page/loginpage.html`.
5. View personalized offers on `welcomepage.html`.
6. Open individual category pages or save offers to the wishlist.

## Design Notes

- The interface uses a clean blue-focused visual system with card-based layouts.
- Several pages include dark mode support for improved viewing flexibility.
- Navigation is organized around audience groups and deal categories.
- Interactive UI behavior is implemented with vanilla JavaScript.

## Future Improvements

- Add a complete backend implementation for users, offers, and wishlists.
- Replace hardcoded local API URLs with configurable environment values.
- Consolidate repeated navbar, footer, and styling patterns into shared assets.
- Improve mobile navigation behavior across all category pages.
- Add automated accessibility, HTML validation, and link-checking workflows.
- Add deployment instructions for GitHub Pages or another static hosting provider.

## Contributing

Contributions are welcome. To contribute:

1. Fork the repository.
2. Create a feature branch.
3. Make focused, well-tested changes.
4. Commit with a clear message.
5. Open a pull request describing the update.

## License

No license file is currently included in this repository. Add a license before distributing or reusing the project publicly.
