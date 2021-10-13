## DRDS Applications
Unless otherwise noted, all applications below are Open Source and run on Library IT-owned infrastructure.
* AbID
  * A custom Rails application that generates Absolute Identifiers for physical organization of materials on shelves for Princeton University Library and handles synchronization of those to ArchivesSpace
  * Status: In production
  * Public URL: https://abid.princeton.edu
  * Code Base: https://github.com/pulibrary/abid
  * Product Owner(s): Will Clements
  * Technical Liaison(s): TBD
  * Slack channel(s): #pulfalight (user-centered), #pulfalight-tech (technical)
* Annotations server
  * A proof-of-concept deployment of an annotations server with a web-based GUI for creating annotations, built on Mirador and [SimpleAnnotationServer](https://github.com/glenrobson/SimpleAnnotationServer)
  * Status: Deployed in staging
  * Public URL: https://annotations-staging.princeton.edu
  * Code Base: [Ansible playbook in princeton_ansible](https://github.com/pulibrary/princeton_ansible/blob/main/playbooks/annotations_production.yml)
  * Product Owner(s): TBD
  * Technical Liaison(s): Kate Lynch
  * Slack channel(s): #annotations-development (user-centered and technical)
* Bibdata
  * Catalog middleware for retrieving bibliographic and other useful data from our ILS
  * Status: In production
  * Public URL: https://bibdata.princeton.edu
  * Code Base: https://github.com/pulibrary/bibdata
  * Product Owner(s): Discovery Services Steering Group
  * Technical Liaison(s): Christina Chortaria
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Cicognara
  * A custom Rails application for managing metadata and discovery of the Digital Cicognara Library
  * Status: In production
  * Public URL: https://cicognara.org
  * Code Base: https://github.com/pulibrary/cicognara-rails
  * Product Owner(s): Holly Hatheway
  * Technical Liaison(s): TBD
  * Slack channel(s): #digital_library (user-centered), #cicognara (technical)
* DataSpace
  * A DSpace 5.x instance for institutional data including research data content, select Library-owned PDFs, and electronic theses and dissertations
  * Status: In production
  * Public URL: https://dataspace.princeton.edu
  * Code Base: Contractor-managed GitLab repository (contact technical liaisons for access)
  * Product Owner(s): DSpace Migration Working Group
  * Technical Liaison(s):  James Griffin, Kate Lynch, Bess Sadler
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Electronic Theses and Dissertations Process
  * Data transformation and loading processes managed by Library IT to support Special Collections annual review and publication of electronic theses, and quarterly-ish publication of dissertations in DataSpace
  * Status: In production
  * Public URLs: [Theses Collection in DataSpace](https://dataspace.princeton.edu/handle/88435/dsp019c67wm88m); [Doctoral Dissertations Collection in DataSpace](https://dataspace.princeton.edu/handle/88435/dsp01td96k251d)
  * Code Base: https://github.com/pulibrary/etd_transformer
  * Product Owner(s): Lynn Durgin
  * Technical Liaison(s): James Griffin, Bess Sadler
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Open Access Repository (OAR)
  * A DSpace 5.x instance for access and discovery of faculty publications
  * Status: In production
  * Public URL: https://oar.princeton.edu
  * Code Base: Contractor-managed GitLab repository (contact technical liaisons for access)
  * Product Owner(s): Yuan Li
  * Technical Liaison(s): James Griffin, Kate Lynch
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* OAWaiver
  * A lightweight Rails application for managing waivers for access to faculty publications in the OAR
  * Status: In production
  * Public URL: https://oawaiver.princeton.edu
  * Code Base: https://github.com/pulibrary/oawaiver
  * Product Owner(s): Yuan Li
  * Technical Liaison(s): James Griffin
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Open Publishing
  * An instance of OJS for the [Princeton Open Access Publishing Program](https://library.princeton.edu/services/open-access-publishing-program), to provide hosting for Open Access peer-reviewed journals
  * Status: In development, near launch (launching end of October 2021)
  * Public URL: https://openpublishing.princeton.edu
  * Code Base: https://github.com/pulibrary/openpublishing
  * Product Owner(s): Yuan Li
  * Technical Liaison(s): Bess Sadler
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Orangelight
  * The [Blacklight](https://projectblacklight.org/)-based front end for our Library catalog
  * Status: In production
  * Public URL: https://catalog.princeton.edu
  * Code Base: https://github.com/pulibrary/orangelight
  * Product Owner(s): Discovery Services Steering Group
  * Technical Liaison(s): Christina Chortaria
  * Slack channel(s): #catalog (user-centered), #orangelight (technical)
* Orangetheses
  * A Ruby gem for harvesting electronic theses from DataSpace to index into Orangelight
  * Status: In production
  * Public URL: N/A
  * Code Base: https://github.com/pulibrary/orangetheses
  * Product Owner(s): Lynn Durgin
  * Technical Liaison(s): James Griffin
  * Slack channel(s): #catalog or #dspace (user-centered), #orangelight (technical)
* Ouranos
  * A deployment service for PUL applications that uses [Capistrano](https://capistranorb.com/) and [heaven](https://github.com/atmos/heaven)
  * Status: In development
  * Public URL: N/A
  * Code Base: https://github.com/pulibrary/ouranos
  * Product Owner(s): TBD
  * Technical Liaison(s): James Griffin
  * Slack channel(s): #robots (deployment), #devs (technical)
* PDCDiscovery
  * A Princeton Data Commons front end for discovery of Research Data, harvested from DataSpace
  * Status: In development
  * Public URL: https://pdc-discovery-staging.princeton.edu
  * Code Base: https://github.com/pulibrary/pdc_discovery
  * Product Owner(s): Princeton Research Data Service
  * Technical Liaison(s): Bess
  * Slack channel(s): #research_data_development (user-centered), #dspace-dev (technical)
* Symplectic Elements
  * An instance of Symplectic Elements used to harvest and review open access articles to publish in the OAR; currently maintained by Library IT, hosted on OIT Windows server infrastructure
  * Status: In production
  * Public URL: https://oaworkflow.princeton.edu
  * Code Base: N/A (externally managed by Digital Science)
  * Product Owner(s): Yuan Li
  * Technical Liaison(s): James Griffin
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* ThesisCentral
  * An instance of [Vireo](https://github.com/TexasDigitalLibrary/Vireo) for managing the annual upload of student theses for inclusion in DataSpace; currently maintained by Library IT, hosted on OIT Amazon infrastructure
  * Status: In production
  * Public URL: https://thesis-central.princeton.edu
  * Code Base: https://github.com/PrincetonUniversityLibrary/thesiscentral-vireo
  * Product Owner(s): Lynn Durgin
  * Technical Liaison(s): James Griffin
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)