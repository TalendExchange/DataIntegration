# slenk
  <http://www.talend.com/>
  <nospam+slenk@talend.com>

## <a href='./components/XML BIG FILES/readme.md'><img src='./components/XML BIG FILES/logo.jpg' width='40' height='40'> XML BIG FILES</a>
 :warning: Compatibility not known

If you have to handle large XML files then have a look at this as a possible solution. Why? Once you try to load a large (> 500 MB or so) XML you won't get a response from the solution anymore or get heap space errors.
This approach is read the big XML as CSV,then split into small pieces and finally iterate on the small XMLs and do whatever you have to with it afterwards.



<img src='./components/XML BIG FILES/sample.jpg'>
