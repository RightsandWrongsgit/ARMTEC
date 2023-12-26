
# Which YML files do what

| automated_cron.settings.yml               | Can set the Interval |
| comment.settings.yml                      | Log ip addresses: false or true |
| comment.type.comment.yml                  | Allows comments on content: true or false |
| contact.form.feedback.yml                 | Website feedback: true or false and designate recipients of message |
| contact.form.personal.yml                 | Personal contact form: true or false and user as recipient |
| contact.settings.yml                      | Protect against feedback Flooding, set count limit and interval |
| core.base_field_override.page.promote.yml | Promote to front page options |
| core.date_format.fallback.yml             | Pattern for fallback date format and opportunity to lock it |
| core.date_format.html_date.yml            | HTML year/month/day pattern and opportunity to lock it |
| core.date_format.html_datetime.yml        | HTML year/month/day/hour/minute/second pattern and opportunity to lock it |
| core.date_format.html_month.yml           | HTML year/month pattern and opportunity to lock it |
| core.date_format.html_time.yml            | HTML time pattern hour/minute/second and opportunity to lock it |
| core.date_format.html_time.yml            | HTML year/week pattern and opportunity to lock it |
| core.date_format.html_time.yml            | HTML year pattern and opportunity to lock it |
| core.date_format.html_yearless_date.yml   | HTML month/day pattern and opportunity to lock it |
| core.date_format.long.yml                 | pattern: 'l, F j, Y - H:i' |
| core.date_format.medium.yml               | pattern: 'D, m/d/Y - H:i' |
| core.date_format.short.yml                | pattern: 'm/d/Y - H:i' |
| core.date_format.olivero_medium.yml       | pattern: 'j F, Y' |
| dblog.settings.yml                        | Database row_limit (Checkout Watchdog Prune module for coordinated  alternative.) |
| field.settings.yml                        | Set purge_batch_size that runs with cron for database clean up








NOTE: There are also all sorts of field, block, form, menu, action, and view related yml files in your configuration.  Most of those are complex enough in interactions among several that direct editing would be pretty risky if you are a pretty advanced Drupal user. If anyone feels they would like to include some of those, feel free to add to the above table.  If any listed appear to be misrepresented, go ahead and edit in your recommended changes. 
