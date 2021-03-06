## RDSS Applications
Unless otherwise noted, all applications below are Open Source and run on Library IT-owned infrastructure.
* Annotations server
  * A proof-of-concept deployment of an annotations server with a web-based GUI for creating annotations, built on Mirador and [SimpleAnnotationServer](https://github.com/glenrobson/SimpleAnnotationServer)
  * Status: Deployed in staging and production
  * Public URL: https://annotations.princeton.edu
  * Staging URL: https://annotations-staging.princeton.edu
  * Code Base: [Ansible playbook in princeton_ansible](https://github.com/pulibrary/princeton_ansible/blob/main/playbooks/annotations_production.yml)
  * Product Owner: TBD
  * Slack channel(s): #annotations-development (user-centered and technical)
* Cicognara
  * A custom Rails application for managing metadata and discovery of the Digital Cicognara Library
  * Status: In production
  * Public URL: https://cicognara.org
  * Staging URL: https://cicognara-staging.princeton.edu
  * Code Base: https://github.com/pulibrary/cicognara-rails
  * Product Owner: Holly Hatheway
  * Slack channel(s): #digital_library (user-centered), #cicognara (technical)
* DataSpace
  * A DSpace 5.x instance for institutional data including research data content, select Library-owned PDFs, and electronic theses and dissertations
  * Status: In production
  * Public URL: https://dataspace.princeton.edu
  * Code Base: [Please see the documentation for the git repository details](dataspace/git.md)
  * Product Owner: DSpace Migration Working Group
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Electronic Theses and Dissertations Process
  * Data transformation and loading processes managed by Library IT to support Special Collections annual review and publication of electronic theses, and quarterly-ish publication of dissertations in DataSpace
  * Documentation: [Dissertation import](https://pulibrary.github.io/etd_transformer/process-dissertations.html) and [Senior Theses import](https://pulibrary.github.io/etd_transformer/process-theses.html)
  * Status: In production
  * Public URLs: [Theses Collection in DataSpace](https://dataspace.princeton.edu/handle/88435/dsp019c67wm88m); [Doctoral Dissertations Collection in DataSpace](https://dataspace.princeton.edu/handle/88435/dsp01td96k251d)
  * Code Base: https://github.com/pulibrary/etd_transformer
  * Product Owner: Lynn Durgin
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Open Access Repository (OAR)
  * A DSpace 5.x instance for access and discovery of faculty publications
  * Status: In production
  * Public URL: https://oar.princeton.edu
  * Code Base: [Please see the documentation for the git repository details](oar/git.md)
  * Product Owner: Hannah Hadley
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* OAWaiver
  * A lightweight Rails application for managing waivers for access to faculty publications in the OAR
  * Status: In production
  * Public URL: https://oawaiver.princeton.edu
  * Code Base: https://github.com/pulibrary/oawaiver
  * Product Owner: Hannah Hadley
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
* Nomisma
  * A set of Ruby scripts to generate RDF files from PUL's Numismatic data in the Library catalog frontend, for [Nomisma](http://nomisma.org/)
  * Status: Staged for production
  * Public URL: N/A
  * Code Base: https://github.com/pulibrary/nomisma
  * Product Owner: Alan Stahl
  * Slack channel(s): #catalog (user-centered), #devs (technical)
* Open Publishing
  * An instance of Open Journal System (OJS) for the [Princeton Open Access Publishing Program](https://library.princeton.edu/services/open-access-publishing-program), to provide hosting for Open Access peer-reviewed journals
  * Status: In production
  * Public URL: https://openpublishing.princeton.edu
  * Code Base: https://github.com/pulibrary/openpublishing
  * Product Owner: TBD
  * Slack channel(s): #digital_open_data_and_research (user-centered and technical)
  * [Public monitoring page](https://0f636d4c-7961-4c35-aece-0e58925491bd.site.hbuptime.com/)
  * [Backup and restore instructions](ojs.md)
* Open Books
  * An instance of Open Monograph Press (OMP) for the [Princeton Open Access Publishing Program](https://library.princeton.edu/services/open-access-publishing-program), to provide hosting for Open Access books
  * Status: In development, near launch (launching summer 2022)
  * Public URL: https://openbooks.princeton.edu
  * Code Base: https://github.com/pulibrary/openbooks
  * Product Owner: TBD
  * Slack channel(s): #digital_open_data_and_research (user-centered and technical)
* Ouranos
  * A deployment service for PUL applications that uses [Capistrano](https://capistranorb.com/) and [heaven](https://github.com/atmos/heaven)
  * Status: In development
  * Public URL: N/A
  * Code Base: https://github.com/pulibrary/ouranos
  * Product Owner: TBD
  * Slack channel(s): #robots (deployment), #devs (technical)
* PDC_Describe
  * Description application for Princeton Data Commons content and more
  * Status: In development
  * Public URL: https://pdc-describe-prod.princeton.edu (must be connected to VPN)
  * Staging URL: https://pdc-describe-staging.princeton.edu (must be connected to VPN)
  * Code Base: https://github.com/pulibrary/pdc_describe
  * Product Owner: Hannah Hadley
  * Slack channel(s): #digital_open_data_and_research (user-centered and technical)
* PDC_Discovery
  * A Princeton Data Commons front end for discovery of Research Data, harvested from DataSpace
  * Status: In production
  * Public URL: https://datacommons.princeton.edu/discovery
  * Staging URL: https://pdc-discovery-staging.princeton.edu
  * Code Base: https://github.com/pulibrary/pdc_discovery
  * Product Owner: Hannah Hadley
  * Slack channel(s): #digital_open_data_and_research (user-centered and technical)
* Symplectic Elements
  * An instance of Symplectic Elements used to harvest and review open access articles to publish in the OAR; currently maintained by Library IT, hosted on OIT Windows server infrastructure; in the process of migrating to a hosted solution with the vendor Digital Science
  * Status: In production
  * Public URL: https://oaworkflow.princeton.edu
  * Code Base: N/A (externally managed by Digital Science)
  * Product Owner: Hannah Hadley
  * Slack channel(s): #digital_open_data_and_research (user-centered and technical)
* ThesisCentral
  * An instance of [Vireo](https://github.com/TexasDigitalLibrary/Vireo) for managing the annual upload of student theses for inclusion in DataSpace; currently maintained by Library IT, hosted on OIT Amazon infrastructure
  * Status: In production
  * Public URL: https://thesis-central.princeton.edu
  * Code Base: https://github.com/PrincetonUniversityLibrary/pul-vireo
  * Deprecated Code Base: https://github.com/PrincetonUniversityLibrary/thesiscentral-vireo
  * Product Owner: Lynn Durgin
  * Slack channel(s): #dspace (user-centered), #dspace-dev (technical)
