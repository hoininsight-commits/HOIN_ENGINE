# Make.com Project Structure

## 1. Project Initialization
*   **Action**: Delete all existing Scenarios, Folders, and Drafts.
*   **New Project**: HOIN_ENGINE

## 2. Folder Structure
1.  **01_Core_Collectors**: Data ingestion scenarios.
2.  **02_Theme_Learning**: AI analyis and text processing.
3.  **03_Utils**: Utility and maintenance scripts.

## 3. Scenario Specifications

### Scenario 1: Macro_Rates (Folder: 01_Core_Collectors)
*   **Trigger**: HTTP (Scheduled)
*   **Flow**:
    1.  `HTTP` (Get Data)
    2.  `Router` (Branch by metric type)
    3.  `Iterator` (Process list of records)
    4.  `Airtable - Create/Update record`
*   **Logic**: Upsert based on `metric_id` + `date`.

### Scenario 2: Macro_Rates_Backfill (Folder: 01_Core_Collectors)
*   **Trigger**: Manual only (On-demand)
*   **Constraint**: Never merge with real-time scenario.

### Scenario 3: EconHunter_YouTube (Folder: 02_Theme_Learning)
*   **Recurrence**: Scheduled
*   **Flow**:
    1.  `YouTube/RSS Watch`
    2.  `Text Aggregator`
    3.  `LLM - Theme Extraction`
    4.  `LLM - Reason Inference`
    5.  `Airtable - Create record (theme_learning)`
*   **Output JSON Schema**:
    ```json
    {
      "theme": "String",
      "inferred_reason": "String",
      "related_data_axes": ["Array", "of", "Strings"]
    }
    ```
