# Customize Metadata (4)

**Overriding the Metadata Wizard Template Page**

```shell
mkdir -p my_geonode/templates/layouts
cp /home/geo/Envs/geonode/src/geonode/geonode/layers/templates/layouts/panels.html my_geonode/templates/layouts/
vim my_geonode/templates/layouts/panels.html
```

```python
    ...
             {{ layer_form.data_quality_statement }}
          </div>
          <div>
              <span><label for="{{ layer_form.doi|id }}">{{ layer_form.doi.label }}</label></span>
              <input id="id_resource-doi" name="resource-doi"
                     type="text"
                     class="has-external-popover"
                     data-container="body"
                     data-content="a DOI will be added by Admin before publication." data-html="true" data-placement="right"
                     placeholder="a DOI will be added by Admin before publication."
                     value="{{ layer_form.doi.value }}">
          </div>
    </div>
    ...
```