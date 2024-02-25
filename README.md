# alpha-key.bst

This is a variation on the
[BibTeX style file `alpha.bst`](https://ctan.org/tex-archive/biblio/bibtex/base?lang=en)
(see [documentation](https://mirrors.ctan.org/biblio/bibtex/base/btxdoc.pdf))
that enables you to override the algorithm generating labels
(like [ABC<sup>+</sup>00])
using the `key` field in your BibTeX entries.

While `alpha.bst` gives first priority to the `author` field and uses `key`
only as a fallback, `alpha-key.bst` gives first priority to the `key` field
and uses `author` as a fallback.
The first three letters of `key` become the label.

## Example

For example, suppose you wanted to cite
[the following paper](https://erikdemaine.org/papers/DarkRays_CCCG2023/),
which has an artificial first author representing the entire group:

> MIT CompGeom Group, Hugo A. Akitaya, Erik D. Demaine, Adam Hesterberg, Anna Lubiw, Jayson Lynch, Joseph O’Rourke, and Frederick Stock, “Super Guarding and Dark Rays in Art Galleries”, in Proceedings of the 35th Canadian Conference on Computational Geometry, 2023, pages 51–61.

`alpha.bst` would generate a key like [MAD<sup>+</sup>23], but this mixes
the group name with author names.  With `alpha-key.bst`, you can use the `key`
field to override the generated key to [MIT23] as follows:

```bibtex
@InProceedings{DarkRays_CCCG2023,
  key           = {MIT CompGeom Group},
  author        = {{MIT CompGeom Group} and Hugo A. Akitaya and Erik D. Demaine and Adam Hesterberg and Anna Lubiw and Jayson Lynch and Joseph O'Rourke and Frederick Stock},
  title         = {Super Guarding and Dark Rays in Art Galleries},
  booktitle     = {Proceedings of the 35th Canadian Conference on Computational Geometry},
  year          = 2023,
  pages         = {51--61},
}
```
