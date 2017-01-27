---
layout: post
title: MidiWriterJS - A JavaScript Library for Creating Expressive MIDI Files
categories: JavaScript MIDI
excerpt: Being a musician and a programmer I've always been interested in the MIDI file format and the possible web applications that could leverage it.  When I first started programming I really wanted to do something with MIDI so I looked up the spec for the MIDI file format but was very intimidated by the details, like woah.
---

[MidiWriterJS](https://github.com/grimmdude/MidiWriterJS "View on GitHub") is a small JavaScript library which provides an API for programatically generating MIDI files.  It supports most features of MIDI including multiple tracks, meta events such as key signature and time signature, velocity control, and more.

## About
Being a musician and a programmer I've always been interested in the MIDI file format and the possible web applications that could leverage it.  When I first started programming I really wanted to do something with MIDI so I looked up the [spec](http://cs.fit.edu/~ryan/cse4051/projects/midi/midi.html) for the MIDI file format but was very intimidated by the details, like woah.  So I shelved it and proceeded to build simpler applications, many musical in nature, which helped me build my skillset.  What I like about about MIDI is how universal it is; once you have a MIDI file you can use one of the many applications available to play it, transpose it, notate it, and modify it.

Flash forward to the present; I thought it would be interesting to see if I could use the Web Audio API to record a single note and convert it to MIDI.  I got to the point where I could detect the frequency and duration of the note  and was ready to plug that data into a MIDI generating library for the conversion.  Thing is, I wasn't having very good luck finding a suitable JavaScript library that did what I needed.  The thought of creating one myself crossed my mind so I went and took a second look at the MIDI file spec.  I pulled up the [same web page](http://cs.fit.edu/~ryan/cse4051/projects/midi/midi.html) as I did years earlier and what do you know, it made much more sense than it did the first time I saw it.  I actually understood how the hex values worked and what byte length meant!  So at that point I was determined to put my programming knowledge to the test and write a MIDI file generator.

## Purpose
By combining this library with a pitch and rhythm generating algorithm you could potentially create unique pieces of music.  With some basic constraints I would imagine you could get something sounding pretty good.  Another idea I had was using this library to create audio "visualizations" of a dataset.  For instance if you set some time based data to a beat, say one day equals one quarter note, and set the data points to pitches/velocity/octaves it could be consumed through the ears or even as written notation.

Of course you could also use this library in a more conventional way and incorporate it into some type of interface such as a piano roll or notation editor to provide a MIDI export feature. 

## Example
The full documentation can be found on the [GitHub page](https://github.com/grimmdude/MidiWriterJS), so I won't go into too much detail here.  Though, here's an example that should give you a basic idea of how the API is used to write the melody for "Hot Cross Buns":

{% highlight javascript %}
var MidiWriter = require('midi-writer-js');
var track = new MidiWriter.Track();
track.addEvent([
            new MidiWriter.NoteEvent({pitch: ['E4','D4'], duration: '4'}),
            new MidiWriter.NoteEvent({pitch: ['C4'], duration: '2'}),
            new MidiWriter.NoteEvent({pitch: ['E4','D4'], duration: '4'}),
            new MidiWriter.NoteEvent({pitch: ['C4'], duration: '2'}),
            new MidiWriter.NoteEvent({pitch: ['C4', 'C4', 'C4', 'C4', 'D4', 'D4', 'D4', 'D4'], duration: '8'}),
            new MidiWriter.NoteEvent({pitch: ['E4','D4'], duration: '4'}),
            new MidiWriter.NoteEvent({pitch: ['C4'], duration: '2'})
    ], function(event, index) {
    // Sets the sequential property to true for all events
    return {sequential:true};
  }
);

var write = new MidiWriter.Writer([track]);
console.log(write.dataUri());
{% endhighlight %}