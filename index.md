<div>
{% if site.style == 'list' %}
    <ul>
{% elsif site.style == 'nlist' %}
    <ol>
{% endif %}
{% assign directory = '' %}
{% for file in site.static_files %}
    {% if site.extensions == null or site.extensions contains file.extname %}
        {% assign dirs = file.path | split: '/' %}
        {% if dirs[1] != directory and  site.style == 'dir' %}
            {% if directory != '' %}
            </dl>
            {% endif %}
            {% assign directory = dirs[1] %}
            <dt>{{ directory }}</dt>
            <dl>
        {% endif %}
        {% if site.directories == null or site.directories contains dirs[1] %}
            {% if site.style contains 'list' %}
                <li>
            {% elsif site.style == 'dir' %}
                <dd>
            {% endif %}
            {% if site.html_link contains file.extname %}
                {% assign index = file.path.size | minus: file.extname.size %}
                {% assign fpath = file.path | slice: 0, index %}
                {% if site.truncate == null %}
                <a href="{{ site.github.baseurl }}{{ fpath }}">{{ fpath | slice: 1, fpath.size }}</a> (<a href="{{ site.github.baseurl }}{{ file.path }}">{{ file.extname }}</a>)
                {% else %}
                <a href="{{ site.github.baseurl }}{{ fpath }}">{{ fpath | slice: 1, fpath.size | truncate: site.truncate }}</a> (<a href="{{ site.github.baseurl }}{{ file.path }}">{{ file.extname }}</a>)
                {% endif %}
            {% else %}
                {% if site.truncate == null %}
                <a href="{{ site.github.baseurl }}{{ file.path }}">{{ file.path | slice: 1, file.path.size }}</a>
                {% else %}
                <a href="{{ site.github.baseurl }}{{ file.path }}">{{ file.path | slice: 1, file.path.size | truncate: site.truncate }}</a>
                {% endif %}
            {% endif %}
            {% if site.style contains 'list' %}
                </li>
            {% elsif site.style == 'dir' %}
                </dd>
            {% elsif site.style == null %}
                <br>
            {% endif %}
        {% endif %}
    {% endif %}
{% endfor %}
{% if site.style == 'list' %}
    </ul>
{% elsif site.style == 'nlist' %}
    </ol>
{% elsif site.style == 'dir' %}
    </dl>
{% endif %}
</div>

This site is done with [jeklist](https://github.com/fgallaire/jeklist)
