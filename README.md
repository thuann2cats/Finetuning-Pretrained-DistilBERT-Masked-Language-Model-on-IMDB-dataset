In this [experiment](finetuning-masked-language-model.ipynb), I followed the NLP tutorial on HuggingFace to finetune a pre-trained masked language model on a subset of the *imdb* movie review dataset. The code was mostly from the [HuggingFace tutorial](https://huggingface.co/learn/nlp-course/chapter7/3?fw=pt). For learning purpose, I added my comments to explain the purpose of the code and some cells to check the content the nested data objects, which other learners may refer to if necessary.

Overall, it was an interesting domain adaptation experiment. The pre-trained masked language model originally predicted [MASK] tokens with generic words. But after finetuning, the model learned to fill in the [MASK]s with words related to movies, since it got to see more movie reviews. For example, the input sequence was `This is a great [MASK]`.

**Before finetuning:**
```
This is a great deal.
This is a great success.
This is a great adventure.
This is a great idea.
This is a great feat.
```
**After finetuning:**
```
this is a great film.
this is a great movie.
this is a great idea.
this is a great one.
this is a great story.
```