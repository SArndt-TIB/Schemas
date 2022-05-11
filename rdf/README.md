# .xsd/.xml to .rdf

## e57m

1. Load [xml\2015_07_15_duraark_e57m_1_2.xsd](xml\2015_07_15_duraark_e57m_1_2.xsd) with OpenRefine.
2. Display as rows.
3. Apply [preparatory operations](OpenRefine\2015_07_15_duraark_e57m_1_2-xsd-prep_grel.json)
4. Apply [rdf export skeleton](OpenRefine\2015_07_15_duraark_e57m_1_2_rdf-skeleton-open-refine.json)
5. Export project to RDF Turtle.

## e57m dummy data

1. Load [xml\2015_06_03_e57m_dummy.xml](xml\2015_06_03_e57m_dummy.xml)
2. Display as rows.
3. Apply [OpenRefine\e57_dummy-data_rdf-skeleton-open-refine.json](OpenRefine\e57_dummy-data_rdf-skeleton-open-refine.json).
4. Export project to RDF Turtle.

### Known issues

1. Different treatment of return_maximum during application of OpenRefine RDF export as: <http://data.duraark.eu/vocab/e57m/return_maximum> and <http://data.duraark.eu/vocab/e57m/return_maximumP>
2. xml-sequences are not properly represented or defined in rdf schema file and rdf dummy data (could be further adressed with SHACL).
3. Cardinalities for sequences are not properly represented in rdf schema file:
   ```xml
   							<xs:element name="index_bounds" minOccurs="0" maxOccurs="1">
								<xs:annotation>
									<xs:documentation>The points in of the scans can be organized in rows, columns or by return numbers. For the respective organization form in use, minimum and maximum values need to be defined to describe the valid indices for the bounds.</xs:documentation>
								</xs:annotation>
								<xs:complexType>
									<xs:sequence minOccurs="0">
										<xs:element name="row_minimum" type="xs:integer" minOccurs="0" maxOccurs="1"/>
										<xs:element name="row_maximum" type="xs:integer" minOccurs="0" maxOccurs="1"/>
										<xs:element name="col_minimum" type="xs:integer" minOccurs="0" maxOccurs="1"/>
										<xs:element name="col_maximum" type="xs:integer" minOccurs="0" maxOccurs="1"/>
										<xs:element name="return_minimum" type="xs:integer" minOccurs="0" maxOccurs="1"/>
										<xs:element name="return_maximum" type="xs:integer" minOccurs="0" maxOccurs="1"/>
									</xs:sequence>
								</xs:complexType>
							</xs:element>
   ```
4. xml attributes minOccurs and maxOccurs have been modeled as integers with properties owl:minCardinality and owl:maxCardinality, which is violated by value "unbounded".