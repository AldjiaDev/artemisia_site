# README

Artemisia — Rails Magazine-Style Website

A technical overview for developers and contributors

📑 Project Summary

Artemisia is a Ruby on Rails 7 application demonstrating a magazine-style UI/UX system built for artistic portfolio websites.

It serves as a front-end architecture example for:

multi-page editorial layouts

double-page reading experiences (print-like)

consistent right-column navigation

responsive adaptations

image-driven visual hierarchy

This project does not include a database or admin backend.
It focuses solely on frontend structure, architecture, design system and component logic inside a Rails app.

🏗 Architecture Overview
Directory Structure
app/
  controllers/
    pages_controller.rb
  views/
    pages/
      home.html.erb
      about/
        index.html.erb
      exhibitions/
        index.html.erb
      works/
        index.html.erb
      contact/
        index.html.erb
  assets/
    stylesheets/
      magazine.css      # full editorial design system
    images/
      artemisia-cover.jpg
      about.jpg
      works-hero.jpg
      work1.jpg
      work2.jpg
      work3.jpg
      work4.jpg

⚙ Technology Stack
Backend

Ruby 3.x

Ruby on Rails 7.x (importmap)

Frontend

Bootstrap 5.3 (grid + utilities only)

Custom editorial CSS (magazine.css)

SVG inline icons (Instagram, X/Twitter, Facebook, YouTube)

No JavaScript framework (Alpine/Stimulus optional)

Assets

Rails asset pipeline for images and CSS

Importmap for JavaScript bundling

No Webpacker / esbuild / Vite

🎨 UI/UX & Design System (Technical)

All design logic is centralized in app/assets/stylesheets/magazine.css, which contains:

🧱 Layout primitives

full-screen cover (.mag-cover)

double-page layouts (.about-double-page, .exhibitions-double-page, etc.)

unified aside navigation (.mag-right-column)

gutters using pseudo-elements

editorial column system (max-width constraints)

🎚 Typography system

clamp() for scalable titles

serif/sans-serif pairing

optical margin / spacing rules

print-like line height ratios

🎛 Components

navigation blocks (.mag-right-block)

pull quotes

footer modules

artwork cards

responsive grid system

🪄 Animations

subtle fade/slides for navigation

optional “page flip” overlay (CSS animation)

🌐 Routing

All pages are static and handled through PagesController:

Rails.application.routes.draw do
  root "pages#home"

  get "about",       to: "pages#about"
  get "exhibitions", to: "pages#exhibitions"
  get "works",       to: "pages#works"
  get "contact",     to: "pages#contact"
end

🚀 Setup & Installation
1. Clone the repository
git clone https://github.com/AldjiaDev/artemisia_site.git
cd artemisia_site

2. Install dependencies
bundle install

3. Run the application
bin/rails s


Open in browser:

http://localhost:3000

🧪 Testing (optional section)

No test suite is currently implemented.
Recommended stack for future integration:

RSpec

Capybara

ViewComponent (for isolating magazine components)

🗺 Future Improvements
🔹 Technical

Extract navigation blocks into ViewComponents

Convert static content into YAML + helper

Add i18n support

Add caching for static pages

Move layout logic into Rails partials

Introduce Stimulus for interactive sections

🔹 Product

Add CMS (ActiveAdmin or a lightweight custom backend)

Add dynamic artwork management

Add RSS feed for exhibitions

Add SEO meta tags + OpenGraph

Add dark mode (print-inspired)

👩‍💻 Author — Technical Profile
Aldjia Benkhelifa

Full-Stack Ruby on Rails Developer
Specialized in editorial design systems & artistic interfaces

Portfolio: https://aldjia.dev

GitHub: https://github.com/AldjiaDev

Podcasts: ART au féminin, Dev Zone

📄 License

This project is provided for demonstration and technical reference.
All rights reserved.
