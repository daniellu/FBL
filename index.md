---
title: Hello World!
---

<link rel="stylesheet" type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
<link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.10.15/css/dataTables.bootstrap.min.css">
<script type="text/javascript" src="https://cdn.datatables.net/r/bs-3.3.5/jqc-1.11.3,dt-1.10.8/datatables.min.js"></script>


<h2>Results of Craiglist Spider</h2>


<table id="craiglistTable"  class="table table-striped table-bordered" width="100%">
    <thead>
        <tr>
            <th>Title</th>
            <th>Price</th>
            <th>City</th>
            <th>Post Date</th>
            <th>Link</th>
        </tr>
    </thead>
    <tbody>
    {% for post in site.data.craigslist %}    
        {% if post.title != null %}
        <tr>
            <td>{{ post.title }}</td>
            <td>{{ post.price }}</td>
            <td>{{ post.city }}</td>
            <td>{{ post.post_date }}</td>
            <td><a href="{{ post.url }}">View</a></td>
        </tr>
        {% endif %}
    {% endfor %}
    </tbody>
</table>

<script>
$(document).ready(function() {
    $('#craiglistTable').DataTable();
} );
</script>
