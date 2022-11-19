# OptOutCheck

This repository contains datasets and the extended version of the following paper

**Do Opt-Outs Really Opt Me Out?** [[Download](https://dl.acm.org/doi/abs/10.1145/3548606.3560574)]
Duc Bui, Brian Tang, and Kang G. Shin
*In Proceedings of the 2022 ACM SIGSAC Conference on Computer and Communications Security (CCS ’22), November 7–11, 2022, Los Angeles, CA, USA. ACM, New York, NY, USA, 19 pages.*

## Datasets

### Opt-out Policy Dataset

- Folder `optout_policy_dataset` contains datasets used to train and test opt-out policy classifiers.

    - File `multi_label_export.csv` contains labeled sentences extracted from the privacy policies of online trackers. The file has the following columns:
        - `cookie_domain`: contains domains of the online trackers which stated the policies.

        - `stmt`: contains policy statements extracted from the privacy policies of the trackers.

        - `No-data-collection`: contains value 1 if the statement is classified as `No-data-collection` opt-out policy class, or value 0 if otherwise. A sentence of this class means that opting out will stop data collection via third-party cookies.

        - `No-tracking`: contains value 1 if the statement is classified as `No-tracking` opt-out policy class, or value 0 if otherwise. A sentence of this class means that opting out will stop the tracking of users' activities via third-party cookies.

        - `No-data-coll.-for-oba`: contains value 1 if the statement is classified as `No-data-coll.-for-oba` opt-out policy class, or value 0 if otherwise. A sentence of this class means that opting out will stop data collection of users' activities for targeted advertising.

        - `No-display-OBA`: contains value 1 if the statement is classified as `No-display-OBA` opt-out policy class, or value 0 if otherwise. A sentence of this class means that opting out will stop the display of targeted advertising to users.

        - `other`: contains value 1 if the statement is not classified as any of the above opt-out policy classes, or value 0 if otherwise.

    - Folder `train_data` has data files that are more convenient for training the opt-out policy classifiers. These files contain rows extracted from the `multi_label_export.csv` file.

        - File `No-tracking.csv` contains the `stmt` and `No-tracking` columns from `multi_label_export.csv`.
        - File `No-data-collection.csv` contains the `stmt` and `No-data-collection` columns from `multi_label_export.csv`.

- Folder `optout_cookie_dataset` contains files used to train (`train.csv`) and test (`test.csv`) the opt-out cookie classifier. Each of the files contains the following columns:
  - `name`: contains cookie names.
  - `value`: contains cookie values.
  - `is_optout_cookie`: contains value 1 if the cookie is an opt-out cookie, or value 0 if otherwise.
