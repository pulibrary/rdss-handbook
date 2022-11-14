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

### 2022/11/02 - 2022/11/15 🌼

```mermaid
gantt
    title RDSS Sprint, 2022/11/02 - 2022/11/15
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section TigerData
    MediaFlux desktop client exploration: td1, 2022-11-02, 10d
    MediaFlux aterm/Ruby exploration: td1, 2022-11-02, 10d
    TigerData and MediaFlux project research: td1, 2022-11-02, 10d
    section PDC_Describe
    Finalize DataCite fixtures: pdc1, 2022-11-02, 10d
    DataSpace data migration preparation: pdc1, 2022-11-02, 10d
    section Open Source Community
    Samvera Community maintenance: osc1, 2022-11-10, 3d
````

### 2022/10/10 - 2022/11/01 🎃

This was the beginning of a new sprint cycle framework, hence the slightly longer timeframe.

```mermaid
gantt
    title RDSS Sprint, 2022/10/10 - 2022/11/01
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    File downloads with Globus: pd1, 2022-10-10, 10d
    Email notifications: pd2, 2022-10-10, 10d
    ORCID support for contributors: pd3, 2022-10-10, 10d
    DataCite implementation and ingest form: pd4, 2022-10-10, 10d
    PPPL Migration Kick-off Planning: pd5, 2022-10-17, 5d
    section DSpace support
    Add arks to dissertations for Alma: dsm1, 2022-10-17, 5d
    Masters thesis collections support: dsm2, 2022-10-10, 3d
    Embargo troubleshooting: dsm3, 2022-10-13, 2d
    section PDC_Discovery
    Solr node repair: pdc1, 2022-10-18, 2d
    section DataSpace Sunsetting
    Elements migration wrap-up and testing: dss1, 2022-10-10,8d
```

### 2022/09/26 - 2022/10/07 🚌

```mermaid
gantt
    title RDSS Sprint, 2022/09/26 - 2022/10/07
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    File handling: pd1, 2022-09-26, 10d
    DataCite implementation and ingest form: pd2, 2022-09-26, 10d
    Improved error handling: pd3, 2022-09-26, 10d
    Indexing to PDC Discovery: pd4, 2022-09-26, 10d
    Globus trust root: pd5, 2022-09-26, 10d
    section OpenPublishing
    OJS launch prep and translation support: ojs1, 2022-09-26, 4d
    section Cicognara
    Item count troubleshooting and version support: 2022-10-03, 3d
    section DSpace support
    New collections and users: dsm1, 2022-09-26, 5d
    OAR cleanup: dsm2, 2022-10-04, 2d
    section DataSpace Sunsetting
    Elements migration: dss1, 2022-09-26, 10d
    section Open Source Community
    Blacklight Summit: osc1, 2022-10-03, 3d
```

### 2022/09/12 - 2022/09/23 🍂

```mermaid
gantt
    title RDSS Sprint, 2022/09/12 - 2022/10/23
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    Launch plan: pd1, 2022-09-12, 10d
    DataCite implementation: pd2, 2022-09-12, 10d
    Submission form improvements: pd3, 2022-09-12, 10d
    Storage workflow: pd4, 2022-09-12, 10d
    ARK and DOI handling: pd5, 2022-09-12, 10d
    Collection save and show: pd6, 2022-09-12, 10d
    section DataSpace Sunsetting
    Elements migration: dss1, 2022-09-12, 10d
```

### 2022/08/29 - 2022/09/09 🚂

```mermaid
gantt
    title RDSS Sprint, 2022/08/29 - 2022/09/09
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    File handling: pd1, 2022-08-29, 10d
    DataCite implementation and serialization: pd2, 2022-08-29, 10d
    Submission workflow: pd2, 2022-08-29, 10d
    Test suite improvements: pd2, 2022-08-29, 10d
    section DSpace support
    Mudd IP Range Fixes: dsm1, 2022-09-05, 4d
    2022 Thesis Reports for Alumni/Donor records: po2, 2022-09-05, 4d
    section DataSpace Sunsetting
    Elements migration: dss1, 2022-08-29, 10d
    section Professional Development
    Product Owner Training - September Cohort: po1, 2022-09-06, 3d
    section OpenPublishing
    Translation and theme support: ojs1, 2022-09-06, 4d 
```

### 2022/08/15 - 2022/08/26 🍔

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


### 2022/08/01 - 2022/08/12 🍉

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

### 2022/07/18 - 2022/07/29 🫐

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
