# Pokéboard credits

Pokéboard is a fan-made Pokémon board game. Original Pokémon names, characters, sprites, music and other original material belong to their respective rights holders. This notice does not grant rights to third-party material.

Game engine: Godot 4.7.2 (MIT). Full engine and component notices are in GODOT_LICENSES.txt.

The following asset acknowledgements accompany this build.

## assets/badges/SOURCES.txt

Original Pokemon FireRed/LeafGreen Kanto trainer-card badge icons.
Prepared 2026-09-30 from the pret/pokefirered FireRed disassembly.
Pinned revision: 037335f4c725d7c9aecdac87066f2002b4bd7e14
Source download: https://raw.githubusercontent.com/pret/pokefirered/037335f4c725d7c9aecdac87066f2002b4bd7e14/graphics/trainer_card/badges.png
Original SHA-256: 213fcf06d1125b42df17c9de249fa8cd76a428da2b38582a04c9b1f52b2130c1
Original source sheet: firered_badges.png (128 x 16 indexed pixels).
Individual badges: 16 x 16 indexed pixels, with the original RGB palette.
Palette index zero marked transparent, matching original BG rendering.
All visible pixel indices and colors are preserved; no resampling or recoloring.
FireRed/LeafGreen displays these original badge icons as polished silver.
Use nearest filtering when displaying the sprites at a larger size.
Sheet columns follow flags BADGE01_GET through BADGE08_GET, left to right.
Original draw implementation and mapping:
https://github.com/pret/pokefirered/blob/037335f4c725d7c9aecdac87066f2002b4bd7e14/src/trainer_card.c#L1465-L1483
https://github.com/pret/pokefirered/blob/037335f4c725d7c9aecdac87066f2002b4bd7e14/data/scripts/set_gym_trainers.inc

File | Source rectangle (x, y, width, height) | Gym | Leader | Prepared SHA-256
boulder.png | (0, 0, 16, 16) | Pewter City | Brock | def82b3602ed6cbeeb1fa30ecf1d2e95326889d432d84782025972a8b4dd1703
cascade.png | (16, 0, 16, 16) | Cerulean City | Misty | 4e8e16af51c3ef1d92c075a924b5ccbdd1062dc5519bfc26bcdaf5becadf63bb
thunder.png | (32, 0, 16, 16) | Vermilion City | Lt. Surge | d1a81a2703c80517bd85234c599ed94f448eb6a54ae2917d4d9492ecf20e58e6
rainbow.png | (48, 0, 16, 16) | Celadon City | Erika | 7ba0b26fdf66f2dbf0550daea23c9bbda679ee198bee19f916351a2e141ee674
soul.png | (64, 0, 16, 16) | Fuchsia City | Koga | 4669928ff13269b0ee0e26612f0da2ffa353850224b102765b1af664a0bad5d2
marsh.png | (80, 0, 16, 16) | Saffron City | Sabrina | 7e15c85555928bf4bcc866909ac536196f1392a7dae3642002ebc28633d32d53
volcano.png | (96, 0, 16, 16) | Cinnabar Island | Blaine | d7249388e6c7d42bd19525f9d103821a703c69800bc8f33265748922571d8398
earth.png | (112, 0, 16, 16) | Viridian City | Giovanni | b96bd53fe44396ccd61492f3de595a5335c91b59eb9f5cd8238b96fff0b91d26

Preparation: python tools/prepare_badges.py (offline from checked-in source sheet).
Refresh source: python tools/prepare_badges.py --download (pinned, hash-verified).
Original Pokemon artwork belongs to its respective rights holders.
Stored locally for offline gameplay; no network requests occur during the game.

## assets/music/evolution_sources/GYM_SOURCES.md

# Gym Leader music

The FireRed/LeafGreen Gym Leader score uses [mus_vs_gym_leader.mid](https://github.com/pret/pokefirered/blob/master/sound/songs/midi/mus_vs_gym_leader.mid), voice group 155. The victory theme uses [mus_victory_gym_leader.mid](https://github.com/pret/pokefirered/blob/master/sound/songs/midi/mus_victory_gym_leader.mid), voice group 171. Both use their published instrument samples from pret/pokefirered. These offline renditions preserve notes, tempo, panning, and loop markers; they approximate the original GBA envelopes and synthesis. Rebuild with `python tools/prepare_gym_audio.py` (NumPy required). Source/output hashes and loop frames are recorded in `gym_render.json`.

## assets/music/evolution_sources/SOURCES.md

# Evolution audio sources

Prepared October 4, 2026.

The intro, evolution theme, success fanfare, and reveal sound use the published FireRed/LeafGreen MIDI scores from [pret/pokefirered](https://github.com/pret/pokefirered). Original game music, effects, and instrument samples belong to their respective rights holders.

The WAVs are an offline rendition of those scores with the source horn, trumpet, timpani, snare, cymbal, and square-wave PCM samples, plus recreated PSG pulse and programmable-wave instruments. Notes, tempo changes, note velocities, channel volume, panning, pitch bends, and loop markers come from the score. This is not a recording or bit-exact emulation of the original GBA audio hardware; envelopes, pulse antialiasing, pitch modulation, and the final mix are approximations.

No external synthesizer or soundfont is required. Rebuild offline with `python tools/prepare_evolution_audio.py`; NumPy is the only additional dependency. Source and output SHA-256 hashes, native loop frames, and WAV format details are in `render.json`.

The [original evolution scene](https://github.com/pret/pokefirered/blob/master/src/evolution_scene.c) calls MUS_EVOLUTION_INTRO, MUS_EVOLUTION, SE_EXP, and MUS_EVOLVED in that order. The game helper puts all MUS cues (intro, evolution theme, and success fanfare) on Music, and the SE_EXP reveal cue on SFX so each volume slider remains independent.

Source files:

- [07.pcm](https://github.com/pret/pokefirered/blob/master/sound/programmable_wave_samples/07.pcm)
- [direct_sound_data.inc](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_data.inc)
- [keysplit_tables.inc](https://github.com/pret/pokefirered/blob/master/sound/keysplit_tables.inc)
- [midi.cfg](https://github.com/pret/pokefirered/blob/master/sound/songs/midi/midi.cfg)
- [mus_evolution.mid](https://github.com/pret/pokefirered/blob/master/sound/songs/midi/mus_evolution.mid)
- [mus_evolution_intro.mid](https://github.com/pret/pokefirered/blob/master/sound/songs/midi/mus_evolution_intro.mid)
- [mus_evolved.mid](https://github.com/pret/pokefirered/blob/master/sound/songs/midi/mus_evolved.mid)
- [programmable_wave_data.inc](https://github.com/pret/pokefirered/blob/master/sound/programmable_wave_data.inc)
- [sc88pro_french_horn_60.wav](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_samples/sc88pro_french_horn_60.wav)
- [sc88pro_french_horn_72.wav](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_samples/sc88pro_french_horn_72.wav)
- [sc88pro_orchestra_cymbal_crash.wav](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_samples/sc88pro_orchestra_cymbal_crash.wav)
- [sc88pro_orchestra_snare.wav](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_samples/sc88pro_orchestra_snare.wav)
- [sc88pro_square_wave.wav](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_samples/sc88pro_square_wave.wav)
- [sc88pro_timpani.wav](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_samples/sc88pro_timpani.wav)
- [sc88pro_trumpet_60.wav](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_samples/sc88pro_trumpet_60.wav)
- [sc88pro_trumpet_72.wav](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_samples/sc88pro_trumpet_72.wav)
- [sc88pro_trumpet_84.wav](https://github.com/pret/pokefirered/blob/master/sound/direct_sound_samples/sc88pro_trumpet_84.wav)
- [se_exp.mid](https://github.com/pret/pokefirered/blob/master/sound/songs/midi/se_exp.mid)
- [voice_groups.inc](https://github.com/pret/pokefirered/blob/master/sound/voice_groups.inc)

October 4 update: evolution playback no longer uses the SE_EXP reveal cue at the user’s request. The source/rendered WAV is retained for reproducibility, but the evolution audio helper only plays MUS_EVOLUTION_INTRO, MUS_EVOLUTION and MUS_EVOLVED. The Gym Leader score and additional samples are documented in GYM_SOURCES.md and gym_render.json.

## assets/pokemon/shiny/SOURCES.txt

Original FireRed/LeafGreen shiny front and back sprites from PokeAPI/sprites.
Stored unchanged at 64x64 with original transparency for offline gameplay.
Source repository: https://github.com/PokeAPI/sprites
Original Pokemon artwork belongs to its respective rights holders.

front/1.png | Bulbasaur | c954940ab5c4b0e475831ab26844415f1de1f254837c7bf6cb43422feef6f16b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/1.png
back/1.png | Bulbasaur | 4b992cbec7d251f640125d2313da2e979878e28e1a60f83faf96545f20b9b8a9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/1.png
front/2.png | Ivysaur | f2d5656b1b1d34a2f70652f4b5e2d8f565df3c00cd5dc504807566b533734c4b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/2.png
back/2.png | Ivysaur | 0fbd3d59f57e1611746537d51f98f53ff41879293864064fe6c87248ff449b32 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/2.png
front/3.png | Venusaur | c79cfb027fd7ecfd303f95954908accdf075f3d0f75e8285e27abe7722477e74 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/3.png
back/3.png | Venusaur | 2ae273f94c8b570f5c733f6443fc3b2be9a2c4f3c516859f78ba4c9245088b00 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/3.png
front/4.png | Charmander | 7a8af7f483787ef3ce92052a811230b4d619d504b4c14d3a5b091dc33417e5ec | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/4.png
back/4.png | Charmander | 3ca7f51e09a737f26b8cece93e1234f90365ce0767f10b7bc97eea5af9d561d0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/4.png
front/5.png | Charmeleon | 3a3f881545f5a02e6d3d42196bf04f04b12d9f98002b4e5f758a149359136ea1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/5.png
back/5.png | Charmeleon | 3f1d8b9db67cda712a3699a5da99c2042f79e6bb73b78826a3777140ac73e5f7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/5.png
front/6.png | Charizard | e27ae0732401f2aefa734318a4c3c88c011d39877a43a6f42db6a5e274582b44 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/6.png
back/6.png | Charizard | d7306c16856a32fc5fc5378dd37fa26bb881ae4f5e82747681eda7a0b5793dc3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/6.png
front/7.png | Squirtle | 1ad5e4a51806d52138d82a1f18553a6622dfe848196d1cf39e163e6918c08854 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/7.png
back/7.png | Squirtle | 4d3b6f4cf78005fff8f00a5d8aaef4acb242488757d25881e0a9adac7620a0b4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/7.png
front/8.png | Wartortle | ea6a52c1645fd694ce3433c35874c7d00464feba7ba35b7035c0153f1223d330 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/8.png
back/8.png | Wartortle | b298934eadc6cdb2aa20102d9fe38b6ca0f348f64e9f1a7acd8b0bb8cbd5114e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/8.png
front/9.png | Blastoise | 0584bcf7b9daf065d30a9aa9acad383676bafff08d24aab16f6a16d47932d7b5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/9.png
back/9.png | Blastoise | 9a04e4ba3e4460b93e6c0d07154dd768c6bea59b17ebb4d5a59d257d9ee67dbb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/9.png
front/10.png | Caterpie | e05aab6440d74e45fe3ac98427a5481e4c1e77143938d9bd00feb6e22189e95f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/10.png
back/10.png | Caterpie | 2c561e6734cdda8fb39eed07e6697ddbfbb2a87c9d74b1ffb4405018cc4c1c76 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/10.png
front/11.png | Metapod | 54e10a610d4346da345d869ff63fa250f2d54c1dad88893122bd338542a3bfe9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/11.png
back/11.png | Metapod | 814fb5309c5062ac1763bab222e99f1f2b97d3e68681e5f5bfaed999faaea64a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/11.png
front/12.png | Butterfree | eb7323009ef98bfffa96254f685e9abe902b83fbddc5392ac8afcaaa397e5d46 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/12.png
back/12.png | Butterfree | 0be029a87b636dd3c6be2637db8b4795773d782ef5d0bab17dd6b84009e04a38 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/12.png
front/13.png | Weedle | 831120d53b3fa3ad203a6f45be1e8665ee4614078f150a06883bd2c6fdb75521 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/13.png
back/13.png | Weedle | c90da59ed57e0449721f9d78cdc4a58b0c3e34db0ed9c60f5722035a374d8ca3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/13.png
front/14.png | Kakuna | 046e604066c5827984fe45a669f7d2836477bfc784b6c7998b132c0b2cae5276 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/14.png
back/14.png | Kakuna | 6f8380fd4419fdf5f64e450fe9a5c0bc2a04538a0b31c0aa1625bea7eb90ac5d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/14.png
front/15.png | Beedrill | c8b4dce9cdbf602447ab5e3512fd6776946573f3225e50c992d738d5632e7a81 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/15.png
back/15.png | Beedrill | 76756c469e5d1c266cc16be97278a4c092ee4c253804fa227e300e9c3c6969bc | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/15.png
front/16.png | Pidgey | ad7e93ef09a513b03cf6eaa7f96f16c89a76b9543baee9400dc348b71c658ce7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/16.png
back/16.png | Pidgey | 3e174b584f818aa0722310666d80b613436c993418f56ecf2af45145ae16e836 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/16.png
front/17.png | Pidgeotto | 09903c48823606e405a20b29a16d651250adde564083a47bb508f85314766248 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/17.png
back/17.png | Pidgeotto | 44ad9a9e5010504b385b9eb44f329fe59e447376b911ede25c2d89635639516c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/17.png
front/18.png | Pidgeot | ffa6a79c8c172ac7110c1c81892bfc917a8c098c697e55a1c77d96df9568c5bb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/18.png
back/18.png | Pidgeot | 9b7bebdc9ddce581b2695ebc8feef686f861347dddf059d92966c7ebe90d38fa | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/18.png
front/19.png | Rattata | 07d1b42faf814c39c7690186f793b99ab99743084aab3218ac84cae8df17b949 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/19.png
back/19.png | Rattata | 6846cb8a4035b6ae607f02f96bbc52bc6bf9685c3ab58c2a9126ec0588321f04 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/19.png
front/20.png | Raticate | 2c8313164808fc9b35f0c6400124d7ba4aab76cf97d2667bc81081802a56ba15 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/20.png
back/20.png | Raticate | 2762fae5b5bc13b714f09da0a98952c3029a57de26e09d463bd00f492a5fcb21 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/20.png
front/25.png | Pikachu | d7e0acf3340e1d3dec340ffdbc62661443a8f79093d5824daa491c26eff83034 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/25.png
back/25.png | Pikachu | ec41691ad9044bc90c623519f5ca9d6e39b782ce79a56eb361f1e1c226f8229b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/25.png
front/26.png | Raichu | 07dd4c426905bbcb68c5b85a1df8334e8cc98200a91da7646669be37c43b077f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/26.png
back/26.png | Raichu | 6f182c2f508e2856ecfcfdd3d51fe0f0d01fb8228041ed23498d0dcb23885691 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/26.png
front/27.png | Sandshrew | 8a0d67203a924b80b7ef777bb919d21915add7062f0e426182db5219860a5f08 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/27.png
back/27.png | Sandshrew | 7d410b4e76fe803915b6bf32eab29a6fde4e3d0310f8a601ddf259e411d4aca4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/27.png
front/28.png | Sandslash | 1aa26d5aa2717d17635329d7ef00e724f20c76429c0ecbee32cadebea0cd6e93 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/28.png
back/28.png | Sandslash | bad7c5c0db830791ddf0efa63fd294c85870e3424ece3ab9931a76bc166a0e97 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/28.png
front/31.png | Nidoqueen | 0a60b26f8f202ab2a99c890525310a8b4b1ee8d166a3c22e4c8cad4649ff8fa8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/31.png
back/31.png | Nidoqueen | 384660401db38ca033fa82282c7d62730b54babf01fa18e4d086a491f6182d6a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/31.png
front/34.png | Nidoking | 43e319154961d4dfdde3fb3c124c1c209afc0f57cc1a9fb469c9026c94a86629 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/34.png
back/34.png | Nidoking | 76d0e9dbf2e1a5e5c0e43e21ff80783b584aa9b882780f3fe38593f52c5f7d13 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/34.png
front/35.png | Clefairy | 5d4fdcad8af5244758be2107dc241b586aaf603d9e2e6784ef544e0611309c9e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/35.png
back/35.png | Clefairy | c038773ee9467be783f0b189f1f92effe3ec1930a0b7d9bdab4f74642232c313 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/35.png
front/36.png | Clefable | 5b8d1846016b3b6e27fab41ee333cc466aa95eaff299bcfadec7a50fc52397f7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/36.png
back/36.png | Clefable | fea19af81229e9430836ced4ad2cf5ada649e82bb1e0753ce08e387d4cf1724e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/36.png
front/37.png | Vulpix | af97c9df284b7b3cc9f5797924554ce2672d8d55eaa63a5fced1cc23973fc187 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/37.png
back/37.png | Vulpix | b34b81621f63bd033ba66a8ce8118908d7038e5748645909ed4cfa3a7d3bbb08 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/37.png
front/38.png | Ninetales | 08772a09c1e943e5b95556fcc29ff85a4b61991f96f17fa480c644d255a2de30 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/38.png
back/38.png | Ninetales | ec8bdc3658bdada9b57779d4ee34f2fd35661edd06726fa68460930c5a49747a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/38.png
front/41.png | Zubat | 254364d73ec1579686cd09715321fae8761d39efb833f58ec0396382ffe956c7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/41.png
back/41.png | Zubat | dd670c4a1227dcd131aa90539696fbb56d0a5fe21c86660e63d80570f1a6c602 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/41.png
front/42.png | Golbat | 4e447b2fceecc199773bc047d843b7f6efafb6f14bd02f216280af9b7014e0f5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/42.png
back/42.png | Golbat | 4d9786c28bee10129f50fe6114f651f238491ff76038970d49197228688d41b7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/42.png
front/43.png | Oddish | 3768ae3f2645305478f8fd16f841602af8dc6138839500ab1e25c30ef5663497 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/43.png
back/43.png | Oddish | 73cc6af97cc5d8967ec0d668c5f64046e93f3d33b843502c444a8804b956e1d2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/43.png
front/44.png | Gloom | abae59b7f9e404fe1e9ccb477a49359acef751693191bb9e268712a18c81e24d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/44.png
back/44.png | Gloom | ae0e2b178efb624ba18678f88192f800bdb74343e5653c4179587170926dcdeb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/44.png
front/45.png | Vileplume | 2b28f705023031cfcbaec40470a8d66c70d697b8769e09f7fb47d3916baef59d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/45.png
back/45.png | Vileplume | 4b3cda8e2f0653d6a8c91398c07fdacaaae28c8160c095d07f8613e643602f7f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/45.png
front/46.png | Paras | 8cc2e06ca6ef6d7ce1fd75cdfb3ec8674382857672f81a71c9b877306c4504f3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/46.png
back/46.png | Paras | 30245ca67ebf53ed42da08bae5e4f6f111965b4af7af70e64684be2c8dd9ed1e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/46.png
front/47.png | Parasect | 561ce5c13135e2f517ae0da5a1563cc8343e57d22ba434cf103c2d3509f3b60a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/47.png
back/47.png | Parasect | 208e2223fa9b0bb3a8871d38fa8e5afe8b9297d1ee8e74b379db12bd96642664 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/47.png
front/51.png | Dugtrio | 2add67f818b71d2ea4aff280a0af84c3fda53b9ce3e62a6b5acc5c5cd9a82675 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/51.png
back/51.png | Dugtrio | e7cbe8709c6dea42e0ca9e7a1fe22d96722c684e6222eeae22d106957b28b7c8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/51.png
front/58.png | Growlithe | 3f70ff4402d42ef67d14bdaebb7ef77b9ecd9bcf279c4c18a43aeae995e07302 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/58.png
back/58.png | Growlithe | 58df0591f30f56b63e9b28824015254b6285a4d980b115ad2d9599535284f26c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/58.png
front/59.png | Arcanine | edeca209cf8575401c859ad5c7802cafed6a560cb72702ec2f3bae0d51675cc6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/59.png
back/59.png | Arcanine | bc793527404d62672f5c18a3ba4b94dae4c567b2f39fd4926075c2af2016b6f2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/59.png
front/64.png | Kadabra | 9352a8bf30b5f827b40a3977ab155881a4ea6f97b3aff16354b789957416fb35 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/64.png
back/64.png | Kadabra | 48e7051be2198b6111adc3f90aa52d012db761cd403c24a5c8e6aba2eb69fce2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/64.png
front/65.png | Alakazam | fcf16e568f0e5c8f1b0a2ff712c13681b7be810bc27e3c865102bac28654f71d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/65.png
back/65.png | Alakazam | 62e5725017fc2c94a9741e4d29de00e20c39e4a8e7154611a61a4bd806b4b1ee | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/65.png
front/68.png | Machamp | b1fdd80de544c3824fb45258ddbbf11819d385cf763e0b42b1a923cfb36bd2f7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/68.png
back/68.png | Machamp | 3be81da6e946a658a917876b0048360565a5349ab49d11fee8ccc18ff7539869 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/68.png
front/69.png | Bellsprout | 3a14494d3af85e8e5f9ad361f8ef1ba36fef85ba63ee94c78b7f9d4164c7c5af | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/69.png
back/69.png | Bellsprout | 9b065bab740422c509d82f518b53de69a13915a8f1a20a3fd7e9c98d6798928c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/69.png
front/70.png | Weepinbell | 0db86f213e5b50f04d2485fc268fafa3bb4d1a79a0c4360135b9e5f7068ec91d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/70.png
back/70.png | Weepinbell | e22ec404a38fcd03d1afacf69f8540febb9aa25883dc549a4d0b659a8b90b5fe | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/70.png
front/71.png | Victreebel | 9d72bcb34c41f69e034309a8eba22d7a77d6cb702e1946d7bbd98f00e172edca | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/71.png
back/71.png | Victreebel | 7b91a618e3645468faf56fd019cc213067472c849696953be735d6e65acf4c65 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/71.png
front/72.png | Tentacool | 95299556bf41274ac7d40d80ac8d48e53cce99bdb0e6eb31b07467515bc3934a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/72.png
back/72.png | Tentacool | 4738b51ef4078e16a572de511271a7b2bcea4b84486f2a7bda5980c46db114d8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/72.png
front/73.png | Tentacruel | 504ed467c9ea6704167513c61b6ff518ca389ee43624b91ebdf43ac8fa73e627 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/73.png
back/73.png | Tentacruel | 23071722cbdb3d28e1bd283e3b709b9903a991629059aebbc116f83b29885f93 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/73.png
front/74.png | Geodude | 30cc8428440ffbe18ca1d8dadb4dde907a8ce748a19ceb2969ed23544e2b82b1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/74.png
back/74.png | Geodude | 31ef8d9f13aaab6048f05bbbfb5724fe778e0f4b9e2eb8fd56cceb930d3ae550 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/74.png
front/75.png | Graveler | c73e8bf7c56559dbc1fa261594c5e1d94918df64a802a3e9d3fbea9f55c438b5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/75.png
back/75.png | Graveler | 94e633f5989a991369b9f204389bacd7430519ef0b627327afd12508ca929f64 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/75.png
front/76.png | Golem | 19cc5b83ff41a280f5f6c08860b885d4adcc77c201e56427400f9bd1fb8d8b25 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/76.png
back/76.png | Golem | 891fc4267de0b95545d1627bd6099d829e40b0fc0423a8cb33e4f5d338cf8fb2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/76.png
front/77.png | Ponyta | 704b6ace10ae1840d4fdc90094ac3b554290bc07811e453f156a1ee603459514 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/77.png
back/77.png | Ponyta | a5872a3aa846cdd62cd78b92035404496f4192a8303da2f4a62aad0783ac5c76 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/77.png
front/78.png | Rapidash | b03358e91a0f60561b7a9ccc2d150c7f15b231b5e8a3e5ace01e0942d24f5680 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/78.png
back/78.png | Rapidash | 92348959c832b25fd433cfad9d3d520f0cd02c9f3c52d890fb7a838bb75ff059 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/78.png
front/84.png | Doduo | 9cf1deb646af8ab4d4592b2b22ab26f49f099c480a47562e1f0914738ec5772d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/84.png
back/84.png | Doduo | 11bb4d479214cd25916a2cd74cc86cd1e238599b65cdc93824ec0fc09966c921 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/84.png
front/85.png | Dodrio | eb0b1c5386d4d895fe96eb14adc624b2b23e010ba42999f32e079ae668ffcbde | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/85.png
back/85.png | Dodrio | e66d4a1dfae4ae96ecae27fc8328dc747188505c17fb1bf8b1a5b63d77b191d0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/85.png
front/87.png | Dewgong | 27f13070c88203216bb8b7a96efacaef4412258bcd930f40e782cf36ec80dbe5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/87.png
back/87.png | Dewgong | 1d8b09b40f1bd5ca5f89ae03741c0d3faba29f7634ca78a27ff186285664cd47 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/87.png
front/89.png | Muk | 61e00a118c7d7fac7111e540b24cbacca50507384481934272e95e490404cdcd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/89.png
back/89.png | Muk | d80b3f5b5cbcc35b7bc5698261d9e2130de65cbc353834d7675d1c784c0799d4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/89.png
front/91.png | Cloyster | bd325f93641c1d3c64f5c2faa5bc419594b02ffbd06459d1e1da31a1b70ee172 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/91.png
back/91.png | Cloyster | f33be334710a650393f16d03b38108556b5ad54ee6cc5b1442a5522da5e754e6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/91.png
front/94.png | Gengar | ae4188d275724588b76020f77812b6687b85fe9cf57f0440a007c9577f3770af | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/94.png
back/94.png | Gengar | ced0eab2e94291c84a41e9f81d3055c2f80feaaf05f07fa4f90ff37331e36767 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/94.png
front/95.png | Onix | 4e49e63881dddc26fa8493bdabf4cbd4badb0e35511fe2ab214363d60a969b14 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/95.png
back/95.png | Onix | e8d64b60e78298005f57dfb5f46c5b94cd00b292281cef94d924eda25cc2bfb8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/95.png
front/96.png | Drowzee | e2c08750f38f0f7cbf5de9825fe20853e2696f69a15ba491c5e6e0939e2eb0f7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/96.png
back/96.png | Drowzee | d7418d056baf6312152132547067b881015e2880ba79edc1336489c01e4af051 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/96.png
front/97.png | Hypno | ed70822b58296056b0b961e08a0c1a81b136e8a899187941aed4512479aaa8a6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/97.png
back/97.png | Hypno | 91ae74defdc2aeee2d79c8699d79ec81da1758007438559d38fce30b239003e9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/97.png
front/100.png | Voltorb | cb0b457809fe4af019bed0c82bac596406d9f1063e871b7b368218e7bcf271bb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/100.png
back/100.png | Voltorb | d54fd02cb8cc6100f93c59a04d4489515aef1f95a07b20c9639f4a631f1da0f2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/100.png
front/107.png | Hitmonchan | d04b20105d064db61674a56126a5e0bb5bb311c4d80bae6d2e3b0e9d37da5724 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/107.png
back/107.png | Hitmonchan | fef7f1a5c0315758a1ec64d1f64a5bf9abe81aad959c7f71ee96c9cad68f367d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/107.png
front/109.png | Koffing | 4b0c361a5f60a4d1ddf6172523626d412f38e908616d2ff8305807a28c7e1341 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/109.png
back/109.png | Koffing | 401a97d99cbf32b8b5acbb209951da5de0de3a691d27729cc8a05313e1575236 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/109.png
front/110.png | Weezing | 7e6d2a4e300749242aa523855d87e6c06ac0a1e909a81cfb0c563242b2d91900 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/110.png
back/110.png | Weezing | cb3e64db6105abb517011d578fba0a1f18d67ccde9637191b9bd787db2de4a1d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/110.png
front/112.png | Rhydon | e19e419406c324a8210ce2199133ad80251b598430748be9c79d41fe906ebb58 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/112.png
back/112.png | Rhydon | 1e6cc3229851d50be6c80e87a148d61e33f90f6c3201f9a0b741cbb2fca00c8a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/112.png
front/114.png | Tangela | d1399602d3a45bcb62f94bcfe9ebdf7862fc5cc8abe2169ee481a068c25d9996 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/114.png
back/114.png | Tangela | 64cdcdcc6ecea0a380ad9cefad556f46fd3c65c067146110573ceaacb2603e90 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/114.png
front/120.png | Staryu | cdef239e8fc56ee105454f74351b26566c12128a8fbad4eabaa0da2033d4289a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/120.png
back/120.png | Staryu | c061396d6fd41e6fc39bb56109bf1b394d8cb04ce115a8deda402a671f1fe4f5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/120.png
front/121.png | Starmie | dcbad0eb0522ab33ff52cf8b7833a703d47fe3b23d906def3e9e8249d94b9f6b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/121.png
back/121.png | Starmie | ea13626461327730ae1acfb2708aa646e1a2e606de3e9ce8861d1401f7af9e21 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/121.png
front/122.png | Mr. Mime | c9a0eda9d04b81212f6a586706752b346e9c4a68f45236f95841dac61a0c6a6b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/122.png
back/122.png | Mr. Mime | d2df5a870a6386e445e17f8fb1a11bc220623531c5c778ba8a3dd2a81b423074 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/122.png
front/129.png | Magikarp | 3a99ad281768e6ac7d4c3d769e19991a9e0954e9e6bcaab04ab2e8e0c931c390 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/129.png
back/129.png | Magikarp | a8292e2d27d59f9bcb651efd70ac839f34ca57ec3384d21e0eb6a1b0bc71f8a1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/129.png
front/130.png | Gyarados | 9034a1ae52105d19cea479d7c85ce36b0d69cfa737290f88d65d31701fce85cd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/130.png
back/130.png | Gyarados | 85e16346024e2b385ef4939e5f8a3a2c4d14b419d07b7e91105ef434849d6fbd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/130.png
front/131.png | Lapras | acd9a9f8553ed659c029f9b94d5ed08fad78cb14254c32422a448559841c8dfd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/131.png
back/131.png | Lapras | fb9de8284c2d5cf6f5240a9cb467f5a0c6334c1eb58f3a484985d379521b127e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/131.png
front/133.png | Eevee | b468a53e251de4acac929dee8b9066addcad1ac214d24544d3290519f9067bbf | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/133.png
back/133.png | Eevee | 85052b6d604763d85debf8bb88ac8637dbf30e2ba0af450e97875d57a18ed6e6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/133.png
front/134.png | Vaporeon | 5be3b1ed359c7c359ec9407da29dd8708a3a9a19aafe7bfee0258d07297f6ab4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/134.png
back/134.png | Vaporeon | 311850ad7b70ca40a4d8be46ef7ca8727a8e46559032c35d3d5cd1dc4cff411b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/134.png
front/135.png | Jolteon | 7e1af90e9171f33ce5d5c3d95e007e7786cd386e615693db1ca2a1ee96439079 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/135.png
back/135.png | Jolteon | b37cc5858236d583d4dc7443f86e21fc2f7f4474188342c4eddfac718fb64a69 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/135.png
front/136.png | Flareon | 132625a591efa03f49f91aa78305b1bb2dd7e8dc7613d0d9f6372dc54d075813 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/136.png
back/136.png | Flareon | 79a4d06d631948ca22bf6c2ff4fa62a16fc6e4344f6bce9603f8b8c424d0cd2a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/136.png
front/142.png | Aerodactyl | 3e0012232d8f067f1ad13d7190966841432233ebac4daa690f4442b3bb64b3ac | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/142.png
back/142.png | Aerodactyl | 2d2545f83d8d2d5cd4a1cd5ee85c5d5424da54c6716b8917b1c95b938f0f4e7e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/142.png
front/149.png | Dragonite | f72633c877b1f9de6e3bcd4a820ed046efe7f7255d32ca28e185570680ba2f57 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/149.png
back/149.png | Dragonite | 570822520420a723957dc7f533768e52017e19d68d1eac9b8f95e46fa4387f20 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/149.png

Power Plant event sprite additions — 2026-10-02
Original FireRed/LeafGreen 64x64 transparent PNGs, unchanged.
Source: https://github.com/PokeAPI/sprites; original artwork belongs to its respective rights holders.
Stored locally for offline gameplay.
shiny/front/81.png | Magnemite | d01528f7deae88fccb30a873b2ff9161283ffb32b49282d94ea8f33e5c27a7e6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/81.png
shiny/back/81.png | Magnemite | 7c7cf5b72d7dc799a32335fd8cbdb8e5b3f2ccdbab8913a5e5b27b69589ce019 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/81.png
shiny/front/125.png | Electabuzz | 35f5d97ec9ba8be5d3c44dd37eb8a2524ecab84cf7d3b8b173c0303c68c0294d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/125.png
shiny/back/125.png | Electabuzz | 9e4016ca0bd10cf63ec3718b3d6de6c5891ffae1067ce2e8b35c73883acf91c4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/125.png
shiny/front/145.png | Zapdos | 16ecdd82667f4e1ce3a0f6b02de7a2b2138d8c29ee5ab2532e6a2e7774bd7569 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/145.png
shiny/back/145.png | Zapdos | d57bce366e6067537f4f357684ba61ccde565db1ab92bf2e8ef64033d4e03936 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/145.png

Victory Road event sprite additions — 2026-10-02
Original FireRed/LeafGreen 64x64 transparent PNGs, unchanged.
Source: https://github.com/PokeAPI/sprites; original artwork belongs to its respective rights holders.
Stored locally for offline gameplay.
shiny/front/66.png | Machop | f7003a181d2e82d27f0917b9e6c8e6077873eadbf4237cf19bed1757266db0a1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/66.png
shiny/back/66.png | Machop | 39b1992befeae308b5b78ea2233c3dd043e5dff2a7afbdf19a2bf3588403f9c5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/66.png
shiny/front/146.png | Moltres | 62719b5c19e682cbd05477aceb50086d043781077e74c3f4c2bfb49fab6e7372 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/146.png
shiny/back/146.png | Moltres | 48112f3c3973d5df30664ed73658edb45895400d223fd6333bd7aa30088c38de | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/146.png

Seafoam Islands event sprite additions — 2026-10-02
Original FireRed/LeafGreen 64x64 transparent PNGs, unchanged.
Source: https://github.com/PokeAPI/sprites; original artwork belongs to its respective rights holders.
Stored locally for offline gameplay.
shiny/front/86.png | Seel | c9641d80bed7ce357d0547bbad9d21dcdb22b4a6ea00d77538677400ec923ff7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/86.png
shiny/back/86.png | Seel | 2c26327ad5628fd767f3b0267ca46cc416912028850c018cd3f0eba92ce37c12 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/86.png
shiny/front/144.png | Articuno | 6c98a2422b16985a261c7bcff3cb70dc09da669974b094691a36e3640c018ca1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/144.png
shiny/back/144.png | Articuno | 4719b96a3d3f8c330e103293c86aabe9e75e21f1ceb4cae67993857b72e5dcdd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/144.png

Complete Kanto 151 shiny sprite coverage — 2026-10-03
Original FireRed/LeafGreen 64x64 transparent PNGs, unchanged.
Source: https://github.com/PokeAPI/sprites; original artwork belongs to its respective rights holders.
Stored locally for offline gameplay.
shiny/front/1.png | Bulbasaur | c954940ab5c4b0e475831ab26844415f1de1f254837c7bf6cb43422feef6f16b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/1.png
shiny/back/1.png | Bulbasaur | 4b992cbec7d251f640125d2313da2e979878e28e1a60f83faf96545f20b9b8a9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/1.png
shiny/front/2.png | Ivysaur | f2d5656b1b1d34a2f70652f4b5e2d8f565df3c00cd5dc504807566b533734c4b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/2.png
shiny/back/2.png | Ivysaur | 0fbd3d59f57e1611746537d51f98f53ff41879293864064fe6c87248ff449b32 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/2.png
shiny/front/3.png | Venusaur | c79cfb027fd7ecfd303f95954908accdf075f3d0f75e8285e27abe7722477e74 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/3.png
shiny/back/3.png | Venusaur | 2ae273f94c8b570f5c733f6443fc3b2be9a2c4f3c516859f78ba4c9245088b00 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/3.png
shiny/front/4.png | Charmander | 7a8af7f483787ef3ce92052a811230b4d619d504b4c14d3a5b091dc33417e5ec | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/4.png
shiny/back/4.png | Charmander | 3ca7f51e09a737f26b8cece93e1234f90365ce0767f10b7bc97eea5af9d561d0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/4.png
shiny/front/5.png | Charmeleon | 3a3f881545f5a02e6d3d42196bf04f04b12d9f98002b4e5f758a149359136ea1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/5.png
shiny/back/5.png | Charmeleon | 3f1d8b9db67cda712a3699a5da99c2042f79e6bb73b78826a3777140ac73e5f7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/5.png
shiny/front/6.png | Charizard | e27ae0732401f2aefa734318a4c3c88c011d39877a43a6f42db6a5e274582b44 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/6.png
shiny/back/6.png | Charizard | d7306c16856a32fc5fc5378dd37fa26bb881ae4f5e82747681eda7a0b5793dc3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/6.png
shiny/front/7.png | Squirtle | 1ad5e4a51806d52138d82a1f18553a6622dfe848196d1cf39e163e6918c08854 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/7.png
shiny/back/7.png | Squirtle | 4d3b6f4cf78005fff8f00a5d8aaef4acb242488757d25881e0a9adac7620a0b4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/7.png
shiny/front/8.png | Wartortle | ea6a52c1645fd694ce3433c35874c7d00464feba7ba35b7035c0153f1223d330 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/8.png
shiny/back/8.png | Wartortle | b298934eadc6cdb2aa20102d9fe38b6ca0f348f64e9f1a7acd8b0bb8cbd5114e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/8.png
shiny/front/9.png | Blastoise | 0584bcf7b9daf065d30a9aa9acad383676bafff08d24aab16f6a16d47932d7b5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/9.png
shiny/back/9.png | Blastoise | 9a04e4ba3e4460b93e6c0d07154dd768c6bea59b17ebb4d5a59d257d9ee67dbb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/9.png
shiny/front/10.png | Caterpie | e05aab6440d74e45fe3ac98427a5481e4c1e77143938d9bd00feb6e22189e95f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/10.png
shiny/back/10.png | Caterpie | 2c561e6734cdda8fb39eed07e6697ddbfbb2a87c9d74b1ffb4405018cc4c1c76 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/10.png
shiny/front/11.png | Metapod | 54e10a610d4346da345d869ff63fa250f2d54c1dad88893122bd338542a3bfe9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/11.png
shiny/back/11.png | Metapod | 814fb5309c5062ac1763bab222e99f1f2b97d3e68681e5f5bfaed999faaea64a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/11.png
shiny/front/12.png | Butterfree | eb7323009ef98bfffa96254f685e9abe902b83fbddc5392ac8afcaaa397e5d46 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/12.png
shiny/back/12.png | Butterfree | 0be029a87b636dd3c6be2637db8b4795773d782ef5d0bab17dd6b84009e04a38 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/12.png
shiny/front/13.png | Weedle | 831120d53b3fa3ad203a6f45be1e8665ee4614078f150a06883bd2c6fdb75521 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/13.png
shiny/back/13.png | Weedle | c90da59ed57e0449721f9d78cdc4a58b0c3e34db0ed9c60f5722035a374d8ca3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/13.png
shiny/front/14.png | Kakuna | 046e604066c5827984fe45a669f7d2836477bfc784b6c7998b132c0b2cae5276 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/14.png
shiny/back/14.png | Kakuna | 6f8380fd4419fdf5f64e450fe9a5c0bc2a04538a0b31c0aa1625bea7eb90ac5d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/14.png
shiny/front/15.png | Beedrill | c8b4dce9cdbf602447ab5e3512fd6776946573f3225e50c992d738d5632e7a81 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/15.png
shiny/back/15.png | Beedrill | 76756c469e5d1c266cc16be97278a4c092ee4c253804fa227e300e9c3c6969bc | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/15.png
shiny/front/16.png | Pidgey | ad7e93ef09a513b03cf6eaa7f96f16c89a76b9543baee9400dc348b71c658ce7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/16.png
shiny/back/16.png | Pidgey | 3e174b584f818aa0722310666d80b613436c993418f56ecf2af45145ae16e836 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/16.png
shiny/front/17.png | Pidgeotto | 09903c48823606e405a20b29a16d651250adde564083a47bb508f85314766248 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/17.png
shiny/back/17.png | Pidgeotto | 44ad9a9e5010504b385b9eb44f329fe59e447376b911ede25c2d89635639516c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/17.png
shiny/front/18.png | Pidgeot | ffa6a79c8c172ac7110c1c81892bfc917a8c098c697e55a1c77d96df9568c5bb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/18.png
shiny/back/18.png | Pidgeot | 9b7bebdc9ddce581b2695ebc8feef686f861347dddf059d92966c7ebe90d38fa | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/18.png
shiny/front/19.png | Rattata | 07d1b42faf814c39c7690186f793b99ab99743084aab3218ac84cae8df17b949 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/19.png
shiny/back/19.png | Rattata | 6846cb8a4035b6ae607f02f96bbc52bc6bf9685c3ab58c2a9126ec0588321f04 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/19.png
shiny/front/20.png | Raticate | 2c8313164808fc9b35f0c6400124d7ba4aab76cf97d2667bc81081802a56ba15 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/20.png
shiny/back/20.png | Raticate | 2762fae5b5bc13b714f09da0a98952c3029a57de26e09d463bd00f492a5fcb21 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/20.png
shiny/front/21.png | Spearow | 8d86991c2874f4ee74ba2495f633fa1ef344e0b0f9101282494b49ba5e114892 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/21.png
shiny/back/21.png | Spearow | 7eea24a2dbb0cde610edb5e3c73d1272957b2e73624e9b671ff4dc3c5730d4b5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/21.png
shiny/front/22.png | Fearow | a6b343ee83649a786b3662d71f2d1269ea30b2b488093d6fabb3cd7a53a80858 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/22.png
shiny/back/22.png | Fearow | 96ca9cafdca7429bb3a6173dc1a3c51f3606375aa7ee4372ad614db1c2fe36ab | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/22.png
shiny/front/23.png | Ekans | a720c492d9134a96b7459d2487f14157a2d58079fd7b85d1fa9e350569e05c68 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/23.png
shiny/back/23.png | Ekans | a7419b960868bca039c71e4dec9142daa36bc110d4c0ceadf66a6c375982e90d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/23.png
shiny/front/24.png | Arbok | fb9b8770c1546dbc797bc04baf7c7ba5a92e604eabaa37035b4bd017ff2c0fd8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/24.png
shiny/back/24.png | Arbok | 3fba6454ee1f073bdab395f21135624dab129ccf5a90eb34d30008c5b728003a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/24.png
shiny/front/25.png | Pikachu | d7e0acf3340e1d3dec340ffdbc62661443a8f79093d5824daa491c26eff83034 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/25.png
shiny/back/25.png | Pikachu | ec41691ad9044bc90c623519f5ca9d6e39b782ce79a56eb361f1e1c226f8229b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/25.png
shiny/front/26.png | Raichu | 07dd4c426905bbcb68c5b85a1df8334e8cc98200a91da7646669be37c43b077f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/26.png
shiny/back/26.png | Raichu | 6f182c2f508e2856ecfcfdd3d51fe0f0d01fb8228041ed23498d0dcb23885691 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/26.png
shiny/front/27.png | Sandshrew | 8a0d67203a924b80b7ef777bb919d21915add7062f0e426182db5219860a5f08 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/27.png
shiny/back/27.png | Sandshrew | 7d410b4e76fe803915b6bf32eab29a6fde4e3d0310f8a601ddf259e411d4aca4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/27.png
shiny/front/28.png | Sandslash | 1aa26d5aa2717d17635329d7ef00e724f20c76429c0ecbee32cadebea0cd6e93 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/28.png
shiny/back/28.png | Sandslash | bad7c5c0db830791ddf0efa63fd294c85870e3424ece3ab9931a76bc166a0e97 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/28.png
shiny/front/29.png | Nidoran♀ | 7d6ae8554a269659826ba37ced62af9b9be8cedf0ae3d0ce95aa4c33f7c095d2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/29.png
shiny/back/29.png | Nidoran♀ | 2185fa2a0402a97994331bcb669e1f550eb697977b77cab2bf90e8e6ca3e53da | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/29.png
shiny/front/30.png | Nidorina | c46c16e004c1f5be5e880e794d894f62e8a2189aa140a5028a004155fa5f5fe8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/30.png
shiny/back/30.png | Nidorina | e1dc25f479b07289faadc99d536194812676f890842a796f21e251c501aa7b17 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/30.png
shiny/front/31.png | Nidoqueen | 0a60b26f8f202ab2a99c890525310a8b4b1ee8d166a3c22e4c8cad4649ff8fa8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/31.png
shiny/back/31.png | Nidoqueen | 384660401db38ca033fa82282c7d62730b54babf01fa18e4d086a491f6182d6a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/31.png
shiny/front/32.png | Nidoran♂ | 22df315d95fa2a805876c6a8c8b0f4550b540a6d48d692afd294db16c69e22d7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/32.png
shiny/back/32.png | Nidoran♂ | e8302eb13079aa72245dd1de0f55522a4ff2bc45ce36a7f215360127f222db62 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/32.png
shiny/front/33.png | Nidorino | 339ea3bde2d4200d5339340b2f6fabcf5a04cb2ddc5b9d8dae9a3097f5b4c210 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/33.png
shiny/back/33.png | Nidorino | b906e884af1a69dfef52d5bd616a1f57d7fc2edf24c0d60d22a3a75007d138f6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/33.png
shiny/front/34.png | Nidoking | 43e319154961d4dfdde3fb3c124c1c209afc0f57cc1a9fb469c9026c94a86629 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/34.png
shiny/back/34.png | Nidoking | 76d0e9dbf2e1a5e5c0e43e21ff80783b584aa9b882780f3fe38593f52c5f7d13 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/34.png
shiny/front/35.png | Clefairy | 5d4fdcad8af5244758be2107dc241b586aaf603d9e2e6784ef544e0611309c9e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/35.png
shiny/back/35.png | Clefairy | c038773ee9467be783f0b189f1f92effe3ec1930a0b7d9bdab4f74642232c313 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/35.png
shiny/front/36.png | Clefable | 5b8d1846016b3b6e27fab41ee333cc466aa95eaff299bcfadec7a50fc52397f7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/36.png
shiny/back/36.png | Clefable | fea19af81229e9430836ced4ad2cf5ada649e82bb1e0753ce08e387d4cf1724e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/36.png
shiny/front/37.png | Vulpix | af97c9df284b7b3cc9f5797924554ce2672d8d55eaa63a5fced1cc23973fc187 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/37.png
shiny/back/37.png | Vulpix | b34b81621f63bd033ba66a8ce8118908d7038e5748645909ed4cfa3a7d3bbb08 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/37.png
shiny/front/38.png | Ninetales | 08772a09c1e943e5b95556fcc29ff85a4b61991f96f17fa480c644d255a2de30 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/38.png
shiny/back/38.png | Ninetales | ec8bdc3658bdada9b57779d4ee34f2fd35661edd06726fa68460930c5a49747a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/38.png
shiny/front/39.png | Jigglypuff | 265c5b25582e42361bab235eeaec64afbd0c88633e0f31c9a73b6b24fb2d19c0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/39.png
shiny/back/39.png | Jigglypuff | 47c3332e5234394117b9959b2e98208120e693518473998d87513988e325af24 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/39.png
shiny/front/40.png | Wigglytuff | 46c010f0d4e29484b42143485120ea6af93b18564681f82c927d13fe5004786f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/40.png
shiny/back/40.png | Wigglytuff | 966add3c345efd13bdfd3687d3790f73fe107ca921b337f0370310a16d42a4a4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/40.png
shiny/front/41.png | Zubat | 254364d73ec1579686cd09715321fae8761d39efb833f58ec0396382ffe956c7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/41.png
shiny/back/41.png | Zubat | dd670c4a1227dcd131aa90539696fbb56d0a5fe21c86660e63d80570f1a6c602 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/41.png
shiny/front/42.png | Golbat | 4e447b2fceecc199773bc047d843b7f6efafb6f14bd02f216280af9b7014e0f5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/42.png
shiny/back/42.png | Golbat | 4d9786c28bee10129f50fe6114f651f238491ff76038970d49197228688d41b7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/42.png
shiny/front/43.png | Oddish | 3768ae3f2645305478f8fd16f841602af8dc6138839500ab1e25c30ef5663497 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/43.png
shiny/back/43.png | Oddish | 73cc6af97cc5d8967ec0d668c5f64046e93f3d33b843502c444a8804b956e1d2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/43.png
shiny/front/44.png | Gloom | abae59b7f9e404fe1e9ccb477a49359acef751693191bb9e268712a18c81e24d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/44.png
shiny/back/44.png | Gloom | ae0e2b178efb624ba18678f88192f800bdb74343e5653c4179587170926dcdeb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/44.png
shiny/front/45.png | Vileplume | 2b28f705023031cfcbaec40470a8d66c70d697b8769e09f7fb47d3916baef59d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/45.png
shiny/back/45.png | Vileplume | 4b3cda8e2f0653d6a8c91398c07fdacaaae28c8160c095d07f8613e643602f7f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/45.png
shiny/front/46.png | Paras | 8cc2e06ca6ef6d7ce1fd75cdfb3ec8674382857672f81a71c9b877306c4504f3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/46.png
shiny/back/46.png | Paras | 30245ca67ebf53ed42da08bae5e4f6f111965b4af7af70e64684be2c8dd9ed1e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/46.png
shiny/front/47.png | Parasect | 561ce5c13135e2f517ae0da5a1563cc8343e57d22ba434cf103c2d3509f3b60a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/47.png
shiny/back/47.png | Parasect | 208e2223fa9b0bb3a8871d38fa8e5afe8b9297d1ee8e74b379db12bd96642664 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/47.png
shiny/front/48.png | Venonat | 7956d2b1f985a872246e75f55849d8b1183543f6cdb2730e557687f3c722a9ac | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/48.png
shiny/back/48.png | Venonat | 2378916b74f3f5cf6bc102e83548943d25f958d14c904dda6e0975a276b9e363 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/48.png
shiny/front/49.png | Venomoth | 362a6218947804cc90a88c0541bb92cd4b613d590ab7f0106d6c9d6ad4c967db | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/49.png
shiny/back/49.png | Venomoth | 2d5edb6542ea25503cd07edc8042687570d60cf0e5e57286ce4874512a221cbe | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/49.png
shiny/front/50.png | Diglett | 11ee5740a817ff0cb7da09cd992df6872d64e570941bc56191640911159caf5f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/50.png
shiny/back/50.png | Diglett | 15d5dcb83288a16dc1684481df60226520af8e42820df96d6e5ff5f4d4235d53 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/50.png
shiny/front/51.png | Dugtrio | 2add67f818b71d2ea4aff280a0af84c3fda53b9ce3e62a6b5acc5c5cd9a82675 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/51.png
shiny/back/51.png | Dugtrio | e7cbe8709c6dea42e0ca9e7a1fe22d96722c684e6222eeae22d106957b28b7c8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/51.png
shiny/front/52.png | Meowth | 28a29f6adf2f32d8601e27153ec0225f975c13ef44a1693ffa08b0f406162965 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/52.png
shiny/back/52.png | Meowth | d7f85c5a896d58d89bf9be130f045489dd0d13bc479b614e04d8bf1ed7dcf676 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/52.png
shiny/front/53.png | Persian | 7c2d57b0fb67b885a30b017099dd95a6479b4a6b47acf56e88af8a37762bdee5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/53.png
shiny/back/53.png | Persian | ea27d443d71f34d778203ed8e6d04b3ca1b6807633cc0e8f3146b56e185b4331 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/53.png
shiny/front/54.png | Psyduck | 720e1a81defbf5177826e20d57b395a69f7c5ee6f8ae46d57ef7f13e54b29c9c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/54.png
shiny/back/54.png | Psyduck | f6e2635dca42e79aedab849ac19e334e9e6b141bb90e5d486c05a2c0d726e72c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/54.png
shiny/front/55.png | Golduck | 2e8b9051c8ad522a0b09f74bcdbfff81c7f9c9d3f6fdd1399e0dc8d67bc6d519 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/55.png
shiny/back/55.png | Golduck | d4aebebe3d609592be0aabaeb8002465cd67a05e7aba892c246f33e9ea90b9a2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/55.png
shiny/front/56.png | Mankey | 62b2c1dc7c5cba6268a79b77e0d0046032740402f0ab26ff57d6a12183d82855 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/56.png
shiny/back/56.png | Mankey | df8d07ca546606196e4ef20c5b9ec613df3b93c3812881ec0119c1b045c48ee1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/56.png
shiny/front/57.png | Primeape | ccc0226fa3059cef30aca71fc28065e7a46084bff06109e280ba2b4934362edf | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/57.png
shiny/back/57.png | Primeape | ce4fa46b0484e1a1e4487723c2831aa05352b6f09c361e1669a17a5ade59e7da | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/57.png
shiny/front/58.png | Growlithe | 3f70ff4402d42ef67d14bdaebb7ef77b9ecd9bcf279c4c18a43aeae995e07302 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/58.png
shiny/back/58.png | Growlithe | 58df0591f30f56b63e9b28824015254b6285a4d980b115ad2d9599535284f26c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/58.png
shiny/front/59.png | Arcanine | edeca209cf8575401c859ad5c7802cafed6a560cb72702ec2f3bae0d51675cc6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/59.png
shiny/back/59.png | Arcanine | bc793527404d62672f5c18a3ba4b94dae4c567b2f39fd4926075c2af2016b6f2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/59.png
shiny/front/60.png | Poliwag | f2e00a74936d746f9e82d722ef772bdb113f1bc227f1b93ad4b2f5b8a43b0f0d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/60.png
shiny/back/60.png | Poliwag | 6732ac28e4dc0c0f002fd3021d88947a219fd125c03e7f1710d6448e46ce22da | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/60.png
shiny/front/61.png | Poliwhirl | 3153ce4941f77b596770123494420a02d73976ecc3d3d538d390e8e6575497e2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/61.png
shiny/back/61.png | Poliwhirl | 3660c820dfec70e9a6d5485eaf6c770fdf7df350def0bbf392c792b19d6f4b3a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/61.png
shiny/front/62.png | Poliwrath | a954e6eb18ddf7d289fa2282b290b550acf55df445e586ca2a0de926b3647bd1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/62.png
shiny/back/62.png | Poliwrath | 919a02959367c95937683409bd9a95679593fe4b019f52c753091455ed388fce | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/62.png
shiny/front/63.png | Abra | 8d7d88654b988c13e1cc63b1fb7ab2a4c9319a12beb7e9f236399621b9f4fca8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/63.png
shiny/back/63.png | Abra | fdf05a72538271ff75b3112e4e96d60554a655e31abbb240a434dcdd090445a6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/63.png
shiny/front/64.png | Kadabra | 9352a8bf30b5f827b40a3977ab155881a4ea6f97b3aff16354b789957416fb35 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/64.png
shiny/back/64.png | Kadabra | 48e7051be2198b6111adc3f90aa52d012db761cd403c24a5c8e6aba2eb69fce2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/64.png
shiny/front/65.png | Alakazam | fcf16e568f0e5c8f1b0a2ff712c13681b7be810bc27e3c865102bac28654f71d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/65.png
shiny/back/65.png | Alakazam | 62e5725017fc2c94a9741e4d29de00e20c39e4a8e7154611a61a4bd806b4b1ee | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/65.png
shiny/front/67.png | Machoke | 0eb4e7421663f05af62ca9e322313475e92276301eca57530a8872d92935b1ab | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/67.png
shiny/back/67.png | Machoke | c8a8e1915f77ae7ccdfcec83da38d4663030637117aaa87b726e8157018da24c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/67.png
shiny/front/68.png | Machamp | b1fdd80de544c3824fb45258ddbbf11819d385cf763e0b42b1a923cfb36bd2f7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/68.png
shiny/back/68.png | Machamp | 3be81da6e946a658a917876b0048360565a5349ab49d11fee8ccc18ff7539869 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/68.png
shiny/front/69.png | Bellsprout | 3a14494d3af85e8e5f9ad361f8ef1ba36fef85ba63ee94c78b7f9d4164c7c5af | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/69.png
shiny/back/69.png | Bellsprout | 9b065bab740422c509d82f518b53de69a13915a8f1a20a3fd7e9c98d6798928c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/69.png
shiny/front/70.png | Weepinbell | 0db86f213e5b50f04d2485fc268fafa3bb4d1a79a0c4360135b9e5f7068ec91d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/70.png
shiny/back/70.png | Weepinbell | e22ec404a38fcd03d1afacf69f8540febb9aa25883dc549a4d0b659a8b90b5fe | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/70.png
shiny/front/71.png | Victreebel | 9d72bcb34c41f69e034309a8eba22d7a77d6cb702e1946d7bbd98f00e172edca | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/71.png
shiny/back/71.png | Victreebel | 7b91a618e3645468faf56fd019cc213067472c849696953be735d6e65acf4c65 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/71.png
shiny/front/72.png | Tentacool | 95299556bf41274ac7d40d80ac8d48e53cce99bdb0e6eb31b07467515bc3934a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/72.png
shiny/back/72.png | Tentacool | 4738b51ef4078e16a572de511271a7b2bcea4b84486f2a7bda5980c46db114d8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/72.png
shiny/front/73.png | Tentacruel | 504ed467c9ea6704167513c61b6ff518ca389ee43624b91ebdf43ac8fa73e627 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/73.png
shiny/back/73.png | Tentacruel | 23071722cbdb3d28e1bd283e3b709b9903a991629059aebbc116f83b29885f93 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/73.png
shiny/front/74.png | Geodude | 30cc8428440ffbe18ca1d8dadb4dde907a8ce748a19ceb2969ed23544e2b82b1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/74.png
shiny/back/74.png | Geodude | 31ef8d9f13aaab6048f05bbbfb5724fe778e0f4b9e2eb8fd56cceb930d3ae550 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/74.png
shiny/front/75.png | Graveler | c73e8bf7c56559dbc1fa261594c5e1d94918df64a802a3e9d3fbea9f55c438b5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/75.png
shiny/back/75.png | Graveler | 94e633f5989a991369b9f204389bacd7430519ef0b627327afd12508ca929f64 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/75.png
shiny/front/76.png | Golem | 19cc5b83ff41a280f5f6c08860b885d4adcc77c201e56427400f9bd1fb8d8b25 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/76.png
shiny/back/76.png | Golem | 891fc4267de0b95545d1627bd6099d829e40b0fc0423a8cb33e4f5d338cf8fb2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/76.png
shiny/front/77.png | Ponyta | 704b6ace10ae1840d4fdc90094ac3b554290bc07811e453f156a1ee603459514 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/77.png
shiny/back/77.png | Ponyta | a5872a3aa846cdd62cd78b92035404496f4192a8303da2f4a62aad0783ac5c76 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/77.png
shiny/front/78.png | Rapidash | b03358e91a0f60561b7a9ccc2d150c7f15b231b5e8a3e5ace01e0942d24f5680 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/78.png
shiny/back/78.png | Rapidash | 92348959c832b25fd433cfad9d3d520f0cd02c9f3c52d890fb7a838bb75ff059 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/78.png
shiny/front/79.png | Slowpoke | c72f65f5abfa838eaf0dbe9a90e44859d60a657c1257f0676ef439c0eb3767c3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/79.png
shiny/back/79.png | Slowpoke | c509f08a81a99e0e2466d26101ce71ed3792c60eec3a7210863b45cb5e51812b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/79.png
shiny/front/80.png | Slowbro | 58a6cddd7ef7dfefe006e906b8ba9608f4301987813c990e4892d432581199bd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/80.png
shiny/back/80.png | Slowbro | 5c54a5096c1f96d18574387a8823f8fba42a2f81ef31d1b88ddcc5cb699c5dc8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/80.png
shiny/front/82.png | Magneton | b9254907c20807fea08999de7653d9e2c1187c5194f0878e7fc6099fd5be32f3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/82.png
shiny/back/82.png | Magneton | d905190d9085ef5bcdc3d3dbed4d5265be6ea3e4540f0ef7fc8da86925d315dd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/82.png
shiny/front/83.png | Farfetch'd | 3683f8366e170d625e43af8649f4b38ddde22d319b8af7a5dd769da7fe13f801 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/83.png
shiny/back/83.png | Farfetch'd | 4dc0c26d0887686c34f4068e3f02af905ad48a2a3ccef72e93e73562cb0f5758 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/83.png
shiny/front/84.png | Doduo | 9cf1deb646af8ab4d4592b2b22ab26f49f099c480a47562e1f0914738ec5772d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/84.png
shiny/back/84.png | Doduo | 11bb4d479214cd25916a2cd74cc86cd1e238599b65cdc93824ec0fc09966c921 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/84.png
shiny/front/85.png | Dodrio | eb0b1c5386d4d895fe96eb14adc624b2b23e010ba42999f32e079ae668ffcbde | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/85.png
shiny/back/85.png | Dodrio | e66d4a1dfae4ae96ecae27fc8328dc747188505c17fb1bf8b1a5b63d77b191d0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/85.png
shiny/front/87.png | Dewgong | 27f13070c88203216bb8b7a96efacaef4412258bcd930f40e782cf36ec80dbe5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/87.png
shiny/back/87.png | Dewgong | 1d8b09b40f1bd5ca5f89ae03741c0d3faba29f7634ca78a27ff186285664cd47 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/87.png
shiny/front/88.png | Grimer | 8972bdcf12cf2864753623b7b01647605b76f6b18b93d691b5c0825946564050 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/88.png
shiny/back/88.png | Grimer | d8aa699cd2dcabb2419c740079df0ad35050de1ff486668c1e2f2cc2a1e53bee | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/88.png
shiny/front/89.png | Muk | 61e00a118c7d7fac7111e540b24cbacca50507384481934272e95e490404cdcd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/89.png
shiny/back/89.png | Muk | d80b3f5b5cbcc35b7bc5698261d9e2130de65cbc353834d7675d1c784c0799d4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/89.png
shiny/front/90.png | Shellder | e5e81eefb66d708fe841c002e256714b919cf71275d030fa2ee307cf30548596 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/90.png
shiny/back/90.png | Shellder | 9cd9cf750b60543f6d390ab4f7e8b5f211487578bf86e2786a3500a785c02466 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/90.png
shiny/front/91.png | Cloyster | bd325f93641c1d3c64f5c2faa5bc419594b02ffbd06459d1e1da31a1b70ee172 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/91.png
shiny/back/91.png | Cloyster | f33be334710a650393f16d03b38108556b5ad54ee6cc5b1442a5522da5e754e6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/91.png
shiny/front/92.png | Gastly | 64a4d6d1b0689127e6d4d85c3273b56c2db41f735db7b642240ddddb061c99d6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/92.png
shiny/back/92.png | Gastly | f11781d2415ba613dd35d8e684c2f31052f0a2f7dd636a204e9e9faf06a39a67 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/92.png
shiny/front/93.png | Haunter | d74b1ccfd507691ddf5354a44af48c16a82fad5ec42220496b470f179697b23e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/93.png
shiny/back/93.png | Haunter | 6e3733e9bceea20db8cbfdb4fe81b99d1319b6a674c6d9ec07bf9184da166197 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/93.png
shiny/front/94.png | Gengar | ae4188d275724588b76020f77812b6687b85fe9cf57f0440a007c9577f3770af | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/94.png
shiny/back/94.png | Gengar | ced0eab2e94291c84a41e9f81d3055c2f80feaaf05f07fa4f90ff37331e36767 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/94.png
shiny/front/95.png | Onix | 4e49e63881dddc26fa8493bdabf4cbd4badb0e35511fe2ab214363d60a969b14 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/95.png
shiny/back/95.png | Onix | e8d64b60e78298005f57dfb5f46c5b94cd00b292281cef94d924eda25cc2bfb8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/95.png
shiny/front/96.png | Drowzee | e2c08750f38f0f7cbf5de9825fe20853e2696f69a15ba491c5e6e0939e2eb0f7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/96.png
shiny/back/96.png | Drowzee | d7418d056baf6312152132547067b881015e2880ba79edc1336489c01e4af051 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/96.png
shiny/front/97.png | Hypno | ed70822b58296056b0b961e08a0c1a81b136e8a899187941aed4512479aaa8a6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/97.png
shiny/back/97.png | Hypno | 91ae74defdc2aeee2d79c8699d79ec81da1758007438559d38fce30b239003e9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/97.png
shiny/front/98.png | Krabby | 0a8ede4ea6c7c374c9c4481b997804ff57c379a02f7f723c825073b8701efd12 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/98.png
shiny/back/98.png | Krabby | d51e51afedc48a9473fde44e13b7c293e4220a02933aed44609f3cc5344aab35 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/98.png
shiny/front/99.png | Kingler | 6655d05f1596601f56162c23a557ccf9d03ab5ceedf6fc66db60ffab23566f44 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/99.png
shiny/back/99.png | Kingler | 851dccf451c856bf6f36baa286e0bc61b9e6c62b4c07bed44bf94fb2f9dbed7d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/99.png
shiny/front/100.png | Voltorb | cb0b457809fe4af019bed0c82bac596406d9f1063e871b7b368218e7bcf271bb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/100.png
shiny/back/100.png | Voltorb | d54fd02cb8cc6100f93c59a04d4489515aef1f95a07b20c9639f4a631f1da0f2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/100.png
shiny/front/101.png | Electrode | 317eb1a1f96734e69d783803d514fad49b5ade7569a46c99da1c916abb57e75d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/101.png
shiny/back/101.png | Electrode | 9104c871bd9f3eef30c664fdb66d489b4fe953845245419c09d3beb3f61265fd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/101.png
shiny/front/102.png | Exeggcute | 5d9340ec6bcd70e637685509b7a634cd79eacdbc9c31476a4ed7c334e0d73fb8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/102.png
shiny/back/102.png | Exeggcute | 0d1e079c9ac167b609b47f2f7a04b99999ca26e4ca48fcdcc9d77dbb5bb48124 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/102.png
shiny/front/103.png | Exeggutor | a2a3da84cdad10bc3fbcd2c084625321d3849bd5abcf71f5017ddcc87ee910a8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/103.png
shiny/back/103.png | Exeggutor | d73fc5175f0cbd4ccbaef28a1892a7e0ef0953dc6ad898558dd4ddefa889aeeb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/103.png
shiny/front/104.png | Cubone | 48bd5ed2fed7c229878ea2fe1e309641248d1ed4aa92a8b59d29b6d8b02c18cb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/104.png
shiny/back/104.png | Cubone | ff8328e38ffcef950cb7d498c45be11501070afa2258e996e9aee74ccb95fdc3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/104.png
shiny/front/105.png | Marowak | af8ac6b813c9acbda25ca4bf11af716ae18308c6413cc81874dcc9e8b8a222f0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/105.png
shiny/back/105.png | Marowak | 82f642de2c143c7c500a2cc7b505d6321402f67e551182968e33e0b10a5a8dd8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/105.png
shiny/front/106.png | Hitmonlee | 64541e06ca2a6d3c3236cfd995ad8a25a2543f1633a3135f985a66e4642542c5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/106.png
shiny/back/106.png | Hitmonlee | b5afff8f7482107b710183c4206b2583a5c7737ff8324a1e3cef4bdca2d9fe60 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/106.png
shiny/front/107.png | Hitmonchan | d04b20105d064db61674a56126a5e0bb5bb311c4d80bae6d2e3b0e9d37da5724 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/107.png
shiny/back/107.png | Hitmonchan | fef7f1a5c0315758a1ec64d1f64a5bf9abe81aad959c7f71ee96c9cad68f367d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/107.png
shiny/front/108.png | Lickitung | 9349dea984572c7f4d989b6bb151ce8a5af79ffb64a2f6530c65db085cc94981 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/108.png
shiny/back/108.png | Lickitung | 432c2e9a6a821471cb8d40245845acfb78b34ad81eaaa4902253d938be6680d4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/108.png
shiny/front/109.png | Koffing | 4b0c361a5f60a4d1ddf6172523626d412f38e908616d2ff8305807a28c7e1341 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/109.png
shiny/back/109.png | Koffing | 401a97d99cbf32b8b5acbb209951da5de0de3a691d27729cc8a05313e1575236 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/109.png
shiny/front/110.png | Weezing | 7e6d2a4e300749242aa523855d87e6c06ac0a1e909a81cfb0c563242b2d91900 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/110.png
shiny/back/110.png | Weezing | cb3e64db6105abb517011d578fba0a1f18d67ccde9637191b9bd787db2de4a1d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/110.png
shiny/front/111.png | Rhyhorn | cc8e78464a8c9455cfdf875edde909ab5dfeae07cc526916bb8666af15e3adf7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/111.png
shiny/back/111.png | Rhyhorn | cb741dfe3e0a8577c306ac5ead56f0c92273c3186fa56dc09a2816e123aaf298 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/111.png
shiny/front/112.png | Rhydon | e19e419406c324a8210ce2199133ad80251b598430748be9c79d41fe906ebb58 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/112.png
shiny/back/112.png | Rhydon | 1e6cc3229851d50be6c80e87a148d61e33f90f6c3201f9a0b741cbb2fca00c8a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/112.png
shiny/front/113.png | Chansey | 77b1cc74c23b52f0da74db4f5f1ae8c5f2c992884403ebef94b618475a5d913a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/113.png
shiny/back/113.png | Chansey | 5cee922c2d97618fb8ccd09d9c364525882274646d63803e132e8eb39a1c11a0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/113.png
shiny/front/114.png | Tangela | d1399602d3a45bcb62f94bcfe9ebdf7862fc5cc8abe2169ee481a068c25d9996 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/114.png
shiny/back/114.png | Tangela | 64cdcdcc6ecea0a380ad9cefad556f46fd3c65c067146110573ceaacb2603e90 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/114.png
shiny/front/115.png | Kangaskhan | 5e3a22595595c729bc9276141ae2428440cdc567d409c8c6e7d67da66c2f7b34 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/115.png
shiny/back/115.png | Kangaskhan | fd91219d230ef43c20e72ad4099f03f179ced25f7d5750e4d605b8c43b574a1f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/115.png
shiny/front/116.png | Horsea | b290d0bcde1ac48edd5dcc8fe23ecf4f07ac88ed5d57a91181a15d50f24b7f7f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/116.png
shiny/back/116.png | Horsea | ca77953e1184e743e18d93c3befef64ec8d3f950828a10779c6586a5b58ee83f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/116.png
shiny/front/117.png | Seadra | 7631f93cd0ce28aac7e3804509e4f177b8d676520787d2736f20d45a183120b6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/117.png
shiny/back/117.png | Seadra | b6e09078085278f7f9238485dac4d27258ec46489e863420373fa265f2c5a257 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/117.png
shiny/front/118.png | Goldeen | b03c5207300c92b12dd6bb8398acc1dfa9df0be212940cfad369c521764cb5e8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/118.png
shiny/back/118.png | Goldeen | f74b38f3a20f8ebe77e51c80a3a6c6bf5a6ed97a2783809a5dc15d866447e830 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/118.png
shiny/front/119.png | Seaking | 16f7bcc63c3a4b83cb720d67177ca8ee8f0512b5d2de1ca7a00a23c655a3d1e0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/119.png
shiny/back/119.png | Seaking | cd6a05cc278103b9c3a380b039f99fe20cb1402dee11a29c93898beb6cb86060 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/119.png
shiny/front/120.png | Staryu | cdef239e8fc56ee105454f74351b26566c12128a8fbad4eabaa0da2033d4289a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/120.png
shiny/back/120.png | Staryu | c061396d6fd41e6fc39bb56109bf1b394d8cb04ce115a8deda402a671f1fe4f5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/120.png
shiny/front/121.png | Starmie | dcbad0eb0522ab33ff52cf8b7833a703d47fe3b23d906def3e9e8249d94b9f6b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/121.png
shiny/back/121.png | Starmie | ea13626461327730ae1acfb2708aa646e1a2e606de3e9ce8861d1401f7af9e21 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/121.png
shiny/front/122.png | Mr. Mime | c9a0eda9d04b81212f6a586706752b346e9c4a68f45236f95841dac61a0c6a6b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/122.png
shiny/back/122.png | Mr. Mime | d2df5a870a6386e445e17f8fb1a11bc220623531c5c778ba8a3dd2a81b423074 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/122.png
shiny/front/123.png | Scyther | 4bfa05713299796db54e5006a015036d9c23a7dff624edd6c991d57b9df49bfa | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/123.png
shiny/back/123.png | Scyther | 70fe497782f47489953fb054edeea768611b19b435206e217df8eecbfcbdc9c8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/123.png
shiny/front/124.png | Jynx | bd585001a48eb5696bf006cb858318c15c0d98fa1d81fd296870266d8d36a402 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/124.png
shiny/back/124.png | Jynx | 6f3b674905a163eb125b05a0fc1fb1fd54893268b46d33d60f0484051fa2724f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/124.png
shiny/front/126.png | Magmar | 8c5eb112ebbb4550e799257d82cf5d0c93ac900ab7a61bbb4e2b30948429ceb7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/126.png
shiny/back/126.png | Magmar | daf49b846edde6e1b6edd230956f164ab4ab7cb271f0e70810db1516904e057e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/126.png
shiny/front/127.png | Pinsir | 6a9318edae35f182b5bb304481bb6c3d8a80cb287549902854d473822df68c39 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/127.png
shiny/back/127.png | Pinsir | b1d2628f7282eacfb2eeea5dba6aee786cb756cc0b7e4e71da360dd5f5a1b627 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/127.png
shiny/front/128.png | Tauros | 9e4544e7126885d6628195ca58b99d22b2532a94ca0a47291c6decd498a6db44 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/128.png
shiny/back/128.png | Tauros | 034f04133b71b9c5b866161e8e56abb79053846f038a74564432151d76c88dc5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/128.png
shiny/front/129.png | Magikarp | 3a99ad281768e6ac7d4c3d769e19991a9e0954e9e6bcaab04ab2e8e0c931c390 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/129.png
shiny/back/129.png | Magikarp | a8292e2d27d59f9bcb651efd70ac839f34ca57ec3384d21e0eb6a1b0bc71f8a1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/129.png
shiny/front/130.png | Gyarados | 9034a1ae52105d19cea479d7c85ce36b0d69cfa737290f88d65d31701fce85cd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/130.png
shiny/back/130.png | Gyarados | 85e16346024e2b385ef4939e5f8a3a2c4d14b419d07b7e91105ef434849d6fbd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/130.png
shiny/front/131.png | Lapras | acd9a9f8553ed659c029f9b94d5ed08fad78cb14254c32422a448559841c8dfd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/131.png
shiny/back/131.png | Lapras | fb9de8284c2d5cf6f5240a9cb467f5a0c6334c1eb58f3a484985d379521b127e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/131.png
shiny/front/132.png | Ditto | d153071d6a2187f5610adf8867e157e8353b0bb6adda13ce692200f5025279e4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/132.png
shiny/back/132.png | Ditto | 6f758b2d64f76ba70de51b686d99a5bb730af1b3c2d841c0d4eeb08665f65b75 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/132.png
shiny/front/133.png | Eevee | b468a53e251de4acac929dee8b9066addcad1ac214d24544d3290519f9067bbf | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/133.png
shiny/back/133.png | Eevee | 85052b6d604763d85debf8bb88ac8637dbf30e2ba0af450e97875d57a18ed6e6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/133.png
shiny/front/134.png | Vaporeon | 5be3b1ed359c7c359ec9407da29dd8708a3a9a19aafe7bfee0258d07297f6ab4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/134.png
shiny/back/134.png | Vaporeon | 311850ad7b70ca40a4d8be46ef7ca8727a8e46559032c35d3d5cd1dc4cff411b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/134.png
shiny/front/135.png | Jolteon | 7e1af90e9171f33ce5d5c3d95e007e7786cd386e615693db1ca2a1ee96439079 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/135.png
shiny/back/135.png | Jolteon | b37cc5858236d583d4dc7443f86e21fc2f7f4474188342c4eddfac718fb64a69 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/135.png
shiny/front/136.png | Flareon | 132625a591efa03f49f91aa78305b1bb2dd7e8dc7613d0d9f6372dc54d075813 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/136.png
shiny/back/136.png | Flareon | 79a4d06d631948ca22bf6c2ff4fa62a16fc6e4344f6bce9603f8b8c424d0cd2a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/136.png
shiny/front/137.png | Porygon | bc330c952383cccbebae9c787c6a2377be95240e0a8eead8922dc3b0bb650161 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/137.png
shiny/back/137.png | Porygon | 7f9621629ea37073541ebcf59c992efb729d1c0e511947e025515941430169c0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/137.png
shiny/front/138.png | Omanyte | 345c1519f4ade02f1249214d23f438c5888252e3945523d92721d986f655a137 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/138.png
shiny/back/138.png | Omanyte | a738d1131c233196ec201bdf88d5eb3e11ee944a2f86bd9fff8a3e907d8c3603 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/138.png
shiny/front/139.png | Omastar | ed6cf616919eef8e0712ecbfb5b139eaa8d732ea0dc0604945d53ad11b0eaea6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/139.png
shiny/back/139.png | Omastar | dbabe99050a21d1a79563145dd0e0beaaad348b329095e55c1acb83fd8c8d2b8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/139.png
shiny/front/140.png | Kabuto | 7202fe353de8df4845eacfb17b544fd6a4daad44b467981677323f3f32d54974 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/140.png
shiny/back/140.png | Kabuto | 9d13decbaca2f2ce3480122b731cb7955c3ad78b13894f5e67f2d0d77cd97708 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/140.png
shiny/front/141.png | Kabutops | 5be03f45c060adcb92e59cb9703061303a43f1dd0f868331d569dff5e498a409 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/141.png
shiny/back/141.png | Kabutops | 89c1732b017f142d3d6e6227d50c853f3168a4c52676789cb60109f56c6f9235 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/141.png
shiny/front/142.png | Aerodactyl | 3e0012232d8f067f1ad13d7190966841432233ebac4daa690f4442b3bb64b3ac | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/142.png
shiny/back/142.png | Aerodactyl | 2d2545f83d8d2d5cd4a1cd5ee85c5d5424da54c6716b8917b1c95b938f0f4e7e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/142.png
shiny/front/143.png | Snorlax | fd47579d3763f90d6228f365de7ba828c0b56c2f9bd212ef35f874926424cfd2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/143.png
shiny/back/143.png | Snorlax | 23b8262e9313478734a8499a5ae6e4b6323e4fc41c5ef1416bf8f72ae5c4faed | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/143.png
shiny/front/147.png | Dratini | cbeee3bac80944fe3bafc71ccbb86a97a3ebb0b25c8115f963c753afc652d6a9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/147.png
shiny/back/147.png | Dratini | 0ed0d2d893576657b47561c2044a6c00e13ee5edc9bd8dc30a46787e0cb435a5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/147.png
shiny/front/148.png | Dragonair | 78869748da73e2107c2b59905af6550c66bb7f022a9e9a5368adccc59142c506 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/148.png
shiny/back/148.png | Dragonair | 1dd96ab4d4bb65444367a57b63f1718b0b304acfe0682ce406d0c06fab84b6a0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/148.png
shiny/front/149.png | Dragonite | f72633c877b1f9de6e3bcd4a820ed046efe7f7255d32ca28e185570680ba2f57 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/149.png
shiny/back/149.png | Dragonite | 570822520420a723957dc7f533768e52017e19d68d1eac9b8f95e46fa4387f20 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/149.png
shiny/front/150.png | Mewtwo | 0b16f3fc6a8cb560aeadfe9514c13a63da92092985659b8844d496abc80380a9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/150.png
shiny/back/150.png | Mewtwo | 8282e64cad154bc5b6e9e6f187b3570313febeed825f80f06ac125ed1d588b78 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/150.png
shiny/front/151.png | Mew | 43b52df11916d48ab569258ae2eec86e45ac0cd85567fe0a86db29601004989d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/shiny/151.png
shiny/back/151.png | Mew | 0f35ed50721cd000869fab3cd9fc6ae721318ccf256df9ef61db4e0e5264f6d5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/shiny/151.png

## assets/pokemon/SOURCES.txt

FireRed/LeafGreen front and back sprites from the PokeAPI sprite repository.
Repository: https://github.com/PokeAPI/sprites
Front asset path: sprites/pokemon/versions/generation-iii/firered-leafgreen/{id}.png
Back asset path: sprites/pokemon/versions/generation-iii/firered-leafgreen/back/{id}.png
Downloaded 2026-09-30. Original 64 x 64 transparent PNG files, unchanged.
The six matching starter sprites reuse the originals already in assets/starters.
Pokemon names and artwork belong to their respective rights holders.
Stored locally for offline gameplay; no network requests occur during the game.

Coverage: all currently named species in the game's starter, wild, evolution, Gym, League, and debug data.
1: Bulbasaur
2: Ivysaur
3: Venusaur
4: Charmander
5: Charmeleon
6: Charizard
7: Squirtle
8: Wartortle
9: Blastoise
10: Caterpie
11: Metapod
12: Butterfree
13: Weedle
14: Kakuna
15: Beedrill
16: Pidgey
17: Pidgeotto
18: Pidgeot
19: Rattata
20: Raticate
25: Pikachu
26: Raichu
27: Sandshrew
28: Sandslash
31: Nidoqueen
34: Nidoking
35: Clefairy
36: Clefable
37: Vulpix
38: Ninetales
41: Zubat
42: Golbat
43: Oddish
44: Gloom
45: Vileplume
46: Paras
47: Parasect
51: Dugtrio
58: Growlithe
59: Arcanine
64: Kadabra
65: Alakazam
68: Machamp
69: Bellsprout
70: Weepinbell
71: Victreebel
72: Tentacool
73: Tentacruel
74: Geodude
75: Graveler
76: Golem
77: Ponyta
78: Rapidash
84: Doduo
85: Dodrio
87: Dewgong
89: Muk
91: Cloyster
94: Gengar
95: Onix
96: Drowzee
97: Hypno
100: Voltorb
107: Hitmonchan
109: Koffing
110: Weezing
112: Rhydon
114: Tangela
120: Staryu
121: Starmie
122: Mr. Mime
129: Magikarp
130: Gyarados
131: Lapras
133: Eevee
134: Vaporeon
135: Jolteon
136: Flareon
142: Aerodactyl
149: Dragonite

Power Plant event sprite additions — 2026-10-02
Original FireRed/LeafGreen 64x64 transparent PNGs, unchanged.
Source: https://github.com/PokeAPI/sprites; original artwork belongs to its respective rights holders.
Stored locally for offline gameplay.
front/81.png | Magnemite | d6f750cdb4513a6d19a0aec9335f55442a7bfa7b62f320ae6dc4242a030c295b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/81.png
back/81.png | Magnemite | 8ff227801555a951394de33f51b2c78da6f711ee7b441f759989c9394eac4004 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/81.png
front/125.png | Electabuzz | bcb9e4790b4bdd2cfbcae4dfead5ccb44160646c1eac741d6b4c8fdd6c26f241 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/125.png
back/125.png | Electabuzz | d831e1dc3ac0455206af567c0d1dd4cdd1c21d30c647a0b881b470034dc28559 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/125.png
front/145.png | Zapdos | 1eafdea0501cb6cad51f65af39f329f8052c07957f7eb227b48fc60cdd13ba3d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/145.png
back/145.png | Zapdos | 71fc5f8ba6815a9b15d1cfeb40833897e3760834ddf4f66f9f5f2c3069cc1773 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/145.png

Victory Road event sprite additions — 2026-10-02
Original FireRed/LeafGreen 64x64 transparent PNGs, unchanged.
Source: https://github.com/PokeAPI/sprites; original artwork belongs to its respective rights holders.
Stored locally for offline gameplay.
front/66.png | Machop | 1bba54a7cb2d169a9b23a6810d7f0760cf348629ee02a724542e369a06f5d0ed | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/66.png
back/66.png | Machop | d69a3d5f178ffa7e96f8d01e0aaad4fbf856947563eafa31271b67170a25c558 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/66.png
front/146.png | Moltres | baf8fdfcfe8ab9e9ae67de83f847edd1c4f519cea329ef859c55816729c75db0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/146.png
back/146.png | Moltres | ae32457c718db91d171d152a74c6dd83ab3f7ccb4a147495d51d77768dbece07 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/146.png

Seafoam Islands event sprite additions — 2026-10-02
Original FireRed/LeafGreen 64x64 transparent PNGs, unchanged.
Source: https://github.com/PokeAPI/sprites; original artwork belongs to its respective rights holders.
Stored locally for offline gameplay.
front/86.png | Seel | 71808d9a9d5481b70c139c8463736fdde7bd05c2a9e4179c68a412dc98e77f35 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/86.png
back/86.png | Seel | adeba8c4ee20340fad9d49e8cb074f52a5ba97038e7935a1febc0791c1a1ea57 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/86.png
front/144.png | Articuno | 514896da354b744692f43894df3e369cf315f2f1d45c90972ac1a4e302cc9ef8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/144.png
back/144.png | Articuno | f564c900cb373ac9eb574320d5e734eccfb69d2b87f2701622fcecc27dd7d5af | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/144.png

Complete Kanto 151 normal sprite coverage — 2026-10-03
Original FireRed/LeafGreen 64x64 transparent PNGs, unchanged.
Source: https://github.com/PokeAPI/sprites; original artwork belongs to its respective rights holders.
Stored locally for offline gameplay.
front/1.png | Bulbasaur | 523c5d50a673c3a46a68a96bd32a63fcfae9192637fb6407198a43746c38f7e3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/1.png
back/1.png | Bulbasaur | 86c9f369b71e831de04ce6964bc9b62a6b8a82cad5309c0fa0fdbd96c3acb805 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/1.png
front/2.png | Ivysaur | 8805361d6c2f5d46890d18a16c9e3f9d638ccc7ae26e7b68dedf1d6258bb32f5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/2.png
back/2.png | Ivysaur | 1e87d4889d0da8c4dc2c12d50335e0b2831cfa04bc914846205f3217008a2510 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/2.png
front/3.png | Venusaur | bfc3f6ba4c13b211f9f91942c0d252be67cb04390967eb17193e9ab9ff24467b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/3.png
back/3.png | Venusaur | 9f9d24f450871168912d56d4c10ebda586df29ec6cf1a0fcddd5b85f8bb909f2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/3.png
front/4.png | Charmander | 0235fcad1ca309f303947ae1688d7564636971c30a0c707b6ee123e697f76022 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/4.png
back/4.png | Charmander | e5753a2daeb132a71971b93b1abf4efd653816825138b53fb866ec05fabfcaa1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/4.png
front/5.png | Charmeleon | d4fcc3d239674c98e8db95643d8e02f4a4817c61f87ac8405d476dece000ecab | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/5.png
back/5.png | Charmeleon | b710f3f5b37c7e9fb9fe4acfad5478ea1d45637727909fcd74cc3a7b62ee1d40 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/5.png
front/6.png | Charizard | 2896ad7b2231bb914ad5109a24b6d25443af738cb48ab232d8feb1a5d35882d2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/6.png
back/6.png | Charizard | dc97e1d1ec1e10e41945656c8fcfd316fc4c1f2ed67e8231c407b5859427d516 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/6.png
front/7.png | Squirtle | 30d6413a70495a23d4af23a941bae57f5373f7b6fec1e05eb8ef78a0636898bc | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/7.png
back/7.png | Squirtle | 97d8ea70ffad0a9d189388c600f1c3f979cc6733ee5d03672b95f860c2976d1b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/7.png
front/8.png | Wartortle | a01c0d8bdcdaa5b0c8e3c4f82b3284a29642196a24e1a1d37ef23b622aa452b6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/8.png
back/8.png | Wartortle | 0f5e7c9581f2374602c2ef56a9917a3b65b88550a7e477cb3c875350f289b254 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/8.png
front/9.png | Blastoise | d5a2a13fd2887003a98ed9656927bb7a95b83b9cf1078d68fb4a2b1f5b8fcc77 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/9.png
back/9.png | Blastoise | 732e95e17378f25e3a9f301f193b9ec9df44187a116c92b1c36728cb7a60782b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/9.png
front/10.png | Caterpie | b744770221a976558e56677c6d37577d3a74e8fca40fcf1f4710070c2750dd4a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/10.png
back/10.png | Caterpie | b02e71bb4034e9b5f0cfbd96370b9019ecfcb253a981007a0ea4325e2c8cf050 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/10.png
front/11.png | Metapod | 6a5490ff9c8396102ed8f53fe0b13a44fdec31c7fb9e7c0a7c4b8470255f8b42 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/11.png
back/11.png | Metapod | cd77b69c2162823a26eea3a6f10210aa1ee73078fa113efeba6d51e60cb3d2ba | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/11.png
front/12.png | Butterfree | 8c585036c073df2fd4c51a9c1384b0af4b8a855e80f293b1eb374ffd612c8471 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/12.png
back/12.png | Butterfree | 6f54ba8ca6bfacea143a230572021588072a2747f3d4d23bccf42471a698dedd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/12.png
front/13.png | Weedle | 9ee9225c4b1bba90d4aa78b33f8757fa4282a6ad7b81df62fa371f570176a9bd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/13.png
back/13.png | Weedle | 22391334ec26f06a218af43cb64d33b62a656b61e38210df416f82d2f10bb381 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/13.png
front/14.png | Kakuna | c4b35f0538d9cb18ae20d32ddfa8d0e778638ab96a1bbeed89a70339f1b17a9f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/14.png
back/14.png | Kakuna | 02d0a01600464e7460cbea1d84ee8ef31b0d6be2dafec219d3105c5821cb563e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/14.png
front/15.png | Beedrill | 86ff4125366e827f8e29011d45a7ccad807c08cc2376570bb8981b9bf4e73c68 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/15.png
back/15.png | Beedrill | 00d5591a0eacb23573f4a88399911dde60ed718bf15179c10e5dfa396e9a8d9e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/15.png
front/16.png | Pidgey | 14508ecd9bba58857442c7cfb8dd7ce322489f06c7618d92b72b5eb6a95b8da4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/16.png
back/16.png | Pidgey | 4dddfe44164e71bf2517a3cf761486c4dd0d4cd02823bf1962f79957a18230c2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/16.png
front/17.png | Pidgeotto | 8d58b7cae35d662640bff82415833f6a3de23f378ed6ed24344da382ea6213c6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/17.png
back/17.png | Pidgeotto | 1f893196f5ebb0c85aca184cca3a71163e3c5d2b0f990a49f71d1a1907245525 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/17.png
front/18.png | Pidgeot | fc23443ebfb3847fae9c009e6eb7955b3aa8191c7c25d6d775e34f88f0ff3daa | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/18.png
back/18.png | Pidgeot | 9be05e2cb8804420f83944f02314095c485e8d44c0a00713c87c12fb756bc004 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/18.png
front/19.png | Rattata | 5c2d6f950e1bc082fb9915d1cbdf87a83ee2d996873fdb27526a08fe3680b6de | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/19.png
back/19.png | Rattata | 7b954b8373e6a042c23674550ce640c325b563f65794f285b799369639cd390a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/19.png
front/20.png | Raticate | 84b8ef2d8328751521a4812a067e83c7c9be275ce36b157e863e8bf45e8d5955 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/20.png
back/20.png | Raticate | 272a13e8d0dd985fb1a3f66100e9d84b1775cd9ba6e339e61f02879322b4d46d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/20.png
front/21.png | Spearow | 1e276b5104fe736f8261e21ede30aafc522182425e5518914f6ddff5f8d76ce4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/21.png
back/21.png | Spearow | ada79c072c54c5faf11be9a8c9e77af98bc6695d221b0d173249d0b657d6c349 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/21.png
front/22.png | Fearow | 29cd362bb3a5cf5f01e2bfddf5dedbaeffa6312a39fdaa83d4d8e1b475ba4a1c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/22.png
back/22.png | Fearow | 544b30c74d6bf53d0ca19d3ea0c572f1a2235d11fe5a584d2e46bbea7dfbaec0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/22.png
front/23.png | Ekans | eb86c0898709489fb7739d5681d0ab3a450e9b2f576dcc5c3a9c97d46091c4d5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/23.png
back/23.png | Ekans | 72f69c4e822d5de7efe095d7d4948d4d8a8c9e0cc7ee427b6497d4f4b376e66f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/23.png
front/24.png | Arbok | bf295cb2c77f0cb96e6b1fc772165cc90f7b8b90b4463862e569a11c1a4ed326 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/24.png
back/24.png | Arbok | 2905cb1a5fb62f6a3b04d6d6264e90ace147ca3379af5dd6ceeaf81a54737e33 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/24.png
front/25.png | Pikachu | 49e9816a16c0c886233e25d9b91f7ee86ac5083c93aa973a9b210528555f72ec | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/25.png
back/25.png | Pikachu | 0c0f50a5be4074b7fffbc04359449a264b4700f27160db8a013dd6153a22cecc | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/25.png
front/26.png | Raichu | af6a86a41a69993fc3fad0e60d6c3b4d3281d9267c3e7029b69e7420100ac2cd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/26.png
back/26.png | Raichu | c0d64f605da3fabe0f1cb9fa011bfc184bf7155bdde3d3300c4ca96755d4ed88 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/26.png
front/27.png | Sandshrew | 8c96ee76ce61a52e9bff9765e1dad952e3bc4bf09932e88aa87496d49a9e4dfe | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/27.png
back/27.png | Sandshrew | 1a17dc8dc6179a5758c138ee3495e66c7919a6562553bbfc971e412dda1c410b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/27.png
front/28.png | Sandslash | 7d04e663db25d0d021839f443728738735f1c709c6127049fd3255ef2a791f1b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/28.png
back/28.png | Sandslash | 5f16a9773653a080bedbfe038739b7ef377462057cdcac3c47bde30fae9c6a48 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/28.png
front/29.png | Nidoran♀ | 5d95155bf6cd1dbc700458ccd6411ef3d4cb90f7e11b1925ce5b07b2188a3746 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/29.png
back/29.png | Nidoran♀ | 877a96d757ccf23f318cf0ecb87215c84fe2510ba9e79c1fc4f4409f5b268e2a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/29.png
front/30.png | Nidorina | c720069bd795b768c99479a082330196032fa922719e6f77f279144a07a23632 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/30.png
back/30.png | Nidorina | 095f2b61fc8ee6c89ee7d6e5acdc9078a295bd68f2da675cddb8b6b784ec839f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/30.png
front/31.png | Nidoqueen | a7e4a0752da32d42b8c9f3996f5b48c24152c49d204decd44989b98f38d23be6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/31.png
back/31.png | Nidoqueen | 9e29ac6f012dc0b92cf526a66f0b66a45c48da0b7f48f13f56bfb93f0399e060 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/31.png
front/32.png | Nidoran♂ | 2852bbb4baa49ea46e9b4e0a29aeb6be4bc0b8e473feb3dae6b2ebf2060a49b7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/32.png
back/32.png | Nidoran♂ | 49fe88c51f08d0bd91dada5a318d5ec40626583ce6471ab8f35f4bccc0e51d37 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/32.png
front/33.png | Nidorino | 8c0529387e81788a062deb78fda647e7a474a1789e653f4d42d0b4deae79bcb9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/33.png
back/33.png | Nidorino | c7128fe6e16179e15cbc3b46cdc163c208dafc00e7999ac292d04e0a62bc1f60 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/33.png
front/34.png | Nidoking | 6fb59244a962d9ecbd9e6ea47972ebe2b9509848b3697ae47e85839e1ecaa8e4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/34.png
back/34.png | Nidoking | ce70e0c9ce9351ca4d5743e009ec8e2d068b59162f53b6339f40745ea83b0d05 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/34.png
front/35.png | Clefairy | cbc6812a0213613fbbbe255320ac9829e8bfccd20bdfcf2ef1cdff8d78d1694f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/35.png
back/35.png | Clefairy | f3ce7d94015d15698642cd5ae6f379d2c0f66490db3ad4744d4a4da188557cd4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/35.png
front/36.png | Clefable | e71329b76f2eefb453917eb72b82a1e41437c933447778d960a0404880130198 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/36.png
back/36.png | Clefable | 9d9e79e004cce1ca53f3fb9362a3b4689476efc5ca4141bf199fbc670753675a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/36.png
front/37.png | Vulpix | 41ea68136056ebec56142b9c2f2fe8c8c70558d2f0f358dadf8d31f4a598d48f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/37.png
back/37.png | Vulpix | afaf7e3c561de9cf6b58f5eb1aa36b11470d1493939152def7aca4018f432643 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/37.png
front/38.png | Ninetales | 1dee112ffcfe6c1239c9247cab74973f5651b8d6394ad6eb2a5cd517cd899953 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/38.png
back/38.png | Ninetales | 54d97fb39bcd54f7a77e8651e337d46af8e0ce4cfdab8789dd28b8a8e9fb7ef7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/38.png
front/39.png | Jigglypuff | 8f9189b80976246f8e62d22969b963d96ae2a3f7e1476ed8a979b569e722a758 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/39.png
back/39.png | Jigglypuff | 5142d8874f3d0944843d4c7a6cc02c4859f26c98114b90d20fdc849181fca05f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/39.png
front/40.png | Wigglytuff | ffa81342af0ff60f4eb9670962a2e26c002d9d19cfa1fca1713730ae9d72ef77 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/40.png
back/40.png | Wigglytuff | 1bcab8aab027122525a6656eb352d3675db3ea5cd4af3b7e1c519a1e87c8a88f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/40.png
front/41.png | Zubat | 4cd2c5803d87cc7b7a1e870038aa3d95d59596fa2fe782dbbe289490b263e510 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/41.png
back/41.png | Zubat | 5ca5b07d9055d9054456386ae64d6ee22c6e8d18f7e778832f23f086f2892903 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/41.png
front/42.png | Golbat | ece5bd941920e24a39de25d6cb8ce9e4023b9aeaf499a736d194f9d59181e4c1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/42.png
back/42.png | Golbat | efdf96f9435d68e144d465f6a193856c88e6b10f0ad5078e3fec58f6283c5e2c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/42.png
front/43.png | Oddish | 715312c9b27426ec2b6399661ae57155b989c4c05deb82799ab3d87e6429edd2 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/43.png
back/43.png | Oddish | 5729b51805600bd0907d37ae8f8c132b9de932ac49429a6d6a72a73d31a82c92 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/43.png
front/44.png | Gloom | f7c44ea822e5d351f59c9ed914a157cb5e3bb7b4728196ebe0d8b66b6e1827b8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/44.png
back/44.png | Gloom | 58e4dcdb5d8746463f199191a8d2f3b13cb876b9b544334a3b4003a446ae73f0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/44.png
front/45.png | Vileplume | 242ef44251829f0ea6ab979e8472d9e9a3755f6bf19ea6f2bfa9a08f98fed117 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/45.png
back/45.png | Vileplume | 8f71b6f0f0255b34e807c4e1904f4c357daf0920622bcad16a989836b0fc562b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/45.png
front/46.png | Paras | d76b3d616d9562072e7a6af3eb6c0eed0dae72896283f2801b192271c4244621 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/46.png
back/46.png | Paras | 96892120bd88e0c8dfd0e010c163fa1fc0172c191f7e5fff4199ae497e4fb0ec | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/46.png
front/47.png | Parasect | 676927540ed34862840f600ba71b2e50ad1a415ab8b9d8bdf57382489d06e7e5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/47.png
back/47.png | Parasect | 252c0639104b30c2ae358c9d23cf2ece97411bae4c821946069d1ac9163b38ce | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/47.png
front/48.png | Venonat | 189f733da03ee3f59e77be057f0d3de8b35c570ca321239d51e05c302c13d565 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/48.png
back/48.png | Venonat | 1e0d6a57baab9d39241b9512a2122adaddf05715e5a467c8f84a4587640fbf89 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/48.png
front/49.png | Venomoth | b1b4b9cebea058c30fac72f6f7f14fb04b7300cfeaee0510c0497bb2b38059bb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/49.png
back/49.png | Venomoth | cb1886b2ac307f2ca70850b134b460727fc7452a75cbd4bf7f9aa009e7a0437d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/49.png
front/50.png | Diglett | e97aa686e573a270817e348f6022e8ad59396fdde976b4001815229a28aaef62 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/50.png
back/50.png | Diglett | 6f4b563b62c0079d52ab0f8d7f4ab8a0b19f668a63934d599d18a62768332d86 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/50.png
front/51.png | Dugtrio | b50e38a76a00e487d74f8a5f690a2e6116ae04b10104833577af8e7e35635482 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/51.png
back/51.png | Dugtrio | ee8f9dcadd1386ac266cc254b52544cef6552976e2cb64e373004eecd39e3cac | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/51.png
front/52.png | Meowth | 0a7f87b804c27cbad10b56ec98a976df9b7a713709cfe7416b9636c4186b363b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/52.png
back/52.png | Meowth | d7422f72e3d6b2dd289d2636600b96cb2d83dc9b5ad352c4973fa6e2f980fb26 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/52.png
front/53.png | Persian | 8b8286b0ec59f14937ca8c1005a7961e3a3559a4f80a9d55f6a5355d3617d0f3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/53.png
back/53.png | Persian | 9fd75a52e8bb4a40df4e971c5bea1b76ecbf59496e037cded4479dd6a32c4d3d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/53.png
front/54.png | Psyduck | 924ec9da2611ee500ac5af290e5276f4fa7dae8b3af4190a48f6136fdbf30eaf | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/54.png
back/54.png | Psyduck | d52f45ea2c36ec302a3ed56ec61260836bba11aca0290b19ff7ca71e57ceb338 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/54.png
front/55.png | Golduck | 45fc4e244fb9bd05ca95e7f90624266b2f88981332cf062cfbb53c8eee10fd0f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/55.png
back/55.png | Golduck | 5d25678fbad73bcd91f7f45b2e3ad53c2dfa5ebeea3e616191f68efdb3d8a8a9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/55.png
front/56.png | Mankey | da03832c776ed4302f452ec49a6d60720d06c238fee294a95bc441e33d5128ef | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/56.png
back/56.png | Mankey | 4bab91dc36e31ab46017a10c664f25e28f7e4faaf77ff69a3f50b36c8d025b03 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/56.png
front/57.png | Primeape | 8f8b46cb7793c6af3bcb2c77fee52725c9438ae91fd3ceacf9f0434cbf3bf0da | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/57.png
back/57.png | Primeape | 0cfcbbbe3a321b2066a62d21d7a0030749fab1fedfe7330abed1ad8728e2e3f8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/57.png
front/58.png | Growlithe | 1af43df18840da7033fd6b31b5017df0ea48e11281eaa9c543c80218a6bac0dc | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/58.png
back/58.png | Growlithe | bf10d41c3fbb1666a9941bcfe16a48526d224d2b477e5f951bf7817351456152 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/58.png
front/59.png | Arcanine | 23b096f8dc0b66b09a848fdd7058682747a2fbbd842fde97e791aced3815a3ab | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/59.png
back/59.png | Arcanine | 73e11346a87ae85a41f3c5754c129f9198585e77dc43332eb8e9aac7b23c227f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/59.png
front/60.png | Poliwag | 234f76b5fb2bf7610973a2177727dd660ee7b93b927933f1781f272a7d163531 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/60.png
back/60.png | Poliwag | d9c53cbd7c157963918a873d54c44be185ced199e87c2c68e001980414f7cd0f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/60.png
front/61.png | Poliwhirl | 5f90a1ba5bb199d76f478264b64ffc08185a0820321e5aee1819ab024eff6e7f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/61.png
back/61.png | Poliwhirl | faae11ecdc0ee32c69896c52b3e1aad9e24cc78a2e5aa112d19e2b0d094e41a0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/61.png
front/62.png | Poliwrath | f55344f9c4c9fa44885420015b066dee9ed9694705e867f2175fd5207d850ecd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/62.png
back/62.png | Poliwrath | 181c82dea8a767f376dcadf68b522fa5e316b35846e9784bd9aaa300b111d4da | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/62.png
front/63.png | Abra | b4a72562bd1ecb892f620cc180f9bd2da4d3d6a8ee75ddda8bb6196c5e77f4d3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/63.png
back/63.png | Abra | f35e34c2758b22cf4158b23d71838fcd8b38a8276cdf290cfd8832043b5fdc8d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/63.png
front/64.png | Kadabra | 03cb7b93219852d42c5a6cc6637e8e6aa56bf7dede1560a6bb56bc0795f6ad76 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/64.png
back/64.png | Kadabra | a6677a78bb4bbb2c9cbb3e516e62e894b76b16e1eca3cbdde73cc08ecce37efc | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/64.png
front/65.png | Alakazam | 2158d2e2818ad618b14d677beaf9e0c59c5bb19b7945096ec0c69cf79b8b9831 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/65.png
back/65.png | Alakazam | 5f0618e8dd4b63f26719e86fc5b5e69646d6235ffb31f8ae95cc150d4933cdf8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/65.png
front/67.png | Machoke | 32feca433b6b53edc1ae6e5053b446636fc25c4158f9cc992f21be9a0f227914 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/67.png
back/67.png | Machoke | dd2258c9471c6b21bcecc16ade8a3e4464b83d17c6a448a724f24adc31c9f5ad | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/67.png
front/68.png | Machamp | eba22204b29744e92d98248c6e37f5f13339017aa80df19d32dff914f28ad0a9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/68.png
back/68.png | Machamp | 994504c8f8237be52b2dbd2cac164bb4a20404b5c6e2c5b977d3234e6cd68ec8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/68.png
front/69.png | Bellsprout | 00ea8ace96153ef2c864331d36ef20b24f2df469dca88ee9477f6ae99e271792 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/69.png
back/69.png | Bellsprout | 2c1d6c9a4ceed6231e163ffa4be658cf892d3f74b75b941be0a558bfc5a15445 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/69.png
front/70.png | Weepinbell | 6682125708ac9238abb9526f1d3ac2de044f8df323c470014a82f19ae3b8a85d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/70.png
back/70.png | Weepinbell | 0d608bb2aa793d3993885afe0b425cbeb76a281434c4dee27d72daf2fc34adcc | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/70.png
front/71.png | Victreebel | 22401b25207cb1ef368f2e6316bec8e0c2d724ddba8612c7b2a80fbc29cf73d4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/71.png
back/71.png | Victreebel | 6b3a439589d4a1ee9a32987f3ac09ea7ecbb9d0aaea9a0312a6d3d6eab10622b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/71.png
front/72.png | Tentacool | da79a852531f7e09bff4f61ea81d43961bd7ef16c698ecc2131f1418515c1d62 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/72.png
back/72.png | Tentacool | 45b753f2d455692c4d332a40db03fcdd5c25012ce83897500b424b7d7cda3f9c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/72.png
front/73.png | Tentacruel | 7d63b1c53364c82b71aad1a0c272336d91237ae01720f3803a9bd887e6b52779 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/73.png
back/73.png | Tentacruel | 2c7ad44a3cb34a2789cb6dc2029e99256d3e9d1d79e9e929cd9c98691e0a2983 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/73.png
front/74.png | Geodude | 58fd3d3a5a480c0f813ef116381681753d85e8f90224ee02fb16740deac34d19 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/74.png
back/74.png | Geodude | 49597d2d0758a8a69588b515494dde8d9f3dd2c72abbe10f1c827304580e44a6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/74.png
front/75.png | Graveler | 8ba45c4022c0db399fe4aa82faab4be560e6d028bc5fddaa066afc3e453b384c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/75.png
back/75.png | Graveler | f6b920d9fc14292e38f895790288ebc0569950b4d807f6e4fb3e65a8899f9665 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/75.png
front/76.png | Golem | 3fbd93054e52166ab3d8347750ad6c37523e8498fd0c161cdc4273fc46b01ccb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/76.png
back/76.png | Golem | b68e2461fc8e0bb0da75f02a09c15aecd9a82cd5e187de39f5e25cdf691b0498 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/76.png
front/77.png | Ponyta | 0f05da39a3c90a880631adf1f48c57469ee17f1da0edb715b3143d4369726870 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/77.png
back/77.png | Ponyta | 7da1267149e67abdadfbab3c547943db425ab3db6304ceef590cc849f68d4552 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/77.png
front/78.png | Rapidash | 7eab5524ba5af5be8df1e9f5c041b247a8a6afa47b109d3b88794c5b42695c85 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/78.png
back/78.png | Rapidash | 5dfb0d0caab6e984dc58a2207bfeec12e50add09e42c0bb2b8a25352a96110e3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/78.png
front/79.png | Slowpoke | 25ef8b0709c042419a235f8f07d98e6a7c0fd8decdbb5878897b6bfd86082808 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/79.png
back/79.png | Slowpoke | 33433ea6484d762d7dc2ef214bdf7ac2a418e9179a1eadfaeecb68db9f32c951 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/79.png
front/80.png | Slowbro | b5322c2fd9351a022703034e20d73cc38c440e1e54d8ec29a1bd465ec930d128 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/80.png
back/80.png | Slowbro | da05a56dea6599c582965fe9498213c45979f232a091c327fd5397298789929d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/80.png
front/82.png | Magneton | 982e9f8e39117fc511e7c96235b316dc02c4ef25ab46f4cf633cc7981acdff61 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/82.png
back/82.png | Magneton | a7334336a8e75ec4014b0ee6fce020209b059279b7aeadca8bee2d16c856a556 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/82.png
front/83.png | Farfetch'd | 2d12000866b9a53d7b165d39cf2e588cba22cebd0941198bbdfc302d4bed9c0b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/83.png
back/83.png | Farfetch'd | a046cea958a2a1397a77f724c6f0a2a00e18f345b43fb62238b7f4d135d21206 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/83.png
front/84.png | Doduo | 1fe4a895af2364ed210842da8636665feca14da020667b23d38a6ebdc33f0f37 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/84.png
back/84.png | Doduo | b89ad3ca6b24c1548a22e3cbaf0307cde05ce7f3564c23d8c58b5ab185783c04 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/84.png
front/85.png | Dodrio | 8c7fd6755829ef083cea59f4287e13f4869358e362e17e9dc46e560e04eda8b9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/85.png
back/85.png | Dodrio | 322be93d553da463640964e481284ad61240f8c14e40ec960862458eb3c73bab | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/85.png
front/87.png | Dewgong | f906985daa21b77ce441e1b3930f8b65d29e5dd57538ea31020dde52e51d228e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/87.png
back/87.png | Dewgong | 08ab27426d2c70762befea62e80dd1c4397d5c820c6113d2e5111b03f93dc2f7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/87.png
front/88.png | Grimer | 0ed6417c5107daa8b27853b71300d8562201a0a7daad8ccb6b35b60226c6e932 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/88.png
back/88.png | Grimer | c0f992df82f9c791c1eba264472a59bb63506a1c94d202430b949e8493cc6d8c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/88.png
front/89.png | Muk | dc5fd46472fa92d8d2d054a8a079b0465a234ee3e6fef036d1064a03f7eecc48 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/89.png
back/89.png | Muk | 7122cf69d3d1c9d9ebec3fb65cf2cbdb5da9ed2319762968f503b5aeef55386b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/89.png
front/90.png | Shellder | 172341310bf58bd0aae57932c5b46fff11498851f8de4c54851b95ffe3a018d7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/90.png
back/90.png | Shellder | 51bffcc50b20939bcc19a9ea77d258ea6fa2e0a44c8e4cf637f31a8a498d51f9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/90.png
front/91.png | Cloyster | 953ccafb36c9f62682e1c1b7662150516bc649625983536e71b8ab7638fc9bd9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/91.png
back/91.png | Cloyster | 2346c296dbf8dcf1761effdf44bb177e069e75385ef0abb8bf6277c5ade35085 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/91.png
front/92.png | Gastly | 2ba311e52f218c49733642e8aaed45d240a1597f59f09f04b4231f6f47c10e03 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/92.png
back/92.png | Gastly | 9e2f46ef5b32d9acb8ec9fbfbec8a11ba60762f962e9fb7e6a44e2ddf750daed | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/92.png
front/93.png | Haunter | f671f2cf9b8b4f918da115aaaf3e0e09ef66f02387c9e9b554661ae21e20e350 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/93.png
back/93.png | Haunter | baf9418cfd4bbc3845413ab73b3beedcbd34a96042ba0d8d771cb07bec824666 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/93.png
front/94.png | Gengar | 516cf00380dcd1da7e2a300849e124fddbef5cf868d8e3075678635b8410fc84 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/94.png
back/94.png | Gengar | 9ac14961ad7d537177f249e24c3c6d1d04ab0cbf8e9181e0af656ae0fe803eb7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/94.png
front/95.png | Onix | e8928f6143a9c839c43bd505e574ebf19d4365610f18caaa6e3eab33bb1d7ac7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/95.png
back/95.png | Onix | 5b9d2a71f10c85c0d0a646de53f5b431fc7099677dbdaddd3fff7dda824bec22 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/95.png
front/96.png | Drowzee | 583ed929104dff5876235178934550cda4ba4063a6f5bf86883cc2f21e17e498 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/96.png
back/96.png | Drowzee | 81158838e88e93928c4080d4517be40e11e36c43968cb9e75aed13f6448f66fa | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/96.png
front/97.png | Hypno | 96ed3b57428d6bb33cee45d2d5ff663f160f069e0e9e5ea7ecdff42bcdca482d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/97.png
back/97.png | Hypno | ba1d5df86122f65be84ecf6b80341f6e0c6f388ca27234bb5b86818c20abc1cd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/97.png
front/98.png | Krabby | dce337819a912ee8cd5d8586b9956009aeccd85304b3b5ef75f4a1c29939ac7e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/98.png
back/98.png | Krabby | fee88fe9ed50f827b6ccd26e55f5eea89866e237b70087d31a48e8c62e991a56 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/98.png
front/99.png | Kingler | 246dae1a3ccc9161603e7ba0e4c288cdc98ef402b16b503eb01419e39d902a91 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/99.png
back/99.png | Kingler | 82ba43ad81c630d95ca86a8c4d730ef66161627094dbcd37953221ec4347800d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/99.png
front/100.png | Voltorb | 1aa37472be37e84778ac71e075015a2c2fa2814da76ff94be7aefa2f497dbc3e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/100.png
back/100.png | Voltorb | 71f340168de36e7aa598efe5ae50428e0391365b4152903e96eadcd16c5936f0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/100.png
front/101.png | Electrode | a3b3d1caf5ba2dc0cf6ae77636ef47ec7cc9661772dde25bb9e72e25299d7d5a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/101.png
back/101.png | Electrode | 29e154909d0b7b0fca8093f6c0ffc0902eeb9b7b006b9831c587c4ec72044a0d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/101.png
front/102.png | Exeggcute | e5ed8a4899fe20710031eb0a6efc108330c7622a59e4ee70d40ede4db7aff2fa | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/102.png
back/102.png | Exeggcute | 31f7b8bb2a6d20129149800d527f4e285f9e7857ff5ebdd8af70e2686eb6561c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/102.png
front/103.png | Exeggutor | 55bbbacfdef887569dcf6ba37152a35495580a1b4b46e9c4197439e7f236f769 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/103.png
back/103.png | Exeggutor | 1d807f73383ab5e373d203603cefd2b8d5f55092399aa98a8d502415fce88281 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/103.png
front/104.png | Cubone | f8479997c8aa5b9f2d64f423524de4a2276c292e7e53ecb661ccaef61368be72 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/104.png
back/104.png | Cubone | 05c50e7c9285953cfc1c06dca820aa027a385e231fca11ea1f1124b9fb1a1a7a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/104.png
front/105.png | Marowak | 99119499c81ec25a35ef9503b2170a80a9473e423facd352a4356eaabac23f39 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/105.png
back/105.png | Marowak | ca42b2e4e4faf511b4ca53417620b148fc509c0f97d2d55485cd8325a591bafa | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/105.png
front/106.png | Hitmonlee | 5630e8dae1fa64576d01cd2cc8fa0ff6c8b3a8d30c0df88bf8fd174f626051df | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/106.png
back/106.png | Hitmonlee | 40cf53cb1d4a9c4c1dc530e731e1aa1402a2c636198a1db9973e24bbe75333fb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/106.png
front/107.png | Hitmonchan | f1b661b4a27b79c419d32921ed37f5d8a7a086b92c49e9dc28137d7a4127dcdc | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/107.png
back/107.png | Hitmonchan | 506b52f281d36838a23552ea384ba8921cec65dc16b958dd68cdaabbf81a0378 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/107.png
front/108.png | Lickitung | b499b17048bf7941bd6efe6c794fd05ff078cf2ffa1d6ccb41a9c406a7eb3361 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/108.png
back/108.png | Lickitung | c89941a442f43cb55cbdb9afdcd0ee3a921049e6644766336c3fd191771debf6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/108.png
front/109.png | Koffing | 93fa37fb3845de613da3aa5d45ad71ae46e0aea612280032edf74d31d765888b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/109.png
back/109.png | Koffing | 7d0399837e9bf410e8e215c3e2e67420fb00729fc505afa8b382da0ae021aece | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/109.png
front/110.png | Weezing | f7450bf6af898e75c2d74a7ce48bb5e225c03d2d988f9e57a79d035926f08a69 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/110.png
back/110.png | Weezing | c6d087f3a374ca3b361d1c814bddb04cf1607650bee65cde5cd3a4ee51746525 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/110.png
front/111.png | Rhyhorn | e5869dc77d5517c399738cefafde1d5c6aaca48e8a7c43f4f3a7bfc24f95474b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/111.png
back/111.png | Rhyhorn | e7255685e433af464d84f6238a54f74114700829304f12aae13d76c356862ead | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/111.png
front/112.png | Rhydon | 2046240a62bb6e04d8f3003aaa39270da450d3b08c2eef83d52145af72973488 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/112.png
back/112.png | Rhydon | eeec87f7350ccbd28277564438daf5201f6185a04e3286242ae037458041bac5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/112.png
front/113.png | Chansey | 3526cf80a37cd841385a7ea8392ea44ee9433199c9b4d7884eefc39862c20f84 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/113.png
back/113.png | Chansey | 69d612c00990ff0bd91910c317703d0c6c6e807e76c8a37541e592c30542803b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/113.png
front/114.png | Tangela | 6643c8425e2c73a6b18692273cf92e3c04f94acb5b3c98c1575cf7590a22457b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/114.png
back/114.png | Tangela | 810749a228d467f88ed60747bbb8f508b96b5b31f5c9817afe5e811784e14c10 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/114.png
front/115.png | Kangaskhan | c65892cf4f9b054b4888c9669b1b0055a7a00639f3836ae8926a15ff60ad3717 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/115.png
back/115.png | Kangaskhan | b907a9d6ca24f8affe54b430ee1c0cc368763860c2e02066fb43b03ac1cd291a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/115.png
front/116.png | Horsea | 45caef351524c56b97e0f8f887cf41ec00f1be2f57a4a0eb877129e0e229066f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/116.png
back/116.png | Horsea | 35f8ab18086054648ae80e112c47f7312c8308cb51ee1382250480df2caeda55 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/116.png
front/117.png | Seadra | 1e5649f3fa89d1efe4df087a59b9160d1bae2ddb61d7a7f9cd4571e46a6578d8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/117.png
back/117.png | Seadra | 87b651415b24762332f7a66809181a33ee20acc5f44d96e95ae6449a7e662a08 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/117.png
front/118.png | Goldeen | b2ee0e08857195d9822449a197aff9a2eccb703a88278e0bfae430cec5f448e5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/118.png
back/118.png | Goldeen | 23c28a5564656f4eb5f53feb673e15a34bd9d9ca13bee51a6aa01f825e644b9e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/118.png
front/119.png | Seaking | de03fe27bd09420f3a1035f475f884115faafe25c97dd3edd7a0cc559889d168 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/119.png
back/119.png | Seaking | 0d55af5f78b3324403bb3778e156d7a70248eb638211e9810f10d67ea28330bb | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/119.png
front/120.png | Staryu | f86303fca52fed61d3073d4713d12b141c05b9c3d82c7e8433b7492382fdef7c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/120.png
back/120.png | Staryu | bf1c5fee9aac4ea7f54fe9572152fbeb6cd5d8e0fd4025257adbbe00dffbeee9 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/120.png
front/121.png | Starmie | 8c02a25f227c71f9c2063dda7011fc4d5cc6764417a4525915b46a2a55d99938 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/121.png
back/121.png | Starmie | 8b3dcbde89204348a9a8f58c862823ec63bd1308b72646e4313ffd5577debadc | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/121.png
front/122.png | Mr. Mime | b75554898d2fc401cdcd2165a3dd2bafe62a11e473654a3a5eb7bdf346120a64 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/122.png
back/122.png | Mr. Mime | a30eb4af3db8a390f7ae1b62c0df120221be1334f6aec4189731be9f0ca4e418 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/122.png
front/123.png | Scyther | 7eb4fef999bd1cc867e6f54858957c738a52b431cc8457a5dbfa195872ba29a8 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/123.png
back/123.png | Scyther | 0bca1031651883a6f3ac3091b1807c79a5a42d6a6a341ab9695950e6f9ea5b1f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/123.png
front/124.png | Jynx | 68fa0b6c507a35ab24bb4d118740130c368edcd61398e444523c2f88030023cd | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/124.png
back/124.png | Jynx | 86914bf90d6c1aa578461eeb960eb4975b75432f77a84da8d735eb29df8b7a05 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/124.png
front/126.png | Magmar | 8ad1697a01394dbd99e03262b5f208a43461999a75ac0c63879489dce3fb3e63 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/126.png
back/126.png | Magmar | b2cd607ecb15b1782ca297a0d63f17f97119e8fa6e6017ba07131030da96474c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/126.png
front/127.png | Pinsir | 50f6f0d08560ebbe2f12ca697a717371e56c90e51eaa1e98b8f5aa21a788f4d3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/127.png
back/127.png | Pinsir | d142452b82fc841a19ae72cbcff347b4702cc98f56025165d610886b69cb15fe | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/127.png
front/128.png | Tauros | 92dc05a6fb21673a4eda0d7ba704764a2a895c2047f404e504b35ba899d93aa1 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/128.png
back/128.png | Tauros | 6de5942b5f8d2ec9cba77581387b95bf75f3f2b3d067bf9c29d6e7e5d5e82e2f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/128.png
front/129.png | Magikarp | 5cb91302b551316fa84974ae40823f6951476c2b59ecfb0ac162c464c0be428a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/129.png
back/129.png | Magikarp | ebe3ccf5fcdd65d92a1ea9cd457caeb9ec47fffdd73e01b30080e882e4c5dbf0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/129.png
front/130.png | Gyarados | 33b7f64d4098f8d91ec176332d414b981a6e6cc68b2b44665d80353851d47a76 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/130.png
back/130.png | Gyarados | 581c344548fd28376001ec62d138a42ed92c81407fab77904b2c8ab83c22ccfa | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/130.png
front/131.png | Lapras | fb001b05934f9a8181fd2bba9a9f5e195ef4a28d94f39dfc6f0260c86cd8ae2f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/131.png
back/131.png | Lapras | 53fb9cf5da591a5741e0b8a44a655be55dcc3d3a19b6059ae1eaace8c78f501d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/131.png
front/132.png | Ditto | d85901c8fbdc2304d73b5bb349f9c0ca2b58bb9b2a0425f4dd179e2512856c6c | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/132.png
back/132.png | Ditto | d315d53f34583a2efd8c4d6ed58513869178ba330441b90504480cfd95b38535 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/132.png
front/133.png | Eevee | e570cccf3ae4be311cf9ba3abba731a2b579a71b1c837bc642d4e6cc9a20ed0f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/133.png
back/133.png | Eevee | 64dd88398c057084dde461edb047303fd1bbfa41df78ae4368127099ff57c1ae | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/133.png
front/134.png | Vaporeon | 8ee93ba0bf97942fcdfc0a2d32da8bcd1b41cc9b5026ddcd03cd5707ebdc5896 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/134.png
back/134.png | Vaporeon | 41d98e175d5d3e29fe69094ae39f7c42cdae07d38118b12438e42b0585d4a2c5 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/134.png
front/135.png | Jolteon | 7a795f6e21a720bf8a29a3fca909659708b843c02ea80372a25018a7cf311e2e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/135.png
back/135.png | Jolteon | 8d100871bb0e76541b2e6b6b49ce4df6842f336f7f102a1d98645bc110e79a4d | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/135.png
front/136.png | Flareon | 69e7a1faf82f500e2eeec03341822d468e6e662c208119e77dc332a90eedc88e | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/136.png
back/136.png | Flareon | e5815ce94044fd0f0bd050349fa1068f7391422466792e9693cbafd3fdc73b5f | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/136.png
front/137.png | Porygon | 3af512cc369a06b7942e2b38c15dcba19c20fb8119846e5665137c4d5b6bb2c7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/137.png
back/137.png | Porygon | 34f5bf4f7b69bff43a8d3e1ea5f942e154200731d434898e834b0c7033d5d306 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/137.png
front/138.png | Omanyte | eff118dbed4c20526705f224444b5b36980408bdeed49c3b09638d28e452807a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/138.png
back/138.png | Omanyte | c5454749ba33b249f6ad322f7d3557d2cce0fe44ba570aa730247f7b9a16f9e3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/138.png
front/139.png | Omastar | 8fcd0b8d93dc221063535072353d72c4a2261f507ecc59215c839914e531f107 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/139.png
back/139.png | Omastar | ad9a9e4b4d4334acf809b292c4f3b567358b08b29ff9e2ff2b09517958176a8b | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/139.png
front/140.png | Kabuto | d9e8a4521a05958671d61166207ee58439f921ade0c56e8b418ec988cbb69e30 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/140.png
back/140.png | Kabuto | 00122c09c45e98e3d5f58b6ecc21a819e1ed3a6f3754862f16c4566a018e5337 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/140.png
front/141.png | Kabutops | 3847b892fc4c58c766660c02e10bd525c192a673db8418271d486a2b72084d72 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/141.png
back/141.png | Kabutops | 9af2c50ab99acb5cb6bcd08005ca4f4e5610b4f4575cc412472c6d6d233010d0 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/141.png
front/142.png | Aerodactyl | 931cfc4f2ab6e874ccee2d7bef2257578c86881c66a8adc08a792e1a7066b418 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/142.png
back/142.png | Aerodactyl | 10798c22668f435426846465b68d0dd9a2181bc7c732f539e10804c5dd139d01 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/142.png
front/143.png | Snorlax | 0c1363928fa3fb3bda43956c99da3aa5d21e04573e7e4bec2c0cd6670f7076b7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/143.png
back/143.png | Snorlax | f8bebf4cdd44941a046fd013cb6c0c24ae4d64c13583451c38d02804e8534b8a | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/143.png
front/147.png | Dratini | 103a2f15df984d92aa75cc76e494b8804e71f84f9ebc43c15c190f0b0a4f6786 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/147.png
back/147.png | Dratini | 85f19df5fe65c2093277f7445314ed5c30dfdfff9681f175ef8bcc97c0ad1bda | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/147.png
front/148.png | Dragonair | 497526749152d62fca20f819e5ea198e3b5f456ed1ef81bf776df0199d12ec71 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/148.png
back/148.png | Dragonair | 81a1129501d77f725bc082cb476442aa74032202cca71aac5407c05fd56740d3 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/148.png
front/149.png | Dragonite | b91d92fd4a7e2291552d6e4e9e45c4f1d4cc6aec513aee78ec5a457dc0e1f4d6 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/149.png
back/149.png | Dragonite | c4bf3694c671105312da860b38fe0ebd799d0492d6af55da122b9e469a0f6013 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/149.png
front/150.png | Mewtwo | 2aca8417e5a999beb9b0ad53b6528f9bfd78ff268fc7aa44034a8d6561ae15b7 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/150.png
back/150.png | Mewtwo | 26813bc96d10be4e1a4fbbf279937982edb2433a86a100b66c0997def38d3135 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/150.png
front/151.png | Mew | 3d254c06b4ce84173e818cea810f1545b8799bbd581b39a3d739e8ac0abf3926 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/151.png
back/151.png | Mew | e3d34ed7511b8019824e7511d523dea3bf2a2bceed18094698c9809a27234b73 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/versions/generation-iii/firered-leafgreen/back/151.png

## assets/starters/SOURCES.txt

FireRed/LeafGreen front sprites from the PokeAPI sprite repository.
Repository: https://github.com/PokeAPI/sprites
Asset path: sprites/pokemon/versions/generation-iii/firered-leafgreen/{id}.png
IDs: Bulbasaur 1, Charmander 4, Squirtle 7, Pikachu 25, Clefairy 35, Eevee 133.

## assets/tiles/SOURCES.txt

FireRed/LeafGreen overworld Fly bird sprite reference.
Downloaded 2026-10-12 from the pret/pokefirered source repository.
Original Pokémon artwork belongs to its respective rights holders.

Source: https://github.com/pret/pokefirered/blob/master/graphics/field_effects/pics/bird.png
Download: https://raw.githubusercontent.com/pret/pokefirered/master/graphics/field_effects/pics/bird.png
Local unchanged source: frlg_fly_bird_original.png
SHA-256: 6b5885da142a8a75b140f8d5cbdf5d409f3573accb7f1f53f21329ffb9f318c0
PNG dimensions: 64x320, five vertically stacked 64x64 frames.
Frame zero is the bird without a trainer; later frames include the player.
Frame definition: https://github.com/pret/pokefirered/blob/master/src/data/field_effects/field_effect_objects.h
Fly effect use: https://github.com/pret/pokefirered/blob/master/src/field_effect.c

The shared BoardSpace tile renderer draws the original first-frame pixels
directly as native pixel rectangles, using its three original palette colors.
Visible region: x=17..45, y=17..46 (29x30). Palette index zero is transparent.
This keeps the original bird silhouette sharp at tile and editor zoom sizes.
No external image requests occur during gameplay.

## assets/trainers/gyms/SOURCES.json

[
  {
    "file": "brock.png",
    "source": "https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/leader_brock_front_pic.png",
    "sha256": "3972bbf25feefb2f254201dfd9f04064c631cfb25876f424af077600eceff7ea"
  },
  {
    "file": "misty.png",
    "source": "https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/leader_misty_front_pic.png",
    "sha256": "d05c808ba42fbcb036c3e2789d3876d7ca1c5f3733aeb71cc596a2a42a59a77b"
  },
  {
    "file": "surge.png",
    "source": "https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/leader_lt_surge_front_pic.png",
    "sha256": "8146442d7c2cde6abd2c9ac317d0fd5249db7fdd68925f1a0404c896523a4843"
  },
  {
    "file": "erika.png",
    "source": "https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/leader_erika_front_pic.png",
    "sha256": "0d11c7e56c527902d01c217212e91a2410d98be243030fcb3963774441b49ba6"
  },
  {
    "file": "koga.png",
    "source": "https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/leader_koga_front_pic.png",
    "sha256": "ff76be1f341d6827643a5dcf019c0b620105b373aa1692e23231d9cdc71a3e29"
  },
  {
    "file": "sabrina.png",
    "source": "https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/leader_sabrina_front_pic.png",
    "sha256": "10ab8f1a43886c45d489f13a0de6f1f7e91aa11a82d440d7d9a7ecb0cbd2967b"
  },
  {
    "file": "blaine.png",
    "source": "https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/leader_blaine_front_pic.png",
    "sha256": "32f4bc7e2376297fcd23ed29c6060b9d18f1162bd007ab051ab8ca2b773dc310"
  },
  {
    "file": "viridian_gym.png",
    "source": "https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/leader_giovanni_front_pic.png",
    "sha256": "c5859fac3adcc6c789434bfd52253f04958533dc07235ce751064eeef6b77409"
  }
]

## assets/trainers/league/SOURCES.txt

Original Pokemon FireRed/LeafGreen GenIII League trainer battle portraits.
Downloaded 2026-09-30 from the pret/pokefirered FireRed disassembly.
Repository: https://github.com/pret/pokefirered
Source directory: https://github.com/pret/pokefirered/tree/master/graphics/trainers/front_pics
All five original transparent PNG files are stored unchanged (64 x 64).
Blue uses his Champion portrait, not his earlier rival portrait.
Original Pokemon artwork belongs to its respective rights holders.
Stored locally for offline gameplay; no network requests occur during the game.

lorelei.png
Download: https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/elite_four_lorelei_front_pic.png
SHA-256: ee287707cb5a597decdec962ad5546fb25130cb71bff248bcaf95d96fd14db46

bruno.png
Download: https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/elite_four_bruno_front_pic.png
SHA-256: b4d1742c1ced243640dc155164171462fea742f29b29daf1fe798520ada2a040

agatha.png
Download: https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/elite_four_agatha_front_pic.png
SHA-256: 060ba8803315842bf3df92435685b838c23e77fa8c8acfa573ea39768fb12012

lance.png
Download: https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/elite_four_lance_front_pic.png
SHA-256: 0eb0d2493078d71bef3cbffd5097607910fbe36a5161d26ffc010e54c5f4e2ec

blue.png
Download: https://raw.githubusercontent.com/pret/pokefirered/master/graphics/trainers/front_pics/champion_rival_front_pic.png
SHA-256: 18b577f656358a48b59111fbcf88e22c90c431f0a2b32f9550a9228cf46517ce

## assets/trainers/SOURCES.txt

Original Pokemon FireRed/LeafGreen introduction portrait of Professor Oak.
Downloaded 2026-09-30 from the pret/pokefirered FireRed disassembly.
Source: https://github.com/pret/pokefirered/tree/master/graphics/oak_speech/oak
Download: https://raw.githubusercontent.com/pret/pokefirered/master/graphics/oak_speech/oak/pic.png
Original SHA-256: 0968930e1e1d3fb33b4f9ccff09e500445f2dcd002e1921f0b12d0537d8cace6
Prepared SHA-256: 63cb5f386f997b09dee8344d94afe6c43dbc9f2882f0989dc7bfffcee605b776
64 x 96 indexed pixels and original palette preserved exactly.
Palette index zero marked transparent, matching its original game rendering.
Original Pokemon artwork belongs to its respective rights holders.
Stored locally for offline gameplay; no network requests occur during the game.

## Music

The title, menu, Oak setup, encounters and map use the user-supplied Pokémon soundtrack recordings. Other prepared music sources are acknowledged above. Original compositions and recordings remain the property of their respective rights holders.
