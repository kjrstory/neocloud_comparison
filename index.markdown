---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<head>
    <meta charset="utf-8">
    <link rel="icon" type="image/x-icon" href="/favicon.ico"/>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="robots" content="follow,index">
    <META NAME="Title" CONTENT="A Public Cloud Comparison | AWS vs Azure vs Google vs IBM vs Oracle vs Alibaba">
    <META NAME="Keywords" CONTENT="AWS vs Azure vs Google vs IBM vs Oracle vs Alibaba, AWS vs Azure, Azure vs Google">
    <META NAME="Description" CONTENT="A detailed public cloud services comparison & mapping of Amazon AWS, Microsoft Azure, Google Cloud, IBM Cloud, Oracle Cloud.">
    <META NAME="Author" CONTENT="Ilyas">
    <META NAME="Subject" CONTENT="A Public Cloud Comparison | AWS vs Azure vs Google vs IBM vs Oracle vs Alibaba">
    <meta property="og:type" content="website">
    <meta property="og:title" content="A Public Cloud Comparison | AWS vs Azure vs Google vs IBM vs Oracle vs Alibaba">
    <meta property="og:locale" content="en_US">
    <meta property="og:description" content="A detailed public cloud services comparison & mapping of Amazon AWS, Microsoft Azure, Google Cloud, IBM Cloud, Oracle Cloud.">
    <link rel="canonical" href="https://comparecloud.in/">
    <meta property="og:url" content="https://comparecloud.in/">
    <meta property="og:site_name" content="A Public Cloud Comparison | AWS vs Azure vs Google vs IBM vs Oracle vs Alibaba">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:site" content="@Ilyas_tweets">
    <meta name="twitter:creator" content="@Ilyas_tweets">
    <meta name="twitter:description" content="A detailed public cloud services comparison & mapping of Amazon AWS, Microsoft Azure, Google Cloud, IBM Cloud, Oracle Cloud.">
    <meta name="twitter:title" content="A public Cloud Compareison : AWS vs Azure vs Google vs IBM vs Oracle vs Alibaba">
    <title>AWS vs Azure vs Google vs IBM vs Oracle vs Alibaba | A detailed comparison and mapping between various cloud services</title>
</head>
<script type="text/javascript" src="//s7.addthis.com/js/300/addthis_widget.js#pubid=ra-552c144e4f497fe9"></script>
<!-- Place this tag in your head or just before your close body tag. -->
<script async defer src="https://buttons.github.io/buttons.js"></script>
<table class="github">
<tr align="center" >

</tr>
</table>

<table id="comparison">
  <tr align="center" class="header" style="position:sticky;top: 0">
	            <th style="width:7%">Category</th>
            <th style="width:10%">Service</th>
            <th>
              <img  src="assets/img/logo/aws.png" alt="AWS Icon" class="header-img"/>
            </th>
  </tr>
	{% for item in site.data.cloudservices.services %}
	<tr>
		<td>{{item.category}}</td>
		<td>{{item.subcategory}}</td>
		<td>
			<ul>
			    {% for entry in item.service %} 
					{% for record in entry.aws %}
						<li ><img src="{{ "/assets/img/cloudproviders/aws/{{record.icon}}" | append: record.icon | relative_url }}"  alt="{{record.name}}" >
                        <a href="{{record.ref}}" target="_blank" alt="{{record.name}}">{{record.name}}</a></li>
					{% endfor %}	
				{% endfor %}	
			</ul>
		</td>
	</tr>
	{% endfor %}
</table>
