This repository contains datasets and the extended version of the following paper

**Do Opt-Outs Really Opt Me Out?**
Duc Bui, Brian Tang, and Kang G. Shin
*In Proceedings of the 2022 ACM SIGSAC Conference on Computer and Communications (CCS)*


# Datasets

## Opt-out Policy Dataset

- Folder `optout_policy_dataset` contains datasets used to train and test opt-out policy classifiers.
    - File `multi_label_export.csv` contains labeled sentences extracted from opt-out policies of online trackers. The file has the following columns:
        - `cookie_domain`: domains of the online trackers which stated the policies.
        - `stmt`: policy statements extracted from the privacy policies of the trackers.
        - `No-data-collection`: contains value 1 if the statement is classified as `No-data-collection` opt-out policy class, or value 0 if otherwise.
        - `No-tracking`: contains value 1 if the statement is classified as `No-tracking` opt-out policy class, or value 0 if otherwise.
        - `No-data-coll.-for-oba`: contains value 1 if the statement is classified as `No-data-coll.-for-oba` opt-out policy class, or value 0 if otherwise.
        - `No-data-coll.-for-oba`: contains value 1 if the statement is classified as `No-data-coll.-for-oba` opt-out policy class, or value 0 if otherwise.
        - `No-display-OBA`: contains value 1 if the statement is classified as `No-display-OBA` opt-out policy class, or value 0 if otherwise.
        - `No-display-OBA`: contains value 1 if the statement is not classified as any of the above opt-out policy classes, or value 0 if otherwise.
    - Folder `train_data` has the files which are more convenient for using to train the opt-out policy classifiers. These files contain rows extracted from the `multi_label_export.csv` file.
        - File `No-tracking.csv` contains the `stmt` and `No-tracking` columns from `multi_label_export.csv`.
        - File `No-data-collection.csv` contains the `stmt` and `No-data-collection` columns from `multi_label_export.csv`.

- Folder `optout_cookie_dataset` contains files used to train (`train.csv`) and test (`test.csv`) the opt-out cookie classifier. Each of the files contains the following columns:
  - `name`: cookie name.
  - `value`: cookie value.
  - `is_optout_cookie`: contains value 1 if the cookie is an opt-out cookie, or value 0 if otherwise.
