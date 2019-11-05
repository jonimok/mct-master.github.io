---
layout: post
title: 'Orchestrash hackathon performance'
date: 2019-10-24 13:40:30 +0100
categories: Physical-Computing
author: Rayam, Gaute, Thibault, Ulrik
image: /assets/img/group_a/recycle_orchestra.jpg
excerpt: 'The title of our project is "Orchestrash" inspired by the theme of the competition and our approach to solving it, by making individual instruments controlled by recycled materials and "recycling" sound by sampling'
---

## Description

The title of our project is "Orchestrash" inspired by the theme of the competition and our approach to solving it, by making individual instruments controlled by recycled materials and "recycling" sound by sampling.

Below is a video from our group performance. The beautiful video is edited by Rayam.

<iframe align="center" width="560" height="315" src="https://www.youtube.com/embed/xXK0Q3u_iQ0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Technologies

Bela:

- We all used Bela as our sound source and to receive signals form the various sensors.

Sensors:

- Distance sensor to control the lead-voice.
- Pressure sensor attached to a plastic bottle to control the notes of the bass-synth.
- Rotary knobs to control the LFO and lo-pass on the bass-synth.
- Microphone placed in a glass bottle.
- Buttons to trigger samples.

## Instruments

Below, each of us will present their instrument.

### Ultrasonic 'Trasheremin' (Rayam)

The instrument was built using an Ultrasonic Distance Sensor and a ball of trash paper with a pressure sensor stick inside. By one hand (literally) the ultrasonic theremin controls the rate of the amplitude modulations applied to two different signals: one oscillator sending a pure C note and other sending a pure E note. With the other hand, the paper ball -should- control the pitch of the oscillators by changing it with the pressure received when the musician presses the paper ball.

### Sampler/looper (Ulrik)

![Sampler / looper](/assets/img/group_a/ulrik_sampler.jpg)

The sampler was the main rhytmical instrument in the performance. It was a very rudimentary four voice sampler, with four corresponding recording buttons, some of which can be seen in the photo above. One of the sample slots was mapped to a pitch shifter, that I received as a sub module by Thibault, which in turn was controllable by a rotary potentiometer. The samples were recorded live through the analog input on the Bela. During the development and the performance, a contact microphone was used on different sound sources to make the recording. However, any analog sound source could have been used, as the analog input on the Bela supported any 3.5 mm jack connection.

The recording of a sample started when the corresponding button was pressed, and ended when the button was released. After a sample had been recorded, the sample automatically got looped. No time quantization was done due to the limited time frame, so it was quite difficult to get the timing right on the recordings. At the same time, this led to some interesting evolving rhythm patterns, as it was practically impossible to record the samples in perfect synchronization.

### Resonator (Thibault)

![Pd patch of the resonator](/assets/img/group_a/thibault_patch.jpg)

This instrument aims to make music out of acoustic feedback. To do so, a glass bottle is used as a resonator. A microphone is placed inside it, and a speaker lies under it. Routing the microphone to the speaker in Pure Data immediately creates an annoying high pitched feedback. In order to control the pitch, I downloaded a pitch [shifter patch](https://github.com/umlaeute/pd-vanilla/blob/master/doc/3.audio.examples/G09.pitchshift.pd). By mapping a rotary potentiometer to the transposition amount, I managed to find some frequencies producing an interesting sound. But the instrument was just producing a steady pitch, with very few controlling possibilities, as most frequencies would not let feedback grow, and the resulting sound was very week. The best sounding frequency was correspond to a B note, but the rest of the groupe was working in a C minor scale. By adding water into the bottle, I managed to pitch the behaviour of the bottle up to a steady C note.

When Ulrik started to play with his looper in the same room as my resonating bottle, a very interesting artifact was revealed. As my instrument produced sound using an acoustic source, it was in fact reacting to percussive sound. This can be heard at the beginning of our performance video, when the beat starts (0:36). Moreover, when the bass started to play, the bottle was acting differently, with more resonating frequencies. This allowed me to improvise with the others, being able to generate a B sound, and even a higher weird sounding Bb pitch.

### Bass-genie in a plastic bottle (Gaute)

The bass instrument consists of a fairly basic sawtooth wave being fed into a high-cut filter with a variable LFO. The interesting part is the input, and how this was mapped:

The input to Bela was a pressure sensor attached to a plastic bottle, underneath a tight strap. When the bottle was squeezed, the walls of the bottle would expand and push more against the strap, giving different levels to the pressure sensor. The pressure sensor sent voltage variations to Bela where the PD patch converted the voltage variations into integral numbers. The integral numbers were then fed into a "select" object, which sends out a message to the different outputs, depending on the input. The different outputs were then patched to six different sawtooth oscillators, each corresponding to a note in the chosen scale.

![Pardon the birds nest](/assets/img/group_a/Birdsnest.JPG)

The design of the patch could be improved in the future by mapping buttons to transpose it to different scales, more inputs for controlling effects, more advanced oscillators etc. But all in all, I am happy with the result, it did the job and sounded pretty bad-ass.

## Timeline

In the start, we had a vision of how we wanted the instrumentation of our "band" to look like, but we had no idea of how we were supposed to get there. It was through a creative process of exploring the possibilities of the software, within the limitations of the given theme that we ended up with our final concept.

## Division of labour

As the level of knowledge about Pure Data and Bela greatly varies within the group, we found a natural distribution of the labour as we worked on the project. Being able to use the screen sharing tool in Zoom was priceless in order to build on each others strengths and collaborate on the software.

## Achievements

None of us had been using Pd or Bela before, so we all felt like we had accomplished quite a lot at the end of the week, when we were able to construct four interplaying instrument prototypes in just a few hours. During the week, we experimented with different sensors. The hardest one to make use of in Pd was the ultrasonic HC-SR04 sensor, because we had to run an additional C++ program on the Bela to make it work (thanks to Stefano for giving us help to do that). Rayam ended up using this sensor in the performance, which also felt like an accomplishment in itself.

## Challenges

Our challenges mostly consisted of getting the right inputs in Bela to map to the correct parameters in the Pd-patch, within the right values. For instance; getting the pressure sensor to accurately hit the various notes in the bass synth was a challenge due to its very untraditional input method and that it has to start and stop the different oscillators in relation to the pressure applied.

We had a major challenge with getting one of the Pd-patches to work as it should in Bela. Fore some reason the lead synth would not play the same way it did in Pd when loading it to Bela, so we were left with a somewhat sub-optimal solution on that part.

## Performance/reflection

The performance went surprisingly well. The interaction between our instruments ended up better than we hoped. The resonator was reacting to the sampler, as well as the bass synth. We had both a percussive, melodic and a bass instrument, as well as some ambient drone on top.