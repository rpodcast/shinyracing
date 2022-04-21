# Dev notes for slides

TODO: Find a way to use custom fonts inside revealjs slides. Here is a snippet of how I put the font in a Shiny app powered by `{golem}`:

```r
golem_add_external_resources <- function(){
  
  add_resource_path(
    'www', app_sys('app/www')
  )
 
  tags$head(
    favicon(),
    bundle_resources(
      path = app_sys('app/www'),
      app_title = 'hotshots.dashboard'
    ),
    tags$link(rel = "stylesheet", type = "text/css", href = "www/css/TTSupermolotNeue.css"),
    tags$style(HTML("body {font-family: 'TTSupermolotNeue-Bold', sans-serif;}" )),
    # Add here other external resources
    # for example, you can add shinyalert::useShinyalert() 
    waiter::use_waiter()
  )
}
```