# llm_podgen


## Rough Overview
1. Create prompt engineering pipeline that takes user input and generates a podcast script

1. Feed podcast script into text to audio pipeline
    - Elevenlabs API is the best API for now, but there are still artefacts and randomness with each generation



## Getting Started:
1. Run the following setup 
```bash
python3 -m venv .venv
source .venv/bin/activate
# pip3 install pandas requests configparser pydub static-ffmpeg
pip install -r requirements.txt
```

2. Then run this python code in .venv
    - Its important you add this in your virtual environment
```python
static_ffmpeg.add_paths()
```

3. Rename `config_template.ini` to `config.ini` and save your api keys
1. Create a podcast script file in `data/podcast_scripts` as `<podcast_name>.txt`
    - Interviewer paragraphs should start with `**host:** `
    - Guest paragraphs should start with `**guest:** `
    - Will update to better tags later, that are not markdown lol
    - [example script](data/podcast_scripts/lavender_jiang.txt)
1. Define podcast script file name in the `pod_script_fn` variable
1. Alternative speaker ids can be found in [speakers_eleven.json](data/json/speakers_eleven.json)





## Test Case
### Health system-scale language models are all-purpose prediction engines
- [jupyter](eleven_tts.ipynb)
- Used perplexity to generate podcast script from this [publication](https://www.nature.com/articles/s41586-023-06160-y)
- [perplexity prompt](https://www.perplexity.ai/search/Write-a-podcast-MFZdS.0wRaWQBLGwQD6_8g?s=c)
- [stitched together final audio](output/audio_combined/lavender_jiang/lavender_jiang_output_audio.mp3?raw=true)



