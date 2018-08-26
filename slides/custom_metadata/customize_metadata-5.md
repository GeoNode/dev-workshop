# Customize Metadata (5)

**Overriding the Layer Detail Template Page**

```shell
mkdir -p my_geonode/templates/base
cp /home/geo/Envs/geonode/src/geonode/geonode/base/templates/base/_resourcebase_info_panel.html my_geonode/templates/base/
vim my_geonode/templates/base/_resourcebase_info_panel.html
```

```python
    ...
    <dd><a href="/groups/group/{{ resource.group.name }}/activity/">{{ group }}</a> </dd>
    ...

    <dt>DOI</dt>
    <dd>{{ resource.doi }}</dd>

  </dl>
  ...
```