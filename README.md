# cb-oralhistory

# About this branch

This branch is a minimal demo of how one might be able to use [Pagefind](https://pagefind.app/) to perform searching and filtering. It currently indexes only the contents of #item-metadata. Filtering is enabled for fields where the `filter` column in `config-metadata.csv` is `true`. To build, run `python -m pagefind --site _site/items/` or `npx -y pagefind --site _site/items/` *after* performing a CB/Jekyll build (see the Pagefind documentation for details).

The Pagefind search page is at `/pagefind-search`.

## About cb-oralhistory

**cb-oralhistory** is a mix of [CollectionBuilder-CSV](https://github.com/CollectionBuilder/collectionbuilder-csv) and [Oral History as Data (OHD)](https://github.com/oralhistoryasdata/oralhistoryasdata.github.io). It's meant to serve as a starter repository for those wanting to build oral history collections with CollectionBuilder. 

The current demo site features a small mix of transcripts. Item pages are generated by a CSV metadata file that includes the display_template "transcript" as a field. 


## About Oral History as Data
Oral History as Data (OHD) provides a static web framework for users to publish and analyze coded oral history and qualitative interviews on the web. 

Oral History as Data was first built in 2018, coming out of work at the University of Idaho Library's [Center for Digital Inquiry and Learning (CD?L)](https://cdil.lib.uidaho.edu/). 
The framework served as the foundation for several digital humanities projects, including [Voices of Gay Rodeo](https://www.voicesofgayrodeo.com/), [Idaho Queered](https://www.lib.uidaho.edu/queered/), and [CTRL+Shift](https://ctrl-shift.org/). 

The look for OHD is different than CollectionBuilder. Check out the [a demo site](https://oralhistoryasdata.github.io/) to see the differences.

There is some [documentation](https://oralhistoryasdata.github.io/about.html#documentation) for OHD that might be helpful in this context. More fully developed documentation for this project is being developed, but there are several places linked here to get you started.

## About CollectionBuilder-CSV

CollectionBuilder-CSV is a robust and flexible "stand alone" template for creating digital collection and exhibit websites using Jekyll and a metadata CSV.
Driven by your collection metadata, the template generates engaging visualizations to browse and explore your objects.
The resulting static site can be hosted on any basic web server (or built automatically using GitHub Actions).

Visit the [CollectionBuilder Docs](https://collectionbuilder.github.io/cb-docs/) for step-by-step details for getting started and building collections!

## Brief Overview of Building a Collection

The [CollectionBuilder Docs](https://collectionbuilder.github.io/cb-docs/) contain detailed information about building a collection from start to finish--including installing software, using Git/GitHub, preparing digital objects, and formatting metadata.
However, here is a super quick overview of the process:

- Make your own copy of this template repository by clicking the green "Use this Template" button on GitHub (see [repository set up docs](https://collectionbuilder.github.io/cb-docs/docs/repository/)). This copy of the template is the starting point for your "project repository", i.e. the source code for your digital collection site!
- Prepare your collection metadata following the CB-CSV template (see our demo [metadata template on Google Sheets](https://docs.google.com/spreadsheets/d/1nN_k4JQB4LJraIzns7WcM3OXK-xxGMQhW1shMssflNM/edit?usp=sharing) and [metadata docs](https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/)). Your metadata will include links to your digital files (images, pdfs, videos, etc) and thumbnails wherever they are hosted.
- Add your metadata as a CSV to your project repository's "_data" folder (see [upload metadata docs](https://collectionbuilder.github.io/cb-docs/docs/metadata/uploading/)).
- Edit your project's "_config.yml" with your collection information (see [site configuration docs](https://collectionbuilder.github.io/cb-docs/docs/config/)). Additional customization is done via a theme file, configuration files, CSS tweaks, and more--however, once your "_config.yml" is edited your site is ready to be previewed. 
- Generate your site using Jekyll! (see docs for how to [use Jekyll locally](https://collectionbuilder.github.io/cb-docs/docs/repository/generate/) and [deploy on the web](https://collectionbuilder.github.io/cb-docs/docs/deploy/))

Please feel free to ask questions in the main [CollectionBuilder discussion forum](https://github.com/CollectionBuilder/collectionbuilder.github.io/discussions).      

## Important TIMESTAMP Note!

If you put `timestamp` in your transcript .CSV files (we highly recommended that you do) please make sure they use full `[hh:mm:ss]` notation!  You may omit the `hh:` portion for timestamps of less than an hour, but make sure you always specify a full `mm:ss` notation.  For example, 9-minutes 7-seconds should never be specified as `[9:7]` or even `[9:07]`, the proper form is `[00:09:07]` but `[09:07]` will also work.  

## Important DATE Note!

Handling dates in metadata can be tricky and remember that information you enter in your metadata .CSV file comes into the framework as `text`, not as any other data type (so there are no `date` type variables).  This makes custom formatting of things like dates especially tricky.  Consequently, you won't find a lot of `date` formatting in CB, for the most part it will display exactly what you entered.  

This can also present difficulties if you want to sort on something like a `date` field.  So it's recommended that you **always enter dates in the form `yyyy` (only the year), or `yyyy-mm` (year and month), or `yyyy-mm-dd` (a complete discrete date)**.  Doing so will ensure that your dates make sense when displayed AND they will sort properly too.  

----------

## CollectionBuilder 

<https://collectionbuilder.github.io/>

CollectionBuilder is a project of University of Idaho Library's [Digital Initiatives](https://www.lib.uidaho.edu/digital/) and the [Center for Digital Inquiry and Learning](https://cdil.lib.uidaho.edu) (CDIL) following the [Lib-Static](https://lib-static.github.io/) methodology. 
Powered by the open source static site generator [Jekyll](https://jekyllrb.com/) and a modern static web stack, it puts collection metadata to work building beautiful sites.

The basic theme is created using [Bootstrap](https://getbootstrap.com/).
Metadata visualizations are built using open source libraries such as [DataTables](https://datatables.net/), [Leafletjs](http://leafletjs.com/), [Spotlight gallery](https://github.com/nextapps-de/spotlight), [lazysizes](https://github.com/aFarkas/lazysizes), and [Lunr.js](https://lunrjs.com/).
Object metadata is exposed using [Schema.org](http://schema.org) and [Open Graph protocol](http://ogp.me/) standards.

Questions can be directed to **collectionbuilder.team@gmail.com**

## License

CollectionBuilder documentation and general web content is licensed [Creative Commons Attribution-ShareAlike 4.0 International](http://creativecommons.org/licenses/by-sa/4.0/). 
This license does *NOT* include any objects or images used in digital collections, which may have individually applied licenses described by a "rights" field.
CollectionBuilder code is licensed [MIT](https://github.com/CollectionBuilder/collectionbuilder-csv/blob/master/LICENSE). 
This license does not include external dependencies included in the `assets/lib` directory, which are covered by their individual licenses.
