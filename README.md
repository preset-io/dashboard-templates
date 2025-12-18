# Preset Dashboard Templates

A collection of ready-to-use Superset/Preset dashboard templates that can be customized with your own data using AI.

## Repository Structure

```
├── index.yaml              # Template registry
├── categories.yaml         # Available template categories
├── templates/
│   └── sales_dashboard/
│       ├── sales_dashboard.zip   # Superset import file
│       ├── thumbnail.png         # Dashboard preview image
│       └── metadata.yaml         # Template metadata & AI context
```

## How to Use a Template

### 1. Browse Available Templates

View the template catalog in `index.yaml` or browse the `templates/` directory.

Each template includes:
- **ZIP file** - Import directly into Superset/Preset
- **Thumbnail** - Preview of the dashboard
- **Metadata** - Description, required columns, and AI context

### 2. Get Template Files

**Download ZIP (for manual import):**
```
https://raw.githubusercontent.com/preset-io/dashboard-templates/main/templates/sales_dashboard/sales_dashboard.zip
```

**View Thumbnail:**
```
https://raw.githubusercontent.com/preset-io/dashboard-templates/main/templates/sales_dashboard/thumbnail.png
```

**Read Metadata:**
```
https://raw.githubusercontent.com/preset-io/dashboard-templates/main/templates/sales_dashboard/metadata.yaml
```

### 3. Import into Superset/Preset

1. Download the `.zip` file for your chosen template
2. In Superset/Preset, go to **Settings** > **Import Dashboard**
3. Upload the ZIP file
4. Map the dataset to your own data source

## Template Metadata Schema

Each template's `metadata.yaml` contains:

| Field | Description |
|-------|-------------|
| `template_category` | Category (Sales, Marketing, etc.) |
| `template_description` | What the dashboard shows |
| `template_thumbnail_url` | Preview image URL |
| `template_tags` | Searchable tags |
| `is_featured_template` | Highlighted in catalog |
| `template_context` | AI mapping context (see below) |

### AI Context Structure

The `template_context` helps AI map your data to the template:

```yaml
template_context:
  ideal_for:
    - "Transactional sales data"
    - "E-commerce order data"

  required_columns:
    - name: revenue
      type: numeric
      description: "Monetary value of the sale"
      examples: ["revenue", "amount", "total", "price"]

  tabs:
    - name: "Sales Overview"
      purpose: "High-level KPIs"
      charts:
        - chart_name: "Total Revenue"
          viz_type: big_number
          uses: [revenue, order_date]
          purpose: "Single KPI showing total revenue"

  filters:
    - name: "Time Range"
      type: filter_time
      column: order_date
```

## Categories

Available template categories (see `categories.yaml`):

- **Sales** - Revenue tracking, pipeline analysis, sales performance
- **Marketing** - Campaign analytics, conversion funnels, customer acquisition
- **Finance** - Financial reporting, budget tracking, expense analysis
- **Operations** - KPI dashboards, operational metrics, efficiency tracking
- **Product Analytics** - User behavior, feature adoption, product metrics
- **Executive** - High-level overview dashboards, business health metrics
- **Customer Support** - Ticket analytics, response times, customer satisfaction

## Contributing

To add a new template:

1. Export your dashboard from Superset/Preset as a ZIP
2. Create a new folder under `templates/`
3. Add the ZIP file, thumbnail, and `metadata.yaml`
4. Update `index.yaml` with the new template entry
