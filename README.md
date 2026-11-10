# Chinese-Traditional-Music-Short-Video-Dissemination-Dataset
### File List

* **users.csv**: User node attributes (`user_id, account_type, region, join_time, followers_count`)
* **music.csv**: Music node attributes (`music_id, title, instrument, tempo_bpm, mode`)
* **videos.csv**: Video node attributes (`video_id, author_id, description, instrument, genre, region, dialect, music_id, create_time, video_url, plays, likes, comments, shares, hashtags`)
* **video_tags.csv**: Video–tag edges (`video_id, tag`)
* **video_music.csv**: Video–music edges (`video_id, music_id`)
* **edges_user_follow.csv**: User–user follow edges (`src_user_id, dst_user_id`)
* **edges_user_interactions.csv**: User–video interaction edges (`user_id, video_id, interaction_type, timestamp`)
* **cascades.csv**: Propagation cascade samples (`video_id, source_author, layer, user_id, timestamp`)
* **video_split.csv**: Time-based dataset split (`train/val/test`)

### Suggested Tasks

1. **Propagation Popularity Prediction (Regression/Classification)**
   Use video features, author features, and early-stage interaction data to predict propagation outcomes such as **plays, likes, comments, and shares**.

2. **Propagation Cascade Depth Prediction / Node Infection Probability Prediction**
   Use the **cascade data** and **user follow graph** to train Graph Neural Network (GNN) models for predicting cascade depth or the probability that a user/node will participate in the propagation process.

3. **Cultural Tag Recognition**
   Perform **multi-label classification** based on attributes such as `instrument`, `region`, `genre`, and `dialect`, together with textual information from video descriptions.

4. **Recommendation Task (User → Video Link Prediction)**
   Use the **user follow graph** and **user–video interaction edges** to perform link prediction for personalized video recommendation. Suitable models include **GraphSAGE, GAT, and HGT**.
