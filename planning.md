# TakeMeter

## Community

`r/blender` is a Reddit community centered around Blender, a free and open-source software for 3D modeling, animation, rendering, and more. It is a place where users share their projects and seek help with workflow challenges. Discussions typically combine technical problem-solving, artistic feedback, learning resources, software opinions, and community appreciation of creative work.

---

## Labels

| # | Label | Description | Example 1 | Example 2 |
|---|-------|-------------|-----------|-----------|
| 1 | Feedback | It is an evaluation of a render, model, animation, or project. The purpose is to assess the quality or characteristics and to provide guidance for further improvement or development of the work. | I think these are good just need more variation in the facial features and distance between them based on each person to create more unique faces. | My advice would be to start adding small details—panels, screws, antennas—because that's what transforms a ship from a mere "block" into a "real spaceship." |
| 2 | Opinion | It states a preference, belief, or judgment. The purpose is to express a viewpoint or observation rather than provide constructive information. | This is vile, but I can tell it's intentional and also very technically impressive so great work my friend. The roots of the teeth are very unsettling. | Realllly well done. Appreciate the viewport view as well, the animated candle flames were a nice touch and it's good to see that they were cards, no need to reinvent the wheel. |
| 3 | Question | Requests information from other users. It expects a response in the form of a solution. | Is the mesh being generated from grease pencil strokes? | Veeeery nice! Just animating curves and curve lengths & thickness? |
| 4 | Social | Expresses a form of social reaction from a user, such as emotion, encouragement, appreciation, or humor. The purpose is social interaction rather than information exchange. | This is the MOST delicious, appetizing, mouth watering animation I've ever seen. | this is super cool! i've really got to learn motion graphics in Blender |

---

## Hard edge cases

| # | Hard Edge Case | Example | Description | Handling |
|---|----------------|---------|--------|----------|
| 1 | `Feedback` or `Opinion` | The lighting is gorgeous, but the composition feels a little cluttered to me. | It's a judgment about the work and expresses a personal reaction. | If the comment identifies specific aspects of the work, such as lighting, topology, proportions, animation timing, composition, etc., label feedback even when no explicit suggestion is provided. |
| 2 | `Social` or `Opinion` | I absolutely love this! | It contains a preference or opinion and social encouragement. | Opinion is about judgment of the work, while social is about relationship-oriented communication whose primary function is encouragement, appreciation, enthusiasm, humor, congratulations, etc. |
| 3 | `Feedback` or `Question` | Have you tried increasing the subsurface scattering? The skin looks a bit flat right now. | Begins with a question, but follows up with a clear, evaluative observation pointing toward a fix | If the question is used as a set up for constructive inormation, label it as feedback |
| 4 | `Opinion` or `Question` | Is this supposed to feel this unsettling? Because it really works. | Begins with a question, but follows up with a expresion of a strong reaction/judgment | If the question is used as a set up for a form of reaction, label it as an opinion |
| 5 | Links or URLs | www.imgur.com/aBCDefG | Content of text is only made up of a link or URL. | If the link leads to an image, gif, or video it is a form of reaction to the content and is labeled as Social. Otherwise, if it leads to an external website or other source, label it as Feedback. 

---

## Data collection plan

The training data will be collected from comments found under posts in the `r/blender` subreddit. I will try to have an even distribution of labels, around 50 comments per label. If a label is found to be underrepresented, a targeted sampling approach, with greater focus on data that fits the label, will be used to even the distribution, but the label distribution will be entireley dependant on the type of community the data is being gathered from.

---

## Evaluation metrics

The primary metric is how well the model performs across each discourse category and whether it assigns equal importance to all categories. This is to prevent comments under certain labels from dominating the rest, and to ensure that each label gets equal importance.

---

## Definition of success

A successful model yields outputs that are reliable for its intended use. A good benchmark is how often real humans agree with the model's classification.

---

## AI Tool Plan

**Label stress-testing:**
I will provide Claude with my specifications, including label definitions and edge case descriptions, from my `planning.md` file, and ask it to to generate 5–10 posts that sit at the boundary between two labels for manual review.

**Annotation assistance:**
A CSV file containing all the sample comments will be given to Claude and I will ask it to assign labels to each comment. The contents will be manually reviewed by me and revised if needed.

**Failure analysis:**
Claude will be provided with the text output of Google Colab code that contains the wrong predictions generated by the model, then will be asked to identify any specific patterns from each of the cases. I will review its findings to be used for further analysis of the wrong predictions.