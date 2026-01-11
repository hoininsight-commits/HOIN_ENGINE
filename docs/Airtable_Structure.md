# Airtable Structure: HOIN_ENGINE

## 1. Base Information
*   **Name**: HOIN_ENGINE

## 2. Table Definitions

### Table: metrics
*   **Description**: Metadata for each economic indicator.
*   **Columns**:
    *   `metric_id`: Single line text (Primary Key)
    *   `name`: Single line text
    *   `category`: Single select
    *   `unit`: Single line text
    *   `frequency`: Single select
    *   `source`: Single line text
    *   `is_derived`: Checkbox
    *   `parent_metric`: Single line text

### Table: metric_values
*   **Description**: Time-series data values.
*   **Columns**:
    *   `record_id`: Primary (default, Auto-number or Formula)
    *   `metric_id`: Single line text (Foreign Key link implied, or direct text)
    *   `date`: Date (Include time: OFF)
    *   `value`: Number
    *   `fetch_time`: Created time
    *   `status`: Single select

### Table: theme_learning
*   **Description**: AI-derived qualitative themes.
*   **Columns**:
    *   `theme`: Single line text (Primary)
    *   `publish_date`: Date
    *   `inferred_reason`: Long text
    *   `related_data_axes`: Multiple select
    *   `source`: Single select
