# Chapter Information Schema Visual Guide

This document provides visual representations of the Chapter Information Schema structure and its relationships to other schemas in TheStoryTeller system.

## Schema Structure Overview

```
Chapter Information
├── Core Identifiers
│   ├── id
│   ├── title
│   ├── chapter_number
│   ├── file_path
│   ├── created_date
│   ├── last_modified
│   ├── status
│   └── version
│
├── Narrative Context
│   ├── narrative_time
│   │   ├── start_date
│   │   ├── end_date
│   │   └── time_span_description
│   ├── previous_chapter
│   └── next_chapter
│
├── Content Elements
│   ├── word_count
│   ├── reading_time_minutes
│   ├── characters
│   │   ├── primary
│   │   ├── secondary
│   │   └── mentioned
│   ├── locations
│   ├── point_of_view
│   ├── narrative_style
│   └── cultural_references
│
├── Narrative Elements
│   ├── primary_themes
│   ├── secondary_themes
│   ├── key_events
│   ├── event_chain
│   └── chapter_sections
│
├── Analysis Components
│   ├── pacing
│   ├── character_arcs
│   ├── editorial_notes
│   └── setting_details
│
└── Metadata
    ├── creation_date
    ├── last_modified
    ├── version
    ├── canon_status
    └── author
```

## Cross-Schema Relationships

The Chapter Information Schema serves as a central hub connecting multiple other schemas:

```
                          ┌───────────────┐
                          │   Timeline    │
                          │   Database    │
                          └───────┬───────┘
                                  │
                                  │ references
                                  │
┌───────────────┐          ┌──────┴──────┐          ┌───────────────┐
│   Character   │◄─────────┤   Chapter   ├─────────►│   Location    │
│   Database    │  lists   │ Information │   lists  │   Database    │
└───────┬───────┘characters└──────┬──────┘locations └───────────────┘
        │                         │
        │                         │ references
        │                         │
        │                  ┌──────┴──────┐          ┌───────────────┐
        └─────────────────►│    Event    │◄─────────┤     Theme     │
          participates in  │   Database  │ explores  │   Database    │
                          └──────┬──────┘          └───────────────┘
                                 │
                                 │ sequences
                                 │
                          ┌──────┴──────┐
                          │    Event    │
                          │ Relationship│
                          │  Database   │
                          └─────────────┘
```

## Character Arc Documentation

Character arcs within chapters connect to the broader character database:

```
┌─────────────────────────┐                 ┌─────────────────────────┐
│                         │                 │                         │
│   Character Database    │                 │  Chapter Information    │
│                         │                 │                         │
│  ┌─────────────────┐    │                 │  ┌─────────────────┐    │
│  │ char-benkei-001 │    │                 │  │ character_arcs  │    │
│  │                 │    │                 │  │                 │    │
│  │ - biography     │◄───┼─────references──┼──┤ char-benkei-001 │    │
│  │ - personality   │    │                 │  │                 │    │
│  │ - relationships │    │                 │  │ - arc_type      │    │
│  └─────────────────┘    │                 │  │ - starting_state│    │
│                         │                 │  │ - ending_state  │    │
└─────────────────────────┘                 │  │ - pivot_moment  │    │
                                            │  └─────────────────┘    │
                                            │                         │
                                            └─────────────────────────┘
```

## Event Documentation Flow

How events connect through the chapter information schema:

```
┌─────────────────┐     references     ┌─────────────────┐
│ Event Database  ├───────────────────►│    Chapter      │
└────────┬────────┘                    │  Information    │
         │                             └────────┬────────┘
         │                                      │
         │                                      │
         │                                      │
         │                             references events in
         │                                      │
         │                                      │
         ▼                                      ▼
┌─────────────────┐     sequences      ┌─────────────────┐
│Event Relationship├◄──────────────────┤  Chapter Events │
│    Database     │                    │   Sequence      │
└─────────────────┘                    └─────────────────┘
```

## Theme Exploration Tracking

How themes are documented and analyzed across chapters:

```
┌─────────────────┐                    ┌─────────────────┐
│ Theme Database  │◄───references──────┤    Chapter      │
└────────┬────────┘                    │  Information    │
         │                             └────────┬────────┘
         │                                      │
         │                                      │
         │         ┌─────────────────┐          │
         └────────►│ Theme Evolution │◄─────────┘
                   │ across Chapters │
                   └─────────────────┘
```

## Implementation Workflow

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  Write Chapter  │────►│Create Character, │────►│Create Chapter   │
│     Content     │     │Location & Event  │     │Information Entry│
└─────────────────┘     │Database Entries  │     └────────┬────────┘
                        └─────────────────┘              │
                                                         │
┌─────────────────┐     ┌─────────────────┐     ┌────────▼────────┐
│Update Character │◄────┤ Analyze Chapter │◄────┤  Cross-Reference│
│   Arcs in       │     │For Themes & Arcs│     │   Validation    │
│Future Chapters  │     └─────────────────┘     └─────────────────┘
└─────────────────┘
```

## Using This Visual Guide

These diagrams provide a conceptual framework for understanding how the Chapter Information Schema connects various components of your narrative database. When implementing chapter information entries:

1. **Start from the center:** Begin with basic chapter information
2. **Build relationships outward:** Connect to characters, locations, events
3. **Add analytical layers:** Document themes, arcs, and editorial insights
4. **Validate connections:** Ensure all cross-references are accurate

For detailed implementation instructions, refer to the [Chapter Information Implementation Guide](chapter_information_implementation_guide.md) and the [Chapter Information Schema Usage](chapter_information_schema_usage.md) document.
