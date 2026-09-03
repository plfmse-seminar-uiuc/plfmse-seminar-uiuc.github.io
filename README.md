# UIUC PL/FM/SE Seminar website

Static site for the UIUC seminar on Programming Languages, Formal Methods, and
Software Engineering. Served by GitHub Pages from the default branch of
`plfmse-seminar-uiuc/plfmse-seminar-uiuc.github.io`.

Three files, no build step. Edit, commit, and it is live.

| File          | What it is                                        |
| ------------- | ------------------------------------------------- |
| `index.html`  | The whole site                                    |
| `index.css`   | Header band, logistics box, calendar              |
| `favicon.svg` | Favicon                                           |

Bootstrap 5.3 comes from the CDN and is used only for page scaffolding —
`.container`, the spacing utilities, `.display-4`, `.lead`. Both tables are
styled entirely in `index.css`.

## Local preview

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Adding a talk

Each meeting is one `<tbody>` in the calendar table. The same template is in an
HTML comment directly above the rows in `index.html`.

```html
<tbody>
  <tr>
    <td class="date">Sep 9</td>
    <td class="speaker">Speaker Name</td>
    <td><a target="_blank" href="https://link/to/paper">Talk title</a></td>
    <td class="room">3102</td>
  </tr>
</tbody>
```

Two talks on one date go in the **same** `<tbody>` as two `<tr>`s, with the date
and room cells of the second left empty. That keeps them in one shaded band
instead of splitting across two.

| Marker                                        | Use it for                |
| --------------------------------------------- | ------------------------- |
| `class="next"` on the `<tbody>`                | The upcoming meeting      |
| `<span class="badge-next">Next</span>`         | After that speaker's name |
| `class="off"` on the `<tbody>`                 | A break or cancelled week |
| `<span class="badge-external">External</span>` | A visiting speaker        |

Move the `class="next"` marker each week. Drop the `<a>` and leave plain text
when there is no link.

## Still to fill in

Room number, Zoom link, and who is named on the Sep 9 organizational meeting.
