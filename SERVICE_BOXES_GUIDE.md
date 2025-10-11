# Service Boxes Configuration Guide

This guide explains how to customize and add service boxes to your homepage.

## Configuration Files

### 1. Main Configuration: `/data/en/homepage.yml`

The service boxes are configured in the `highlights` section of this file.

```yaml
items:
  - type: highlights
    title: "Our Services"                    # Section title (optional)
    subtitle: "Comprehensive technology solutions for your business"  # Section subtitle (optional)
    items_per_row: 4                        # Number of boxes per row (1-4)
    items:
      - title: "Service Name"               # Service title
        icon: "fa-icon-name"                # FontAwesome icon class
        url: "/services/service-page"       # Link URL (optional)
        description: "Short tech description" # Brief technical description
        content: >                          # Detailed description
          Full description of the service that appears in the box.
          Can be multiple lines and supports Markdown formatting.
```

## Adding New Service Boxes

### Step 1: Add to Configuration

Add a new item to the `items` array in `/data/en/homepage.yml`:

```yaml
- title: "New Service"
  icon: "fa-rocket"
  url: "/services/new-service"
  description: "Technology Stack"
  content: >
    Detailed description of your new service offering
    and its benefits to clients.
```

### Step 2: Create Service Page (Optional)

If you want a dedicated page for the service, create:
`/content/services/new-service.md`

```markdown
---
title: "New Service"
date: 2024-01-15
draft: false
layout: "left-sidebar"
---

# New Service

Detailed content about your new service...
```

### Step 3: Update Menu (Optional)

Add to dropdown menu in `/config.toml`:

```toml
[[menu.main]]
name = "New Service"
url = "/services/new-service"
parent = "Services"
weight = 25
```

## Available FontAwesome Icons

Common service icons you can use:

- `fa-cloud` - Cloud services
- `fa-code` - Web development
- `fa-cogs` - DevOps/Engineering
- `fa-lightbulb` - Consulting
- `fa-mobile-alt` - Mobile development
- `fa-shield-alt` - Security
- `fa-database` - Data services
- `fa-rocket` - Startups/Innovation
- `fa-chart-line` - Analytics
- `fa-network-wired` - Networking
- `fa-server` - Infrastructure
- `fa-lock` - Cybersecurity

## Layout Options

### Items Per Row
- `items_per_row: 1` - Full width boxes
- `items_per_row: 2` - Two columns
- `items_per_row: 3` - Three columns
- `items_per_row: 4` - Four columns (default)

### Box Content Structure

Each service box contains:
1. **Icon** - Square icon with background
2. **Title** - Service name (h3)
3. **Description** - Technical stack/brief description
4. **Content** - Detailed description

## Styling Customization

### Colors

Main theme colors are defined in the SCSS files:
- Primary: `#3c7d7d`
- Hover states automatically use darker shades
- Backgrounds use white with subtle shadows

### Box Dimensions

Current settings:
- Height: `220px` (rectangular)
- Icon size: `3.5em x 3.5em`
- Spacing: Close spacing with `gtr-50`

## Example Complete Configuration

```yaml
items:
  - type: highlights
    title: "Our Services"
    subtitle: "Complete technology solutions"
    items_per_row: 4
    items:
    - title: Cloud Solutions
      icon: fa-cloud
      url: /services/cloud
      description: "AWS, Azure & Google Cloud"
      content: >
        Enterprise cloud infrastructure with 99.9% uptime guarantee.
    - title: Web Development
      icon: fa-code
      url: /services/web-development
      description: "React, Vue.js & Full-Stack"
      content: >
        Modern web applications with responsive design.
    - title: Mobile Apps
      icon: fa-mobile-alt
      url: /services/mobile
      description: "iOS, Android & React Native"
      content: >
        Cross-platform mobile applications for all devices.
    - title: AI Solutions
      icon: fa-robot
      url: /services/ai
      description: "Machine Learning & AI"
      content: >
        Intelligent automation and data-driven insights.
```

## Tips

1. **Keep descriptions short** - Use 2-4 words for technical descriptions
2. **Consistent content length** - Similar content length looks better
3. **Use appropriate icons** - Choose icons that represent your service
4. **Test responsiveness** - Check how boxes look on different screen sizes
5. **Update menu** - Remember to add new services to the dropdown menu