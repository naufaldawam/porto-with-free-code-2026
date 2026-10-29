# Project Hub — Clean White & Blue Portfolio

Project Hub is a personal software-development portfolio for presenting selected projects in one place. It is designed to help visitors quickly understand the work, inspect a project preview when one is available, open its Git repository, and contact the developer about improvements or new work.

The interface follows a clean white-and-blue visual direction: a compact navigation bar, a short introduction with a workspace image, a searchable and filterable project gallery, a project inquiry call-to-action, and a minimal footer. There is intentionally no separate About page or standalone Tech Stack section; the focus stays on the projects themselves.

## What visitors can do

- Browse project cards with a short description and a few relevant technology tags.
- Filter projects by category: **All**, **Web**, **Backend & API**, **Interactive**, and **Tools**.
- Search by project name, description, category, or technology. Press `/` to focus the search field; press `Escape` to clear and leave it.
- Select a project to open a details dialog with two options: **Preview project** and **View Git repository**.
- Use the **Discuss your project** call-to-action to open a contact dialog with **WhatsApp**, **Email**, and **LinkedIn** options.
- Use the mobile navigation on smaller screens.

## How the site works

This is a static website made with **HTML, CSS, and vanilla JavaScript**. It does not require a database, frontend framework, or backend server. Project details and public contact links are stored in `script.js`, while layout and styling are handled by `index.html` and `style.css`.

The project preview and contact dialogs are part of the frontend. If a preview URL, repository URL, or contact detail has not been configured, the corresponding option stays inactive and the site shows a short hint instead of opening a dummy link.

## Project structure

```text
project-hub/
├── index.html              # Page structure and content sections
├── style.css               # Layout, responsive styling, dialogs, and visual system
├── script.js               # Project data, category filters, search, and dialogs
├── assets/
│   ├── workspace.jpg       # Hero workspace image
│   ├── mcu-preview.jpg     # MCU Service preview placeholder
│   ├── payment-preview.jpg # Payment Gateway preview placeholder
│   └── tools-preview.jpg   # Internal Tools preview placeholder
└── README.md               # Project overview and setup guide
```

## Run locally

No build step is required.

1. Extract the project ZIP.
2. Open `index.html` in a browser.
3. Alternatively, open the folder in Visual Studio Code and run it with the Live Server extension.

The fonts are loaded from Google Fonts, so the two web fonts require an internet connection. The page itself is static and can be hosted on a static hosting provider.

## Add or edit projects

Open `script.js` and update the `projects` array near the top of the file. Each entry supports these fields:

| Field | Purpose |
| --- | --- |
| `id` | Unique identifier used by the interface |
| `number` | Small index shown in the project dialog |
| `title` | Project name |
| `categoryLabel` | Short descriptive label shown in the dialog |
| `year` | Project year or reference year |
| `category` | Filter group: `Web`, `Backend & API`, `Interactive`, or `Tools` |
| `description` | Short project summary shown in the gallery and dialog |
| `tech` | Array of small technology tags shown on the card |
| `visual` | CSS preview style: `visual-health`, `visual-payment`, `visual-dashboard`, `visual-3d`, `visual-api`, or `visual-product` |
| `image` | Optional path to a thumbnail under `assets/`; when supplied, it is used instead of the CSS mockup |
| `previewUrl` | Public demo URL; leave empty until it is ready |
| `repoUrl` | Public GitHub or GitLab repository URL; leave empty until it is ready |

Example project entry:

```js
{
  id: 'project-07',
  number: '07',
  title: 'My New Project',
  categoryLabel: 'WEB DEVELOPMENT',
  year: '2026',
  category: 'Web',
  description: 'A short explanation of the problem this project solves.',
  tech: ['HTML', 'CSS', 'JavaScript'],
  visual: 'visual-product',
  previewUrl: 'https://example.com',
  repoUrl: 'https://github.com/username/project'
}
```

Use real URLs and descriptions before publishing. The current six entries are starter content; review their names and summaries and replace them with projects you are allowed to show publicly. Do not publish private client source code, credentials, or confidential screenshots.

## Configure contact options

Near the bottom of `script.js`, edit the `contactDetails` object:

```js
const contactDetails = {
  whatsappNumber: '62812XXXXXXXX',
  email: 'you@example.com',
  linkedinUrl: 'https://www.linkedin.com/in/your-profile/'
};
```

Replace those examples with your real public contact details:

- `whatsappNumber`: international phone number using digits only. For Indonesia, start with `62`; do not include `+`, spaces, or dashes.
- `email`: the email address that should receive project inquiries.
- `linkedinUrl`: the full LinkedIn profile URL starting with `https://`.

The **Get in touch**, **Contact**, footer contact option, and **Discuss your project** links open the same contact dialog. Each option remains inactive until its corresponding detail is configured.

## Design and accessibility

- Uses two font families only: **DM Sans** for the main interface and **IBM Plex Mono** for compact technical labels and metadata.
- Uses a white background, restrained blue accents, thin dividers, and a minimal layout.
- Includes responsive layouts for desktop and mobile, semantic sections, accessible labels for controls, and dialog-based project/contact flows.

## Before publishing

1. Replace sample project content with accurate descriptions of your own work.
2. Add working preview and repository URLs where they are public and appropriate.
3. Replace the sample thumbnail images in `assets/` with genuine project screenshots when available.
4. Fill in all contact details and test each option.
5. Test the category filters, search, project dialogs, contact dialog, and mobile layout.

## License and project data

This repository is a personal portfolio starter. Confirm that you have permission to publish every image, screenshot, logo, project description, repository link, and other asset you include. Add a license file if you intend to grant others explicit reuse rights.
