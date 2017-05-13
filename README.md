# automatic-group-and-page-url


```
<script src="{$system['system_url']}/includes/assets/js/jquery/jquery-3.1.1.min.js"></script>
                                    <script type="text/javascript" charset="utf-8">
                                          $().ready(function () {
                                            $('#username').slugify('#title');
                                            $('[id=slugresult]').slugify('#title');

                                            var pigLatin = function(str) {
                                              return str.replace(/(\w*)([aeiou]\w*)/g, "$2$1ay");
                                            }

                                            $('#pig_latin').slugify('#title', {
                                                slugFunc: function(str, originalFunc) { return pigLatin(originalFunc(str)); }
                                              }
                                            );

                                          });
                                      </script>
```
