---
layout: default
title: Neocloud Services Comparison
---

<table id="comparison" class="comparison">
  <tr class="header" align="center">
    <th style="width:7%">Category</th>
    <th style="width:12%">Service Type</th>

    <th>
      <a href="https://www.coreweave.com" target="_blank">
        <img src="{{ '/assets/img/logo/CRWV_BIG.png' | relative_url }}" alt="CoreWeave" style="height:32px">
        <span style="font-size:0.8em; vertical-align:top; color:#C0C0C0;">Platinum</span>
      </a>
    </th>

    <th>
      <a href="https://crusoe.ai" target="_blank">
        <img src="{{ '/assets/img/logo/crusoe.svg' | relative_url }}" alt="Crusoe" style="height:32px">
      </a>
      <span style="font-size:0.8em; vertical-align:top; color:#DAA520;">Gold</span>
    </th>

    <th>
      <a href="https://nebius.com" target="_blank">
        <img src="{{ '/assets/img/logo/nebius.svg' | relative_url }}" alt="Nebius" style="height:32px">
      </a>
      <span style="font-size:0.8em; vertical-align:top; color:#DAA520;">Gold</span>
    </th>
  </tr>
  
  {% assign csp_list = "coreweave,crusoe,nebius" | split: "," %}

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
                  <img src="{{ '/assets/img/cloudproviders/' | append: csp | append: '/' |  append: record.icon | relative_url }}"
                         alt="{{ record.name }}" style="height:18px; vertical-align:-3px">
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