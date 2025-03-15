# The Shadow Team Chronicles: Character Creation Guide

This guide explains how to create rich, detailed character objects using The Shadow Team Chronicles schema system. Following these instructions will ensure characters are consistently defined and properly integrated into the narrative database.

## Character Schema Structure

The character schema system is modular and hierarchical, allowing for both simplicity and depth:

```
character_schema.json (Root schema)
├── personal_data_schema.json
├── timeline_schema.json
├── relationships_schema.json
├── affiliations_schema.json
├── character_arc_schema.json
├── attributes_schema.json
│   └── [references common/abilities_schema.json]
├── skills_schema.json
├── equipment_schema.json
├── voice_schema.json
├── narrative_function_schema.json
│   └── [references common/narrative_significance_schema.json]
├── visual_representation_schema.json
│   └── [inherits from common/visual_representation_schema.json]
├── identity_schema.json
├── backstory_schema.json
└── character_metadata_schema.json
```

Several schemas rely on common components that are shared across multiple entity types:

- `common/abilities_schema.json` - Used by characters, artifacts, and technologies
- `common/visual_representation_schema.json` - Used by all visually depicted entities
- `common/narrative_significance_schema.json` - Used for thematic and plot functions
- `common/references_schema.json` - Used for cross-referencing between objects

## Step-by-Step Character Creation

### 1. Start with the Base Character Object

Begin by creating a JSON object with the required base properties from `character_schema.json`:

```json
{
  "id": "3f7d0bca-2e27-4edc-8010-41b5f3fb3982", // Generate a UUID v4
  "name": "Hanako Miyashiro",
  "description": "A brilliant cyber-security specialist with a mysterious past who uses her hacking skills to investigate corporate corruption while concealing her own connections to those she's pursuing.",
  "object_type": "character",
  "status": "alive",
  "role": "protagonist"
}
```

### 2. Add Personal Data

Add the `personal_data` object to define basic identifying information:

```json
"personal_data": {
  "full_name": "Hanako Rei Miyashiro",
  "birth_name": "Hanako Rei Chen",
  "titles": ["The Ghost in the Machine", "Captain Miyashiro (former)"],
  "age": {
    "value": 34,
    "appearance": "Late twenties due to minor cybernetic enhancements",
    "notes": "Military-grade life extension treatments have slowed her aging process"
  },
  "gender_identity": "Female",
  "species": "Human (Enhanced)",
  "ethnicity": "Japanese-Chinese",
  "nationality": "Neo-Tokyo Citizen, former United Pacific States operative",
  "languages": [
    {
      "name": "Japanese",
      "fluency": "native"
    },
    {
      "name": "Mandarin Chinese",
      "fluency": "fluent"
    },
    {
      "name": "English",
      "fluency": "fluent"
    },
    {
      "name": "Machine Code",
      "fluency": "expert"
    }
  ],
  "birth_place": {
    "location_id": "7c8f4d21-9e32-4a9b-8cb5-3f7ae9dbc4e5",
    "description": "Born in the Shibuya District of Neo-Tokyo during the Great Blackout, giving her an almost mythical status among hackers."
  }
}
```

### 3. Define Character Attributes

Character attributes define physical and psychological traits:

```json
"attributes": {
  "physical_traits": {
    "appearance": {
      "height": "172 cm (5'8\")",
      "build": "Athletic and lean",
      "hair": "Black with electric blue highlights, shoulder-length, typically worn in a practical ponytail",
      "eyes": "Dark brown with subtle cybernetic enhancements that glow faintly blue when activated",
      "skin": "Light olive complexion",
      "distinctive_features": [
        "Intricate circuitry-pattern tattoo extending from left temple down neck",
        "Barely visible scar across right eyebrow",
        "Neural-port interface behind right ear"
      ],
      "typical_attire": "High-tech urban wear featuring modular components, typically in blacks and blues with glowing circuit accents. Often wears a custom leather jacket with embedded tech and a holographic interface woven into the left sleeve."
    },
    "physical_capabilities": {
      "strength": "Above average due to targeted muscle enhancement",
      "agility": "Exceptional, especially in digital interface movements",
      "endurance": "Enhanced through cybernetic optimization",
      "health": "Excellent with advanced immune system upgrades",
      "special_abilities": [
        {
          "name": "Neural Interface",
          "ability_type": "technological",
          "description": "Can directly connect to and manipulate digital systems through her neural implant",
          "limitations": [
            "Requires proximity to the target system",
            "Extended use causes migraine-like symptoms",
            "Vulnerable to specialized EMP attacks"
          ]
        }
      ]
    }
  },
  "psychological_traits": {
    "personality": {
      "dominant_traits": [
        "Analytical",
        "Guarded",
        "Fiercely independent",
        "Loyal to her principles above all"
      ],
      "virtues": [
        "Unwavering determination",
        "Incredible focus under pressure",
        "Compassionate toward vulnerable individuals"
      ],
      "flaws": [
        "Trust issues stemming from betrayal",
        "Tendency toward isolation",
        "Occasional recklessness when pursuing justice"
      ],
      "defense_mechanisms": [
        "Deflection through sarcasm",
        "Compartmentalization of emotions",
        "Immersion in technology to avoid personal connections"
      ]
    }
  }
}
```

### 4. Add Character Skills

Skills define what the character can do:

```json
"skills": {
  "technical_skills": [
    {
      "name": "Neural Network Hacking",
      "proficiency": "master",
      "description": "The ability to interface directly with and manipulate complex security systems using a combination of cybernetic implants and custom-developed software.",
      "source": "Developed during her time with the Phantom Protocol division and refined through years of independent work."
    },
    {
      "name": "Quantum Encryption Breaking",
      "proficiency": "expert",
      "description": "Can decode even the most sophisticated quantum-encrypted communications, a skill possessed by fewer than 50 people worldwide.",
      "source": "Trained by Dr. Akira Nakamura, the pioneer of quantum computing at Neo-Tokyo University."
    }
  ],
  "combat_skills": [
    {
      "name": "Close-quarters Combat",
      "proficiency": "expert",
      "description": "Specialized in a hybrid fighting style combining military CQC with traditional aikido, focusing on using opponents' momentum against them.",
      "source": "Military training enhanced by private instruction from Master Tanaka."
    }
  ]
}
```

### 5. Add Relationships

Define the character's connections to others using the common reference schema format:

```json
"relationships": {
  "allies": [
    {
      "character_reference": {
        "id": "a7f13b29-64de-48e3-8ca1-b5e3a32cc982",
        "name": "Takeshi Yamamoto",
        "object_type": "character"
      },
      "relationship_type": "trusted hacker colleague",
      "trust_level": "high",
      "history": "Met during the infamous CoreTech security breach where they were initially rivals before joining forces. Has been her most reliable information source for five years."
    }
  ],
  "adversaries": [
    {
      "character_reference": {
        "id": "e9d25c31-8b3f-4ac6-9e54-9fac1c6a7105",
        "name": "Director Marcus Chen",
        "object_type": "character"
      },
      "relationship_type": "former mentor turned enemy",
      "conflict_source": "Discovered he was using her skills to target innocent people and selling security vulnerabilities on the black market.",
      "threat_level": "serious"
    }
  ]
}
```

### 6. Define Character Arc

The character arc tracks their journey and development:

```json
"character_arc": {
  "arc_type": "redemption",
  "starting_state": {
    "worldview": "Believes the system is fundamentally corrupt and that working outside it is the only way to achieve justice.",
    "flaws": ["Inability to trust institutions", "Self-destructive pursuit of justice at any cost"],
    "desires": "To expose those who betrayed her and the corruption within the cybersecurity establishment."
  },
  "internal_conflict": "Struggles between her desire for revenge against those who betrayed her and recognizing that her quest for vengeance is consuming her humanity."
}
```

### 7. Add Narrative Function

Define the character's role in the narrative using common narrative significance components:

```json
"narrative_function": {
  "archetype": "Fallen Guardian",
  "story_role": "protagonist",
  "thematic_representation": [
    {
      "theme": "The cost of justice",
      "representation": "Her increasing moral compromises illustrate the erosion of principles in pursuit of a righteous cause."
    },
    {
      "theme": "Technology's double edge",
      "representation": "Her cybernetic enhancements both empower her and distance her from her humanity."
    }
  ],
  "plot_functions": [
    {
      "function": "Expose corporate conspiracy",
      "significance": "As the primary investigator, she drives the plot by uncovering each layer of corruption."
    }
  ],
  "character_relationships": [
    {
      "character_id": "e9d25c31-8b3f-4ac6-9e54-9fac1c6a7105",
      "relationship_type": "mirror",
      "narrative_purpose": "Director Chen represents what Hanako could become if she completely abandons ethics in favor of pragmatism."
    }
  ]
}
```

### 8. Add Backstory

```json
"backstory": {
  "origin_summary": "Formerly a decorated captain in the United Pacific States Cybersecurity Command, Hanako discovered her division was secretly selling weapons-grade exploits to corporate entities. When she attempted to expose the corruption, she was framed for the very crimes she uncovered. She escaped custody during transfer and has been operating as a ghost in the system ever since, using her skills to expose corruption while evading capture.",
  "childhood": {
    "family_circumstances": "Raised in a middle-class family with her father working as a neural interface programmer and her mother as a cultural preservation specialist. Her upbringing blended traditional Japanese values with cutting-edge technology."
  }
}
```

### 9. Add Visual Representation Using Common Schema

```json
"visual_representation": {
  "essential_visual_elements": [
    {
      "element": "Neural interface port",
      "importance": "defining",
      "description": "A sleek titanium interface behind her right ear with subtle blue illumination when active, represents her hybrid nature between human and machine."
    },
    {
      "element": "Circuit tattoo pattern",
      "importance": "major",
      "description": "Glowing blue circuitry pattern tattoos that extend from left temple down neck and across left collarbone, partially visible beneath clothing."
    }
  ],
  "style_guidelines": {
    "color_palette": {
      "primary_colors": ["#0A1921", "#2B5278"],
      "accent_colors": ["#00B2FF", "#FF4D00"],
      "color_symbolism": "The blue represents technology and her digital life, while the orange represents her lingering humanity and passion."
    }
  },
  "image_generation_prompts": {
    "standard_prompt": "Cyberpunk female hacker with sleek black hair with electric blue highlights, olive skin, athletic build, circuit tattoos glowing blue on face and neck, neural interface port behind ear, wearing high-tech fitted jacket with holographic interface, urban night setting with neon reflections, serious expression, cinematic lighting."
  },
  "animation_guidelines": {
    "movement_style": "Precise, economical movements when focused; fluid and graceful in combat scenarios; occasional nervous micro-gestures when interfacing with technology."
  }
}
```

### 10. Add Metadata

```json
"metadata": {
  "character_id": "3f7d0bca-2e27-4edc-8010-41b5f3fb3982",
  "status": "alive",
  "role": "protagonist",
  "version": "1.2.3",
  "creation_date": "2023-09-15T14:30:00Z",
  "last_modified": "2024-06-23T09:45:22Z",
  "tags": ["hacker", "cyberpunk", "fugitive", "enhanced human", "protagonist"]
}
```

## Best Practices

1. **Maintain UUID Consistency**: Always use the same UUID across references to the same character.

2. **Use References Schema**: When linking to other database objects (locations, organizations, etc.), use the common references schema format with `id`, `name`, and `object_type`.

3. **Leverage Common Schemas**: Use the shared common schemas rather than duplicating structures. This ensures consistency across different entity types.

4. **Skip Optional Elements**: If certain aspects of a character aren't developed yet, skip those sections entirely rather than including empty objects.

5. **Start Simple, Expand Later**: Begin with required properties and the sections most relevant to the current narrative. You can expand character details as the story develops.

6. **Follow Enums**: When properties have enumerated values (like `status` or `role`), strictly use values from the defined lists.

## Character Creation Workflow

1. **Initial Concept**: Create a basic character outline with name, description, status, and role.
2. **Essential Details**: Add personal data, basic attributes, and skills.
3. **Relationships**: Define connections to existing characters using the references schema.
4. **Narrative Context**: Add character arc, narrative function, and backstory.
5. **Visual & Voice**: Define visual representation and voice characteristics, utilizing common schemas where appropriate.
6. **Metadata & Integration**: Add metadata and ensure all references are valid.

## Example: Minimal Viable Character

```json
{
  "id": "3f7d0bca-2e27-4edc-8010-41b5f3fb3982",
  "name": "Hanako Miyashiro",
  "description": "A brilliant cyber-security specialist with a mysterious past.",
  "object_type": "character",
  "status": "alive",
  "role": "protagonist",
  "personal_data": {
    "full_name": "Hanako Rei Miyashiro"
  },
  "attributes": {
    "physical_traits": {
      "appearance": {
        "distinctive_features": ["Neural-port interface behind right ear"]
      }
    }
  },
  "skills": {
    "technical_skills": [
      {
        "name": "Neural Network Hacking",
        "proficiency": "master"
      }
    ]
  },
  "metadata": {
    "character_id": "3f7d0bca-2e27-4edc-8010-41b5f3fb3982",
    "status": "alive",
    "role": "protagonist",
    "creation_date": "2024-06-23T00:00:00Z",
    "last_modified": "2024-06-23T00:00:00Z"
  }
}
```

## Validating Your Character JSON

To validate your character JSON against the schema, use a JSON Schema validator like:

- [JSON Schema Validator](https://www.jsonschemavalidator.net/)
- VS Code with the "JSON Schema" extension
- The command line with tools like AJV

Paste both your character JSON and the character schema to verify compliance before submitting to the database.
