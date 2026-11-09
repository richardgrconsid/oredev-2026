---
title: "Vector Search and Embeddings Talk"
type: talk
event: "Öredev 2026"
date: 2026-11-05
description: "Embeddings and similarity search for text, images and music."
tags: [talk, oredev-2026, embeddings, vector-search, machine-learning]
topics: ["[[Embeddings and Search]]"]
source: Pocket
status: unreviewed
---
> [!summary]
> A single participant, a developer and trainer of thirty years who works in AI and machine learning at IBM in Scotland and is an AI and Cloud MVP at Microsoft, gave a talk on vector search and embeddings. The core idea: an embedding model turns any data — text, images, audio — into a high-dimensional vector of floating point numbers, and similarity between those vectors (usually via cosine similarity over approximate nearest neighbours, as in Spotify's Annoy) lets you find "things that look or sound like this" without needing explicit rules. He walked from text embeddings through image and face embeddings to a hobby project generating DJ mixes from music embeddings, and argued that keyword and vector search are complementary rather than one being better.

## Embeddings and similarity: the basics

- An embedding model takes data in and returns a high-dimensional array of floating point numbers; the same holds for text, images and music.
- Typical small text embedding models have around 1,500 dimensions; the speaker suggested visualizing the idea in three dimensions via RGB, where similar colors sit near each other.
- Similarity can be computed with Euclidean distance, cosine similarity, dot products and others; cosine similarity compares only the angle between vectors (e.g. "dark azure" and "azure" score as the same), while Euclidean distance cares about proximity in space (e.g. cyan closer to azure than dark azure).
- Background: the speaker got into embeddings after seeing a former colleague, Martin, then at Spotify, present embedding-based similar-image search built on Spotify's Annoy library, which uses approximate nearest neighbours and is equivalent to cosine similarity after finding values. The code is available on GitHub.

## Demonstrations and examples

- **Words:** using the Embed Together site from TensorFlow with a Words2Vec-EN dataset of 10,000 words at 200 dimensions, t-SNE dimensional reduction to three dimensions shows clusters — numbers, bike parts, TVs, and music terms like sonata, flute, piano ensemble and classical concert. This is unsupervised learning: finding patterns in data.
- **Images:** roughly 16,000 images embedded at 512 dimensions, reduced to 2D, cluster by visual similarity; images of dogs group together, and dog faces (with eyes and nose) form their own tight cluster — a strong feature for the model.
- **Music:** files from music sessions embedded and labeled by brand; similar-sounding songs clustered, with many from one label appearing together.
- **Text in the notebook:** with the text-embedding-ada-002 model called via API, an array of sentences in several languages (including Swedish, German, Italian, Danish/Norwegian and Dutch) was embedded; the vector came out as 1,536 dimensions.
  - Cosine similarity of a sentence with itself: 1.0. Similar-sentiment sentences: 0.99, 0.91, 0.99. The Swedish sentence compared against a different English sentence dropped to 0.69.
  - He stressed the score is the cosine angle, not a percentage.
- **Cross-language power:** you can search in Swedish and get results in English because sentence embeddings capture meaning.
- **Azure AI Search index:** questions and answers each with their own embeddings. A keyword search for something similar to "how is AI applied in agriculture" surfaced "how is AI applied in agriculture" first, with the actually relevant answer not found because the wording differed; another query surfaced "how does a farming tractor" style answers, and an Italian query scored 0.87/0.99 versus 0.88 for keyword results.
  - Conclusion: keyword search is "incredibly powerful"; the speaker compared them to relational versus non-relational databases — different tools, and an ideal search system would combine keyword and vector search. LLMs can also be used to improve search results.

## Image classification and what features reveal

- **How classification networks see:** a CNN's early kernels detect edges, vertical and horizontal lines; darker layers detect shapes; later layers detect features like cat's eyes, dog's ears, dog's tails, faces, glasses, cars and bones. From these features the network predicts a class, such as cat.
- **Stripping the classifier:** deleting the final classification layer (a linear layer, 10,000 × 1,012, i.e. 1,012 features per class, following 18 convolution layers) and keeping the embeddings gives similar-image search that works in a few lines of Python.
- **Setup:** the pre-trained model recognizes about 500–600 common objects, images are transformed into 224×224 floating-point tensors, and the model is set to evaluation mode.
- **Results:** on dog images the classifier predicted British boxer and bully breed (boxer right, bully wrong); similar-image search returned other similar dogs, including an Irish Terrier query.
- **Transfer to auction cars:** the image-classification model built for an online auction company was "fantastic" at recognizing vehicle type (e.g. Honda and Nissan X-Trail) because it had learned identifying features, delivered in a few lines of Python without graph-algorithm knowledge. The earlier auction use case added a map so buyers could be shown similar items.

## Face embeddings and the Terminator demo

- FaceNet turns faces into embeddings, enabling similar-face search — found in a few lines using a library.
- The speaker's idea for his company's conference booth was a Terminator that recognizes speakers, built by collecting consent from speakers at the conference.
- He built it partly on a crowded Central Line train home, drawing stares from other passengers.
- It generates a reason why each speaker is "deeply scaring us" based on their speaker bio; demonstrated at the Melbourne booth, with the speaker waiting about thirty seconds.
- The agreement: tickets for people who appear at the front in the video.
- The EU ban on public biometric recognition in public places raises a lot of problems for running it; the speaker's view: it could be a problem, and it is a serious issue that people can exploit the technology.

## Music embedding hobby project

- **Origin:** about a year and a half ago in physical time, building something more musical with Spotify to create DJ mixes from songs that mix well together.
- **Spectrograms:** the waveform is amplitude over time; the mel spectrogram shows frequency over time, with low frequencies at one edge and high at the other, making drums, guitar, drops and song sections visible.
- **Genre classification:** two versions — version A, and version B trained on the best classification of the song, which produced a stronger pop/blues classification.
- **Song search:** MP3s embedded, with metadata from DJ software Rekordbox (artist, crafted EDM beat, rhythm, bass) fed into embeddings stored in Azure AI Search; searching for one artist (DD People by a Property) returned similar tracks by the same and other artists (including rock tracks: Therapy, Dylan, the Beatles).
- **The limit:** when you start mixing, it can sound "absolutely terrible"; for a scheduled presentation he had to fake the entire mixing.
- **Music theory fix:** the circle of fifths, created around the 12th–17th century, explains which chords sound good together; C major and A minor share all the white notes, so they mix well. DJs encode this in a Camelot-style catalog with 12A/12B, 11A/11B pairs, effectively the same thing.
- **Approach:** extract the mel spectrogram, derive chords from the notes and frequencies used, apply chord-progression and chord-analysis logic with a shared-chord ratio, and recalculate — the speaker had a compiler dig into the code rather than working it out himself and had not delved into it fully.
- **Audio workstation:** he uses a DAW, and ran his GPU (described as "thirteen miles an hour", i.e. quite powerful) for three months to do the music separation.
- **Separation and lyrics:** music separated from vocals, so sections of lyrics can be isolated; he also ran speech-to-text (not yet added) to enable text search for lyrics by words or by genre such as dance or indie.
- **Section-based mixing:** selecting a section and searching for compatible tracks across other songs, though "they're not that great" — some do sound nice.
- **The one he was pleased with:** a James Hunt vocal; he noted he had probably also found it on YouTube.
- **Next experiment:** using Better Off Alone by Alice Deejay for its distinctive synth tracks, dropping a similar section alongside and searching for sections with lyrics.

## Open questions and loose ends

- Whether the EU ban on public biometric recognition makes the Terminator booth unworkable, or how to handle consent — unresolved; the speaker acknowledged it could be a problem.
- How to improve the mixing algorithm — chord progression, chord analysis and shared-chord ratio remain under-explored for him.
- The YouTube blocking issue when using voiceover, which affects how demos are played back.

## Next steps

- The speaker will be around from 2 o'clock for the rest of the day (of the recording day, 2026-11-05), though he has to be at the party.

## Mind map

![[Vector Search and Embeddings Talk - mind map.png]]

## Sources

- [[Vector Search and Embeddings Talk - summary.pdf]]

## My notes

- 
