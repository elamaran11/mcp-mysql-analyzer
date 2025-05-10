# MySQL Performance Analyzer - MCP Server

## README.md

```markdown
# MySQL Performance Analyzer - MCP Server

A Model Context Protocol (MCP) server for analyzing and optimizing MySQL database performance. This tool provides a comprehensive set of features for identifying performance bottlenecks, recommending optimizations, and analyzing database structure.

## Features

- **Database Structure Analysis**: Analyze tables, columns, indexes, and foreign keys
- **Query Analysis**: Examine execution plans and identify inefficient queries
- **Index Recommendations**: Get suggestions for new indexes to improve performance
- **Query Rewrite Suggestions**: Receive recommendations for optimizing SQL queries
- **InnoDB Buffer Pool Analysis**: Analyze buffer pool usage and get optimization tips
- **Table Fragmentation Analysis**: Identify and fix fragmented tables
- **MySQL Configuration Review**: Review and optimize MySQL settings
- **Read-Only Query Execution**: Safely execute and analyze read-only queries

## Security

- All operations are performed in read-only mode
- Database credentials are securely stored in AWS Secrets Manager
- Query validation prevents any write operations
- Automatic session management and timeouts

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/mysql-performance-analyzer.git
   cd mysql-performance-analyzer
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the server:
   ```bash
   python main.py --port 8000 --host 0.0.0.0
   ```

## Docker Deployment

Build and run the Docker container:

```bash
docker build -t mysql-performance-analyzer .
docker run -p 8000:8000 mysql-performance-analyzer
```

## Usage

The server exposes an MCP endpoint that can be used with compatible clients. It also provides the following HTTP endpoints:

- `/health`: Health check endpoint
- `/sessions`: View active sessions

## Configuration

The server accepts the following command-line arguments:

- `--port`: Port to run the server on (default: 8000)
- `--host`: Host to bind the server to (default: 0.0.0.0)
- `--session-timeout`: Session timeout in seconds (default: 1800)
- `--request-timeout`: Request timeout in seconds (default: 300)

## Tools

### analyze_database_structure
Analyze the database structure and provide insights on schema design, indexes, and potential optimizations.

### get_slow_queries
Identify slow-running queries in the database.

### analyze_query
Analyze a SQL query and provide optimization recommendations.

### recommend_indexes
Recommend indexes for a given SQL query.

### suggest_query_rewrite
Suggest optimized rewrites for a SQL query.

### analyze_innodb_buffer_pool
Analyze InnoDB buffer pool usage and provide optimization recommendations.

### analyze_table_fragmentation
Analyze table fragmentation and provide optimization recommendations.

### show_mysql_settings
Show MySQL configuration settings with optional filtering.

### execute_read_only_query
Execute a read-only SQL query and return the results.

### health_check
Check if the server is running and responsive.

## License

[MIT License](LICENSE)
