# Writing Schema Implementation Guide

This guide provides a **practical step-by-step workflow** for implementing The Shadow Team Chronicles writing schemas in your content creation. For a comprehensive overview of the schemas themselves, see the [Writing Schemas Guide](writing_schemas_guide.md).

## Step-by-Step Implementation Workflow

### Step 1: Define Narrative Position

Begin by determining where your content fits in the narrative structure:

```
Storyline → Volume → Act → Story → Chapter → Passage → Part
```

1. Reference `enums/narrative_structure_schema.json` for structure definitions
2. Include proper metadata with parent references
3. Use the appropriate `object_type` value

**Example:**
```json
{
  "object_type": "passage",
  "parent": {
    "type": "chapter",
    "id": "5a6b7c8d-9e0f-1a2b-3c4d-5e6f7g8h9i0j",
    "name": "Chapter 3: The Descent"
  },
  "sequence_position": {
    "storyline": "The Shadow Team Chronicles",
    "volume": "Neo-Tokyo Rising",
    "act": "Act II: Underground Movement",
    "story": "The Ghost Protocol",
    "chapter": "Chapter 3: The Descent",
    "passage": "Infiltrating the Corporate Archive",
    "passage_number": 2
  }
}
```

### Step 2: Identify Scene Type

Determine your scene's primary function using `enums/scene_type_schema.json`:

1. Consider what the scene needs to accomplish
2. Select the matching scene type from the enum
3. Document the specific purpose

**Example:**
```json
{
  "scene_type": "investigation_discovery",
  "scene_purpose": "Reveals critical information about the blackmail operation and establishes the corporate connection"
}
```

### Step 3: Select Writing Style

Choose an appropriate writing style from `enums/writing_style_schema.json`:

1. Check the `sceneTypeCompatibility` section of the schema
2. Select a style that enhances your scene's purpose
3. Document your style rationale

**Example:**
```json
{
  "writing_style": "cinematic_precise",
  "writing_style_rationale": "To create clear visual focus and precise pacing for the investigation sequence"
}
```

### Step 4: Plan Prose Variation

Select at least three techniques from `enums/prose_variation_technique_schema.json`:

1. Choose techniques that complement your writing style
2. Plan specific implementation approaches
3. Document your implementation strategy

**Example:**
```json
{
  "prose_variation_techniques": [
    {
      "technique": "sentence_structure_variation",
      "implementation_plan": "Use short sentences for moments of discovery, longer sentences for technical processes"
    },
    {
      "technique": "focused_detail_alternation",
      "implementation_plan": "Shift between environmental details, technical information, and character reactions"
    },
    {
      "technique": "rhythm_modulation",
      "implementation_plan": "Create accelerating pace when uncovering key information"
    }
  ]
}
```

### Step 5: Set Additional Parameters

Complete your plan with these supporting elements:

**Narrative Pacing** (from `enums/narrative_pacing_schema.json`):
```json
{
  "narrative_pacing": "deliberate",
  "pacing_rationale": "Allows readers to absorb the significance of discovered information"
}
```

**Emotional Tone** (from `enums/emotional_tone_schema.json`):
```json
{
  "emotional_tone": "tense",
  "emotional_tone_rationale": "Creates appropriate anxiety during the high-stakes infiltration"
}
```

**Description Focus** (from `enums/description_focus_schema.json`):
```json
{
  "description_focus": "visual_primary",
  "description_focus_rationale": "Emphasizes visual details of the secure location and discovered evidence"
}
```

**Scene Transitions** (from `enums/scene_transition_schema.json`):
```json
{
  "transition_from_previous": {
    "transition_type": "location_shift",
    "transition_description": "Moving from the exterior surveillance position to inside the facility"
  },
  "transition_to_next": {
    "transition_type": "revelation_impact",
    "transition_description": "Showing immediate reactions to the discovered information"
  }
}
```

**Dialogue Approach** (from `enums/dialogue_tag_style_schema.json`):
```json
{
  "dialogue_tag_style": "action_integrated",
  "dialogue_style_rationale": "Integrates dialogue with infiltration actions to maintain momentum"
}
```

**Character Dynamics** (from `enums/character_dynamic_schema.json`):
```json
{
  "character_dynamics": [
    {
      "characters": ["Maya", "Yuri"],
      "dynamic": "loyal_partners",
      "dynamic_details": "Professional trust with subtle tension over risk assessment"
    }
  ]
}
```

### Step 6: Create Content Following Schema Guidance

Write your content with deliberate application of all selected schema elements.

### Step 7: Document Implementation

After creating content, document how you implemented each schema element:

```json
"implementation_details": {
  "writing_style_implementation": {
    "style": "cinematic_precise",
    "examples": [
      "Used clear visual framing of the archive environment",
      "Included specific technical details about security systems",
      "Created precise action choreography during infiltration"
    ]
  },
  "prose_variation_implementation": [
    {
      "technique": "sentence_structure_variation",
      "examples": [
        "Simple sentences for tension: 'There. TX-7734.'",
        "Complex sentences for environment: 'The projected interface responded to her stolen credentials, blooming into existence with corporate blues and whites.'"
      ]
    }
  ]
}
```

## Common Implementation Issues and Solutions

### Issue: Writing Style Feels Forced

**Solution:** 
1. Check if your scene type and writing style are compatible in the schema
2. Consider a hybrid approach and document it:

```json
"writing_style": "cinematic_precise",
"writing_style_adaptation": "Incorporated elements of atmospheric_immersive when describing the digital environment"
```

### Issue: Insufficient Prose Variation

**Solution:**
1. Verify you're implementing at least three distinct techniques
2. Plan technique implementation before writing
3. Apply techniques organically rather than mechanically

### Issue: Character Dynamics Inconsistency 

**Solution:**
1. Reference previous content to confirm existing relationships
2. Document any intentional relationship evolution:

```json
"character_dynamics": [
  {
    "characters": ["Maya", "Director Chen"],
    "previous_dynamic": "asymmetric_trust",
    "current_dynamic": "hidden_agenda",
    "evolution_trigger": "Maya's discovery of Chen's involvement in Project Lazarus"
  }
]
```

## Related Documentation

For more detailed guidance and examples, refer to:
- **[Schema Implementation Practical Guide](schema_implementation_practical_guide.md)** - Concrete examples for each schema
- **[Integrated Schema Workflow](integrated_schema_workflow.md)** - End-to-end implementation process
- **[Prose Variation Techniques](prose_variation_techniques.md)** - Detailed variation examples
- **[Writing Schemas Guide](writing_schemas_guide.md)** - Comprehensive schema overview

