# Temporal Localization of Narrated Actions in Vlogs

This repository contains the dataset and code for our todo_conf paper:
[When did it happen? Duration-informed Temporal Localization of Narrated
Actions in Vlogs](todo_arxiv)

## Task Description
![Example instance](images/annotation_example.jpg)
<p align="center"> Given a video and its transcript, temporally localize the human actions mentioned in the video. </p>

## Dataset 
![Example instance](images/model_idea.jpg)
<p align="center">Distinguishing between actions that are narrated by the vlogger but not visible in the video
and actions that are both narrated and visible in the video (underlined), with a highlight on visible actions that represent the same
activity (same color). The arrows represent the temporal alignment between when the visible action is narrated as well as the time it
occurs in the video.</p>

### Annotation Process
1. The extraction of actions from the transcripts and their annotation of *visible/ not visible* in the video 
is described in detail in this [other project](https://github.com/OanaIgnat/vlog_action_recognition).
2. The visible actions are temporally annotated using this [open source tool](https://github.com/OanaIgnat/video_annotations) that we built.

## Data format
The temporal annotations of the visible actions are available at [`data/dict_all_annotations_ordered.json`](data/dict_all_annotations_ordered.json).
The visibility annotations of the actions are available at [`data/miniclip_actions.json`](data/miniclip_actions.json) and you can read more about 
the process in the [other project](https://github.com/OanaIgnat/vlog_action_recognition).

The miniclip name is formed by concatenating its YouTube channel, playlist, video and miniclip index. For miniclip "4p1_3mini_5.mp4":
* 10 = __channel__ index
* p0 = __playlist__ index (0 or 1) in the channel
* 10 = __video__ index in the playlist
* mini_2 = __miniclip__ index in the video

The visible actions are assigned a start and end time at which they are localized in the miniclip. This does not necessarily
correspond to the time the actions are mentioned in the miniclip.

Example format in JSON:

```json
{
  "10p0_10mini_2.mp4": [
    ["go to first start by and shred up your kale", 26.0, 32.0],
    ["place this into a large bowl", 27.0, 31.0],
    ["break down the cell walls of the kale", 41.0, 51.0],
    ["give it a good massage with your hands", 41.0, 50.0],
    ["add in your butter lettuce", 52.0, 55.0]
  ]
}
```
## Citation


# Run the code

## Setup
* I recommend creating a python virtualenv 
```bash
pip install -r requirements.txt
```

## Data requirements


## Usage
1. Check [`args.py`](args.py) to set the arguments
2. 


