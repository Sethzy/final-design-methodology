# Shadcn/UI Implementation Plan: Financial Dashboard

## Component Mapping for Financial Dashboard Interface

### 1. Layout & Navigation Components

#### Left Sidebar

- **Sidebar** - Main sidebar container with navigation
- **Button** - "New Chat" button with plus icon
- **Separator** - Visual dividers between sections
- **Tooltip** - Hover tooltips for navigation items

#### Header Bar

- **Breadcrumb** - "Perplexity Finance > MSFT" navigation
- **Button** - Follow and Share action buttons
- **Badge** - Status indicators and labels

### 2. Main Content Area

#### Company Overview Section

- **Tabs** - Navigation tabs (Overview, Financials, Historical Data, Earnings, Research)
- **Input** - Search bar with magnifying glass icon
- **Button** - Search action buttons (grid, person, question mark icons)

#### Stock Price Display

- **Card** - Price boxes for "At Close" and "After Hours"
- **Badge** - Change indicators (positive/negative)
- **Toggle Group** - Chart controls ($/%, timeframe buttons)

#### Stock Chart

- **Chart** - Line chart component for stock price visualization
- **Aspect Ratio** - Maintain chart proportions

### 3. Data Display Components

#### Company Details Section

- **Table** - Company information table (Symbol, Market Cap, IPO Date, etc.)
- **Card** - Company description container
- **Button** - "Read More" link

#### Financial Profile Section

- **Card** - Section container
- **Table** - Financial metrics table
- **Badge** - Metric labels and values

#### Peers Section

- **Card** - Section container
- **Separator** - Dividers between peer entries
- **Badge** - Price change indicators (green/red)

### 4. Interactive Elements

#### Navigation & Controls

- **Button** - All interactive buttons throughout interface
- **Toggle** - Chart display toggles
- **Tooltip** - Hover information for complex elements

#### Data Visualization

- **Chart** - Stock price line chart
- **Progress** - Usage indicators (if needed)
- **Badge** - Status and change indicators

### 5. Responsive & Mobile Components

#### Mobile Adaptations

- **Sheet** - Mobile sidebar overlay
- **Drawer** - Alternative mobile navigation
- **Collapsible** - Expandable sections on mobile

#### Loading States

- **Skeleton** - Loading placeholders for data
- **Progress** - Loading indicators

### 6. Form & Input Components

#### Search & Filtering

- **Input** - Search bar with icons
- **Select** - Dropdown filters (if needed)
- **Command** - Advanced search with suggestions

#### Data Entry

- **Form** - Any data entry forms
- **Label** - Form field labels
- **Textarea** - Multi-line text input

### 7. Feedback & Notifications

#### User Feedback

- **Alert** - Important notifications
- **Sonner** - Toast notifications
- **Dialog** - Confirmation dialogs

#### Status Indicators

- **Badge** - Status badges throughout
- **Alert** - Error or warning messages

### 8. Advanced UI Components

#### Data Management

- **Table** - All tabular data displays
- **Pagination** - For large data sets
- **Hover Card** - Detailed information on hover

#### Navigation Enhancements

- **Navigation Menu** - Advanced navigation patterns
- **Dropdown Menu** - Context menus
- **Context Menu** - Right-click menus

### 9. Component Hierarchy & Structure

#### Layout Hierarchy

```
AppLayout
├── Sidebar (Left Navigation)
│   ├── Button (Logo/New Chat)
│   ├── Separator
│   └── Navigation Items
├── Main Content
│   ├── Header (Breadcrumb + Buttons)
│   ├── Tabs (Navigation)
│   ├── Card (Price Display)
│   ├── Chart (Stock Visualization)
│   └── Data Sections
│       ├── Table (Company Details)
│       ├── Card (Financial Profile)
│       └── Card (Peers)
└── Footer Elements
```

#### Component Dependencies

- **Sidebar** requires: Button, Separator, Sheet, Tooltip
- **Tabs** requires: No additional dependencies
- **Chart** requires: Aspect Ratio for proper sizing
- **Table** requires: No additional dependencies
- **Card** requires: No additional dependencies

### 10. Implementation Priority

#### Phase 1: Core Layout

1. **Sidebar** - Main navigation structure
2. **Button** - All interactive elements
3. **Card** - Content containers

#### Phase 2: Data Display

1. **Table** - Company and financial data
2. **Badge** - Status and change indicators
3. **Tabs** - Navigation tabs

#### Phase 3: Interactive Features

1. **Chart** - Stock price visualization
2. **Toggle Group** - Chart controls
3. **Input** - Search functionality

#### Phase 4: Enhanced UX

1. **Tooltip** - Hover information
2. **Alert** - Notifications
3. **Skeleton** - Loading states

### 11. Component Customization Notes

#### Color Integration

- Use CSS custom properties from globals.css
- Apply `hsl(var(--primary))` for active states
- Use `hsl(var(--accent))` for accent elements
- Apply `hsl(var(--destructive))` for negative values

#### Typography

- Ensure all components use `var(--font-sans)` (Outfit)
- Apply `var(--font-mono)` for data/ticker symbols
- Use consistent font weights and sizes

#### Spacing & Layout

- Apply `var(--radius)` for consistent border radius
- Use design system spacing variables
- Maintain responsive breakpoints

### 12. Accessibility Considerations

#### Component Accessibility

- **Sidebar** - Proper ARIA labels for navigation
- **Tabs** - Keyboard navigation support
- **Table** - Screen reader friendly structure
- **Chart** - Alternative text descriptions
- **Button** - Proper focus states

#### Color & Contrast

- Ensure sufficient contrast with design system colors
- Provide alternative indicators beyond color
- Support high contrast modes

### 13. Performance Optimization

#### Component Loading

- Lazy load **Chart** component for better performance
- Use **Skeleton** for loading states
- Implement virtual scrolling for large **Table** data

#### Bundle Optimization

- Import only required shadcn components
- Use tree-shaking for unused components
- Consider code splitting for complex features
