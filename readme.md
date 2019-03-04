# gpt-2-poetry

## Try the [demo](https://kylemcdonald.github.io/gpt-2-poetry/).

I used [download-urls.py](https://gist.github.com/kylemcdonald/3cbd09752e340849e4b3cb4f12dd8c85) to quickly download the HTML from [poetryfoundation.org](poetryfoundation.org) based on the urls in `romantic-urls.txt`.

Then I used `Parse Poetry.ipynb` to parse the HTML and extract the title, author, and poem. There are some glitches here with newlines being rendered in some places they shouldn't, and not being rendered in places where they should. This notebook saves a bunch of text files to `output/` that include metadata as the first few lines.

Then I used `Generate GPT-2.ipynb` to generate poems based on random chunks from the poems and the seed words. This notebook saves files to `poems.json` and `generated.json`. To run this notebook, first get [GPT-2](https://github.com/openai/gpt-2/) running, and drop the notebook in the `gpt-2/src/` directory. 

Both Python notebooks import from `utils` which I have separately pushed [here](http://github.com/kylemcdonald/python-utils).

Finally, I load `generated.json` and `poems.json` with JavaScript in `index.html` and display the results.