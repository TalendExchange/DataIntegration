# bcourtine
  <http://blog.courtine.org/>
  <nospam+contact@courtine.org>

## <a href='./components/ExemplesLog4J/readme.md'><img src='./components/ExemplesLog4J/logo.jpg' width='40' height='40'> ExemplesLog4J</a>
 :warning: Compatibility not known

Exemple job, showing various Log4J usecases :

- initialization of loggers before launching the job with tInitLog4J
- direct flow log with tLog4J
- indirect flow log using tWarn, tLogCatcher and tLog4JCatch
- redirection of Talend logs to Log4J with tLogCatcher and tLog4JCatch
- redirection of job statistics to Log4J with tStatCatcher and tLog4J

Job comments are written in French



<img src='./components/ExemplesLog4J/sample.jpg'>

## <a href='./components/StaticMap/readme.md'><img src='./components/StaticMap/logo.jpg' width='40' height='40'> StaticMap</a>
 :warning: Compatibility not known

This component provides tools to store values in a Map.

Unlike the job "globalMap", this Map is static, and can be accessed outside of the job. This Map can be used :
- as an alternative to context variables for job params (if the job is launched by another Java program)
- to keep job infos after execution (if the job is launched by another Java program)
- to share infos between a parent and a child job (in both directions "parent > child" and "child > parent")
<img src='./components/StaticMap/sample.jpg'>

## <a href='./components/StaticThreadLocalMap/readme.md'><img src='./components/StaticThreadLocalMap/logo.jpg' width='40' height='40'> StaticThreadLocalMap</a>
 :warning: Compatibility not known

This component provides tools to store values in a Map.

This routines are the same as the StaticMap routines, but this Map is instanciated once by Thread.

If a Java launcher is used to execute several jobs in different Threads at the same time, using the StaticMap could result in a bug if various jobs use the same keys of the Map.

Theses routines solve this potential bug. But by definition, this routines won't allow to share information between threads.
<img src='./components/StaticThreadLocalMap/sample.jpg'>
