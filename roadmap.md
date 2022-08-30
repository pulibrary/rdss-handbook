# Roadmap

Below is the current roadmap and timeline for RDSS, summer 2022 through January 2023.  It is subject to change as needed, however it is written in markdown, so all history is recorded.

```mermaid
gantt
    title RDSS 2022 - 2023 Roadmap
    axisFormat  %Y-%m
    dateformat YYYY-MM
    section PDC_Decribe
    Submission/curation workflow :active, pd1, 2022-08, 60d
    Metadata schema, file submission :active, pd2, 2022-08, 60d
    Research Data content reconciliation/migration :active, pd3, 2022-08, 90d
    Globus implementation :active, pd4, 2022-08, 30d
    Curation station integration: pd5, after pd4, 30d
    PDC Describe launch tasks: pd6, after pd5, 30d
    section DSpace Support
    2022 Thesis migration :active, dsp1, 2022-08, 30d
    DataSpace maintenance :active, dsp2, 2022-08, 2023-02
    OAR maintenance :active, dsp2, 2022-08, 2023-02
    section Dataspace Sunsetting
    Hosted Elements migration :active, ds1, 2022-08, 60d
    Working with embargoes in Figgy: ds2, 2022-10, 30d
    Migrating Library PDFs to Figgy: ds4, after td2, 60d
    Migrating Dissertations to Figgy/Orangelight: ds5, after td2, 60d
    Migrating Theses to Figgy/Orangelight: ds6, after td2, 60d
    PPPL OSTI reporting: ds3, after pd5,60d
    section POAPP
    OJS launch: po1, 2022-09, 15d
    OMP launch: po2, 2022-12, 15d
    section TigerData
    API spike and requirements evaluation: td1, 2022-11, 30d
    Onboarding: td2, 2023-01, 30d
    section Open Source Community Work
    N/A: os1
```

## Past Sprints

This section documents past RDSS sprints.  This documentation began in late July 2022, as a result of All-Hands RDSS team discussion.

### 2022/08/15 - 2022/08/26

```mermaid
gantt
    title RDSS Sprint, 2022/08/15 - 2022/08/26
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section 2022 Theses
    Import to DataSpace and enhance metadata: th1, 2022-08-15, 10d
    Thesis form fixes: 2022-08-15, 3d
    section DSpace Support
    IP range fixes: 2022-08-17, 4d
    section PDC_Describe
    File handling: pd1, 2022-08-15, 10d
    DataCite implementation and ingest form: pd2, 2022-08-15, 10d
    DOI handling and approval workflow: pd2, 2022-08-15, 10d
    State machine backing: pd2, 2022-08-15, 10d
    section OpenPublishing
    OJS launch prep: ojs1, 2022-08-22, 3d
    section DataSpace Sunsetting
    Elements migration: 2022-08-15, 10d
```


### 2022/08/01 - 2022/08/12

```mermaid
gantt
    title RDSS Sprint, 2022/08/01 - 2022/08/12
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section 2022 Theses
    Import to DataSpace: th1, 2022-08-01, 10d
    section DSpace Support
    EZID fixes: 2022-08-11, 1d
    section Emergency Response
    Secrets leak fixes: 2022-08-10, 2d
    section PDC_Describe
    File uploading: pd1, 2022-08-01, 5d
    DataCite implementation and ingest form: pd2, 2022-08-01, 10d
    Globus staging and production deployment: 2022-08-01, 10d
    section OpenPublishing
    OJS launch prep: ojs1, 2022-08-01, 5d
    section DataSpace Sunsetting
    Elements migration: 2022-08-01, 10d
```

### 2022/07/18 - 2022/07/29

```mermaid
gantt
    title RDSS Sprint, 2022/07/18 - 2022/07/29
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section All-Hands
    ITIMS All-Hands Week: ah1, 2022-07-18, 5d
    section 2022 Theses
    Import to DataSpace: th1, 2022-07-25, 5d
    section PDC_Describe
    File uploading: pd1, 2022-07-25, 5d
    DataCite: pd2, 2022-07-25, 5d
    Globus staging deployment: 2022-07-25, 5d
    section DataSpace Sunsetting
    Elements migration: 2022-07-18, 10d
```
