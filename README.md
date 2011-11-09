My fork of the [Popcorn.js](http://popcornjs.org/) `popcorndoc` plugin.

I have made some changes to the options and regular expression used to
find the Gist URL or ID.

```javascript
// Start by creating our example with the Popcorn vimeo plugin.
Popcorn.vimeo(
  '#video',  // Video element
  'http://player.vimeo.com/video/123456'  // Vimeo URL
)
  // And we'll begin documenting some Gist code.
  .popcorndoc({
    start: 0,  // Seconds to start -- so at beginning of video
    end: 10,   // Seconds to end -- so at 0:10 mark of video
    lines: '2,15,18-25',  // Lines to highlight in the Gist
    target: 'gist-container',  // DIV to load Gist in
    gist: 'gist.github.com/12345'  // URL of Gist
  })

  // A different Gist without highlighting.
  .popcorndoc({
    start: 20,
    end: 25,
    lines: null,   // Highlight none of the lines.
    target: 'gist-container',
    gist: '24680'  // String ID of Gist -- must be a string.
  })

  // Now let's grab a Gist and actually run that bad boy.
  .popcorndoc({
    start: 25,
    end: 60,
    target: 'gist-container',
    gist: '36912',
    runIn: 'iframe-div'  // DIV to load example in iframe
  })

  // And, we'll finally play out this example code.
  .play()
```
