# Online Media and Post Extraction Template

Use this file when distilling experience from Douyin, Bilibili, Zhihu, Xiaohongshu, podcasts, newsletters, forums, comments, or other online sources.

## Source Access Rules

- If only a URL or title is available, mark the source as `metadata-only` or `title-only`.
- If a transcript, subtitles, or timestamp notes are available, mark it as `transcript-read`; do not claim the original video was watched.
- If post or thread text was inspected, mark it as `post-read`.
- If only selected comments were inspected, mark it as `comments-read`.
- Treat likes, views, saves, shares, and hot comments as signals of audience response, not proof that a method works.

## Extraction Layers

### 1. Metadata Layer

Platform:

Creator / author:

Title:

URL / file:

Publish date:

Engagement signals:

Access status:

### 2. Claim Layer

Creator's main claim:

Problem the source tries to solve:

Target audience:

What the source argues against:

### 3. Demonstration Layer

Concrete action shown or recommended:

Context where it was used:

Inputs required:

Steps:
1. 
2. 
3. 

Visible or claimed result:

### 4. Comment / Feedback Layer

Repeated audience feedback:

Counterexamples or objections:

Useful corrections:

Noise or low-confidence reactions:

### 5. Transfer Layer

Transferable pattern:

Applicable conditions:

Non-transferable context:

Hidden prerequisites:

Risks:

Validation signal:

## Experience Card

```markdown
## Experience Name

Source ID:
Platform:
Creator / author:
Access status:

Observed claim:

Demonstrated action:

Applicable when:

Do not apply when:

Step-by-step method:
1. 
2. 
3. 

Evidence level:
- creator claim / demonstrated case / repeated comments / external verification / user-tested

Validation metric:

Misuse warning:

Atomic rules:
- 
```

## Platform-Specific Warnings

| Source | Watch For | Required Handling |
|---|---|---|
| Short video | performance bias, oversimplified tips, missing context | extract condition, prerequisite, risk, and validation signal |
| Long video / Bilibili | scattered advice, narrative filler | timestamp claims and separate examples from principles |
| Zhihu article | polished argument, anecdotal evidence, comment disagreement | separate author thesis, support, objections, and uncertainty |
| Comment section | survivorship bias, crowd emotion, repeated practical detail | treat as hypotheses unless independently verified |
| Influencer workflow | personal context hidden behind advice | identify what depends on the creator's resources, audience, or timing |
