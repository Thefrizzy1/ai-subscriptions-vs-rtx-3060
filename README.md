# AI subscriptions vs one RTX 3060

Everything from the the_frizzy1 video in one place: what was tested, the exact prompts, the measured numbers, and a link to every model, workflow and tool.

**The question:** if you paid for every AI tool in the video you would spend about **$304 a month**. How much of that can one RTX 3060 with 12 GB of VRAM replace for free?

**The answer in the video:** five of seven cancelled, about **$139 a month** saved.

☕ If this saved you a subscription: [Buy me a coffee](https://buymeacoffee.com/the_frizzy1)

All free workflows live here: **[The_frizzy1-Workflows](https://github.com/Thefrizzy1/The_frizzy1-Workflows)**

---

## Contents

- [The machine](#the-machine)
- [The bill](#the-bill)
- [How every test works](#how-every-test-works)
- [1. Images: GPT Image 2.5 vs FLUX 3 Klein](#1-images-gpt-image-25-vs-flux-3-klein)
- [2. Video: Kling 3.0 vs LTX 2.5](#2-video-kling-30-vs-ltx-25)
- [3. Voice: ElevenLabs v4 and Fish S2.1 Pro vs ZONOS3-Mini and VibeVoice 7B](#3-voice-elevenlabs-v4-and-fish-s21-pro-vs-zonos3-mini-and-vibevoice-7b)
- [4. Music: Lyria 3 vs ACE-Step 1.5](#4-music-lyria-3-vs-ace-step-15)
- [5. Chat: Claude vs a local model in LM Studio](#5-chat-claude-vs-a-local-model-in-lm-studio)
- [6. Higgsfield vs my swap workflows](#6-higgsfield-vs-my-swap-workflows)
- [The scoreboard](#the-scoreboard)
- [Every link](#every-link)
- [What is not measured](#what-is-not-measured)

---

## The machine

| Part | What |
|---|---|
| GPU | RTX 3060, 12 GB VRAM |
| RAM | 32 GB |
| Software | [ComfyUI](https://github.com/comfyanonymous/ComfyUI) 0.45.3, [LM Studio](https://lmstudio.ai), Chrome |

Every local number below is from this machine.

## The bill

Creator-level plans, per month, as shown in the video:

| Tool | A month |
|---|---|
| ChatGPT | $20 |
| Claude | $100 |
| ElevenLabs | $22 |
| Suno | $30 |
| Higgsfield | about $65 |
| Kling | $37 |
| Midjourney | $30 |
| **Total** | **about $304** |

The cheapest plan of each adds up to $141 a month.

The paid side was run on [OpenArt](https://tolt.link/the_frizzy1) (my affiliate link, I get a small part if you sign up; Plus plan, $34 a month for 12,000 credits), because it has GPT Image, Kling, ElevenLabs, Fish Audio and Lyria in one place. All the paid tests in the video together cost **245 credits, about 70 cents**: one image (5), one 5 second Kling clip (175), two voice clips (40), one song (25).

## How every test works

1. The paid tool and the RTX 3060 get **the same prompt**.
2. Three things are compared: how good the result is, how long it took, what it cost.
3. A verdict: **cancel** (the free version is good enough) or **keep** (the paid one is still clearly better).

Times on the paid side are OpenArt's own timestamps. Times on the 3060 are ComfyUI's "Prompt executed" line or the tool's own readout.

---

## 1. Images: GPT Image 2.5 vs FLUX 3 Klein

**Prompt**

```
A golden retriever astronaut in a white and yellow spacesuit sitting on the moon, Earth rising behind him, soft rim light, cinematic photo, 35mm lens, shallow depth of field, highly detailed fur and visor reflections
```

| | Paid: GPT Image 2.5 (OpenArt) | Free: FLUX 3 Klein on the RTX 3060 |
|---|---|---|
| Time | 12.7 s | 13.3 s warm, 256 s on the very first run (it loads every model) |
| Cost | 5 credits | 0 |

**Workflow:** [FLUX 3 Klein · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/flux/flux3-klein-12gb) (model downloads are listed in that folder). Model by [Black Forest Labs](https://github.com/black-forest-labs).

**Verdict: cancel.** GPT Image followed the prompt a little better, FLUX 3 gets very close and is just as fast once it is warm.

## 2. Video: Kling 3.0 vs LTX 2.5

**Prompt**

```
A golden retriever in a bright yellow raincoat runs through a rainy neon-lit city street at night, puddles splashing, the camera tracks alongside at dog height, cinematic lighting, shallow depth of field
```

| | Paid: Kling 3.0 (OpenArt, 5 s, 720p) | Free: LTX 2.5 on the RTX 3060 (text to video, 5 s, 1280x704) |
|---|---|---|
| Time | 7:15 | 10:04 |
| Cost | 175 credits, about 50 cents | 0 |

**Workflow:** [LTX 2.5 Ultimate · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/ltx/ltx-2.5-ultimate-12gb). Set the mode to T2V, type the prompt, 5 seconds, Run. Model by [Lightricks](https://github.com/Lightricks/LTX-Video).

**Verdict: cancel.** Kling's motion is a bit cleaner, LTX 2.5 looked more cinematic in this scene, and 7 minutes against 10 is not worth a subscription.

## 3. Voice: ElevenLabs v4 and Fish S2.1 Pro vs ZONOS3-Mini and VibeVoice 7B

| Model | Where | What | Measured |
|---|---|---|---|
| ElevenLabs v4 | OpenArt, stock voice "Adam", default settings, no tags | text to speech | 12.2 s of speech in 6.2 s, 20 credits |
| Fish S2.1 Pro | OpenArt | clone of my voice from a 20 s clip | 11.4 s of speech in 6.8 s, 20 credits |
| ZONOS3-Mini | Chrome, on the RTX 3060 | clone of my voice | 11.3 s of audio in 2.3 s, 920 MB download on the first visit |
| VibeVoice 7B, full model | ComfyUI, on the RTX 3060 | clone of my voice from a 60 s clip | one 8.4 s line took 434 s, 524 s and 640 s in three runs |

**Two blind tests in the video**

- *Which one sounds most like me?* ZONOS3-Mini, VibeVoice 7B, Fish S2.1 Pro, same sentence. My pick: **VibeVoice 7B**.
- *Which one sounds most human?* Fish S2.1 Pro, VibeVoice 7B, ElevenLabs v4, same sentence. My pick: **VibeVoice 7B**, then Fish, then ElevenLabs.

**ZONOS3-Mini in the browser:** open the [ZONOS3-Mini local playground](https://zyphra.com/zonos3-mini/localplayground/lite), pick "Your clip", upload a voice clip, "Clone voice", type the text, Generate. It runs on your own GPU through the browser. By [Zyphra](https://github.com/Zyphra).

**VibeVoice 7B in ComfyUI, step by step**

1. Install the node pack [wildminder/ComfyUI-VibeVoice](https://github.com/wildminder/ComfyUI-VibeVoice) into `ComfyUI/custom_nodes` and restart ComfyUI.
2. Put the full model [VibeVoice-7B](https://huggingface.co/vibevoice/VibeVoice-7B) (about 18 GB) in `ComfyUI/models/tts/VibeVoice/VibeVoice-7B`. The node downloads it there by itself on the first run if it is missing.
3. Build three nodes: **Load Audio** (your voice clip) into `speaker_1_voice` of **VibeVoice TTS**, and its audio output into **Save Audio**.
4. Settings used in the video: model `VibeVoice-7B`, 4-bit quantize **off** (full precision), attention `sdpa`, cfg 1.3, 10 steps, sampling off, seed 7.
5. Write the text with a speaker tag in front, for example `[1] And this is VibeVoice 7B, the full model, cloning my voice.`
6. Run. On 12 GB about 9.4 GB of the model sits on the card and the rest in RAM, which is why it is slow.

The original model is [microsoft/VibeVoice](https://github.com/microsoft/VibeVoice). There are smaller quantized versions that fit into 12 GB. To my ear they sound robotic again, so I use the full one.

**Verdict: cancel ElevenLabs.** It was a disappointment in this test, even the Fish clone sounded better to me. To be fair: v4 is their newest model and it is made to be steered with tags, and this test used a stock voice with no tags, so someone who knows the tool may get more out of it. For your own voice, the full VibeVoice 7B on your own card won both tests. You just have to wait for it.

## 4. Music: Lyria 3 vs ACE-Step 1.5

**Prompt**

```
Upbeat synth-pop song about a gamer whose old graphics card refuses to die, driving drums, warm analog synths, catchy chorus, male vocal, 118 bpm
```

| | Paid: Google Lyria 3 (OpenArt) | Free: ACE-Step 1.5 XL Turbo on the RTX 3060 |
|---|---|---|
| Time | 30 s song in 10.2 s | 30 s song in 21.7 s |
| Cost | 25 credits | 0 |

**ACE-Step 1.5 in ComfyUI:** it runs on core ComfyUI nodes, no custom nodes. Guide: [ComfyUI ACE-Step 1.5 tutorial](https://docs.comfy.org/tutorials/audio/ace-step/ace-step-v1-5). Files: [Comfy-Org/ace_step_1.5_ComfyUI_files](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files). Settings used: 8 steps, cfg 1, euler / simple, shift 3, 118 bpm, A minor, 30 seconds, style tags plus my own lyrics. Model by [ACE-Step](https://github.com/ace-step/ACE-Step-1.5).

**Verdict: cancel Suno.** I do not pay for Suno, so the paid song here is Lyria 3. It is not the same song, both sound great.

## 5. Chat: Claude vs a local model in LM Studio

**Question**

```
I have an RTX 3060 with 12GB of VRAM and 32GB of RAM. Write me a short plan for a YouTube video comparing paid AI subscriptions with free local AI, with five chapters and one honest downside for each.
```

| | Paid: Claude (Opus 5.5) | Free: Bonsai 2 27B in LM Studio on the RTX 3060 |
|---|---|---|
| Answer time | about 13 s | about 86 s, 74 of them thinking |
| Speed | not measured | 29.7 tokens a second |
| Size | | 7.6 GB file, fits on the card |

**Tool:** [LM Studio](https://lmstudio.ai).

**Verdict: keep Claude.** A local model is nice to have, and small agents can do part of the work, but in the breadth of the answers nothing on my card comes close to a frontier model.

## 6. Higgsfield vs my swap workflows

Higgsfield Plus is 59 euros a month. I did not run Higgsfield itself; this chapter shows what the free workflows do on the RTX 3060.

| What | Workflow |
|---|---|
| Swap the person in a video, whole clip, original sound | [H3 Character Swap · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/minimax/h3-character-swap-12gb) |
| An AI influencer: the same invented face in any scene | [AI Influencer · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/minimax/ai-influencer-12gb) |
| Swap with one still (Viggle remake) | [Viggle-Animate (H3)](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/minimax/viggle-animate-h3) |
| Dance and meme swaps | [SCAIL-2 Character Swap · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/scail/scail2-character-swap-12gb) |

Seedance 2.5 prices on OpenArt, for scale: 5 s at 480p is 300 credits (about $0.85, this one was run), 5 s at 720p is 650 credits (about $1.84, quoted), 10 s at 720p is 1,300 credits (about $3.68, quoted).

**Verdict: keep it if you need realism, or find Seedance 2.5 cheaper somewhere else.** For memes, swaps and an AI influencer the free workflows are enough.

---

## The scoreboard

| Tool | A month | Verdict | Free replacement on the RTX 3060 |
|---|---|---|---|
| ChatGPT (image) | $20 | cancel | FLUX 3 Klein |
| Claude | $100 | **keep** | |
| ElevenLabs | $22 | cancel | VibeVoice 7B, ZONOS3-Mini |
| Suno | $30 | cancel | ACE-Step 1.5 |
| Higgsfield / Seedance 2.5 | about $65 | keep for realism, or find it cheaper | H3 swap workflows |
| Kling | $37 | cancel | LTX 2.5 |
| Midjourney | $30 | cancel | FLUX 3 Klein |

**About $139 a month saved.** Keep only Claude and it is $204.

## Every link

**My workflows (free)**
- [The_frizzy1-Workflows](https://github.com/Thefrizzy1/The_frizzy1-Workflows), the home of all of them
- [FLUX 3 Klein · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/flux/flux3-klein-12gb)
- [LTX 2.5 Ultimate · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/ltx/ltx-2.5-ultimate-12gb)
- [H3 Character Swap · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/minimax/h3-character-swap-12gb)
- [AI Influencer · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/minimax/ai-influencer-12gb)
- [Viggle-Animate (H3)](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/minimax/viggle-animate-h3)
- [SCAIL-2 Character Swap · 12 GB](https://github.com/Thefrizzy1/The_frizzy1-Workflows/tree/main/workflows/scail/scail2-character-swap-12gb)

**Free models and tools**
- [ComfyUI](https://github.com/comfyanonymous/ComfyUI)
- FLUX 3 Klein: [Black Forest Labs](https://github.com/black-forest-labs)
- LTX 2.5: [Lightricks](https://github.com/Lightricks/LTX-Video)
- VibeVoice 7B: [model](https://huggingface.co/vibevoice/VibeVoice-7B), [ComfyUI node pack](https://github.com/wildminder/ComfyUI-VibeVoice), [original project](https://github.com/microsoft/VibeVoice)
- ZONOS3-Mini: [local playground](https://zyphra.com/zonos3-mini/localplayground/lite), [Zyphra](https://github.com/Zyphra)
- ACE-Step 1.5: [project](https://github.com/ace-step/ACE-Step-1.5), [ComfyUI files](https://huggingface.co/Comfy-Org/ace_step_1.5_ComfyUI_files), [ComfyUI guide](https://docs.comfy.org/tutorials/audio/ace-step/ace-step-v1-5)
- [LM Studio](https://lmstudio.ai)

**Paid tools in the test**
- [OpenArt](https://tolt.link/the_frizzy1) (my affiliate link): GPT Image 2.5, Kling 3.0, ElevenLabs v4, Fish S2.1 Pro, Lyria 3
- [ElevenLabs](https://elevenlabs.io)

**My videos on the single topics**
- [Free image workflow (Qwen Image 2.1 Ultimate)](https://www.youtube.com/watch?v=N7X0QBZ_r9c)
- [LTX 2.5 full setup](https://www.youtube.com/watch?v=TlV72fg9skw)
- [5 free voice clone models](https://www.youtube.com/watch?v=kr0rs2reDpA)
- [Genjutsu on a 3060](https://www.youtube.com/watch?v=zkhLZUGIIfE)
- [My free AI influencer](https://www.youtube.com/watch?v=2eaY7fs70iA)

## What is not measured

- Electricity. "$0" means no subscription.
- VRAM and RAM peaks for the voice and music runs.
- Higgsfield itself was not run.
- ElevenLabs on its own site with a tuned voice and tags. If you pay for it, tell me how it compares.
- Prices are the ones shown in the video in November 2026. Check each site before you decide.

---

the_frizzy1 on [YouTube](https://www.youtube.com/@the_frizzy1) · [CivitAI](https://civitai.com/user/The_frizzy1) · [Hugging Face](https://huggingface.co/The-frizzy1)
