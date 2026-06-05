# FKhatib Lab - Research Website Revamp
This project is part of a volunteer collaboration to redesign and modernize the research lab website.
The site is built using Astro and uses JSON-based content management to simplify future updates. Most content can be updated without modifying any Astro components.

## Objectives

- Improve site structure and usability
- Create a modern responsive design
- Simplify content updates for publications, media, contact and CV pages

## Design

The website redesign UI/UX was created in Figma.

Figma design file:
[Figma link](https://www.figma.com/design/Da23ctadzMskq2QxLz9nj8/website-revamp?node-id=2-428&p=f&t=EEX3t7Z2iO8b1mBh-0)

## Tech Stack

- Astro
- TypeScript
- CSS

Node.js version: 22.12.0 or later

## Local Development, Running the Project

Install dependencies:

```bash
npm install
```

Start development server:

```bash
npm run dev
```

Build production version:

```bash
npm run build
```

Preview production build on local machine:

```bash
npm run preview
```

## Folder Structure
```
src/
├── components/
├── data/
├── layouts/
├── pages/
└── styles/

public/
└── images/
```

```
| Folder         | Purpose                         |
| -------------- | ------------------------------- |
| src/components | Reusable UI components          |
| src/layouts    | Shared page layouts             |
| src/pages      | Website pages                   |
| src/data       | JSON content files              |
| src/styles     | Stylesheets                     |
| public/images  | Images used throughout the site |
```

## How to Update Publications

Publication data is stored in:

src/data/publications.json

Example:

Append a structure like the following to the publications.json file
```
{
    "title": "ABC Research",
    "authors": ["Khatib F", "Weirauch MT"],
    "journal": "Bioinformatics",
    "year": 2026,
    "volume":"22(14): 252-259",
    "doi": "",
    "pdf": "https://www.cis.umassd.edu/~fkhatib/Papers/Knotfind.pdf"
}
```

Note: If any of the keys are empty, do not omit the key. Instead, keep the value as empty, as shown for the 'doi' key in the example. 

This will:
Add new publications to the JSON file.
Publications automatically appear on the Publications page.
Publications are automatically sorted by year.
Search functionality updates automatically.

## How to update Media 

Media items are stored in:

src/data/media.json

There are three sections in the json file:

featuredVideos, moreVideos, otherMedia.

To add a video that should be displayed on the top of the list, use featuredVideos section.
To add other videos, use moreVideos section. 
Example:
```
{
    "title": "Tackling Covid-19 with Foldit",
    "subtitle": "Citizen Science Association Webinar",
    "videoUrl": "https://www.youtube.com/embed/OX36TJQfaIA?start=965"
}
```
Note: If you do not have a subtitle for the video, do not omit the 'subtitle' key. Instead, keep the value as empty. 

To add other media mentions, use 'otherMedia'.

Example:
```
{
    "source": "NPR",
    "title": "When Scientists Fail, It's Time To Call In The Gamers",
    "url": "https://www.npr.org/......"
},
```
Note: If you do not have a source where the article is published, do not omit the 'source' key. Instead, keep the value as empty.

## How to Update Contact Information

Contact information is stored in:

src/data/contact.json

Can update:

Email
Phone
Office
Fax

To add a new contact card, add a new item in the items array, either before the existing items or at the end of it. Example:
```
items: [
    .....,
    .....,
    {
        "title": "Instagram",
        "value": "insta_handle",
        "icon": "/images/icons/insta.svg"
    }
]
```
To add or replace icons, place the icon in the /images/icons folder in the public folder, and update the icon path in the json file.

## How to Update CV Information

CV content is stored in:

src/data/cv.json

To update any information in the profile card, make changes in the 'profile' section.

To update any other section (e.g., Education or Research and Professional Experience), make changes within the 'sections' array.

To add a new section (e.g., Awards), add a new item in the 'sections' array, either before the existing items or at the end of it. Example:
```
items: [
    .....,
    .....,
    {
      "title": "Awards",
      "items": [
        "Award 1"
      ]
    }
]
```
Note: To style the contents in the 'items' array, you can use HTML.

## Images

All images are stored in:

public/images/

## Building for Production

Note: GitHub Pages was used only for demonstration purposes.

Generate a production build:

The GitHub Pages deployment workflow was created for demonstration purposes only.

For production deployment:

1. Run `npm install`

```bash
npm install
```

2. Run `npm run build`

```bash
npm run build
```
3. Deploy the generated `dist/` folder to the target hosting environment'

Astro will create a `dist/` directory containing the static website files.

The contents of the `dist/` folder should be deployed to the web server or hosting platform.

Example:
```
project/
├── src/
├── public/
├── dist/   ← deploy this folder
└── package.json
```

## Deployment Notes

After running:

```bash
npm run build
```

the generated `dist/` folder contains the complete static website.

Deploy the contents of the `dist/` folder to your hosting provider.

For local verification:

```bash
npm run preview
```
This serves the production build locally before deployment.

### Node.js Requirement

This project requires:

Node.js v22.12.0 or later

Earlier Node.js versions may fail during Astro builds.