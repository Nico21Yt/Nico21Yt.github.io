<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>
<br>
* indicates author with **equal contribution**, † indicates the **corresponding author**.
<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative; padding-right: 15px; padding-left: 15px;">
    {% if link.image %} 
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width: 100%; height: auto;">
    {% endif %}
    {% if link.conference_short %} 
    <abbr class="badge">{{ link.conference_short }}</abbr>
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: 20px;">
    <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
    <div class="author">{{ link.authors }}</div>
    <div class="periodical"><em>{{ link.conference }}</em></div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0 link-btn" role="button" target="_blank">PDF</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0 link-btn" role="button" target="_blank">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0 link-btn" role="button" target="_blank">Project Page</a>
      {% endif %}
      {% if link.bibtex %} 
      <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0 link-btn" role="button" target="_blank">BibTex</a>
      {% endif %}
      <button onclick="openModal('{{ link.id }}')" class="btn btn-sm z-depth-0 link-btn" role="button">Abstract</button>
    </div>
    {% if link.notes %} 
    <strong><i style="color:#e74d3c">{{ link.notes }}</i></strong>
    {% endif %}
    {% if link.others %} 
    {{ link.others }}
    {% endif %}
  </div>
</div>
</li>

<br>

{% endfor %}

</ol>
</div>

<!-- 模态窗口结构 -->
<div id="modal" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeModal()">&times;</span>
    <div id="modal-body">
      <!-- 摘要内容将被插入到这里 -->
    </div>
  </div>
</div>

<script>
  function openModal(id) {
    var abstractContent = document.getElementById('abstract-' + id).innerHTML;
    document.getElementById('modal-body').innerHTML = abstractContent;
    document.getElementById('modal').style.display = "block";
  }

  function closeModal() {
    document.getElementById('modal').style.display = "none";
  }

  window.onclick = function(event) {
    var modal = document.getElementById('modal');
    if (event.target == modal) {
      modal.style.display = "none";
    }
  }
</script>
