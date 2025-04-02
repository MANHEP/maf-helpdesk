# Manchester Analysis Facility help pages

Some description of the docs

## Contributing

The documentation source is hosted on GitHub in
[maf-helpdesk](https://github.com/MANHEP/maf-helpdesk)
repository.

[ccd]: https://how-to.docs.cern.ch
[ccd-mkdocs]: https://how-to.docs.cern.ch/gitlabpagessite/create_site/creategitlabrepo/create_with_mkdocs/

To serve the docs locally, you can clone the repo and use `mkdocs` see your changes.

```bash
git clone https://github.com/MANHEP/maf-helpdesk.git
cd maf-helpdesk
python -m venv .venv && source .venv/bin/activate
python -m pip install -r requirements.txt
mkdocs serve
```

You will see a link to open a locally hosted version of the documentation pages in a browser.
These will auto-update with changes to the source files.


