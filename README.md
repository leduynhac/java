# java
java notes

<h1>UrlRewrite</h1>
<p>
References:<br/>
- http://tuckey.org/urlrewrite/<br/>
- https://devtidbits.com/2011/11/28/tuckey-urlrewrite-how-to/<br/>  
</p>
<p>
  <b>UrlRewriteFilter</b> is a Java Web Filter for any compliant web application servers <br/>
(such as Tomcat, JBoss, Jetty or Reson), which allows you to rewrite URLs before they get to your code. <br/>
It is a very powerful tool just like <b>Apache's mode_rewrite</b>.<br/>
</p>
<h2>Installation</h2>
<p>
  <b>Step 1:</b> Add urlrewritefilter-4.0.3.jar to WEB-INF/lib<br/>
  Or add Maven dependency:<br/>
    &lt;dependency&gt;<br/>
        &lt;groupId&gt;org.tuckey&lt;/groupId&gt;<br/>
        &lt;artifactId&gt;urlrewritefilter&lt;/artifactId&gt;<br/>
        &lt;version&gt;4.0.3&lt;/version&gt;<br/>
    &lt;/dependency&gt;<br/>
</p>
<p>
  <b>Step 2:</b> add its filter declaration into WEB-INF/web.xml<br/>
    &lt;filter&gt;<br/>
        &lt;filter-name&gt;UrlRewriteFilter&lt;/filter-name&gt;<br/>
        &lt;filter-class&gt;org.tuckey.web.filters.urlrewrite.UrlRewriteFilter&lt;/filter-class&gt;<br/>
          &lt;!-- you can disable status page if desired<br/>
        can be: true, false (default true) --&gt;<br/>
        &lt;init-param&gt;<br/>
          &lt;param-name&gt;statusEnabled&lt;/param-name&gt;<br/>
          &lt;param-value&gt;true&lt;/param-value&gt;<br/>
        &lt;/init-param&gt;<br/>
    &lt;/filter&gt;<br/>
    &lt;filter-mapping&gt;<br/>
        &lt;filter-name&gt;UrlRewriteFilter&lt;/filter-name&gt;<br/>
        &lt;url-pattern&gt;/*&lt;/url-pattern&gt;<br/>
        &lt;dispatcher&gt;REQUEST&lt;/dispatcher&gt;<br/>
        &lt;dispatcher&gt;FORWARD&lt;/dispatcher&gt;<br/>
    &lt;/filter-mapping&gt; <br/>
</p>
<p>
  <b>Step 3:</b> add urlrewrite.xml into WEB-INF<br/>
</p>
<p>
  <b>Step 4:</b> restart Web server and test UrlRewrite installtion via http://127.0.0.1:8080/rewrite-status to see output<br/>
</p>
