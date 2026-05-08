# Poakpong TheX Company

**Poakpong TheX Company** is a Drupal Recipe designed to instantly scaffold a professional corporate demo website. It automates the setup of a company profile using the Thex theme, sample pages, menu links, reusable footer content, and custom corporate branding via the Asset Injector module.

This recipe is ideal for developers or site builders who need to quickly spin up a polished "Company Profile" demo site with essential configurations pre-applied.

## Key Features

### Theme Setup:
- Enables **Thex** as the default frontend theme.
- Enables **Claro** as the admin theme for a modern backend experience.
- Places site branding, main navigation, main content, status messages, and the company footer block in Thex regions.

### Corporate Branding:
- Sets the site name to "สหอัคนี จำกัด (มหาชน)"
- Sets the slogan to "Saha Akanee PCL."
- Custom CSS: Automatically creates an Asset Injector entity with predefined CSS for header styling, corporate fonts, and brand colors.

### Editable Demo Content:
- Creates sample Drupal pages for Home, About, Products, Investor Relations, News, Contact, and Careers.
- Creates main menu links for the primary navigation.
- Creates a reusable custom block for the footer.
- Keeps the demo sections editable through Drupal's standard content, block, and menu administration screens.

### Configuration:
- Disables open user registration (sets to "Administrators only")—a standard practice for corporate sites.

### Dependencies:
- Composer downloads `drupal/thex` and `drupal/asset_injector`.
- The recipe applies Drupal core recipes for the Basic page content type, Basic custom block type, and Full HTML text format before importing demo content.

## Prerequisites
- Drupal 10.3+ or Drupal 11.x.
- Composer.

## Installation Guide

### Prerequisites
Before running this recipe, please ensure that:
1. You have an installed Drupal site.
2. You have placed the `poakpong_thex_company` folder inside the `recipes` directory of your Drupal project (e.g., `your-project-root/recipes/poakpong_thex_company`).

### Steps

#### 1. Download the Recipe
Go to your Drupal project root and download the recipe into your existing `recipes` folder:

```bash
cd recipes
git clone https://github.com/poakpong/poakpong_thex_company.git
cd ..
```

(Note: The `cd ..` command returns you to the project root for the next steps.)

#### 2. Add the Recipe to the Project

Run the following commands at the project root to register and require the recipe:

```bash
composer config repositories.poakpong_thex_company path recipes/poakpong_thex_company
composer require poakpong/poakpong_thex_company
drush cache:rebuild
```

#### 3. Run the Recipe

Navigate to the web directory and apply the recipe:

```bash
cd web
php core/scripts/drupal recipe ../recipes/poakpong_thex_company -v
```

Alternatively, with Drush 13 or later:

```bash
drush recipe ../recipes/poakpong_thex_company
```

#### 4. Export Config and Clear Cache

Go back to the project root to export the new configurations:

```bash
cd ..
drush config:export -y
drush cache:rebuild
```

## Editing After Installation

- Pages: go to `/admin/content` and edit the generated page nodes.
- Menu: go to `/admin/structure/menu/manage/main` and edit the generated main menu links.
- Footer block: go to `/admin/content/block` and edit the "Company footer" custom block.
- Block placement: go to `/admin/structure/block` and adjust Thex regions if your theme layout needs a different arrangement.
