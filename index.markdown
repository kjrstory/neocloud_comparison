---
layout: default          # minima 레이아웃
title: AWS Compute Services
---

<!-- ── 표를 확실히 ‘표답게’ 보이게 하는 최소 스타일 ── -->
<style>
  #comparison{border-collapse:collapse;width:100%;margin-top:1rem}
  #comparison th,#comparison td{border:1px solid #ccc;padding:.4em .6em}
  #comparison th{background:#f7f7f7;position:sticky;top:0}
  #comparison ul{margin:0;padding-left:1.2em}
</style>

<table id="comparison">
  <tr class="header" align="center">
    <th style="width:7%">Category</th>
    <th style="width:12%">Service Type</th>
    <th>
      <img src="{{ '/assets/img/logo/aws.svg' | relative_url }}"
           alt="AWS Logo" style="height:32px">
    </th>
    <th>
      <img src="{{ '/assets/img/logo/coreweave.png' | relative_url }}" 
           alt="CoreWeave" style="height:32px">
    </th>
  </tr>

  {% assign csp_list = "aws,coreweave" | split: "," %}

  {% for item in site.data.cloudservices.services %}
    <tr>
      <td>{{ item.category }}</td>
      <td>{{ item.subcategory }}</td>

      {% for csp in csp_list %}
        <td>
          <ul>
          {% for entry in item.service %}
            {% if entry[csp] %}
              {% for record in entry[csp] %}
                <li>
                  <img src="{{ '/assets/img/cloudproviders/' | append: csp | append: '/' | append: record.icon | relative_url }}"
                      alt="{{ record.name }}" style="height:18px;vertical-align:-3px">
                  <a href="{{ record.ref }}" target="_blank">{{ record.name }}</a>
                </li>
              {% endfor %}
            {% endif %}
          {% endfor %}
          </ul>
        </td>
      {% endfor %}
    </tr>
  {% endfor %}

</table>
