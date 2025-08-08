# InsightEdge – AI-powered Consumer Insights Generation

![InsightEdge](images/InsightEdge.png)

A Fivetran and Databricks-powered Streamlit data application for Consumer Packaged Goods (CPG) with advanced AI Agent Workflows.

## Overview

InsightEdge is an AI-powered consumer insights generation system that helps CPG companies transform large datasets into actionable insights. This Streamlit on Databricks data application helps product development, marketing, and sales teams make informed decisions, identify emerging trends early, and improve customer satisfaction through real-time analysis of consumer data.

The application features sophisticated AI Agent Workflows that provide transparent, step-by-step analysis of consumer insights data, transforming complex market research into actionable product development and marketing strategies. Each analysis focus area operates through specialized mini-agents that simulate the decision-making process of experienced consumer insights analysts and CPG strategists.

The application utilizes a synthetic consumer insights dataset that simulates data from major feedback platforms, market research sources, and social media. This synthetic data is moved into Databricks using a custom connector built with the Fivetran Connector SDK, enabling reliable and efficient data pipelines for CPG analytics.

## AI Agent Workflows

### Agent Architecture Overview

InsightEdge employs a sophisticated multi-agent architecture designed specifically for consumer insights analysis. Each focus area operates through specialized AI agents that break down complex consumer behavior tasks into transparent, sequential steps that mirror the thought processes of experienced market researchers and CPG consultants.

### Focus Area Agents

#### Overall Performance Agent
**Business Challenge**: Marketing analysts manually review hundreds of customer feedback reports, social media posts, and market research data daily, spending 4+ hours identifying consumer trends and actionable insights for product development.

**Agent Solution**: Autonomous consumer insights workflow that analyzes multi-source data from Medallia, Nielsen, and social platforms to identify emerging trends, consumer preferences, and generate prioritized product development recommendations.

**Agent Workflow Steps**:
1. **Consumer Data Initialization** - Loading comprehensive consumer insights dataset with enhanced validation across customer records and product categories
2. **Consumer Insights Assessment** - Advanced calculation of consumer satisfaction indicators with sentiment analysis
3. **Market Pattern Recognition** - Sophisticated identification of consumer behavior patterns with social media sentiment correlation
4. **AI Consumer Intelligence Processing** - Processing comprehensive market data through selected AI model with advanced reasoning
5. **CPG Insights Report Compilation** - Professional consumer insights analysis with evidence-based recommendations and actionable marketing insights

#### Optimization Opportunities Agent
**Business Challenge**: Product development teams spend 3+ hours daily manually identifying optimization opportunities across customer segments, product positioning, and market trend analysis to improve product-market fit.

**Agent Solution**: AI-powered consumer optimization analysis that automatically detects segment targeting gaps, product positioning inefficiencies, and market trend opportunities with specific implementation recommendations for marketing campaigns.

**Agent Workflow Steps**:
1. **Consumer Optimization Data Preparation** - Advanced loading of consumer behavior data with enhanced validation for insights improvement identification
2. **Market Inefficiency Detection** - Sophisticated analysis of customer segment targeting and product positioning with evidence-based inefficiency identification
3. **Consumer Behavior Correlation Analysis** - Enhanced examination of relationships between customer demographics, purchasing behaviors, and product satisfaction
4. **Marketing System Integration Optimization** - Comprehensive evaluation of consumer insights integration with existing Medallia, Nielsen, and social media platforms
5. **AI Marketing Optimization Intelligence** - Generating advanced consumer targeting recommendations using selected AI model with CPG reasoning
6. **Consumer Strategy Finalization** - Professional marketing optimization report with prioritized implementation roadmap and consumer insights impact analysis

#### Financial Impact Agent
**Business Challenge**: CPG financial analysts manually calculate complex ROI metrics across product lines and marketing campaigns, requiring 3+ hours of financial modeling to assess consumer insights impact on sales growth.

**Agent Solution**: Automated CPG financial analysis that calculates comprehensive ROI, identifies revenue optimization opportunities across product categories, and projects consumer insights benefits with detailed product launch forecasting.

**Agent Workflow Steps**:
1. **CPG Financial Data Integration** - Advanced loading of consumer insights financial data and CPG revenue metrics with enhanced validation across customers
2. **Consumer Revenue Impact Calculation** - Sophisticated ROI metrics calculation with product sales analysis and consumer insights implementation cost savings
3. **Product Sales Impact Assessment** - Enhanced analysis of CPG revenue impact with consumer preference metrics and product-market fit correlation analysis
4. **Marketing Spend Efficiency Analysis** - Comprehensive evaluation of marketing resource allocation efficiency across consumer segments with campaign ROI optimization
5. **AI CPG Financial Modeling** - Advanced consumer insights financial projections and marketing ROI calculations using selected AI model
6. **Consumer Economics Report Generation** - Professional CPG financial impact analysis with detailed consumer insights ROI calculations and product revenue forecasting

#### Strategic Recommendations Agent
**Business Challenge**: CPG executives spend hours manually analyzing competitive market positioning and developing strategic technology roadmaps for consumer insights advancement and brand differentiation.

**Agent Solution**: Strategic consumer intelligence workflow that analyzes competitive advantages, identifies emerging technology integration opportunities with AR/IoT, and creates prioritized product innovation roadmaps for market expansion.

**Agent Workflow Steps**:
1. **CPG Market Intelligence Assessment** - Advanced loading of consumer goods market context with competitive positioning analysis across consumers and product categories
2. **Consumer Insights Competitive Advantage Analysis** - Sophisticated evaluation of competitive positioning against traditional market research with AI-powered consumer insights effectiveness analysis
3. **Emerging Technology Integration** - Enhanced analysis of integration opportunities with AR, IoT, and emerging consumer technologies across consumer data dimensions
4. **Product Innovation Strategy Development** - Comprehensive development of prioritized product development roadmap with evidence-based consumer insights adoption strategies
5. **AI Consumer Strategic Processing** - Advanced consumer insights strategic recommendations using selected AI model with long-term competitive positioning
6. **Consumer Intelligence Report Generation** - Professional consumer insights strategic roadmap with competitive analysis and product development plan ready for CMO executive review

### Agent Execution Flow

1. **Agent Initialization** - User selects focus area and AI model, triggering specialized agent activation
2. **Data Context Loading** - Agent accesses consumer feedback data, market research, and social media sentiment metrics
3. **Step-by-Step Processing** - Agent executes sequential workflow steps with real-time progress visualization
4. **Consumer Intelligence Integration** - Selected Databricks serving endpoint processes CPG context with specialized prompting
5. **Results Compilation** - Agent generates comprehensive consumer insights analysis with actionable marketing recommendations
6. **Report Delivery** - Professional CPG report delivered with implementation roadmap and success metrics

## Data Sources

The application is designed to work with data from major consumer insights platforms and databases:

### Consumer Insights Data Sources (Simulated)
- **Customer Feedback**: 
  - Medallia
  - Qualtrics
  - SurveyMonkey
- **Market Research**: 
  - Nielsen
  - Euromonitor
- **Social Media**: 
  - Twitter
  - Facebook
  - Instagram

For demonstration and development purposes, we've created a synthetic dataset that approximates these data sources and combined them into a single table exposed through an API server. This approach allows for realistic CPG analytics without using protected consumer information.

## Key Features

- **AI Agent Workflows**: Transparent, step-by-step consumer insights analysis through specialized mini-agents for each focus area
- **Agent Progress Visualization**: Real-time display of agent processing steps with CPG context and completion tracking
- **Focus Area Specialization**: Dedicated agents for Overall Performance, Optimization Opportunities, Financial Impact, and Strategic Recommendations
- **Consumer Intelligence Integration**: Seamless integration with multiple Databricks serving endpoints for specialized CPG analysis
- **AI-powered consumer insights generation**: Leverages generative AI to analyze customer feedback, market research, and social media data to provide actionable insights
- **Integration with synthetic consumer data**: Simulates data from major feedback platforms, market research sources, and social media
- **Comprehensive data application**: Visual representation of key metrics including customer satisfaction, revenue growth, product ratings, and inventory metrics
- **Custom Fivetran connector**: Utilizes a custom connector built with the Fivetran Connector SDK to reliably move data from the API server to Databricks

## Streamlit Data App Sections

### Metrics
- **Key Performance Indicators**: Track customer satisfaction, revenue growth, product ratings, and stockout rates
- **Segment & Category Analysis**: Visualize customer segment distribution and product category breakdown
- **Price Optimization Analysis**: Review price optimization results and recommendations
- **Satisfaction vs Growth Quadrant Analysis**: Map products by satisfaction and growth rates
- **Inventory & Order Analysis**: Monitor inventory turnover, overstock rates, and order fulfillment

### AI Insights with Agent Workflows
Generate AI-powered insights through transparent agent workflows with different focus areas:
- **Overall Performance**: Comprehensive analysis of the consumer insights generation system through autonomous consumer insights workflow
- **Optimization Opportunities**: Areas where consumer insights can be improved via AI-powered consumer optimization analysis
- **Financial Impact**: Cost-benefit analysis and ROI in CPG terms through automated CPG financial analysis
- **Strategic Recommendations**: Long-term strategic implications for improvement via strategic consumer intelligence workflow

Each focus area includes:
- **Business Challenge Description**: Detailed explanation of the specific CPG problem being addressed
- **Agent Solution Overview**: Description of how the AI agent workflow solves the challenge
- **Real-time Progress Tracking**: Step-by-step visualization of agent processing with consumer insights context
- **Agent Execution Controls**: Start/stop controls for managing agent workflow execution
- **Professional CPG Reports**: Comprehensive analysis reports with implementation roadmaps

### Insights History
Access previously generated agent-driven insights for reference and comparison, including agent execution details and model selection.

### Data Explorer
Explore the underlying data with pagination controls.

## Setup Instructions

### Prerequisites

#### Required Accounts & Resources
- **Databricks Workspace** with:
  - SQL Warehouse: `ts-databricks-azure-sql-serverless-demo`
  - Model Serving Endpoints (Claude, Llama models)
  - Unity Catalog with structure: `ts-catalog-demo`.`cpg_connector_dbx`.`cpg_records`
  - Databricks Apps capability
- **Fivetran Account** with:
  - Databricks destination
  - Custom connector capability

#### Python Requirements
```
altair==5.5.0
databricks-sql-connector==4.0.0
pandas==2.2.3
requests==2.32.3
streamlit==1.42.0
```

### Implementation Steps

#### 1. Repository Setup
```
CPG-CONSUMERINSIGHTS/
├── app.py
├── app.yaml
├── requirements.txt
├── .gitignore
├── README.md
└── images/
```

#### 2. Data Pipeline Setup

##### Fivetran Configuration
1. Ensure the API server hosting the synthetic consumer insights data is operational
2. Configure the custom Fivetran connector (built with Fivetran Connector SDK) to connect to the API server
3. Start the Fivetran sync to move data into a `cpg_records` table in your Databricks Unity Catalog
4. Verify data is being loaded correctly by checking the table in Databricks

##### Unity Catalog Setup
Set up the following structure in Unity Catalog:
- **Catalog**: `ts-catalog-demo`
- **Schema**: `cpg_connector_dbx`
- **Table**: `cpg_records`

#### 3. Serving Endpoints Configuration

Configure the following Databricks serving endpoints:
- `databricks-claude-sonnet-4`
- `databricks-claude-opus-4`
- `databricks-claude-3-7-sonnet`
- `databricks-meta-llama-3-1-8b-instruct`
- `databricks-meta-llama-3-3-70b-instruct`
- `databricks-gemma-3-12b`
- `databricks-llama-4-maverick`

#### 4. App Deployment

##### Option A: Local Development
```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
streamlit run app.py
```

##### Option B: Databricks Apps Deployment via VS Code

**Sync the files**
Move to the folder with your source code:

```bash
cd cpg-consumerinsights
```

Sync source files into Databricks:

```bash
databricks sync --watch . /Workspace/Users/kelly.kohlleffel@fivetran.com/cpg-consumerinsights
```

**Deploy to Databricks Apps**

```bash
databricks apps deploy cpg-consumerinsights --source-code-path /Workspace/Users/kelly.kohlleffel@fivetran.com/cpg-consumerinsights
```

##### Option C: Databricks UI Deployment
1. Navigate to Workspace > Apps
2. Create new app
3. Upload app.py and configuration files
4. Configure app resources
5. Deploy

## Data Flow

1. **Synthetic Data Creation**: A synthetic dataset approximating real consumer insights data sources has been created and exposed via an API server:
   - Customer Feedback: Medallia, Qualtrics, SurveyMonkey
   - Market Research: Nielsen, Euromonitor
   - Social Media: Twitter, Facebook, Instagram

2. **Custom Data Integration**: A custom connector built with the Fivetran Connector SDK communicates with the API server to extract the synthetic consumer insights data

3. **Automated Data Movement**: Fivetran manages the orchestration and scheduling of data movement from the API server into Databricks

4. **Data Loading**: The synthetic consumer insights data is loaded into Databricks Unity Catalog as a `cpg_records` table in a structured format ready for analysis

5. **Agent Workflow Execution**: AI agents process the consumer insights data through specialized workflows, providing transparent step-by-step analysis

6. **Data Analysis**: Databricks SQL and serving endpoints analyze the data to generate insights through agent-driven processes

7. **Data Visualization**: Streamlit on Databricks presents the analyzed data in an interactive data application with agent workflow visualization

## Data Requirements

The application expects a table named `cpg_records` in Unity Catalog which contains synthetic data simulating various consumer insights systems. This data is retrieved from an API server using a custom Fivetran connector built with the Fivetran Connector SDK:

### Customer Data
- `customer_id`
- `customer_segment` (Low-Value, Medium-Value, High-Value)
- `customer_satisfaction_rate`
- `customer_ltv` (Customer Lifetime Value)

### Product Data
- `product_id`
- `product_category`
- `product_subcategory`
- `product_rating`
- `product_price`
- `product_review_count`

### Order Data
- `order_id`
- `order_date`
- `order_status` (Delivered, Shipped, Pending, Cancelled)
- `order_total`
- `order_frequency`
- `average_order_value`

### Inventory & Operations
- `inventory_level`
- `inventory_turnover`
- `stockout_rate`
- `overstock_rate`
- `demand_forecast`

### Financial Metrics
- `revenue_growth_rate`
- `price_elasticity`
- `price_optimization_flag`
- `price_optimization_result` (Success, Failure)
- `price_optimization_recommendation`
- `price_optimization_date`

### Fivetran Metadata
- `record_id`
- `_fivetran_synced`
- `_fivetran_deleted`

## Environment Configuration

### Required Environment Variables

```yaml
# Databricks Connection
DATABRICKS_HOST: https://your-workspace.databricks.com
DATABRICKS_SQL_HTTP_PATH: /sql/1.0/warehouses/your-warehouse-id
DATABRICKS_TOKEN: your-databricks-token

# Unity Catalog Configuration
UC_CATALOG: ts-catalog-demo
UC_SCHEMA: cpg_connector_dbx
UC_TABLE: cpg_records

# Serving Endpoints
DBX_ENDPOINT: databricks-claude-sonnet-4
DBX_ENDPOINT_2: databricks-claude-opus-4
DBX_ENDPOINT_3: databricks-claude-3-7-sonnet
DBX_ENDPOINT_4: databricks-meta-llama-3-1-8b-instruct
DBX_ENDPOINT_5: databricks-meta-llama-3-3-70b-instruct
DBX_ENDPOINT_6: databricks-gemma-3-12b
DBX_ENDPOINT_7: databricks-llama-4-maverick

# Serving Endpoint URLs
DATABRICKS_SERVING_ENDPOINT_URL: https://your-workspace.databricks.com/serving-endpoints/databricks-claude-sonnet-4/invocations
DATABRICKS_ENDPOINT_2_URL: https://your-workspace.databricks.com/serving-endpoints/databricks-claude-opus-4/invocations
DATABRICKS_ENDPOINT_3_URL: https://your-workspace.databricks.com/serving-endpoints/databricks-claude-3-7-sonnet/invocations
DATABRICKS_ENDPOINT_4_URL: https://your-workspace.databricks.com/serving-endpoints/databricks-meta-llama-3-1-8b-instruct/invocations
DATABRICKS_ENDPOINT_5_URL: https://your-workspace.databricks.com/serving-endpoints/databricks-meta-llama-3-3-70b-instruct/invocations
DATABRICKS_ENDPOINT_6_URL: https://your-workspace.databricks.com/serving-endpoints/databricks-gemma-3-12b/invocations
DATABRICKS_ENDPOINT_7_URL: https://your-workspace.databricks.com/serving-endpoints/databricks-llama-4-maverick/invocations
```

## Benefits

- 12% increase in product sales: $1,200,000 additional sales/year
- 10% reduction in product development costs: $500,000 savings/year
- 15% improvement in customer satisfaction: 12% increase in satisfied customers
- 10% reduction in marketing costs: $200,000 savings/year
- **Enhanced Consumer Transparency**: Agent workflows provide clear visibility into consumer insights analysis reasoning and decision-making processes
- **Accelerated Market Research**: Automated agent processing reduces manual analysis time from hours to minutes for complex consumer trend assessments

## Technical Details

This application uses:
- **AI Agent Workflow Engine**: Custom agent orchestration system for transparent, step-by-step consumer insights analysis
- **Multi-Agent Architecture**: Specialized agents for different CPG focus areas with domain-specific processing
- **Agent Progress Visualization**: Real-time display of agent execution steps with consumer insights context and completion tracking
- **Streamlit on Databricks** for the user interface with enhanced agent workflow displays
- **Databricks Serving Endpoints** for AI-powered insights generation through agent-managed prompting
- **Multiple AI models** including Claude 4 Sonnet, Claude 4 Opus, Claude 3.7 Sonnet, Llama 3.1/3.3, Gemma, and Llama 4 Maverick for agent intelligence
- **Databricks SQL** for data processing within agent workflows
- **Fivetran Connector SDK** for building a custom connector to retrieve synthetic consumer insights data from an API server
- **Custom Fivetran connector** for automated, reliable data movement into Databricks Unity Catalog

## Troubleshooting Tips

### Common Issues
1. **Connection Errors**:
   - Verify SQL warehouse `ts-databricks-azure-sql-serverless-demo` is running
   - Check Databricks token permissions in `databricks-token-secret`
   - Confirm Unity Catalog access to `ts-catalog-demo`.`cpg_connector_dbx`.`cpg_records`

2. **Serving Endpoint Issues**:
   - Verify all 7 endpoint URLs in environment variables
   - Check endpoint status in Databricks workspace
   - Review timeout settings for Claude and Llama models

3. **Data Loading Issues**:
   - Confirm Unity Catalog table structure matches expected schema
   - Check Fivetran sync status for cpg_records table
   - Verify `_fivetran_deleted = false` filter is working

4. **Agent Workflow Issues**:
   - Check serving endpoint connectivity for selected models
   - Review agent progress logs for CPG-specific processing
   - Verify model selection and availability across all 7 endpoints

## Success Metrics

- Accuracy of insights generated
- Time-to-market for new products
- Customer satisfaction ratings
- Return on investment (ROI) for marketing campaigns
- **Agent Workflow Efficiency**: Time reduction from manual consumer insights analysis to automated agent-driven insights
- **Consumer Insights Transparency Score**: User confidence in product development recommendations through visible agent reasoning
- **CPG Analysis Accuracy**: Improvement in marketing decision quality through systematic agent processing

## Key Stakeholders

- Product Development Teams
- Marketing Teams
- Sales Teams
- Chief Marketing Officer (CMO)
- **Consumer Insights Analysts**: Professionals who benefit from transparent agent workflow visibility
- **Brand Management Teams**: Staff who implement agent-recommended consumer insights strategies

## Competitive Advantage

InsightEdge provides actionable insights with transparent agent workflows that enable companies to make informed product development and marketing decisions, stay ahead of the competition, and improve customer satisfaction. The agent-based architecture provides unprecedented visibility into consumer insights analysis reasoning, building trust and confidence in AI-driven CPG decisions. This creates a competitive advantage by delivering products that meet consumer preferences while maintaining complete transparency in the decision-making process.

## Long-term Evolution

In the next 3-5 years, InsightEdge will evolve to incorporate more advanced generative AI techniques and sophisticated agent architectures, including:

- **Multi-modal Agent Learning**: Agents that can process visual content, social media imagery, and consumer behavior videos from diverse digital platforms
- **Collaborative Agent Networks**: Multiple agents working together to solve complex consumer insights challenges across different product categories
- **Adaptive Agent Intelligence**: Self-improving agents that learn from market outcomes and refine their analytical approaches
- **Advanced Agent Orchestration**: Sophisticated workflow management for complex, multi-step consumer insights analysis processes
- **Integration with Emerging Consumer Technologies**: Agent connectivity with augmented reality shopping experiences, IoT product tracking, and personalized recommendation systems for comprehensive consumer insights

The system will expand to include integration with emerging technologies such as augmented reality and the Internet of Things (IoT), expansion to new markets and regions, and development of more advanced AI algorithms to improve insights generation accuracy, all orchestrated through advanced agent workflows that provide complete transparency and control over the consumer insights analysis process.