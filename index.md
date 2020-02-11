---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "cp"    # what kind of Carpentry (must be either "lc" or "dc" or "swc").  
venue: "OSG AHM 2020 - User Training"        # brief name of host site without address (e.g., "Euphoric State University")
address: "tbd"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latlng: "32.7903116,-117.2546711"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "March 19, 2020"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "8:30am - noon"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2020-03-19      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2020-03-19        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Lauren Michael", "Mats Rynge"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
# helper: [""]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["lmichael@wisc.edu", "rynge@isi.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %}
For a workshop please delete the following block
{% endcomment %}
<div class="alert alert-warning" style="font-size: 120%;">
Could your Gateway or other computational work benefit from the ability to concurrently run hundreds or thousands of independent computations, for free? The Open Science Grid (OSG) facilitates distributed high-throughput computing (dHTC) via a partnership of national labs, universities, and other organizations who contribute and share computing capacity for use by researchers across and beyond the United States. Individual researchers, institutions, or multi-institutional collaborations can access OSG via local submission points or through the OSG Connect service (freely available to U.S. academic, government, and non-profit researchers).   <br>
  
  During this 3-hour tutorial, you'll learn to run examples of large HTC workloads and multi-step workflows via the OSG Connect service. If time permits, the OSG User Support team will also help you run your own sample workload on OSG.
</div>

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">General Information</h2>

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> A computer with an ssh client. We will have training/test accounts for participants to test-drive job submission in the Open Science Grid. 
</p>

{% comment %}

ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.

<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
{% endcomment %}

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<div class="row">
  <div class="col-md-8">
    <h2>Schedule and Links</h2>
    <table class="table table-striped">
      <tr><td>8:30-9:10</td> <td>Introduction to the Open Science Grid</td> <td><a href="https://docs.google.com/presentation/d/1TpLzOx2A9IRKZbZKV7XS4lR72-Eo8R9N5dj5Z0l3gxA/edit?usp=sharing">Slides</a></td></tr>
      <tr><td>9:10-9:30</td><td>Introduction to Job Submission with HTCondor</td><td><a href="https://support.opensciencegrid.org/support/solutions/articles/5000633410-osg-connect-quickstart">Tutorial</a></td></tr>
      <tr><td>9:30-9:40</td><td>Where Jobs Run in the OSG</td><td><a href="https://support.opensciencegrid.org/support/solutions/articles/12000061978-finding-osg-locations">Tutorial</a></td></tr>
      <tr><td>9:40-10:00</td><td>Submitting Multiple Jobs with HTCondor</td><td><a href="https://support.opensciencegrid.org/support/solutions/articles/12000062019-scaling-up-python">Tutorial</a></td></tr>
      <tr><td>10:00-10:30</td><td>Break</td><td></td></tr>
      <tr><td>10:30-11:15</td><td>Additional HTCondor Features</td><td><a href="https://docs.google.com/presentation/d/1MMLMFzqqJY7z1mcHJD3A_EuiqU1docq5ld2QlVFPz2s/edit?usp=sharing">Slides</a></td></tr>
      <tr><td>11:15-noon</td><td>BLAST workflow example</td><td><a href="https://support.opensciencegrid.org/support/solutions/articles/12000062020-blast-example-with-split-files">Tutorial</a></td></tr>
    </table>
  </div>
</div>


