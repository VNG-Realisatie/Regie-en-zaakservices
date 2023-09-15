---
layout: page-with-side-nav
title: Documentatie Regie- en zaakservices
folder_files:
  - title: Koppelvlakspecificatie Regie-zaak services v1.0 (pdf)
    path: documenten/Koppelvlakspecificatie_Regie-zaak_services_v1.0.pdf
    group: 10
    versie: 1.0
    status: Definitief
    omschrijving: 
    datum: 20151102
  - title: Regie- en Zaakservices - versie 1.0 - schemas (zip)
    path: documenten/Regie-zaak.zip
    group: 10
    versie: 1.0
    status: Definitief
    omschrijving: 
    datum: 20151102
  - title: Testset Regie- en Zaakservices (zip)
    path: documenten/Testset_Regie-_en_Zaakservices.xlsx.zip
    group: 10
    versie: 1.0
    status: Definitief
    omschrijving: 
    datum: 20160411
---

# Documentatie

## Regie- en zaakservices 1.0

<table>
	<thead>
		<tr>
			<th>Document</th><th>Versie</th><th>Beheerstatus</th><th>Beschrijving</th><th>Versiedatum</th>
		</tr>
	</thead>
	<tbody>
		{% for i in page.folder_files %}
			{% if i.group == 10 %} 
				<tr>
					<td>
					  <a href="{{ i.path | base_url }}">
						{{ i.title }}
					  </a>
					</td>
					<td>{{ i.versie }}</td>
					<td>{{ i.status }}</td>
					<td>{{ i.omschrijving }}</td>
					<td>{{ i.datum }}</td>
				</tr>
			{% endif %} 
		{% endfor %}
	</tbody>
</table>
