# pyimgflip
pyimgflip provides an easyPython wrapper for Imgflip's meme generator API.

See https://api.imgflip.com for more information.

## Examples:

List all memes available by name

    import pyimgflip
    api = pyimgflip.Imgflip()
    memes = api.get_memes()
    for meme in memes:
        print(meme.name)

Post a random meme and print its url

    import pyimgflip
    import random
    api = pyimgflip.Imgflip(username='your_username', password='******')
    memes = api.get_memes()
    meme = random.choice(memes)
    print("Generating a meme from template: " + meme.name)
    result = api.caption_image(meme, "Top Text", "Bottom Text")
    print("Meme available at URL: " + result['url'])
