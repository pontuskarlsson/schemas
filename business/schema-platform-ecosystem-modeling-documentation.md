# Platform Ecosystem Modeling Schema Documentation

This document describes the Platform Ecosystem Modeling Schema, which is based on the Platform Ecosystems Modeling Language (PEML) developed by Pauli et al. (2020). The schema provides a practical implementation approach for modeling platform ecosystems while adapting and extending some PEML concepts.

## Original PEML Concepts

PEML was developed to provide a comprehensive way to model platform ecosystems. The key concepts from PEML that we've incorporated include:

### Actor Types
- **Platform Owner (PO)**: The actor who provides and governs the platform
- **Complementor (C)**: Actors who offer compatible modules/services
- **User (U)**: Actors who consume the platform's value propositions

### Boundary Resources
Three types of interfaces that enable interaction with the platform:
- **Social**: Partner programs, workshops, knowledge exchange
- **Development**: SDKs and development tools
- **Application**: APIs and technical interfaces

### Value Propositions
Two types of value propositions:
- **Main Value Proposition**: Single, overarching platform value proposition
- **Standard Value Propositions**: Multiple specific value propositions for different platform aspects

### Links
Different types of connections between actors:
- Platform-actor links
- Actor-platform links
- Peripheral links (indirect influence)

### Leverage Types
How actors benefit from the platform:
- Innovation leverage
- Production leverage
- Transaction leverage

## Schema Adaptations and Extensions

Our schema makes several practical adaptations to PEML concepts:

### Entity-Role Structure
- **Entity**: Represents real-world actors (individuals or organizations)
- **Roles**: Specific functions an entity can perform
- Each role is associated with exactly one actor type (PO, C, or U)
- Entities can have multiple roles

### Platform Structure
- **Sides**: Explicitly defines supply and demand sides
- **Actor Types**: Defines valid roles for each actor type (PO, C, U)
- **Boundary Resources**: As defined in PEML
- **Owner**: Reference to the entity that owns the platform

### Value Proposition and Role Relationships
- One mandatory main value proposition for the platform
- Multiple standard value propositions allowed
- Bidirectional relationship between roles and value propositions:
  - Roles list the value propositions they contribute to or consume
  - Value propositions list their associated roles
- Each value proposition must have a unique identifier

## Implementation Details

### Entity Definition
```json
{
  "id": "entity1",
  "type": "individual",
  "roles": [...]
}
```

### Role Definition
```json
{
  "id": "role1",
  "name": "Content Creator",
  "actorType": "C",
  "valuePropositions": ["vp1", "vp2"],
  "resources": [...],
  "activities": [...]
}
```

### Value Proposition Definition
```json
{
  "id": "vp1",
  "name": "Content Distribution",
  "type": "standard",
  "associatedRoles": ["role1", "role2"],
  "leverageTypes": ["innovation", "transaction"]
}
```

### Platform Definition
```json
{
  "name": "Platform Name",
  "owner": "entity1",
  "sides": {
    "supply": {
      "name": "Content Providers"
    },
    "demand": {
      "name": "Content Consumers"
    }
  },
  "actorTypes": {
    "platformOwner": {
      "validRoles": ["Platform Administrator"]
    },
    "complementors": {
      "validRoles": ["Content Creator", "Service Provider"]
    },
    "users": {
      "validRoles": ["Content Consumer", "Service Consumer"]
    }
  }
}
```

## Validation Rules

### Value Propositions
- Exactly one main value proposition must exist
- Each value proposition must have a unique ID
- References between roles and value propositions must be valid

### Roles
- Each role must belong to a valid actor type
- Role names must match the platform's defined valid roles for their actor type

### Platform Structure
- Must define both supply and demand sides
- Must define valid roles for all actor types
- Must reference a valid entity as platform owner

## Usage Guidelines

### Modeling Best Practices
1. Start with defining the platform structure including sides and valid roles
2. Define the main value proposition first
3. Add standard value propositions as needed
4. Create entities and assign appropriate roles
5. Establish relationships between roles and value propositions

### Common Patterns
1. Users typically start on the demand side
2. Entities can progress from users to complementors
3. Platform owner roles are typically fixed
4. Value propositions should clearly relate to specific roles

## Schema Evolution Notes

The schema is designed to be extensible while maintaining compatibility with core PEML concepts. Future extensions might include:

- More detailed role progression tracking
- Enhanced boundary resource specifications
- Additional relationship types
- Metrics and performance indicators

## References

Based on:
Pauli, T., Marx, E., Dunzer, S., & Matzner, M. (2020). Modeling Platform Ecosystems. In ER Forum, Demo and Posters 2020.
