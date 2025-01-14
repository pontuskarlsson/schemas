# JSON Schema Collection

A curated collection of JSON schemas for standardizing various data structures. These schemas provide consistent patterns for data validation and documentation across different domains.

## Overview

This repository hosts multiple JSON schemas designed to:
- Provide clear data structure definitions
- Enable data validation
- Ensure consistency in data formats
- Document data requirements
- Support interoperability between systems

## Available Schemas

### Meta Schema
Located at `/schema.json`, this is the foundation schema that all other schemas in this collection must follow. It ensures consistent structure and metadata across all schemas, including:
- Version control and compatibility tracking
- Clear authorship and licensing information
- Status management (draft, stable, deprecated, retired)
- Documentation requirements

### Domain-Specific Schemas
*(This section will grow as more schemas are added)*

## Using These Schemas

1. **Reference a Schema**
   ```json
   {
     "$schema": "https://raw.githubusercontent.com/pontuskarlsson/schemas/main/[path-to-schema].json"
   }
   ```

2. **Validate Your Data**
   - Use any JSON Schema validator that supports Draft 2020-12
   - Ensure your data includes all required fields
   - Follow the patterns and formats specified in the schema

3. **Version Compatibility**
   - Check the schema's version information
   - Review compatibility requirements
   - Note any deprecation notices

## Schema Development

All schemas in this collection:
- Follow JSON Schema Draft 2020-12 specification
- Include comprehensive metadata
- Maintain version control
- Provide clear documentation
- Include usage examples

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. All new schemas must conform to the meta-schema specification.

## License

This project is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License - see the [LICENSE.md](LICENSE.md) file for details.

[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg