# Chapter Information Schema Quick Reference

This quick reference provides a concise overview of the Chapter Information Schema, its key components, and common usage patterns.

## Essential Components at a Glance

### Core Identifiers (Required)
```json
{
  "id": "chapter-warriors-oath-001",
  "title": "The Warriors Oath",
  "chapter_number": 2,
  "file_path": "path/to/chapter.md",
  "status": "draft"
}
```

### Narrative Timeline (Required)
```json
"narrative_time": {
  "start_date": "1180-03-15",
  "end_date": "1180-03-19"
}
```

### Characters (Required)
```json
"characters": {
  "primary": ["char-yoshi-001", "char-benkei-001"],
  "secondary": ["char-tanaka-hunter-001"],
  "mentioned": ["char-monastery-abbot-001"]
}
```

### Key Events (Required)
```json
"key_events": [
  "event-benkei-oath-001",
  "event-journey-north-begins-001"
]
```

## Common Usage Patterns

### 1. Document Character Arcs
Track how characters change within a chapter:
```json
"character_arcs": {
  "char-benkei-001": {
    "arc_type": "transformation",
    "starting_state": "Directionless warrior",
    "ending_state": "Devoted retainer",
    "pivot_moment": "event-benkei-oath-001"
  }
}
```

### 2. Analyze Thematic Elements
Document primary and secondary themes:
```json
"primary_themes": ["theme-finding-purpose-001"],
"secondary_themes": ["theme-protocol-necessity-001"]
```

### 3. Track Chapter Structure
Break down narrative sections:
```json
"chapter_sections": [
  {
    "title": "The Duel at Gojo Bridge",
    "narrative_function": "Establishes the battle where Yoshi defeats Benkei"
  },
  {
    "title": "The Warrior's Oath",
    "narrative_function": "Depicts Benkei's pledge of loyalty to Yoshi"
  }
]
```

### 4. Add Editorial Notes
Include guidance for revisions and future development:
```json
"editorial_notes": {
  "strengths": ["Strong characterization"],
  "areas_for_improvement": ["Expand political context"],
  "follow_up_chapters": ["Address Taira pursuit"]
}
```

## Common Pitfalls to Avoid

1. **Missing Cross-References**: Ensure all character, location, and event IDs exist in their respective databases
2. **Inconsistent Character Categorization**: Maintain consistent criteria for categorizing characters
3. **Timeline Conflicts**: Check that chapter dates align with the broader narrative timeline
4. **Incomplete Character Arcs**: Document both starting and ending states for character development
5. **Outdated Information**: Update chapter information entries when chapter content changes

## When to Create or Update Chapter Information

- **Planning Stage**: Create a skeleton entry during chapter planning
- **First Draft**: Populate with basic details after completing initial draft
- **Revision**: Update character and theme analyses during revision
- **Final Draft**: Complete all analytical components before finalizing

## For Further Information

- [Chapter Information Schema Usage](chapter_information_schema_usage.md) - Comprehensive usage guide
- [Chapter Information Implementation Guide](chapter_information_implementation_guide.md) - Step-by-step implementation
- [Chapter Information Schema Visual Guide](chapter_information_schema_visual_guide.md) - Visual representations
