# Apache Beam Complete Feature Demonstration

## Video Walkthrough

Watch the complete code walkthrough and execution demonstration:

[Apache Beam Feature Demonstration - Video Walkthrough](https://youtu.be/baQRIm9-Ang)

## Overview

This notebook provides a comprehensive demonstration of Apache Beam's core features using a real-world E-Commerce Analytics Pipeline. The project processes customer transaction data through various transformations to demonstrate all major Apache Beam concepts.

## Author
- Name: Kalhar Mayurbhai Patel
- SJSU ID: 019140511

## Features Demonstrated

### 1. ParDo (Parallel Processing)
- Custom DoFn for transaction enrichment
- Parallel element-wise transformations
- Tax calculation and purchase categorization

### 2. Map & Filter
- Element extraction and transformation
- High-value transaction filtering
- Customer-purchase tuple mapping

### 3. Composite Transforms
- CustomerAnalytics: Reusable customer analysis pipeline
- ProductAnalytics: Product revenue aggregation
- Modular and reusable transform components

### 4. Pipeline I/O
- Reading from JSON files (ReadFromText)
- Writing to multiple output formats (CSV, JSON)
- File-based data ingestion and export

### 5. Partition
- Customer segmentation by spending tier
- Bronze, Silver, and Gold tier classification
- Targeted marketing campaign generation

### 6. Windowing
- Fixed Windows: 10-minute tumbling windows
- Sliding Windows: 15-minute windows with 5-minute slides
- Session Windows: Activity-based grouping with 10-minute gaps

## Use Case: E-Commerce Analytics Pipeline

The notebook builds a complete analytics pipeline that:
- Generates 100 sample e-commerce transactions
- Enriches transactions with computed fields (tax, final amount, purchase size)
- Segments customers based on total spending
- Analyzes sales patterns across time windows
- Partitions customers for targeted marketing
- Produces comprehensive reports and visualizations

## Requirements

```
apache-beam[interactive]
pandas
matplotlib
seaborn
```

## Installation

```bash
pip install apache-beam[interactive]
```

## Usage

1. Open the notebook in Google Colab
2. Run all cells sequentially
3. Review generated outputs in the `output/` directory
4. Examine visualization charts

## Output Files

The pipeline generates the following outputs:

- `transactions.json` - Input transaction data
- `high_value_customers.csv` - Customers with transactions over $300
- `bronze_customers.txt` - Bronze tier marketing campaigns
- `silver_customers.txt` - Silver tier marketing campaigns
- `gold_customers.txt` - Gold tier marketing campaigns
- `premium_transactions.json` - High-value transactions (>$500)
- `pipeline_summary.json` - Execution summary and statistics
- `pipeline_visualization.png` - Results visualization charts

## Key Concepts

- **PCollection**: Immutable distributed dataset
- **PTransform**: Data transformation operation
- **DoFn**: User-defined processing function
- **Pipeline**: Directed Acyclic Graph (DAG) of transformations
- **Windowing**: Time-based data grouping for aggregation
- **Side Outputs**: Multiple outputs from a single transform

## Pipeline Architecture

```
Input (JSON) 
    → ParDo (Enrich) 
    → Map (Extract Metrics) 
    → Filter (High Value)
    → Composite Transform (Analytics)
    → Partition (Customer Tiers)
    → Windowing (Time-based Analysis)
    → Output (CSV, JSON)
```

## Resources

- [Apache Beam Documentation](https://beam.apache.org/documentation/)
- [Beam Python SDK](https://beam.apache.org/documentation/sdks/python/)
- [Beam Programming Guide](https://beam.apache.org/documentation/programming-guide/)
- [Interactive Beam Playground](https://beam.apache.org/get-started/try-beam-playground/)

## License

This project is created for educational purposes as part of a course assignment.

## Acknowledgments

- Apache Beam community for excellent documentation and examples
- Course instructors for assignment guidance and resources
