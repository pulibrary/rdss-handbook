## RDSS Applications
Unless otherwise noted, all applications below are Open Source and run on Library IT-owned infrastructure.
* Annotations server
  * A proof-of-concept deployment of an annotations server with a web-based GUI for creating annotations, built on Mirador and [SimpleAnnotationServer](https://github.com/glenrobson/SimpleAnnotationServer)
  * Status: Deployed in staging
  * Public URL: https://annotations-staging.princeton.edu
  * Code Base: [Ansible playbook in princeton_ansible](https://github.com/pulibrary/princeton_ansible/blob/main/playbooks/annotations_production.yml)
  * Product Owner(s): TBD
  * Slack channel(s): #annotations-development (user-centered and technical)
* Cicognara
  * A custom Rails application for managing metadata and discovery of the Digital Cicognara Library
  * Status: In production
  * Public URL: https://cicognara.org
  * Code Base: https://github.com/pulibrary/cicognara-rails
  * Product Owner(s): Holly Hatheway
  * Slack channel(s): #digital_library (user-centered), #cicognara (technical)
* DataSpace
  * A DSpace 5.x instance for institutional data including research data content, select Library-owned PDFs, and electronic theses and dissertations
  * Status: In production
  * Public URL: https://dataspace.princeton.edu
  * Code Base: Contractor-managed GitLab repository (contact technical liaisons for access)
  * Product Owner(s): DSpace Migration Working Group
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Electronic Theses and Dissertations Process
  * Data transformation and loading processes managed by Library IT to support Special Collections annual review and publication of electronic theses, and quarterly-ish publication of dissertations in DataSpace
  * Documentation: [Dissertation import](https://pulibrary.github.io/etd_transformer/process-dissertations.html) and [Senior Theses import](https://pulibrary.github.io/etd_transformer/process-theses.html)
  * Status: In production
  * Public URLs: [Theses Collection in DataSpace](https://dataspace.princeton.edu/handle/88435/dsp019c67wm88m); [Doctoral Dissertations Collection in DataSpace](https://dataspace.princeton.edu/handle/88435/dsp01td96k251d)
  * Code Base: https://github.com/pulibrary/etd_transformer
  * Product Owner(s): Lynn Durgin
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Open Access Repository (OAR)
  * A DSpace 5.x instance for access and discovery of faculty publications
  * Status: In production
  * Public URL: https://oar.princeton.edu
  * Code Base: Contractor-managed GitLab repository (contact technical liaisons for access)
  * Product Owner(s): Yuan Li
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* OAWaiver
  * A lightweight Rails application for managing waivers for access to faculty publications in the OAR
  * Status: In production
  * Public URL: https://oawaiver.princeton.edu
  * Code Base: https://github.com/pulibrary/oawaiver
  * Product Owner(s): Yuan Li
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Nomisma
  * A set of Ruby scripts to generate RDF files from PUL's Numismatic data in the Library catalog frontend, for [Nomisma](http://nomisma.org/)
  * Status: Staged for production
  * Public URL: N/A
  * Code Base: https://github.com/pulibrary/nomisma
  * Product Owner(s): Alan Stahl
  * Slack channel(s): #catalog (user-centered), #devs (technical)
* Open Publishing
  * An instance of OJS for the [Princeton Open Access Publishing Program](https://library.princeton.edu/services/open-access-publishing-program), to provide hosting for Open Access peer-reviewed journals
  * Status: In development, near launch (launching end of October 2021)
  * Public URL: https://openpublishing.princeton.edu
  * Code Base: https://github.com/pulibrary/openpublishing
  * Product Owner(s): Yuan Li
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
  * [Public monitoring page](https://0f636d4c-7961-4c35-aece-0e58925491bd.site.hbuptime.com/)
  * [Backup and restore instructions](ojs.md)
* Ouranos
  * A deployment service for PUL applications that uses [Capistrano](https://capistranorb.com/) and [heaven](https://github.com/atmos/heaven)
  * Status: In development
  * Public URL: N/A
  * Code Base: https://github.com/pulibrary/ouranos
  * Product Owner(s): TBD
  * Slack channel(s): #robots (deployment), #devs (technical)
* PDCDiscovery
  * A Princeton Data Commons front end for discovery of Research Data, harvested from DataSpace
  * Status: In development
  * Public URL: https://pdc-discovery-staging.princeton.edu
  * Code Base: https://github.com/pulibrary/pdc_discovery
  * Product Owner(s): Princeton Research Data Service
  * Slack channel(s): #research_data_development (user-centered), #dspace-dev (technical)
* Symplectic Elements
  * An instance of Symplectic Elements used to harvest and review open access articles to publish in the OAR; currently maintained by Library IT, hosted on OIT Windows server infrastructure
  * Status: In production
  * Public URL: https://oaworkflow.princeton.edu
  * Code Base: N/A (externally managed by Digital Science)
  * Product Owner(s): Yuan Li
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* ThesisCentral
  * An instance of [Vireo](https://github.com/TexasDigitalLibrary/Vireo) for managing the annual upload of student theses for inclusion in DataSpace; currently maintained by Library IT, hosted on OIT Amazon infrastructure
  * Status: In production
  * Public URL: https://thesis-central.princeton.edu
  * Code Base: https://github.com/PrincetonUniversityLibrary/pul-vireo
  * Deprecated Code Base: https://github.com/PrincetonUniversityLibrary/thesiscentral-vireo
  * Product Owner(s): Lynn Durgin
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
