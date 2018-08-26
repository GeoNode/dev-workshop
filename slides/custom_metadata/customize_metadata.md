# Customize Metadata

Where to start? The model is defined in the core at `geonode/geonode/base/models.py` folder:

```python
class ResourceBase(PolymorphicModel, PermissionLevelMixin, ItemBase):
    """
    Base Resource Object loosely based on ISO 19115:2003
    """
    ...
    # internal fields
    uuid = models.CharField(max_length=36)
    owner = models.ForeignKey(settings.AUTH_USER_MODEL, blank=True, null=True, related_name='owned_resource',
                              verbose_name=_("Owner"))
    contacts = models.ManyToManyField(settings.AUTH_USER_MODEL, through='ContactRole')
    title = models.CharField(_('title'), max_length=255, help_text=_('name by which the cited resource is known'))
    date = models.DateTimeField(_('date'), default=datetime.datetime.now, help_text=date_help_text)
    date_type = models.CharField(_('date type'), max_length=255, choices=VALID_DATE_TYPES, default='publication',
                                 help_text=date_type_help_text)
    edition = models.CharField(_('edition'), max_length=255, blank=True, null=True, help_text=edition_help_text)
    abstract = models.TextField(_('abstract'), blank=True, help_text=abstract_help_text)
    purpose = models.TextField(_('purpose'), null=True, blank=True, help_text=purpose_help_text)
    maintenance_frequency = models.CharField(_('maintenance frequency'), max_length=255, choices=UPDATE_FREQUENCIES,
                                             blank=True, null=True, help_text=maintenance_frequency_help_text)
    ...
```