# {{title}}
> [!info] Bibliography
> {{bibliography|replace("\n"," ")}}

## Information

| Key          |                                   Value                                   |
| :----------- | :-----------------------------------------------------------------------: |
| Date         |                  {% if date %}                    {{date                  | format("YYYY-MM")}} {% endif %} |
| Author       |                         {{authors}}{{directors}}                          |
| Contributors |                             {{contributors}}                              |
| Tags         |                           {{hashTags}}, #zotero                           |
| Journal      |                            #{{publicationTitle                            | replace(" ","-")}}              |
| DOI          |                            [{{DOI}}]({{url}})                             |
| Extra        |                                  {{extra                                  | replace("\n","\t")}}            |
| Type         |                           {{type}} {{itemType}}                           |
| Publisher    |                               {{publisher}}                               |
| Others       | {{archiveLocation}}    {{libraryCatalog}}    {{rights}}    {{callNumber}} |
| Zotero Link  |                             {{pdfZoteroLink}}                             |

## Abstract
> [!abstract]
> {{abstractNote}}

## Annotations
> [!warning]
> ANYTHING OUT OF %begin%...%end% BLOCK WILL BE CLEARED WHEN UPDATE

{% persist "annotations" %}
{% set annots = annotations | filterby("date", "dateafter", lastImportDate) %}
{% if annots.length > 0 %}***Imported on {{importDate | format("YYYY-MM-DD HH:mm")}}***
***
{% for annot in annots %}{% if annot.type == "image" %}> [!Image]
> ![]({{annot.imageRelativePath|replace(" ","%20")}})  [(p.{{annot.page}})](zotero://open-pdf/library/items/{{annot.attachment.itemKey}}?page={{annot.page}}&annotation={{annot.id}})

{% if annot.comment %}{{annot.comment}}{% endif %}
{% elif annot.type == "note" %}> [!note]
> <span style="color: {{annot.color}}">{{annot.comment | nl2br | replace("\n","")}} </span> [(p.{{annot.page}})](zotero://open-pdf/library/items/{{annot.attachment.itemKey}}?page={{annot.page}}&annotation={{annot.id}})

{% else %}> [!Highlight]
> <mark style="background: {{annot.color}}">{{annot.annotatedText | nl2br| replace("\n","")}} </mark> [(p.{{annot.page}})](zotero://open-pdf/library/items/{{annot.attachment.itemKey}}?page={{annot.page}}&annotation={{annot.id}})

{% if annot.comment %}{{annot.comment}}{% endif %}
{% endif %}{% endfor %}
***{% endif %}
{% endpersist %}

## Zotero-Notes

{{markdownNotes}}


## Notes
{% persist "Obsidian-Notes" %}



{% endpersist %}
> [!danger]
> NEVER MODIFY ANYTHING BELOW