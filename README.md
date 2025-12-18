# Preset Dashboard Templates

A collection of ready-to-use Superset/Preset dashboard templates that can be customized with your own data using AI.

## Repository Structure

```
├── categories.yaml         # Available template categories
├── templates/
│   └── sales_dashboard/
│       ├── thumbnail.png         # Dashboard preview image
│       ├── metadata.yaml         # Template metadata & AI context
│       ├── tags.yaml             # Template tags
│       ├── charts/               # Chart definitions (YAML)
│       ├── dashboards/           # Dashboard definitions (YAML)
│       ├── databases/            # Database connections (YAML)
│       └── datasets/             # Dataset configurations (YAML)
```

## How to Use a Template

### 1. Browse Available Templates

Browse the `templates/` directory to see available templates.

Each template includes:
- **Thumbnail** - Preview of the dashboard
- **Metadata** - Description, tags, and AI context
- **Charts** - Individual chart definitions in YAML
- **Dashboards** - Dashboard layout definitions
- **Datasets** - Dataset configurations
- **Databases** - Database connection templates

### 2. Get Template Files

**View Thumbnail:**
```
https://raw.githubusercontent.com/preset-io/dashboard-templates/master/templates/sales_dashboard/thumbnail.png
```

**Read Metadata:**
```
https://raw.githubusercontent.com/preset-io/dashboard-templates/master/templates/sales_dashboard/metadata.yaml
```

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

1. Create a new folder under `templates/`
2. Add the YAML definitions for charts, dashboards, datasets, and databases
3. Add a thumbnail image and `metadata.yaml`
4. Add a `tags.yaml` with relevant tags
