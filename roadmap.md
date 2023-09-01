# Roadmap

Below is the current roadmap and timeline for RDSS, summer 2022 through January 2023. It is subject to change as needed, however it is written in markdown, so all history is recorded.

```mermaid
gantt
    title RDSS 2023
    axisFormat  %Y-%m
    dateformat YYYY-MM
    section PDC
    MVP software stabilizing: pd1,2023-05-01, 92d
    MVP testing and launch support: pd2,2023-07-31,62d
    PDC post-MVP features: pd3,2023-10-01,31d
    section TigerData
    TigerData training and MVP: td1,2023-08-08,54d
    TigerData MVP software: td2,2023-11-01,61d
    section DSpace Support
    2023 Thesis import: dsp1,2023-06-18,60d
    Sunsetting DSpace recommendations: dsp2,2023-05-01,153d
    DataSpace maintenance: dsp3,2023-05-01,245d
    OAR maintenance: dsp4,2023-05-01,245d
    section Open Publishing
    OJS maintenance: op1,2023-05-01,245d
    OMP maintenance: op2,2023-05-01,245d
```

## Past Sprints

This section documents past RDSS sprints. This documentation began in late July 2022, as a result of All-Hands RDSS team discussion.

### RDSS Sprint, 2023/08/23 - 2023/09/05 1️⃣
```mermaid
gantt
    title RDSS Sprint, 2023/08/23 - 2023/09/05
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes weekends
    section PDC
    Support for PPPL data migration: pdc1, 2023-08-23, 10d
    Public URL and VPN adjustments: pdc2, 2023-08-28, 5d
    Node upgrade: pdc3, 2023-08-29, 2d
    Honeybadger and Datadog enhancements: pdc4, 2023-08-23, 10d
    Collection arks redirect to PDC: pdc5, 2023-08-29, 3d
    UI bug fixes: pdc6, 2023-08-28, 2d
    DataSpace collections preservation enhancements and documentation: pdc7, 2023-08-23, 4d
    section DSpace Support
    Emergency service degradation response: 2023-08-28, 1d
    Dissertation XSLT improvements: 2023-08-28, 2d
    section Cicognara
    Static site enhancements: 2023-08-24, 5d
    Data index troubleshooting: 2023-08-24, 1d
    section TigerData
    Search committee work: td1, 2023-08-23, 10d
    Docker deployment enhancements and documentation: td2, 2023-08-23, 10d
    Aterm commands documentation: td3, 2023-08-23, 10d
    Rails application code cleanup and refactor: td4, 2023-08-23, 10d   
```

### RDSS Sprint, 2023/08/09 - 2023/08/22 🦑
```mermaid
gantt
    title RDSS Sprint, 2023/08/09 - 2023/08/22
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes weekends
    section PDC
    DOI and ARK management for production: pdc1, 2023-08-09, 10d
    Monitoring for Describe: pdc2, 2023-08-09, 10d
    Migration support for PPPL : pdc3, 2023-08-09, 10d
    UI bug fixes: pdc4, 2023-08-09, 10d
    File upload bug fixes: pdc5, 2023-08-09, 10d
    Describe network bug fixes: pdc6, 2023-08-09, 10d
    DataSpace collections preservation enhancements: pdc7, 2023-08-09, 10d
    section TigerData
    Search committee work: td1, 2023-08-09, 10d
    Rails deployment enhancement and documentation: td2, 2023-08-16, 5d
    MediaFlux Rails code cleanup: td3, 2023-08-16, 5d
    MediaFlux client documentation: td4, 2023-08-16, 5d
```

### RDSS Sprint, 2023/07/26 - 2023/08/08 🌊
```mermaid
gantt
    title RDSS Sprint, 2023/07/26 - 2023/08/08
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes weekends
    section PDC
    DOI and ARK management and form enhancements for production: pdc1, 2023-07-26, 10d
    Preservation enhancements: pdc2, 2023-07-26, 10d
    Globus access, documentation, training: pdc3, 2023-07-26, 10d
    Large file upload improvements: pdc4, 2023-07-26, 10d
    Indexing from Describe to Discovery: pdc5, 2023-07-26, 10d
    Migration automation work: pdc6, 2023-07-26, 10d
    Introducting notification types and dashboard: pdc7, 2023-07-26, 10d
    User dashboard security enhancements: pdc8, 2023-07-26, 10d
    DataCite publication troubleshooting: pdc9, 2023-07-26, 10d
    PPPL reporting feed fixes: pdc10, 2023-08-06, 2d
    Monitoring for Describe: pdc11, 2023-08-02, 4d
    section DSpace Maintenance
    ThesisCentral QA outage: ds1, 2023-08-06, 1d
    DataSpace outage: ds2, 2023-08-08, 1d
    Masters theses work: ds3, 2023-07-26, 8d
    Symplectic errors: ds4, 2023-07-26, 4d
    section Senior Theses
    Import Senior Theses for 2023: st1, 2023-07-26, 10d
    section TigerData
    Search committee work: td1, 2023-07-26, 10d
```

### RDSS Sprint, 2023/07/12 - 2023/07/25 🍧
```mermaid
gantt
    title RDSS Sprint, 2023/07/12 - 2023/07/25
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes weekends
    section PDC
    PPPL collections indexing: pdc1, 2023-07-12, 5d
    JSON metadata endpoint enhancements: pdc1, 2023-07-12, 10d
    Discovery Solr troubleshooting: pdc1, 2023-07-19, 3d
    Change history enhancements: pdc1, 2023-07-12, 10d
    Preservation enhancements: pdc1, 2023-07-12, 10d
    File display performance enhancements: pdc1, 2023-07-12, 10d
    Ingestion form enhancements for README, creator, licenses: pdc1, 2023-07-12, 10d
    Migration automation work: pdc1, 2023-07-17, 7d
    Help text form and page enhancements in UI: pdc1, 2023-07-12, 10d
    Indexing from Describe to Discovery: pdc1, 2023-07-12, 10d
    Email notification improvements: pdc1, 2023-07-12, 10d
    section TigerData
    Search committee work: td1, 2023-07-12, 10d
```

### RDSS Sprint, 2023/06/28 - 2023/07/11 🍒
```mermaid
gantt
    title RDSS Sprint, 2023/06/28 - 2023/07/11
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes weekends
    section PDC
    PPPL collections indexing: pdc1, 2023-06-28, 10d
    Banner posting to DataSpace: pdc2, 2023-06-28, 10d
    File upload enhancements for performance and navigation: pdc3, 2023-06-28, 10d
    File preservation experimentation: pdc4, 2023-06-28, 10d
    Migration specs enhancements: pdc5, 2023-06-28, 10d
    PPPL specs review and acceptance: pdc6, 2023-06-28, 10d
    Continued support for ROR in ingest form: pdc7, 2023-06-28, 10d
    Theming enhancements to Describe: pdc8, 2023-06-28, 10d
    README upload enhancements: pdc9, 2023-06-28, 10d
    DataSpace collections preservation work: pdc10, 2023-06-28, 10d
    section Senior Theses
    Import Senior Theses for 2023: st1, 2023-06-28, 10d
    section DSpace
    JSP bug fixes: ds1, 2023-06-28, 10d
    Import Masters Theses for May 2023: ds1, 2023-06-28, 10d
    section TigerData
    Search committee work: td1, 2023-06-28, 10d
```

### RDSS Sprint, 2023/06/14 - 2023/06/27 ☀️
```mermaid
gantt
    title RDSS Sprint, 2023/06/14 - 2023/06/27
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes weekends
    section PDC
    Banner posting to DataSpace: pdc1, 2023-06-20, 5d
    File upload enhancements for performance and navigation: pdc2, 2023-06-20, 5d
    File preservation experimentation: pdc3, 2023-06-20, 5d
    Migration specs enhancements: pdc4, 2023-06-20, 5d
    PDC preservation enhancements: pdc6, 2023-06-20, 5d
    User accounts page enhancements: pdc7, 2023-06-20, 5d
    DataSpace collections preservation work: pdc1, 2023-06-20, 5d
    section Senior Theses
    Import Senior Theses for 2023: st1, 2023-06-20, 5d
    section All Hands
    All Hands participation: ah1, 2023-06-14, 4d
    section TigerData
    Search committee work: td1, 2023-06-20, 5d
```

### RDSS Sprint, 2023/05/31 - 2023/06/13 🛴
```mermaid
gantt
    title RDSS Sprint, 2023/05/31 - 2023/06/13
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes weekends
    section PDC
    Ingest form enhancements for README and ROR support: pdc1, 2023-05-31, 10d
    File upload improvements: pdc2, 2023-05-31, 10d
    Migration specs enhancements: pdc3, 2023-05-31, 10d
    Globus authentication management: pdc4, 2023-05-31, 10d
    Admin menu enhancements: pdc5, 2023-05-31, 10d
    section DataSpace Maintenance
    Filename download fixes: dsp1, 2023-06-01, 5d
    Rotate LastPass secrets: dsp2, 2023-06-08, 2d
    section All Hands
    Poster, conference, and team meetings prep: ah1, 2023-05-31, 10d
    section TigerData
    Search committee work: td1, 2023-05-31, 10d
```

### RDSS Sprint, 2023/05/17 - 2023/05/30 🏕️
```mermaid
gantt
    title RDSS Sprint, 2023/05/17 - 2023/05/30
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC
    Ingest form updates: pdc1, 2023-05-17, 10d
    Preservation workflow: pdc2, 2023-05-17, 10d
    Large file upload improvements: pdc3, 2023-05-17, 10d
    Uptime and performance monitoring: pdc4, 2023-05-17, 10d
    section DataSpace Maintenance
    Bitstream download fixes: dsp1, 2023-05-22, 5d
    Sunsetting group work: dsp1, 2023-05-17, 10d
    section All Hands
    Poster, conference and team meetings prep: ah1, 2023-05-17, 10d
    section TigerData
    Search committee work: td1, 2023-05-17, 10d
```


### RDSS Sprint, 2023/05/02 - 2023/05/16 🐛
```mermaid
gantt
    title RDSS Sprint, 2023/05/02 - 2023/05/16
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC
    PPPL specs finalizing and reloading: pdc1, 2023-05-02, 10d
    Improvements to file import process for migration: pdc2, 2023-05-02, 10d
    Ingestion form and input formatting improvements: pdc3, 2023-05-02, 10d
    Migration specs enhancements (ORCID IDs, related DOIs, etc): pdc4, 2023-05-02, 10d
    Preservation research and development: pdc5, 2023-05-02, 10d
    Indexing records to PDC Discovery from Describe: pdd3, 2023-05-02, 10d
    section DSpace Maintenance
    DataSpace file upload issues: dsp1, 2023-05-02, 4d
    OAR file upload issues: dsp2, 2023-05-02, 4d
    Elements vendor work cleanup: dsp3, 2023-05-08, 4d
    Mudd Reading Room machines support: dsp4, 2023-05-10, 5d
    DSpace secrets review and rotation: dsp5, 2023-05-02, 10d
    section Open Publishing
    Publishing workflow troubleshooting: op1, 2023-05-02, 4d
    section Professional Development
    Samvera Virtual Connect: td1, 2023-05-02, 2d
```

### RDSS Sprint, 2023/04/05 - 2023/04/18 🐞
```mermaid
gantt
    title RDSS Sprint, 2023/04/05 - 2023/04/18
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    PPPL specs finalizing and loading: pdc1, 2023-04-05, 10d
    Feature to import DataSpace file payloads: pdc2, 2023-04-05, 10d
    Ingest status bar improvements: pdc3, 2023-04-05, 5d
    Downloadable report for PPPL/OSTI: pdc4, 2023-04-05, 10d
    section PDC_Discovery
    Indexing records to PDC Discovery from Describe: pdd3, 2023-04-05, 10d
    section Cicognara
    Static site changes: cic1, 2023-04-05, 8d
    section DataSpace Maintenance
    Dissertation loading: dsp1, 2023-04-11, 2d
    Expand ETD Transformer for new dissertation workflows: dsp2, 2023-04-05, 5d
    section ThesisCentral Emergency Work
    Database emergency service restore: tc1, 2023-04-05, 5d
    Pre-emergency restore service re-linking: tc2, 2023-04-05, 5d
    Database EC2 sustainable restore and cutover: tc3, 2023-04-10, 5d
    section TigerData
    MediaFlux documentation for local development: td1, 2023-04-05, 3d
    Refactoring Ruby code from TigerData demo: td2, 2023-04-05, 3d
```

### 2023/03/22 - 2023/04/04 🕸️ 
```mermaid
gantt
    title RDSS Sprint, 2023/04/05 - 2023/04/18
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    PPPL specs finalizing and loading: pdc1, 2023-03-22, 10d
    Feature to import DataSpace file payloads: pdc2, 2023-03-22, 10d
    section PDC_Discovery
    Add OSTI reporting endpoint specs finalizing and loading: pdcd1, 2023-03-27, 5d 
    section DataSpace Maintenance
    New dissertation loading process: dsm1, 2023-03-22, 5d  
    section ImageCat
    ImageCat Rails application development: imc1, 2023-03-22, 10d
    section IT Fellowship
    IT Fellowship interviews: itf1, 2023-03-22, 3d
```

### 2023/03/08 - 2023/03/21 🕷️ 
```mermaid
gantt
    title RDSS Sprint, 2023/04/05 - 2023/04/18
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section RDSS Retreat 
    Retreat: rdss1, 2023-03-13, 1d
    section Professional Development 
    Code4Lib 2023: c4l1, 2023-03-14, 4d
    section IT Fellowship
    IT Fellowship interviews: itf1, 2023-03-20, 2d
```

### 2023/02/22 - 2023/03/07 ☔ 
```mermaid
gantt
    title RDSS Sprint, 2023/02/22 - 2023/03/07
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    PPPL specs finalizing and loading: pdc1, 2023-02-22, 10d
    File upload improvements: pdc2, 2023-02-22, 10d
    Describe form enhancements (ROR for funders and pause/notification): pdc3, 2023-02-22, 10d
    section PDC_Discovery
    Add OSTI reporting endpoint specs finalizing and loading: pdc1, 2023-02-22, 10d       
    section TigerData
    Test MediaFlux local development: td2, 2023-02-22, 5d
    section Professional Development
    Code4Lib Preparation: td2, 2023-02-27, 5d
```

### 2023/02/08 - 2023/02/21 💝 
```mermaid
gantt
    title RDSS Sprint, 2023/02/08 - 2023/02/21
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    PPPL specs finalizing and loading: pdc1, 2023-02-08, 10d
    Improvements to S3 file upload and retrieval: pdc3, 2023-02-08, 10d
    Show page improvements: pdc3, 2023-02-08, 10d
    section DataSpace Maintenance
    Dissertation loading, January 2023: dsm1, 2023-02-08, 4d
    Enable emailing service in hosted Elements: dsm2, 2023-02-13, 5d    
    section TigerData
    TigerData project review: td1, 2023-02-08, 3d
    MediaFlux Developer 101 Training: td2, 2023-02-20, 5d
    Generate baseline Rails application: td3, 2023-02-08, 10d
    CAS authentication on TigerData app: td4, 2023-02-13, 5d
    TigerData application deployment: td4, 2023-02-08, 10d
    section Security
    OAR secrets rotation: sec1, 2023-02-08, 5d
    OAWaiver secrets rotation: sec1, 2023-02-08, 5d
    section Samvera
    Samvera Core Components Maintenance: sam1, 2023-02-08, 10d  
```

### 2023/01/25 - 2023/02/07 🎠 
```mermaid
gantt
    title RDSS Sprint, 2023/01/25 - 2023/02/07
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    DataSpace data migration and fixtures enhancement: pdc1, 2023-01-25, 10d
    Improvements to S3 file retrieval: pdc3, 2023-01-25, 10d
    Ingest form improvements: pdc4, 2023-01-25, 10d
    Ark ID validation/handling improvements: pdc5, 2023-01-25, 10d
    Globus onboarding in PRDS: pdc6, 2023-01-25, 3d
    section DataSpace Maintenance
    HR Feed Implementation for Elements: dsm1, 2023-01-25, 8d
    DataSpace preservation workflow development and testing: dsm2, 2023-01-25, 10d
    Dissertation loading, January 2023: dsm2, 2023-02-02, 4d
    New Masters Theses Collection: dsm3, 2023-02-02, 2d
    section Security
    LastPass secrets rotation: sec1, 2023-01-25, 10d
    section Samvera
    Samvera Core Components Maintenance: sam1, 2023-01-25, 10d
    section Organizational
    Annual self appraisals and goals: org1, 2023-01-25, 10d
```

### 2023/01/11 - 2023/01/24 🕯

```mermaid
gantt
    title RDSS Sprint, 2023/01/11 - 2023/01/24
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    Curator workflow improvements: pdc1, 2023-01-11, 10d
    Indexing file information to PDC Discovery: pdc2, 2023-01-11, 10d
    Globus training for new curators: pdc3, 2023-01-18, 2d
    Provenance log UI enhancements: pdc4, 2023-01-11, 10d
    Email notification system: pdc5, 2023-01-11, 10d
    section PDC_Discovery
    Deduplication of indexing between DataSpace and PDC Describe: pdd1, 2023-01-11, 10d
    Indexing file information to PDC Discovery: pdd2, 2023-01-11, 10d
    Indexing records to PDC Discovery from Describe: pdd3, 2023-01-11, 10d
    section DataSpace Maintenance
    Serials collection audit: dsp1, 2023-01-16, 5d
    ThesisCentral QA maintenance: dsp2, 2023-01-11, 10d
    section Open Source Community
    Samvera Community maintenance: osc1, 2023-01-11, 10d
```

### 2022/12/28 - 2023/01/10 🧃

```mermaid
gantt
    title RDSS Sprint, 2022/12/28 - 2023/01/10
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    Email notifications system: pdc1, 2022-12-28, 10d
    Add licenses to migration specs: pdc2, 2022-12-28, 3d
    User license acceptance workflow: pdc3, 2023-01-02, 4d
    Provenance log enhancements: pdc4, 2022-12-28, 5d
    section Open Publishing
    Upgrade OJS to PHP 8.1: ojs1, 2022-12-28, 10d
    section DataSpace Maintenance
    Matching arks to dissertation XML: dsp1, 2022-12-28, 4d
    OAR usage metrics report generation: dsp2, 2023-01-02, 3d
    IP restriction fixes for 693 Alexander: dsp3, 2023-01-05, 3d    
    section Cicognara
    Static site theming: cic1, 2023-01-02, 2d
```

### 2022/12/14 - 2022/12/27 🍪

```mermaid
gantt
    title RDSS Sprint, 2022/12/14 - 2022/12/27
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    DataSpace data migration and fixtures enhancement: pdc1, 2022-12-14, 10d
    Indexing to PDC Discovery: pdc2, 2022-12-14, 10d
    Ingest form UI enhancements: pdc3, 2022-12-14, 10d
    Adding funders to DataCite: pdc4, 2022-12-14, 10d
    section Open Publishing
    Upgrading PHP: ojs1, 2022-12-14, 10d
    section DataSpace Maintenance
    Matching arks to dissertation XML: dsp1, 2022-12-14, 4d
    section Cicognara
    Static site theming: cic1, 2022-12-19, 4d
```

### 2022/11/30 - 2022/12/13 🎄

```mermaid
gantt
    title RDSS Sprint, 2022/11/30 - 2022/12/13
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section PDC_Describe
    DataCite XML validation and fixture building: pdc1, 2022-11-30, 10d
    Production data migration preparation: pdc2, 2022-11-30, 10d
    Improvements to S3 file management: pdc3, 2022-11-30, 10d
    Ingest form improvements: pdc3, 2022-11-30, 10d
    section Open Publishing
    Upgrade OJS to PHP 8.1: ojs1, 2022-11-30, 10d
    section DataSpace Maintenance
    HR Feed Implementation for Elements: dsm1, 2022-12-07, 5d
````

### 2022/11/16 - 2022/11/29 🍠

```mermaid
gantt
    title RDSS Sprint, 2022/11/16 - 2022/11/29
    axisFormat  %Y-%m-%dd
    dateformat YYYY-MM-DD
    excludes    weekends
    section TigerData
    TigerData and MediaFlux project research: td1, 2022-11-16, 10d
    TigerData Rails application and VMs: td2, 2022-11-16, 10d
    section PDC_Describe
    Finalize DataCite fixtures: pdc1, 2022-11-16, 10d
    DataSpace data migration preparation: pdc, 2022-11-16, 10d
    section DataSpace Maintenance
    Masters Thesis Collections: dsm1, 2022-11-16, 5d
    Permissions troubleshooting and dissertation ark matching: dsm2, 2022-11-22, 3d
    Dissertation loading: dsm1, 2022-11-28, 2d
    section Cicognara
    Harvard item count troubleshooting: cic1, 2022-11-21, 4d
````


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
```

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
