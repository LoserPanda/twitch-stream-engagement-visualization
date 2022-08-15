# Twitch Stream Engagement Visualization

The aim of this project is to allow visualization of engagement of Twitch streaming service streams. The visualization is built based on stream chat log data which is to be introduced at section [data](#-data).

## Development

### Activating the Vritual Environment

```bash
source venv/local/bin/activate
```

or 

```bash
source venv/bin/activate
```

### Installing the Requirements

```bash
pip install -r requirements.txt
```

### Opening JupyterLab

```bash
jupyter lab
```

Then navigate to [localhost:8888](localhost:8888).

### Deactivate Vritual Environment

```bash
deactivate
```

### Close JupyterLab

```bash
ctrl+c
```

## Data

The original Twitch stream chat log dataset used in this project can be found from [Harvard Dataverse](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VE0IVQ).

### Schema of the Data

| Column | Type | Description |
| :----- | :--- | :---------- |
| body | string | Actual text for user chat |
| channel_id | int | Channel identifier |
| commenter_id | int | User identifier |
| commenter_type | char | User type |
| created_at | ISO 8601 date and time | Time of when chat was entered |
| fragments | JSON list | Chat text including parsing information of Twitch emote |
| offset | float | Time offset between start time of video stream and the time of when chat was entered |
| updated_at | ISO 8601 date and time | Time of when chat was edited |
| video_id | int | Video identifier |


## Visualizations

### Visualization Based on Chat Comment Frequency

The first visualization is based on chat comment frequency within a given time frame. The visualization is a scatter plot with number of comments on the y-axis and the time offset between the start of stream and when the comments where added.

### Visualization Based on Chat Comment Frequency and Comment Body

The second visualization is based on chat comment frequency within given time frame and accommpanied with the comment text body. The solution uses [wordcloud](https://pypi.org/project/wordcloud/) to visualize the most common words within a frequently commented time frame.
