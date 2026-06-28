# PIXEL_CHARACTER_STYLE_GUIDE_V1

This document defines the visual production standard.

When this document conflicts with prompts or temporary instructions, this document takes precedence unless explicitly superseded by a newer approved Style Guide.

Status:
OFFICIAL SOURCE OF TRUTH

---

## Purpose

Define the official pixel character visual production standard for the project.

This guide records the visual language extracted from the approved Guard production sprite and generalizes it for all future character, monster, NPC, and boss sprite production.

Approved style reference:

Guard_Pixel_Static_V2_FinalCleanup_candidate_01.png

This document does not define one character only.
It defines the shared pixel art language that future production sprites must inherit.

---

## 1. Philosophy

The project uses a modern pixel RPG character style.

Sprites should feel like native pixel sprites, not painted illustrations reduced in size.

Primary goals:

- Battlefield readability first
- Native pixel sprite construction
- Large readable colour blocks
- Clean silhouette
- Strong material separation
- Consistent production language
- Stable readability at gameplay scale

The sprite should read clearly during battle before the player notices small details.

---

## 2. Character Standard

Standard character production target:

- 4.5 head proportion
- 35 degree rear-dominant battlefield view
- 140 px battlefield display height
- Rear silhouette priority
- Class recognition before decorative detail

Battlefield view priority:

1. Back-facing silhouette
2. Major equipment shapes
3. Weapon and shield readability
4. Main clothing colour blocks
5. Material identity
6. Small details

The rear-dominant view is part of the gameplay readability standard.
Characters should feel like they are moving into battle, not posing for a front-facing showcase.

---

## 3. Pixel Rendering Rules

### Pixel Cluster Philosophy

Pixel clusters should look intentional.

Use clean connected pixel groups instead of scattered single pixels.
Small isolated pixels should be removed unless they serve a clear readability purpose.

Prefer:

- Connected 2-5 pixel clusters
- Readable block shapes
- Clear material zones
- Stable outer contours

Avoid:

- Random single-pixel noise
- Uncontrolled dithering
- Over-fragmented highlights
- Painterly texture translated into pixels

### Colour Block Philosophy

Major shapes must remain readable as large colour blocks.

Examples:

- Cloak reads as one large blue shape
- Shield reads as one large wooden shape
- Helmet reads as one clean metal shape
- Weapon reads as one clear blade shape

Small detail must never break the main colour block.

### Edge Treatment

Edges should be crisp and readable.

Use hard pixel edges where the silhouette matters.
Anti-aliasing may be used sparingly inside the sprite, but it must not blur the silhouette.

Outer contour readability has higher priority than smoothness.

### Highlight Treatment

Highlights should be hard, readable, and material-specific.

Use small but connected highlight clusters.
Avoid smooth glossy gradients that make the sprite look AI-painted.

### Shadow Treatment

Shadows should support large form readability.

Use grouped shadow masses rather than many tiny dark pixels.
Shadow placement should reinforce the pose, equipment, and rear-facing view.

### Anti-Noise Principles

Remove or simplify:

- Isolated bright pixels
- Isolated dark pixels
- Tiny scratches that do not affect recognition
- Noisy leather wrinkles
- Excessive belt micro-detail
- Decorative stitching at gameplay scale

If a detail does not improve 140 px readability, simplify it.

---

## 4. Material Rules

### Metal

Recommended shade count:
4-5 shades.

Rendering rules:

- Use clean highlight clusters.
- Keep bright highlights controlled.
- Avoid smooth chrome gradients.
- Preserve readable armor plates and helmet shape.

Metal should read as strong and clean, not noisy or over-rendered.

### Cloth

Recommended shade count:
Maximum 4 shades.

Rendering rules:

- Use large readable colour blocks.
- Keep fold shadows broad and simple.
- Avoid excessive wrinkle detail.
- Preserve cloak and robe silhouette.

Cloth should read as a major shape first and fabric texture second.

### Leather

Recommended shade count:
3-4 shades.

Rendering rules:

- Use compact shadow groups.
- Avoid too many tiny wrinkles.
- Keep straps readable through shape and placement.
- Simplify small buckles when needed.

Leather should support equipment readability without becoming visual noise.

### Wood

Recommended shade count:
3-4 shades.

Rendering rules:

- Use broad plank or surface shapes.
- Keep wood grain simple.
- Avoid excessive thin grain lines.
- Preserve the shield's large readable mass.

Wood should read as a material block before individual grain marks.

### Hair

Recommended shade count:
3-4 shades.

Rendering rules:

- Use grouped locks.
- Avoid many isolated strand pixels.
- Keep hair secondary to helmet, face silhouette, and class equipment.

Hair should support character identity without competing with profession readability.

---

## 5. Lighting Rules

Lighting direction:

- Fixed top-left light source.

Lighting treatment:

- Use hard readable highlights.
- Keep highlight clusters intentional.
- Maintain consistent material response.
- Preserve battlefield readability over realism.

Forbidden lighting treatment:

- Smooth AI gradients
- Airbrushed transitions
- Inconsistent light direction
- Over-glossy material rendering
- Highlights that create noisy isolated pixels

---

## 6. Detail Budget

Highest visual priority:

1. Helmet
2. Shield
3. Weapon
4. Main clothing
5. Main armor forms
6. Cape or cloak silhouette

Medium visual priority:

- Boots
- Gloves
- Belt mass
- Shoulder armor
- Hair shape
- Major material transitions

Lowest visual priority:

- Tiny belt details
- Small scratches
- Decorative stitching
- Micro ornaments
- Minor leather wrinkles
- Tiny metal rivets

Low-priority details may be simplified or removed when they reduce readability.

---

## 7. Battlefield Readability Rules

Players should recognize the class before noticing detail.

Readability hierarchy:

1. Class silhouette
2. Primary weapon or equipment
3. Main colour identity
4. Material identity
5. Character-specific details
6. Decorative details

At 140 px display height, a sprite must remain readable without relying on:

- Facial detail
- Tiny ornaments
- Texture noise
- Small engraved patterns
- Full-resolution artwork inspection

If recognition is lost, improve silhouette clarity and large readable shapes before adding detail.

---

## 8. Forbidden Style

Do not use:

- Painterly rendering
- Blurry gradients
- Excessive micro-detail
- Noisy isolated pixels
- Inconsistent lighting
- AI illustration look
- Over-rendered textures
- Smooth downscaled illustration shading
- Random dithering
- Detail density that weakens silhouette readability

Future sprites must not look like high-resolution illustrations scaled down into pixel size.

---

## 9. Approved Reference

Official Character Style Reference A:

Guard_Pixel_Static_V2_FinalCleanup_candidate_01.png

Reference role:

- Official character pixel style reference
- Production standard for sprite rendering language
- Baseline for pixel cluster quality
- Baseline for material simplification
- Baseline for 140 px readability

This reference defines the approved visual direction for character pixel production.

---

## 10. Future Usage

Every future production sprite should inherit this style.

Applicable to:

- Guard
- Archer
- Rogue
- Mage
- Priest
- Monsters
- NPCs
- Bosses

Future assets should preserve their own profession or creature identity while following this shared pixel rendering standard.

This document should be referenced before producing:

- Static production sprites
- Battlefield sprites
- Hub sprites
- Monster sprites
- NPC sprites
- Boss sprites
- Animation-ready sprite bases

---

## Future Review Items

- Confirm whether boss sprites require a separate large-scale pixel rendering extension.
- Confirm whether monsters should use the same 4.5 head proportion rule or only inherit rendering style.
- Confirm whether UI icon pixel rendering should use a separate style guide.

---

Status:
OFFICIAL SOURCE OF TRUTH
