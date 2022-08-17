### Tempuckey Dataset
Tempuckey is a temporally labeled database of hockey videos that span over more than 6.5 hours. The dataset is currently annotated with two hockey actions: *faceoff* (509 instances) and *tripping* (356 instances). There are a total of 690 videos clips; where each clip is 27 seconds long in average and contains one or multiple instances of *faceoff* or *tripping* actions. The table below provides a summary of the dataset information.

<img src="https://github.com/R2D2oid/Tempuckey/blob/master/docs/tempuckey_info.png" alt="Tempuckey Dataset Info" width="800"/>

An example *tripping* action from Tempuckey dataset is displayed below. (<span style="color:green">green</span>) indicates frames that belong to the action and (red) indicates frames that do not belong to that action.

<img src="https://github.com/R2D2oid/Tempuckey/blob/master/docs/tempuckey_tripping_example.png" alt="Tripping" width="600"/>

The videos are obtained from NHL hockey broadcasts and they contain camera movement.
The camera shots in the videos can generally be categorized into three settings: (i) close range shot; (ii) medium range shot; and (iii) far range shot. In order to enable measuring the effect of image scale, we have included the zoom settings of individual clips in the annotations. The following image displays examples of the three shot types.

<img src="https://github.com/R2D2oid/Tempuckey/blob/master/docs/tempuckey_three_shots.png" alt="Tripping" width="600"/>

In addition to the visual annotations, Tempuckey dataset includes textual descriptions from the subtitles. It is important to note the textual descriptions are not directly annotated for the actions that they contain. However, the temporal annotations of the visual content and the subtitle timestamps provide an indirect mean to infer whether the description may be referring to an action. The following table provides a few example subtitle sentences.

<img src="https://github.com/R2D2oid/Tempuckey/blob/master/docs/tempuckey_sentence_examples.png" alt="Tripping" width="600"/>


### Repo Structure

- `videos` folder includes hockey videos. A portion of the videos contain a face-off and/or a tripping event (positive videos).
The videos containing the events of interest are included in `Tempuckey_ground_truth_batchxx.csv` files along with the `start_frame` and `end_frame` when the event starts and ends.

- `annotations` folder contains the groupnd truth labels for the videos that have been manually reviewed.

- `feats` folder contains the extracted features for the clips in the `videos` folder.

- `sentence_segments` folder contains video segments (one per sentence). Their annotations (including the sentences and its start/end time within its associated video) are stored at `sentences.pkl` 
This part of Tempuckey dataset is used to evaluate the out of domain sentence detection model on Video Text Retireval (VTR) task. We generated a short video segment (clip) per each sentence in the subtitles. This format is used to create a Video Text Retreival model to retreive the videos using the sentences and vice versa.

                                                                                                                                                
