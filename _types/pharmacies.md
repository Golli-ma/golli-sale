---
name: pharmacies
short_name: pharmacies

localesSingular:
  fr: Pharmacie
  en: Pharmacy
  ar: صيدلية
localesPlural:
  fr: Pharmacies
  en: Pharmacies
  ar: صيدليات

layout: default
---

Les pharmacies se trouvant sur Salé

{% assign pharmacies_by_neighbordhood = site.pharmacies | group_by: "neighborhood" %}
{% for neighbordhood_pharmacies in pharmacies_by_neighbordhood %}

 <h2>{{ neighbordhood_pharmacies.name }}</h2>
 {% for pharmacy in neighbordhood_pharmacies.items %}
  {% capture pharmacy_link %}{{ pharmacy.url | prepend: site.baseurl }}{% endcapture %}
  <h3><a href="{{ pharmacy_link }}">{{ pharmacy.slug }}</a></h3>
 {% endfor %}
{% endfor %}