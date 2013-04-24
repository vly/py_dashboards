
# Database structure #

The following is the initial document layout.

| key | definition |
| --------|:--------:| 
|uuid | auto generated |
|name	| title of the report |
|description | description of the report|
|introtext | describes content of the report|
|execsummary	| report executive summary |
|owner	| platform user|
|subscribers | recipients of the report ... subscriber-list|
|report_type | bau, project, adhoc|
|report_frequency	| one-off, weekly, monthly, quarterly, annually|
|report_template	| output template... default is table display|
|report_sectioncount	| counter of sections|
|report_created	| date of creation|
|report_lastran	| last report run date |
|report_definitions | annotations, jargon, notes, context|

report_sections : [{section_title		// section title
					section_description	// section description
					section_position	// location of report relative to other ones
					section_type		// shifting (offsets with reoccuring runs), cumsum, custom
					section_parts 		// number of parts making up this report
					section_display		// visualisation used
					section_datasource 	// google analytics, omniture, facebook, twitter...
					section_definitions // annotations
					parts_config : [{part_label // label of the data set (used for index)
									part_request : {startdate, // contextual configs based on section_datasource
													enddate,
													metrics,
													dimensions,
													filters
													segments
													order}
								 }]
					}]

report_data : [{report_date: '2013-02-01', 			// example of data store, easier to insert via $push
				dataset : {report_section_1 : ,
							report_section_2
						  }
			   },
			   {report_date: '2013-01-01',
			    dataset : ...
			   }]
