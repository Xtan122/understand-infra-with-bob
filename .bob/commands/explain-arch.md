# Architecture Documentation Command

## Objective
Analyze the AWS Resource Event Monitor system and generate comprehensive architecture documentation with a visual diagram.

## Step-by-Step Instructions

### 1. File Discovery and Reading
Read and analyze the following files in the project:

**Infrastructure Files (Terraform):**
- `infra/main.tf` - Main infrastructure configuration
- `infra/modules/*/main.tf` - All module configurations
  - `infra/modules/dynamodb/main.tf`
  - `infra/modules/eventbridge/main.tf`
  - `infra/modules/lambda/main.tf`
  - `infra/modules/notifications/main.tf`
- `infra/variables.tf` - Variable definitions
- `infra/outputs.tf` - Output definitions

**Source Code Files:**
- `src/handlers/processor.py` - Event processing logic
- `src/handlers/notifier.py` - Notification handling logic

**Configuration Files:**
- `requirements.txt` - Python dependencies
- `README.md` - Project overview (if available)

### 2. System Analysis
Analyze and document the following aspects:

**Data Flow:**
1. Event sources and triggers
2. Event processing pipeline
3. Data storage mechanisms
4. Notification delivery paths
5. Error handling and retry logic

**Service Interactions:**
1. AWS service dependencies (EventBridge, Lambda, DynamoDB, SNS/SES)
2. Inter-service communication patterns
3. IAM roles and permissions
4. Resource naming conventions

**Key Components:**
1. Lambda functions (purpose, triggers, outputs)
2. EventBridge rules and patterns
3. DynamoDB tables (schema, access patterns)
4. Notification channels (SNS topics, SES configurations)

### 3. Architecture Diagram Requirements

Create a Mermaid.js diagram using **Graph TD** (top-down) format with the following specifications:

**Diagram Structure:**
```mermaid
graph TD
    %% Use clear, descriptive node IDs
    %% Group related services visually
    %% Show data flow direction with arrows
```

**Node Styling Guidelines:**
- Use square brackets `[]` for AWS services
- Use rounded brackets `()` for Lambda functions
- Use cylindrical shape `[()]` for databases
- Use double brackets `[[]]` for external systems
- Avoid using double quotes and parentheses inside square brackets

**Required Elements:**
1. All AWS services involved
2. Lambda function nodes with clear names
3. DynamoDB tables
4. EventBridge rules
5. Notification endpoints
6. Data flow arrows with labels
7. Grouping/subgraphs for logical separation (optional)

**Arrow Labels:**
- Label arrows with event types or data descriptions
- Use action verbs (e.g., "triggers", "stores", "sends", "processes")

### 4. Output Format

Create a file named `ARCHITECTURE.md` with the following structure:

```markdown
# AWS Resource Event Monitor - Architecture

## System Overview
[Brief description of the system purpose and capabilities]

## Architecture Components

### AWS Services
[List and describe each AWS service used]

### Lambda Functions
[Describe each Lambda function, its trigger, and purpose]

### Data Storage
[Describe DynamoDB tables and their schemas]

### Event Flow
[Describe the complete event processing flow]

## Architecture Diagram

```mermaid
graph TD
    [Your Mermaid diagram here]
```

## Data Flow Description

### 1. Event Ingestion
[Describe how events enter the system]

### 2. Event Processing
[Describe processing logic and transformations]

### 3. Data Persistence
[Describe how data is stored]

### 4. Notifications
[Describe notification delivery mechanisms]

## Key Design Decisions
[Document important architectural choices]

## Scalability Considerations
[Describe how the system scales]

## Security Measures
[Document security implementations]
```

### 5. Validation Checklist

Before finalizing, verify:
- [ ] All Terraform modules are analyzed
- [ ] All Lambda handlers are documented
- [ ] Data flow is complete and accurate
- [ ] Mermaid diagram renders correctly
- [ ] All AWS services are represented
- [ ] Arrow directions match actual data flow
- [ ] Node labels are clear and descriptive
- [ ] No syntax errors in Mermaid code
- [ ] Documentation is comprehensive yet concise

## Expected Output

Save the complete architecture documentation to: `ARCHITECTURE.md`

The document should provide a clear understanding of:
- How events flow through the system
- Which services interact with each other
- What data is stored and where
- How notifications are delivered
- The overall system architecture at a glance