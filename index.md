<div>
{% if page.style == 'list' %}
    <ul>
{% endif %}
{% for file in site.static_files %}
    {% if page.extensions == null or page.extensions contains file.extname %}
        {% assign dirs = file.path | split: '/' %}
        {% if page.directories == null or page.directories contains dirs[1] %}
            {% if page.style == 'list' %}
                <li>
            {% endif %}
            {% if page.html_link contains file.extname %}
                {% assign index = file.path.size | minus: file.extname.size %}
                {% assign fpath = file.path | slice: 0, index %}
                {% if page.truncate == null %}
                <a href="{{ site.github.baseurl }}{{ fpath }}">{{ fpath | slice: 1, fpath.size }}</a> (<a href="{{ site.github.baseurl }}{{ file.path }}">{{ file.extname }}</a>)
                {% else %}
                <a href="{{ site.github.baseurl }}{{ fpath }}">{{ fpath | slice: 1, fpath.size | truncate: page.truncate }}</a> (<a href="{{ site.github.baseurl }}{{ file.path }}">{{ file.extname }}</a>)
                {% endif %}
            {% else %}
                {% if page.truncate == null %}
                <a href="{{ site.github.baseurl }}{{ file.path }}">{{ file.path | slice: 1, file.path.size }}</a>
                {% else %}
                <a href="{{ site.github.baseurl }}{{ file.path }}">{{ file.path | slice: 1, file.path.size | truncate: page.truncate }}</a>
                {% endif %}
            {% endif %}
            {% if page.style == 'list' %}
                </li>
            {% endif %}
        {% endif %}
    {% endif %}
{% endfor %}
{% if page.style == 'list' %}
    </ul>
{% endif %}
</div>

This site is done with [jeklist](https://github.com/fgallaire/jeklist)
