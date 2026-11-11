---
# More detailed instructions (including how to fill these variables for an # online workshop) are available at https://carpentries.github.io/workshop-template/customization/index.html#yaml-header
# Required variables
venue: "University of Cambridge"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "Room D, West Hub, J J Thomson Avenue, Eddington, Cambridge CB3 0US"      # full street address of workshop
country: "gb"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the workshop
latitude: 52.2103     # decimal latitude of workshop venue - this should be a number greater than or equal to -90, and less than or equal to 90 (use https://www.latlong.net/)
longitude: 0.0898    # decimal longitude of the workshop venue - this should be a number greater than or equal to -180, and less than or equal to 180 (use https://www.latlong.net)
humandate: "Jan 14-15, 2027"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:30 am - 4:00 pm GMT"    # human-readable times for the workshop e.g., "9:00 am - 4:30 pm CEST (7:00 am - 2:30 pm UTC)"
startdate: 2027-01-14      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2027-01-15        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Samantha Ahern", "Toby Hodges"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Jack Atkinson", "David Kamm"]     # boxed, comma-separated list of helpers' names
email: ["iccs@maths.cam.ac.uk"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions
# Optional variables
collaborative_notes:  # URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
registration: "https://forms.gle/q3ZmGaYg1DdMkKqj8"    # URL of the external registration/signup form (e.g., a Google Form) if not using Eventbrite
what3words:           # what3words (https://what3words.com) address of the workshop venue, without leading slashes e.g. "globe.lessening.computers"
# DON'T CHANGE THIS
layout: workshop
---

{% assign isOfficial = site.official_curricula | has: site.carpentry %}

{% if page.venue == "FIXME" or
      page.address == "FIXME" or
      page.country == "FIXME" or
      page.language == "FIXME" or
      page.latitude == "FIXME" or
      page.longitude == "FIXME" or
      page.humandate == "FIXME" or
      page.humantime == "FIXME" or
      page.startdate == "FIXME" or
      page.enddate == "FIXME" %}
      {% assign fixmes = true %}
{% endif %}

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% if fixmes %}
<div class="alert alert-danger">
    <p>
        This is the AI Carpentry workshop template. Fill in the required variables as described in the <a href="{{site.url}}{{site.baseurl}}/customization/index.html#yaml-header">customisation</a> instructions to remove this message.
    </p>
</div>
{% endif %}

{% if site.carpentry == "ai" %}
{% unless site.curriculum == "user-novice" or site.curriculum == "user-cp" or site.curriculum == "developer" %}
<div class="alert alert-warning">
It looks like you are setting up a website for an AI Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>user-novice</code>, <code>user-cp</code>, <code>developer</code>. After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}


{% comment %}
REGISTRATION

This block links to the external registration/signup form if
'registration' has been set in the header (e.g., a Google Form).
You can delete it if you are not using an external form, or leave
it in, since it will not be displayed if the 'registration' field
in the header is not set.
{% endcomment %}

{% if page.registration %}
<div class="card mb-2">
  <h5 class="card-header">Registration</h5>
  <div class="card-body text-center">
    <p>
      <strong>Interested in attending this workshop?</strong>
      Please fill in the signup form to register your interest.
    </p>
    <p>
      <a href="{{ page.registration }}">
        <button type="button" class="btn btn-primary">Sign up for the workshop</button>
      </a>
    </p>
  </div>
</div>
{% endif %}


{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change the pitch.
{% endcomment %}

<div class="row g-3 pb-3">

  <!-- left column spans 2 rows -->
  <div class="col-md-6">
    <div class="card h-100">
        <h5 class="card-header">AI Carpentry</h5>
        <div class="card-body">
            <p>
            <strong><a href="https://aicarpentry.org">AI Carpentry</a></strong> teaches researchers to make informed use of artificial intelligence.
            </p>
            <p>
            Our mission is to empower people to make informed decisions about the use of artificial intelligence tools and methods in their projects and to prepare them to become advocates for judicious use of AI in research.
            The target audience of AI Carpentry is researchers and data scientists with little to no expertise in machine learning and artificial intelligence methods.
            </p>
            <p>
            Each of our workshops is aimed at a different target audience with their own goals and background knowledge.
            In each case, the goal is to empower learners to make informed decisions about the application of AI in their projects.
            We achieve this by combining conceptual learning with plenty of hands-on exploration and practice.
            </p>
        </div>
    </div>
  </div>

  <!-- right column with two stacked cards -->
  <div class="col-md-6 d-flex flex-column gap-3">
    <div class="card flex-fill">
        <h5 class="card-header">Carpentries Clippings</h5>
        <div class="card-body">
        <p class="text-center">
        <strong>Want to learn more and stay engaged with The Carpentries?</strong>
        </p>
        <p class="text-center">
        Carpentries Clippings is The Carpentries' monthly newsletter, where they share community news, community job postings, and more.
        </p>
        <p class="text-center">
            <a href="https://carpentries.org/newsletter/">
                <button type="button" class="btn btn-success">Sign up to The Carpentries' newsletter</button>
            </a>
        </p>
      </div>
    </div>
    <div class="card flex-fill">
      <h5 class="card-header">Code of Conduct</h5>
      <div class="card-body">
        {% comment%}
        CODE OF CONDUCT
        {% endcomment %}
        <p class="text-center">
        Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/policies/coc/">Code of Conduct</a>, which also outlines how to report an incident if needed.
        </p>

        <p class="text-center">
        <a href="https://goo.gl/forms/KoUfO53Za3apOuOK2">
            <button type="button" class="btn btn-info">Report a Code of Conduct Incident</button>
        </a>
        </p>
      </div>
    </div>
  </div>
</div>

{% if site.pilot %}
This is a pilot workshop, testing out a lesson that is still under development. The lesson authors would appreciate any feedback you can give them about the lesson content and suggestions for how it could be further improved.
{% endif %}


{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://www.latlong.net/ to find the lat/long of an
address.
{% endcomment %}

{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
  {% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
  {% assign online = "true_public" %}
{% else %}
  {% assign online = "false" %}
{% endif %}

<div class="card mb-2">
  <h5 class="card-header">Workshop Logistics</h5>
  <div class="card-body">
    <dl class="mb-0">
    <div class="row">
        <dt class="col-sm-2 col-md-2 py-2 px-3 bg-body-light text-body-secondary fw-bold">Who</dt>
        <dd class="col py-2 px-3 mx-0 mb-0">
            {% comment %}
            AUDIENCE

            Explain who your audience is.  (In particular, tell readers if the
            workshop is only open to people from a particular institution.
            {% endcomment %}
            {% assign who_file = site.carpentry | append: '/who.html' %}
            {% if isOfficial %}
            {% include {{ who_file }} %}
            {% endif %}    
        </dd>
    </div>
    <div class="row">
        <dt class="col-sm-2 col-md-2 py-2 px-3 bg-body-light text-body-secondary fw-bold">Where</dt>
        <dd class="col py-2 px-3 mx-0 mb-0">
            {% if page.latitude and page.longitude and online == "false" %}    
                {{page.address}}.
                Get directions with
                <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
                or
                <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
                {% if page.what3words %}
                    What3Words location:
                    <a href="https://what3words.com/{{page.what3words}}">///{{page.what3words}}</a>.
                {%endif %}
                {% elsif online == "true_public" %}
                    <p id="where">
                        Online at <a href="{{page.address}}">{{page.address}}</a>.
                        If you need a password or other information to access the training,
                        the instructor will pass it on to you before the workshop.
                    </p>
                {% elsif online == "true_private" %}
                    <p id="where">
                        This training will take place online.
                        The instructors will provide you with the information you will need to connect to this meeting.
                    </p>
                {% endif %}        
        </dd>
    </div>
    <div class="row">
        <dt class="col-sm-2 col-md-2 py-2 px-3 bg-body-light text-body-secondary fw-bold">When</dt>
        <dd class="col py-2 px-3 mx-0 mb-0">
            {% comment %}
            DATE

            This block displays the date and links to Google Calendar.
            {% endcomment %}
            {% if page.humandate %}
                <p id="when">
                    {{page.humandate}}; {{page.humantime}}
                    {% include workshop_calendar.html %}
                </p>
            {% endif %}    
        </dd>
    </div>
    <div class="row">
        <dt class="col-sm-2 col-md-2 py-2 px-3 bg-body-light text-body-secondary fw-bold">Requirements</dt>
        <dd class="col py-2 px-3 mx-0 mb-0">
            {% comment %}
            SPECIAL REQUIREMENTS

            Modify the block below if there are any special requirements.
            {% endcomment %}
            <p id="requirements">
            {% if online == "false" %}
                Participants must bring a laptop with a
                Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on.
            {% else %}
                Participants must have access to a computer with a
                Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on.
            {% endif %}
            They should have a few specific software packages installed (listed <a href="#setup">below</a>).
            </p>
        </dd>  
    </div>
    <div class="row">
        <dt class="col-sm-2 col-md-2 py-2 px-3 bg-body-light text-body-secondary fw-bold">Accessibility</dt>
        <dd class="col py-2 px-3 mx-0 mb-0">
            {% comment %}
            ACCESSIBILITY

            Modify the block below if there are any barriers to accessibility or special instructions.
            {% endcomment %}

            <p id="accessibility">
            We are committed to making this workshop accessible to everybody. 
            {% if online == "false" %}
                The workshop organizers have checked that:
                <br/>
                <ul>
                    <li>The room is wheelchair / scooter accessible.</li>
                    <li>Accessible restrooms are available.</li>
                </ul>
            {% endif %}
            </p>
            <p>
            We are dedicated to providing a positive and accessible learning environment for all. 
            We do not require participants to provide documentation of disabilities or disclose any unnecessary personal information. 
            However, we do want to help create an inclusive, accessible experience for all participants. 
            We encourage you to share any information that would be helpful to make your Carpentries experience accessible.
            <!--
            To request accessibility support for this workshop, please fill out the 
            <a href="https://carpentries.typeform.com/to/B2OSYaD0">accessibility support request form</a>.
            If you have questions or need assistance with the accessibility support form please <a href="mailto:team@carpentries.org">email us</a>.
            -->
            </p>
            <p>
            <a href="https://glosario.carpentries.org/">Glosario</a> is a multilingual glossary for computing and data science terms.
            The glossary helps learners attend workshops and use our lessons to make sense of computational and programming jargon written in English by offering it in their native language.
            Translating data science terms also provides a teaching tool for Carpentries Instructors to reduce barriers for their learners.
            </p>
        </dd>
    </div>
    <div class="row">
        <dt class="col-sm-2 col-md-2 py-2 px-3 bg-body-light text-body-secondary fw-bold">Workshop Recordings</dt>
        <dd class="col py-2 px-3 mx-0 mb-0">
            {% comment %}
            WORKSHOP RECORDINGS

            Modify or remove the block below if you plan to record the workshop.
            {% endcomment %}
            <p id="recordings">
            AI Carpentry workshops are designed to be interactive rather than lecture-based, with lessons that build upon one another.
            To foster a positive online learning environment, we strongly recommend that participants join in real time.
            As a result, workshop recordings are not recommended and may not be available to learners.
            </p>
        </dd>
    </div>
    <div class="row">
        <dt class="col-sm-2 col-md-2 py-2 px-3 bg-body-light text-body-secondary fw-bold">Contact</dt>
        <dd class="col py-2 px-3 mx-0 mb-0">
            {% comment %}
            CONTACT EMAIL ADDRESS

            Display the contact email address set in the configuration file.
            {% endcomment %}
            <p id="contact">
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
        </dd>
    </div>
    
    <!-- <div class="row">
        <dt class="col-sm-2 col-md-2 py-2 px-3 bg-body-light text-body-secondary fw-bold">Accessibility</dt>
        <dd class="col py-2 px-3 mx-0 mb-0">
        
        </dd>
    </div> -->

    </dl>
  </div>
</div>


{% comment %}
WHO CAN ATTEND?

If you would like to specify who can attend the workshop, you can use the section below.

Move the 'endcomment' tag above the beginning of the following <p> tag to make this section visible.

Edit the text to match who can attend the workshop. For instance:
- This workshop is open to affiliates to ABC university.
- This workshop is open to the public.
- If you are interested in attending this workshop, contact me@example.com
  for more information

<p id="who-can-attend">
    <strong>Who can attend?:</strong>
    This workshop is open to ....
</p>
{% endcomment %}


{% comment %}
COLLABORATIVE NOTES

If you want to use an Etherpad, go to

https://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.

Note we also have a CodiMD (the open-source version of HackMD) available at https://codimd.carpentries.org
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>
<p>
We will use this <a href="{{ page.collaborative_notes }}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}


{% comment %}
SURVEYS - DO NOT EDIT SURVEY LINKS
<div class="card mb-2">
  <h5 class="card-header">Surveys</h5>
  <div class="card-body">
    <div class="row">
    <div class="col-sm-6">
        <div class="card text-center">
            <div class="card-body">
                <h5 class="card-title">Pre-Workshop Survey</h5>
                <p class="card-text">Please fill out this survey <strong>before attending</strong> the workshop.</p>
                {% if site.carpentry == "incubator" %}
                <a href="{{ site.incubator_pre_survey }}">Pre-workshop Survey</a>
                {% elsif site.incubator_pre_survey %}
                <div class="alert alert-danger">
                WARNING: you have defined custom pre- and/or post-survey links for
                a workshop not configured for The Carpentries Incubator
                (the value of `curriculum` is not set to `incubator` in `_config.yml`).
                Please comment out the `incubator_pre_survey` and `incubator_post_survey` fields
                in `_config.yml` or, if this workshop is teaching a lesson in the Incubator,
                change the value of `carpentry` to `incubator`.
                </div>
                {% elsif site.carpentry == "hpcc" %}
                <a href="{{ site.hpcc_pre_survey }}{{ site.github.project_title }}" class="btn btn-primary">Fill Out the Pre-Workshop Survey</a>
                {% else %}
                <a href="{{ site.pre_survey }}{{ site.github.project_title }}" class="btn btn-primary">Fill Out the Pre-Workshop Survey</a>
                {% endif %}
            </div>
        </div>
    </div>
    <div class="col-sm-6">
        <div class="card text-center">
            <div class="card-body">
                <h5 class="card-title">Post-Workshop Survey</h5>
                <p class="card-text">Please fill out this survey <strong>before you leave</strong> the workshop.</p>
                {% if site.carpentry == "incubator" %}
                <a href="{{ site.incubator_post_survey }}">Post-workshop Survey</a>
                {% elsif site.incubator_post_survey %}
                <div class="alert alert-danger">
                WARNING: you have defined custom pre- and/or post-survey links for
                a workshop not configured for The Carpentries Incubator
                (the value of `curriculum` is not set to `incubator` in `_config.yml`).
                Please comment out the `incubator_pre_survey` and `incubator_post_survey` fields
                in `_config.yml` or, if this workshop is teaching a lesson in the Incubator,
                change the value of `carpentry` to `incubator`.
                </div>
                {% elsif site.carpentry == "hpcc" %}
                <a href="{{ site.hpcc_post_survey }}{{ site.github.project_title }}" class="btn btn-primary">Fill Out the Pre-Workshop Survey</a>
                {% else %}
                <a href="{{ site.post_survey }}{{ site.github.project_title }}" class="btn btn-primary">Fill Out the Post-Workshop Survey</a>
                {% endif %}
            </div>
        </div>
    </div>
    </div>
  </div>
</div>
{% endcomment %}

{% comment %}
SCHEDULE

Show the workshop's schedule.

{% endcomment %}

<div class="card mb-2">
  <h5 class="card-header">Schedule</h5>
  <div class="card-body">
    {% assign schedule_file = site.carpentry | append: '/schedule.html' %}
    {% if isOfficial %}
    {% include {{ schedule_file }} %}
    {% elsif site.carpentry == "incubator" %}
    This workshop is teaching a lesson in <a href="https://carpentries-incubator.org/">The Carpentries Incubator</a>.
    Please check <a href="{{site.incubator_lesson_site}}">the lesson homepage</a> for a list of lesson sections and estimated timings.
    {% endif %}

    {% comment %}
    Edit/replace the text above if you want to include a schedule table.
    See the contents of the _includes/custom-schedule.html file for an example of how one of these schedule tables is constructed.
    {% endcomment %}

    {% if site.pilot %}
    The lesson taught in this workshop is being piloted and a precise schedule is yet to be established.
    The workshop will include regular breaks. Please <a href="mailto:{{page.email}}">contact the workshop organisers</a> if you would like more information about the planned schedule.
    {% endif %}
  </div>
</div>

<hr/>


{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>
<p>
  To participate in an AI Carpentry workshop, you will need access to software as described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors that may be useful on the
  <a href="{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>


{% comment %}
For online workshops, the section below provides:
- installation instructions for the Zoom client
- recommendations for setting up Learners' workspace so they can follow along the instructions and the videoconferencing

If you do not use Zoom for your online workshop, edit the file `_includes/install_instructions/videoconferencing.html` to include the relevant installation instructions.
{% endcomment %}

{% if online != "false" %}
  {% include install_instructions/videoconferencing.html %}
{% endif %}


{% comment %}
These are the installation instructions for the tools used during the workshop.
{% endcomment %}

{% assign setup_file = site.carpentry | append: '/setup.html' %}
{% if isOfficial %}
  {% include {{ setup_file }} %}
{% elsif site.carpentry == "incubator" %}
  Please check the "Setup" page of <a href="{{site.incubator_lesson_site}}">the lesson homepage</a> for instructions to follow to obtain the software and data you will need to follow the lesson.
{% endif %}
