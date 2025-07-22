# UI Implementation Plan: Financial Dashboard Interface

## 1. Overview

Build a financial information web application with:

- **Left Sidebar Navigation**: Persistent navigation with logo, new chat button, and menu items
- **Main Content Area**: Company overview, stock charts, financial data, and peer comparisons
- **Header Bar**: Breadcrumb navigation and action buttons
- **Responsive Layout**: Three-column layout with sidebar, main content, and detailed information panels

---

## 2. Navigation & Layout Structure

### A. Left Sidebar (Fixed Width ~240px)

- **Background**: `hsl(var(--sidebar))` - Light gray (#f8f9fa)
- **Logo Section**: Abstract snowflake/starburst logo with "New Chat" button
- **Navigation Menu**: Vertical list with icons and labels
- **Active State**: `hsl(var(--sidebar-accent))` background highlight for current section
- **Border**: `hsl(var(--sidebar-border))` for subtle separation

### B. Main Content Area (Flexible Width)

- **Header Bar**: Breadcrumb navigation and action buttons
- **Content Grid**: Two-column layout for company info and financial data
- **Chart Section**: Full-width stock price visualization
- **Data Panels**: Company details, financial profile, and peers comparison

---

## 3. Left Sidebar Implementation

### Logo & New Chat Section

- **Logo**: Abstract geometric design (snowflake/starburst pattern)
- **New Chat Button**: Circular button with plus icon
- **Spacing**: 16px padding around elements

### Navigation Menu Items

- **Home** (Active): Magnifying glass icon, light gray background
- **Discover**: Building/globe icon
- **Spaces**: Stacked squares icon
- **Account**: Dollar sign in dark green circle
- **Upgrade**: Upward arrow in circle
- **Install**: Downward arrow in circle

### Styling Specifications

- **Icon Size**: 20px x 20px
- **Text Size**: 14px, medium weight using `var(--font-sans)`
- **Active State**: `hsl(var(--sidebar-accent))` background with `hsl(var(--sidebar-accent-foreground))` text
- **Hover State**: Subtle background change using `hsl(var(--sidebar))`
- **Border Radius**: `var(--radius)` (0.5rem) for consistent rounding

---

## 4. Header Bar Implementation

### Breadcrumb Navigation

- **Text**: "Perplexity Finance > MSFT"
- **Arrow**: Right-pointing chevron
- **Typography**: 16px, medium weight using `var(--font-sans)`
- **Text Color**: `hsl(var(--foreground))`

### Action Buttons

- **Follow Button**: Star outline icon, `hsl(var(--secondary))` background, `hsl(var(--border))` border
- **Share Button**: Share icon, `hsl(var(--accent))` background, `hsl(var(--accent-foreground))` text
- **Button Size**: 32px height, 12px horizontal padding
- **Border Radius**: `var(--radius)` for consistent styling

---

## 5. Main Content Area - Company Overview Section

### Company Header

- **Logo**: Microsoft four-square grid (red, green, blue, yellow)
- **Company Name**: "Microsoft Corporation" - large, bold, `hsl(var(--foreground))` using `var(--font-sans)`
- **Layout**: Logo left, company name right, 16px spacing

### Navigation Tabs

- **Active Tab**: "Overview" - `hsl(var(--primary))` background, `hsl(var(--primary-foreground))` text
- **Inactive Tabs**: `hsl(var(--muted))` background, `hsl(var(--muted-foreground))` text
- **Tab Style**: Pill-shaped, `var(--radius)` border radius
- **Tab Order**: Overview, Financials, Historical Data, Earnings, Research

### Search Bar

- **Placeholder**: "Search for stocks, ETFs, news, and more"
- **Icon**: Magnifying glass on left
- **Action Buttons**: Grid, person, question mark icons on right
- **Arrow Button**: Right arrow in light gray circle

---

## 6. Stock Price Display Section

### Current Price Boxes

- **Left Box (At Close)**:
  - Price: "$510.05" - large, bold using `var(--font-sans)`
  - Change: "-$1.65" and "0.32%" using `hsl(var(--destructive))`
  - Time: Sun icon + "At close: Jul 18, 4:00:00 PM EDT" using `hsl(var(--muted-foreground))`
- **Right Box (After Hours)**:
  - Price: "$509.59" - large, bold using `var(--font-sans)`
  - Change: "-$0.46" and "0.09%" using `hsl(var(--destructive))`
  - Time: Moon icon + "After hours: 6:45:07 AM EDT" using `hsl(var(--muted-foreground))`

### Chart Controls

- **Toggle Buttons**: Dollar sign ($) and percentage (%) - `hsl(var(--muted))` background
- **Timeframe Buttons**: 1D (active), 5D, 1M, 6M, YTD, 1Y, 5Y, MAX
- **Active Timeframe**: `hsl(var(--primary))` background, `hsl(var(--primary-foreground))` text
- **Change Display**: "Change" label + "-$1.65" + "0.32%" using `hsl(var(--destructive))` for negative values

---

## 7. Stock Chart Implementation

### Chart Container

- **Background**: White with faint gray grid lines
- **Y-axis Labels**: 508, 510, 512, 514
- **X-axis Labels**: 12:00 PM, 3:00 PM
- **Chart Line**: Dark red/brown color
- **Reference Line**: Dotted gray line for "Prev close: 511.7"

### Chart Specifications

- **Line Color**: `hsl(var(--destructive))` (red for negative trends)
- **Grid Color**: `hsl(var(--border))` (light gray)
- **Axis Labels**: 12px, `hsl(var(--muted-foreground))` using `var(--font-sans)`
- **Reference Line**: Dashed, `hsl(var(--muted-foreground))`
- **Chart Colors**: Use `hsl(var(--chart-1))` through `hsl(var(--chart-5))` for multiple data series

---

## 8. Company Details Section (Right Panel)

### Company Information Table

- **Layout**: Two-column table structure
- **Left Column (Labels)**: Symbol, Market Cap, IPO Date, CEO, Fulltime Employees, Sector, Industry, Country, Exchange
- **Right Column (Values)**: MSFT, $3.8T, Mar 13, 1986, Satya Nadella, 228K, Technology, Software - Infrastructure, US, NASDAQ Global Select

### Company Description

- **Text**: "Microsoft Corporation develops, licenses, and supports software, services, devices, and solutions worldwide..."
- **Read More Link**: Underlined, `hsl(var(--primary))` color
- **Typography**: 14px, line-height 1.5 using `var(--font-sans)`
- **Text Color**: `hsl(var(--foreground))`

---

## 9. Financial Profile Section (Bottom Left)

### Section Header

- **Title**: "Financial Profile" - bold, `hsl(var(--foreground))`, 18px using `var(--font-sans)`

### Financial Metrics Table

- **Layout**: Two-column grid
- **Metrics Include**:
  - Prev Close: $511.70
  - Market Cap: $3.79T
  - Day Range: $508.33 - $514.64
  - Open: $514.48
  - P/E Ratio: 39.4
  - 52W Range: $344.79 - $514.64

### Styling

- **Label Column**: `hsl(var(--foreground))`, medium weight using `var(--font-sans)`
- **Value Column**: `hsl(var(--foreground))`, regular weight using `var(--font-sans)`
- **Row Spacing**: 8px between rows
- **Border**: `hsl(var(--border))` for table separators

---

## 10. Peers Section (Bottom Right)

### Section Header

- **Title**: "Peers" - bold, `hsl(var(--foreground))`, 18px using `var(--font-sans)`

### Peer Companies List

- **Layout**: Vertical list with separators
- **Each Entry Contains**:
  - Company Name (bold)
  - Ticker Symbol (parentheses)
  - Current Price
  - Percentage Change (green for positive, red for negative)

### Peer Entries

1. **C3.ai, Inc.** (AI): $28.71, +1.23% (green)
2. **BlackBerry Limited** (BB): $3.91, -2.49% (red)
3. **Core Scientific, Inc.** (CORZ): $13.35, -0.89% (red)
4. **CrowdStrike Holdings, Inc.** (CRWD): $475.96, -0.96% (red)

### Styling

- **Separators**: `hsl(var(--border))` horizontal lines
- **Positive Changes**: Custom green (#28a745) - consider adding to CSS custom properties
- **Negative Changes**: `hsl(var(--destructive))` (red)
- **Company Names**: `hsl(var(--foreground))` bold using `var(--font-sans)`
- **Ticker Symbols**: `hsl(var(--muted-foreground))` using `var(--font-mono)`

---

## 11. Footer Elements

### Help Button

- **Location**: Bottom right corner
- **Design**: Circular button with question mark and chat bubble icons
- **Size**: 40px diameter
- **Background**: `hsl(var(--muted))`
- **Border**: `hsl(var(--border))`
- **Border Radius**: `var(--radius)` for consistent styling

---

## 12. Color Palette & Typography

### Primary Colors (Using CSS Custom Properties)

- **Background**: `hsl(var(--background))` - Light gray (#f8f9fa)
- **Card Background**: `hsl(var(--card))` - White (#ffffff)
- **Text Primary**: `hsl(var(--foreground))` - Dark gray (#212529)
- **Text Secondary**: `hsl(var(--muted-foreground))` - Medium gray (#6c757d)
- **Primary Blue**: `hsl(var(--primary))` - Pink (#ff0080)
- **Accent Teal**: `hsl(var(--accent))` - Teal (#00ffd4)
- **Positive Green**: Custom green (#28a745)
- **Negative Red**: `hsl(var(--destructive))` - Red (#ff2a00)

### Sidebar Colors

- **Sidebar Background**: `hsl(var(--sidebar))` - Light gray (#f8f9fa)
- **Sidebar Text**: `hsl(var(--sidebar-foreground))` - Dark gray (#212529)
- **Sidebar Primary**: `hsl(var(--sidebar-primary))` - Pink (#ff0080)
- **Sidebar Accent**: `hsl(var(--sidebar-accent))` - Teal (#00ffd4)
- **Sidebar Border**: `hsl(var(--sidebar-border))` - Light gray (#e5e7eb)

### Typography

- **Primary Font**: `var(--font-sans)` - Outfit, sans-serif
- **Headings**: Bold, 18px-24px using Outfit font
- **Body Text**: Regular, 14px-16px using Outfit font
- **Small Text**: 12px for timestamps and labels
- **Mono Font**: `var(--font-mono)` - Fira Code, monospace for data

### Recommended CSS Custom Properties Additions

To complete the design system, consider adding these custom properties to globals.css:

```css
/* Financial-specific colors */
--positive: 142 76% 36%; /* Green for positive changes */
--positive-foreground: 0 0% 100%;

/* Chart-specific colors for financial data */
--chart-line: 0 100% 50%; /* Red for negative trends */
--chart-positive: 142 76% 36%; /* Green for positive trends */
--chart-neutral: 220 13% 91%; /* Gray for neutral data */

/* Additional spacing for financial components */
--spacing-xs: 0.125rem;
--spacing-sm: 0.25rem;
--spacing-md: 0.5rem;
--spacing-lg: 1rem;
--spacing-xl: 1.5rem;
```

---

## 13. Responsive Considerations

### Breakpoint Strategy

- **Desktop**: Full three-column layout
- **Tablet**: Collapsible sidebar, main content adapts
- **Mobile**: Stacked layout, sidebar becomes overlay

### Component Adaptations

- **Chart**: Maintains aspect ratio, scrollable on small screens
- **Tables**: Stack columns on mobile
- **Navigation**: Becomes hamburger menu on mobile

---

## 14. Component Hierarchy

### Layout Components

1. **AppLayout**: Main container with sidebar and content
2. **Sidebar**: Navigation component
3. **Header**: Breadcrumb and action buttons
4. **ContentGrid**: Two-column layout for main content
5. **ChartContainer**: Stock price visualization
6. **DataPanels**: Company details, financial profile, peers

### Reusable Components

- **NavigationItem**: Sidebar menu items
- **TabButton**: Navigation tabs
- **PriceDisplay**: Stock price boxes
- **MetricTable**: Two-column data tables
- **PeerListItem**: Individual peer company entries
- **ActionButton**: Follow/Share buttons

---

## 15. Implementation Priority

### Phase 1: Core Layout

1. Left sidebar with navigation
2. Header bar with breadcrumbs
3. Basic content grid structure

### Phase 2: Content Sections

1. Company overview and tabs
2. Stock price displays
3. Company details table

### Phase 3: Interactive Elements

1. Stock chart implementation
2. Financial profile data
3. Peers comparison list

### Phase 4: Polish & Responsive

1. Color and typography refinement
2. Responsive breakpoints
3. Hover states and animations
