## Durham Chord Dataset

This is a datasets of chords, to be precise, it consists of 2, 3, 4, 5, 6 pitch combinations using all permutations of 12 pitch-classes in three octaves. All pitch pairings have been created within 13 semitones (12 pitch-classes and an octave) for 2-pitch (12 in total), 3-pitch (66 in total), 4-pitch (220), 5-pitch (495), and 6-pitch (792) combinations across three registers (starting from $E_{3}$, $E_{4}$, and $E_{5}$), resulting in 4755 unique pitch combinations.

We have created this dataset to explore the questions related to consonance and dissonance and the musical and acoustical correlates of this concept.

### Audio files
All pitch combinations have been created using the piano timbre, with _Ableton Live 9_ (a music sequencer software), using the _Synthogy Ivory Grand Pianos II plug-in_. The applied sound font was _Steinway D Concert Grand_. No reverb was used, and the intervals and chords had a fixed velocity (65). The sound examples are available as audio files (mp3) in OSF repository [https://osf.io/4t9fm/](https://osf.io/4t9fm/), see file `audio.zip`.

### Calculated descriptors

`DCD_predictors.csv` is comma-separated text file containing 26 descriptors for each chord with a header (see `data` folder). The chords are ordered in rows and there are 26 predictors in columns. Most of the predictors have been calculated using the models available in the `incon` library (Harrison and Pearce, 2020). Some of them (`CorpPop`, `CorpJazz`, `CorpClas`) are new variants of the `har_19_corpus` and five predictors (`SpecSharp`,`SpecRolloff`, `SpecFlux`,`SpecCentr`, and `SpecIrreg`) have been calculated from the audio files using MIR Toolbox (Lartillot & Toiviainen, 2007). Most of the columns are integers (`int`) but the five first ones are strings (`str`).

`DCD_predictors.csv` is comma-separated text file containing 27 descriptors for each chord with a header. The chords are ordered in rows and there are 27 predictors in columns. Most of the predictors have been calculated using the models available in the `incon` library (Harrison and Pearce, 2020). Some of them (`CorpPop`, `CorpJazz`, `CorpClas`) are new variants of the `har_19_corpus` and five predictors (`SpecSharp`,`SpecRolloff`, `SpecFlux`,`SpecCentr`, and `SpecIrreg`) have been calculated from the audio files using MIR Toolbox (Lartillot & Toiviainen, 2007). Most of the columns are integers (`int`) but the five first ones are strings (`str`).

|Name                    |Type   |Description                                          |
|:-----------------------|:------|:----------------------------------------------------|
|"id"                    |str    | Running number, `0001`, `0002`                      |
|"register"              |str    | -12, 0, +12 denoting the register (see description) |
|"numtones"              |str    | Number of pitches in the chord (from 2 to 6)        |
|"midi"                  |str    | Pitch in MIDI standard, e.g., "52-53" for a semitone|
|"forte"                 |str    | Classification of the chord in Forte system         |
|"gill_09_harmonicity"   |int    | Harmonicity (Gill and Purves, 2009)|
|"stolz_15_periodicity"  |int    | Harmonicity (Stolzenburg, 2015)|
|"har_18_harmonicity"    |int    | Harmonicity (Harrison and Pearce, 2018)|
|"milne_13_harmonicity"  |int    | Harmonicity (Milne et al., 2013)|
|"parn_88_root_ambig"    |int    | Harmonicity (Parncutt et al., 1988)|
|"parn_94_complex"       |int    | Harmonicity (Parncutt et al., 1994)|
|"bowl_18_min_freq_dist" |int    | Harmonicity (Bowling et al., 1988)|
|"hutch_78_roughness"    |int    | Roughness (Hutchinson 1978)|
|"seth_93_roughness"     |int    | Roughness (Sethares 1993)|
|"vass_01_roughness"     |int    | Roughness (Vassilakis 2001)|
|"wang_13_roughness"     |int    | Roughness (Wang 2013)|
|"har_19_corpus"         |int    | Familiarity (Harrison and Pearce, 2019)|
|"SpecSharp"             |int    | Sharpness (Zwicker & Fastl, 1990)|
|"SpecRolloff"           |int    | Spectral Roll-off|
|"SpecFlux"              |int    | Spectral Flux (standard deviation of the change across successive 20 ms frames)|
|"SpecCentr"             |int    | Spectral Centroid |
|"SpecIrreg"             |int    | Spectral Irregularity (Jensen, 1991)|
|"KeyClar"               |int    | Familiarity (Krumhansl, 1990)|
|"CorpPop"               |int    | Familiarity (Eerola and Lahdelma, 2021)|
|"CorpJazz"              |int    | Familiarity (Eerola and Lahdelma, 2021)|
|"CorpClas"              |int    | Familiarity (Eerola and Lahdelma, 2021)|
|"TonDiss"               |int    | Tonal Dissonance (Eerola and Lahdelma, 2021, based on Johnson-Laird et al., 2012)|

