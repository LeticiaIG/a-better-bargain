# Data Center Public Sentiment

An interactive, single-page summary of how communities feel about data centers, built from published survey results and project trackers (2025 to 2026, mostly United States).

The page groups the findings into five themes:

1. Electricity bills
2. Water and environment
3. Life in the neighborhood
4. Jobs and local benefit
5. Transparency and control

Each theme can be viewed through up to four lenses:

- **Complaints**: what people object to
- **Wishes**: what people say would win them over
- **Right now**: what is happening on the ground
- **Measured**: what studies have found so far (electricity only)

Every figure links to where it was reported.

## Run it locally

There is no build step and no dependency to install. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Publish with GitHub Pages

1. Go to **Settings → Pages** in this repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and the `/ (root)` folder, then save.

The site appears at `https://<user>.github.io/<repository>/` after a minute or two.

## Edit the data

All content lives in the `<script>` block at the bottom of `index.html`:

- `S` is the list of sources. Each entry is `key: [label, url]`.
- `T` is the list of themes. Inside each theme, `q` holds complaints, `d` wishes, `a` what is happening now, and `m` measured evidence.
- A bar item is `[percent, label, sourceKey, optionalDisplayText]`.
- A tile item is `[displayValue, label, sourceKey]`.
- `l` lists related themes as `[themeIndex, reason]`.

To add a figure, add its source to `S` if it is new, then add one item to the right list.

## Notes on the data

- Nearly all published polling on this topic is from the United States.
- Each survey uses its own wording and sample, so the figures show a pattern and are not comparable point for point.
- Several polls about conditions were commissioned by groups with a position. The page says which.
- Where an original survey was not directly available, the link goes to the coverage that quoted it.

Compiled 18 November 2026.
