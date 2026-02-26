# Data Shape

## Entities

### User
A registered account. Owns tracks and remixes, has a subscription plan, and is the top-level owner of all content in the system.

### Subscription
A billing plan attached to a User. Defines the tier (Free, Pro, Studio), monthly remix quota, stem access, voice cloning eligibility, and commercial license status.

### Track
An uploaded audio file (MP3 or MP4). Stores the original media, the separated vocal and instrumental stems, and the detected song metadata — tempo, key, and structural segments.

### Stem
A separated audio component extracted from a Track — vocals, drums, bass, or other instrumentation. Used as the source material for regeneration and available for individual download on Pro and Studio plans.

### Style
A style configuration applied to a regeneration. Can be a named genre preset (e.g., "Bossa Nova", "90s Boom Bap") or a free-form custom prompt. Stores the vocal mode setting — keep original or generate AI voice.

### Remix
A regenerated version of a Track produced by applying a Style. The primary output of the platform. Stores the resulting audio, the style used, and the vocal mode applied.

### Export
A downloadable output package derived from a Remix. Can be a full mix (WAV/MP3), a stem bundle, or a social-ready short clip.

## Relationships

- User has many Tracks
- User has one Subscription
- Track has many Stems
- Track has many Remixes
- Remix belongs to one Track
- Remix is produced using one Style
- Remix has many Exports
- Export belongs to one Remix
