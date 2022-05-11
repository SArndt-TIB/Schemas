The transformation of [xml\2015_07_15_duraark_e57m_1_2.xsd](xml\2015_07_15_duraark_e57m_1_2.xsd) to an rdf representation ([rdf\e57m-1-2.ttl](rdf\e57m-1-2.ttl)) and the dummy data file [xml\2015_06_03_e57m_dummy.xml](xml\2015_06_03_e57m_dummy.xml) to [rdf\e57m-dummy.ttl](rdf\e57m-dummy.ttl) has been done with OpenRefine.

The files in this directory contain .json files with re-usable operations expressed in the Google Refine Expression Language (GREL).

The files serve the following purposes:
1. e57m (xsd) to e57 (rdf)
    - [OpenRefine\2015_07_15_duraark_e57m_1_2-xsd-prep_grel.json](OpenRefine\2015_07_15_duraark_e57m_1_2-xsd-prep_grel.json) > prepares the xsd-import for export as rdf
    - [OpenRefine\2015_07_15_duraark_e57m_1_2_rdf-skeleton-open-refine.json](OpenRefine\2015_07_15_duraark_e57m_1_2_rdf-skeleton-open-refine.json) > sets a schema for extracting the OpenRefine project to Turtle or RDF/XML
2. e57 dummy data (xml) to e57 dummy data (rdf):
    - [OpenRefine\e57_dummy-data_rdf-skeleton-open-refine.json](OpenRefine\e57_dummy-data_rdf-skeleton-open-refine.json)  > sets a schema for extracting the OpenRefine project to Turtle or RDF/XML