# Solr

This add-on creates cores according to the configuration
defined in `.ddev/typo3-solr/config.yaml`.

## Installation 

```bash
ddev get ochorocho/ddev-typo3-solr
```

### Create cores and its configuration:

```
ddev solrctl apply
```

### Delete cores and its configuration:

```
ddev solrctl wipe
```

> [!NOTE]  
> After running `wipe`, it may take a few seconds
> until files are synced which may cause issues when
> running `apply` straight after `wipe`


## TYPO3 Configuration

### Site configuration:

![site-configuration.png](images%2Fsite-configuration.png)

Site config values:

```yaml
solr_enabled_read: true
solr_host_read: typo3-solr
solr_path_read: /
solr_port_read: '8983'
solr_scheme_read: http
solr_use_write_connection: false
```

Set core for language to use: 

![site-configuration-core-language.png](images%2Fsite-configuration-core-language.png)

```yaml
languages:
  -
    title: English
    solr_core_read: core_en
...
```

TypoScript - Enable indexing:

```
page.config.index_enable = 1
```

**Maintained by [@ochorocho](https://github.com/ochorocho)**
