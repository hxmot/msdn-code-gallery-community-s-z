# Sqlite Sample for Windows Phone 8.1 (C#-Xaml)
## Requires
- Visual Studio 2013
## License
- MIT
## Technologies
- Windows Phone 8.1
- universal windows app
## Topics
- Using SQLite in Windows Store App
- Using Sqlite in Windows Phone 8.1 apps
## Updated
- 01/20/2015
## Description

<h2><span style="font-family:Verdana,sans-serif; font-size:small">Introduction:</span></h2>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">If you want to implement sqlite database application for windowsphone 8.0,you may helped from my&nbsp;<a href="http://bsubramanyamraju.blogspot.com/2014/08/windowsphone-8-sqlite-storing-data-in.html" target="_blank">previous</a>&nbsp;article.Now
 from this article we will learn about 'Sqlite support in WindowsPhone Store 8.1'.This article is compared with my previous article,so that we can easily understand the changes in WP8.0 &amp; WP8.1 to setup Sqlite environment.</span></p>
<p class="separator"><span style="font-family:Verdana,sans-serif; font-size:small"><a href="http://4.bp.blogspot.com/-G9emSVcUtU0/VL4t6xwZ8BI/AAAAAAAABh8/OV69jGF0fxY/s1600/SQLte.png"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F4.bp.blogspot.com%2F-G9emSVcUtU0%2FVL4t6xwZ8BI%2FAAAAAAAABh8%2FOV69jGF0fxY%2Fs1600%2FSQLte.png&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="409"></a></span></p>
<p><span style="font-size:small">You may read this post at my Original <a title="Sqlite Sample for WP8.1" href="http://bsubramanyamraju.blogspot.com/2015/01/windowsphone-81-sqlite-how-to-store.html" target="_blank">
blog</a>.</span></p>
<p><strong><span style="font-family:Verdana,sans-serif; font-size:small">Requirements:</span></strong></p>
</div>
<h2>
<div>
<ul>
<li><span style="font-family:Verdana,sans-serif; font-size:small">This sample is targeted for windowsphone store 8.1 OS,So make sure you&rsquo;ve downloaded and installed the Windows Phone 8.1 SDK. For more information, see&nbsp;<a href="https://dev.windowsphone.com/en-us/downloadsdk">Get
 the SDK</a>.</span> </li><li><span style="font-family:Verdana,sans-serif; font-size:small">I assumes that you&rsquo;re going to test your app on the Windows Phone emulator. If you want to test your app on a phone, you have to take some additional steps. For more info, see&nbsp;<a href="http://msdn.microsoft.com/en-us/library/windowsphone/develop/dn614128.aspx">Register
 your Windows Phone device for development</a>.</span> </li><li><span style="font-family:Verdana,sans-serif; font-size:small">This post assumes&nbsp;you&rsquo;re using&nbsp;Microsoft Visual Studio Express&nbsp;2013 for Windows.</span>
</li></ul>
</div>
</h2>
<h2><span style="font-family:Verdana,sans-serif; font-size:small">Table of Contents:&nbsp;</span></h2>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">Some extensions to be installed in order to interact with Sqlite from your WP8.1 app.And now it is very easy to setup sqlite environment in our apps.So this post covers all about sqlite with beginners
 level like this.</span></p>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">1)How can i setup SQLite environment?</span></p>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">2)How to perform all SQLite CRUD operations ?</span></p>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">3)How to bind SQLite &nbsp;data to listbox?</span></p>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">4)How to explore my&quot;SQLite&quot; &nbsp;database data?</span></p>
</div>
<h2><span style="font-family:Verdana,sans-serif; font-size:small">Description:</span></h2>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">SQLite is a very light weight database. In this tutorial I&rsquo;ll be discussing how to write classes to handle all SQLite operations.So let's start with above&nbsp;hierarchy&nbsp;which&nbsp;is
 earlier discussed in &quot;Table of&nbsp;Contents&quot;.</span><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
</div>
<div>
<h2><span style="font-family:Verdana,sans-serif; font-size:small">1)How can i setup SQLite environment?</span></h2>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span><span style="font-family:Verdana,sans-serif; font-size:small">Sqlite is directly not available in windowsphone ,and don't worry now it is very easy to setup sqlite in windowsphone
 apps.So we need to follow two steps only (i.e Installing SQLite for Windows Phone SDK,Installing sqlite-net-wp8 package)</span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<div>
<p><span style="font-size:small"><strong>1.1)Installing SQLite for Windows Phone SDK:</strong></span></p>
</div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
</div>
<div>
<p><span style="font-size:small">It&rsquo;s worth noting that the current version (3.8.8.0) has a flaw in the package metadata that prevent it to show up in the Visual Studio 2013 &quot;<strong>Tools | Extensions and Updates</strong>&quot; page. You need to go to the&nbsp;<a href="https://visualstudiogallery.msdn.microsoft.com/5d97faf6-39e3-4048-a0bc-adde2af75d1b" target="_blank">web
 page</a>, download and install the VSIX package by yourself:</span></p>
<p class="separator"><span style="font-size:small"><a href="http://3.bp.blogspot.com/-kpaBXnwBUuM/VL4xM3qK-SI/AAAAAAAABiI/V0pLEm_op28/s1600/SDK.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F3.bp.blogspot.com%2F-kpaBXnwBUuM%2FVL4xM3qK-SI%2FAAAAAAAABiI%2FV0pLEm_op28%2Fs1600%2FSDK.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="243"></a></span></p>
<p>&nbsp;</p>
</div>
<p class="separator"><span style="font-family:Verdana,sans-serif">Click on Download and&nbsp;</span><span style="font-family:Verdana,sans-serif">You can directly open it while downloading, authorize installation and click install when ready.</span></p>
<p class="separator"><span style="font-size:small"><a href="http://1.bp.blogspot.com/-JfzIzyROXEM/U98pXihxaUI/AAAAAAAABDs/-p-AgSJBvnw/s1600/SqliteWPSetupInstaller.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F1.bp.blogspot.com%2F-JfzIzyROXEM%2FU98pXihxaUI%2FAAAAAAAABDs%2F-p-AgSJBvnw%2Fs1600%2FSqliteWPSetupInstaller.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt=""></a></span></p>
<p class="separator">&nbsp;</p>
<p class="separator"><span style="font-size:small"><span style="font-family:Verdana,sans-serif">Open Microsoft&nbsp;<strong>Visual Studio Express 2013 for Windows</strong>&nbsp;and then create new project&nbsp;type Blank App</span><span style="font-family:Verdana,sans-serif">(Ex:SQLiteWp8.1)</span></span></p>
<p class="separator"><span style="font-size:small"><a href="http://1.bp.blogspot.com/-DdeTiwyhGzQ/VL41-hv_IxI/AAAAAAAABio/15JARU-J_zA/s1600/NewProject.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F1.bp.blogspot.com%2F-DdeTiwyhGzQ%2FVL41-hv_IxI%2FAAAAAAAABio%2F15JARU-J_zA%2Fs1600%2FNewProject.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="390"></a></span></p>
<p class="separator"><span style="font-size:small">Open Solution explorer,Right click on 'References' folder of your current project.</span></p>
<p class="separator">&nbsp;</p>
<p><span style="font-size:small"><a href="http://3.bp.blogspot.com/-YOQY03PjJ54/VL4zlAKrUxI/AAAAAAAABiU/-KUplJIfxRU/s1600/AddReference.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F3.bp.blogspot.com%2F-YOQY03PjJ54%2FVL4zlAKrUxI%2FAAAAAAAABiU%2F-KUplJIfxRU%2Fs1600%2FAddReference.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="400" height="352"></a></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small">Then add the reference to the &quot;SQLite for WindowsPhone 8.1&quot; library:</span></p>
<p class="separator"><span style="font-size:small"><a href="http://1.bp.blogspot.com/-NTyzXAA4IIg/VL40a4I0IfI/AAAAAAAABic/6pmWEvQTd8A/s1600/SQLite.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F1.bp.blogspot.com%2F-NTyzXAA4IIg%2FVL40a4I0IfI%2FAAAAAAAABic%2F6pmWEvQTd8A%2Fs1600%2FSQLite.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="440"></a></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small">When done, you can see that the proper references to SQLite and Visual C&#43;&#43; 2013 Runtime have been added to respective project:</span></p>
<p class="separator"><span style="font-size:small"><a href="http://3.bp.blogspot.com/--INcmGB_2n8/VL43KwzfWWI/AAAAAAAABi0/9VqDYafbNtM/s1600/Warning.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F3.bp.blogspot.com%2F--INcmGB_2n8%2FVL43KwzfWWI%2FAAAAAAAABi0%2F9VqDYafbNtM%2Fs1600%2FWarning.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="397" height="400"></a></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small">You may have already noticed, that the references show a warning symbols,to resolve that the next thing to do, before compiling the solution is changing the architecture of the target platform.
 This is the fact that the engine of Sqlite is written in C &#43;&#43;, and the default target platform set in the project is Any CPU. This mode is not supported. To do this in the main menu of VisualStudio have the command &quot;Compile&quot;, then &quot;Configuration Manager&quot;,
 as shown in the figure.</span></p>
<p class="separator">&nbsp;</p>
<p class="separator"><span style="font-size:small"><a href="http://4.bp.blogspot.com/-hAEceo_nvfs/VL4418rEXiI/AAAAAAAABjQ/egrKDWwff6Q/s1600/Config.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F4.bp.blogspot.com%2F-hAEceo_nvfs%2FVL4418rEXiI%2FAAAAAAAABjQ%2FegrKDWwff6Q%2Fs1600%2FConfig.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="196"></a></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><br>
</span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small">In the next dialog, we note that we have several choices of platforms, Any CPU (the default), ARM, x64 and x86.</span></p>
<p class="separator"><span style="font-family:Verdana,sans-serif; font-size:small"><a href="http://4.bp.blogspot.com/-5IYbaL1PBHk/VL44GCHIXqI/AAAAAAAABjE/5MwuYclgJ04/s1600/Error.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F4.bp.blogspot.com%2F-5IYbaL1PBHk%2FVL44GCHIXqI%2FAAAAAAAABjE%2F5MwuYclgJ04%2Fs1600%2FError.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="401"></a></span></p>
<p class="separator"><span style="font-family:Verdana,sans-serif; font-size:small">We have to select the target platform second, where we are trying the application. If we use a tablet, or a phone with ARM processor, we have to select the ARM platform. If
 we are using the emulator or in the case of Windows Phone, a PC in the case of Windows, we have to select x86 or x64, everything depends on your processor if 32 or 64 bits. In my case, I tried the sample application on a emulator &nbsp;with Windows Phone OS
 8.1, so I chose the way of configuration x86.</span></p>
<p>&nbsp;</p>
<h3><span style="font-family:Verdana,sans-serif; font-size:small">1.2)Installing sqlite-net package:</span></h3>
<div>
<p><span style="font-size:small"><span style="font-family:Verdana,sans-serif">After installing the library for SQLite, we need sqlite-net NuGet package.With this library, we will be able to perform all the operations that you normally do in a database, such
 as Insert, Delete, Update and run search queries. Sqlite-net also offers an approach typical ORM. T</span>his package provides two helper classes (<strong>SQLite.cs</strong>&nbsp;and&nbsp;<strong>SQLiteAsync.cs)</strong>,<span style="font-family:Verdana,sans-serif">So
 to install it right click on&nbsp;<strong>your project</strong>&nbsp;(i.e in my case project name is&nbsp;</span>SQLiteWp8.1<span style="font-family:Verdana,sans-serif">) =&gt;Click on &quot;Manage NuGet&nbsp;Packages&quot; and search for &quot;sqlite-net&quot; &nbsp;=&gt; Click
 on &quot;Install&quot; button.After that we should found below dialog:</span></span></p>
</div>
<div>
<p class="separator"><span style="font-size:small"><a href="http://3.bp.blogspot.com/-grFx4A5KaDY/VL492883gsI/AAAAAAAABjg/xpVyppUlp-I/s1600/Sqlite_Net.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F3.bp.blogspot.com%2F-grFx4A5KaDY%2FVL492883gsI%2FAAAAAAAABjg%2FxpVyppUlp-I%2Fs1600%2FSqlite_Net.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="426"></a></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<p class="separator">&nbsp;</p>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<div>
<p><span style="font-size:small">***Wow now whole SQLite set up process is completed,so now we are going to work with all CRUD operations***</span></p>
</div>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<h2><span style="font-family:Verdana,sans-serif; font-size:small">2)How to perform all SQLite CRUD operations ?</span></h2>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<div>
<p><span style="font-size:small"><span style="font-family:Verdana,sans-serif"><strong>Note:&nbsp;</strong>From this step&nbsp;on-wards,most of content will be same as&nbsp;my&nbsp;</span>&nbsp;<a href="http://bsubramanyamraju.blogspot.com/2014/08/windowsphone-8-sqlite-storing-data-in.html" target="_blank">previous</a>&nbsp;article.Please
 be note a few changes made in this post.</span></p>
<p><span style="font-size:small"><br>
</span></p>
<p><span style="font-size:small">So its time to perform all SQLite CRUD(<strong>Create,Read,Update,Delete</strong>) operations.So my thought is in this sample i made one &nbsp;single &quot;<strong>DatabaseHelperClass.cs</strong>&quot; class for whole application and
 handling the SQLite operations with this helper class. Lets see first my table structure first&nbsp;</span></p>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><br>
</span></p>
</div>
<p class="separator">&nbsp;</p>
<p>&nbsp;</p>
<p class="separator"><span style="font-size:small"><a href="http://1.bp.blogspot.com/-PTFbenwUezA/U984O9fwyoI/AAAAAAAABFA/d0uXjIVQmo4/s1600/TableStructure.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F1.bp.blogspot.com%2F-PTFbenwUezA%2FU984O9fwyoI%2FAAAAAAAABFA%2Fd0uXjIVQmo4%2Fs1600%2FTableStructure.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="372"></a></span></p>
<p class="separator">&nbsp;</p>
<div>
<p><span style="font-size:small"><span style="font-family:Verdana,sans-serif">Here i am&nbsp;trying&nbsp;to create Table name is &quot;<strong>Contacts</strong>&quot; in &quot;<strong>ContactsManager.sqlite</strong>&quot;&nbsp;database.So my class &quot;Contacts&quot; with all getter and
 setter methods(<strong>Id,Name,PhoneNumber,CreatedDate</strong>)</span><span style="font-family:Verdana,sans-serif">&nbsp;to maintain single contact as an object.</span></span></p>
</div>
</div>
<div>
<p class="separator"><span style="font-family:Verdana,sans-serif; font-size:small"><br>
</span></p>
<div>
<div class="title">
<p><span style="font-size:small">C#</span></p>
</div>
<div class="pluginLinkHolder">
<p>&nbsp;</p>
</div>
<div class="preview">
<pre class="xaml"><pre class="xaml"><pre class="csharp"><pre class="csharp"><span style="font-size:small"><span style="color:#0000ff">public class</span> <span style="color:#3d85c6">Contacts</span>
    {
        <span style="color:#38761d">//The Id property is marked as the Primary Key</span>
        [SQLite.<span style="color:#3d85c6">PrimaryKey</span>, SQLite.<span style="color:#3d85c6">AutoIncrement</span>]
        <span style="color:#0000ff">public int</span> Id { get; set; }
        <span style="color:#0000ff">public string</span> Name { get; set; }
        <span style="color:#0000ff">public string</span> PhoneNumber { get; set; }
        <span style="color:#0000ff">public string</span> CreationDate { get; set; }
        <span style="color:#0000ff">public</span> Contacts()
        {
            <span style="color:#38761d">//empty constructor</span>
        }
        <span style="color:#0000ff">public</span> Contacts(<span style="color:#0000ff">string</span> name, <span style="color:#0000ff">string</span> phone_no)
        {
            Name = name;
            PhoneNumber = phone_no;
            CreationDate = DateTime.Now.ToString();
        }
    }</span></pre>
</pre>
</pre>
</pre>
</div>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><strong>2.1)Writing DatabaseHelper Class to handle database operations(i.e CRUD):</strong></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><strong><br>
</strong></span></p>
<div class="title">
<p><span style="font-size:small">C#</span></p>
</div>
<div class="pluginLinkHolder">
<p>&nbsp;</p>
</div>
<div class="preview">
<pre class="xaml"><pre class="xaml"><pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__com" style="color:#008000">//This&nbsp;class&nbsp;for&nbsp;perform&nbsp;all&nbsp;database&nbsp;CRUD&nbsp;operations</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">class</span>&nbsp;DatabaseHelperClass&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SQLiteConnection&nbsp;dbConn;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//Create&nbsp;Tabble</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;async&nbsp;Task&lt;<span class="cs__keyword" style="color:#3a3aff">bool</span>&gt;&nbsp;onCreate(<span class="cs__keyword" style="color:#3a3aff">string</span>&nbsp;DB_PATH)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">try</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">if</span>&nbsp;(!CheckFileExists(DB_PATH).Result)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">using</span>&nbsp;(dbConn&nbsp;=&nbsp;<span class="cs__keyword" style="color:#3a3aff">new</span>&nbsp;SQLiteConnection(DB_PATH))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.CreateTable&lt;Contacts&gt;();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">return</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">true</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">catch</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">return</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">false</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">private</span>&nbsp;async&nbsp;Task&lt;<span class="cs__keyword" style="color:#3a3aff">bool</span>&gt;&nbsp;CheckFileExists(<span class="cs__keyword" style="color:#3a3aff">string</span>&nbsp;fileName)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">try</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var&nbsp;store&nbsp;=&nbsp;await&nbsp;Windows.Storage.ApplicationData.Current.LocalFolder.GetFileAsync(fileName);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">return</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">true</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">catch</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">return</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">false</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//&nbsp;Retrieve&nbsp;the&nbsp;specific&nbsp;contact&nbsp;from&nbsp;the&nbsp;database.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;Contacts&nbsp;ReadContact(<span class="cs__keyword" style="color:#3a3aff">int</span>&nbsp;contactid)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">using</span>&nbsp;(var&nbsp;dbConn&nbsp;=&nbsp;<span class="cs__keyword" style="color:#3a3aff">new</span>&nbsp;SQLiteConnection(App.DB_PATH))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var&nbsp;existingconact&nbsp;=&nbsp;dbConn.Query&lt;Contacts&gt;(<span class="cs__string" style="color:#800000">&quot;select&nbsp;*&nbsp;from&nbsp;Contacts&nbsp;where&nbsp;Id&nbsp;=&quot;</span>&nbsp;&#43;&nbsp;contactid).FirstOrDefault();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">return</span>&nbsp;existingconact;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//&nbsp;Retrieve&nbsp;the&nbsp;all&nbsp;contact&nbsp;list&nbsp;from&nbsp;the&nbsp;database.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;ObservableCollection&lt;Contacts&gt;&nbsp;ReadContacts()&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">using</span>&nbsp;(var&nbsp;dbConn&nbsp;=&nbsp;<span class="cs__keyword" style="color:#3a3aff">new</span>&nbsp;SQLiteConnection(App.DB_PATH))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;List&lt;Contacts&gt;&nbsp;myCollection&nbsp;&nbsp;=&nbsp;dbConn.Table&lt;Contacts&gt;().ToList&lt;Contacts&gt;();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ObservableCollection&lt;Contacts&gt;&nbsp;ContactsList&nbsp;=&nbsp;<span class="cs__keyword" style="color:#3a3aff">new</span>&nbsp;ObservableCollection&lt;Contacts&gt;(myCollection);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">return</span>&nbsp;ContactsList;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//Update&nbsp;existing&nbsp;conatct</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">void</span>&nbsp;UpdateContact(Contacts&nbsp;contact)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">using</span>&nbsp;(var&nbsp;dbConn&nbsp;=&nbsp;<span class="cs__keyword" style="color:#3a3aff">new</span>&nbsp;SQLiteConnection(App.DB_PATH))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var&nbsp;existingconact&nbsp;=&nbsp;dbConn.Query&lt;Contacts&gt;(<span class="cs__string" style="color:#800000">&quot;select&nbsp;*&nbsp;from&nbsp;Contacts&nbsp;where&nbsp;Id&nbsp;=&quot;</span>&nbsp;&#43;&nbsp;contact.Id).FirstOrDefault();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">if</span>&nbsp;(existingconact&nbsp;!=&nbsp;<span class="cs__keyword" style="color:#3a3aff">null</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;existingconact.Name&nbsp;=&nbsp;contact.Name;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;existingconact.PhoneNumber&nbsp;=&nbsp;contact.PhoneNumber;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;existingconact.CreationDate&nbsp;=&nbsp;contact.CreationDate;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.RunInTransaction(()&nbsp;=&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.Update(existingconact);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;});&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//&nbsp;Insert&nbsp;the&nbsp;new&nbsp;contact&nbsp;in&nbsp;the&nbsp;Contacts&nbsp;table.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">void</span>&nbsp;Insert(Contacts&nbsp;newcontact)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">using</span>&nbsp;(var&nbsp;dbConn&nbsp;=&nbsp;<span class="cs__keyword" style="color:#3a3aff">new</span>&nbsp;SQLiteConnection(App.DB_PATH))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.RunInTransaction(()&nbsp;=&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.Insert(newcontact);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;});&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//Delete&nbsp;specific&nbsp;contact</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">void</span>&nbsp;DeleteContact(<span class="cs__keyword" style="color:#3a3aff">int</span>&nbsp;Id)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">using</span>&nbsp;(var&nbsp;dbConn&nbsp;=&nbsp;<span class="cs__keyword" style="color:#3a3aff">new</span>&nbsp;SQLiteConnection(App.DB_PATH))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var&nbsp;existingconact&nbsp;=&nbsp;dbConn.Query&lt;Contacts&gt;(<span class="cs__string" style="color:#800000">&quot;select&nbsp;*&nbsp;from&nbsp;Contacts&nbsp;where&nbsp;Id&nbsp;=&quot;</span>&nbsp;&#43;&nbsp;Id).FirstOrDefault();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">if</span>&nbsp;(existingconact&nbsp;!=&nbsp;<span class="cs__keyword" style="color:#3a3aff">null</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.RunInTransaction(()&nbsp;=&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.Delete(existingconact);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;});&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//Delete&nbsp;all&nbsp;contactlist&nbsp;or&nbsp;delete&nbsp;Contacts&nbsp;table</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">void</span>&nbsp;DeleteAllContact()&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">using</span>&nbsp;(var&nbsp;dbConn&nbsp;=&nbsp;<span class="cs__keyword" style="color:#3a3aff">new</span>&nbsp;SQLiteConnection(App.DB_PATH))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//dbConn.RunInTransaction(()&nbsp;=&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//&nbsp;&nbsp;&nbsp;{</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.DropTable&lt;Contacts&gt;();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.CreateTable&lt;Contacts&gt;();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.Dispose();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dbConn.Close();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com" style="color:#008000">//});</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
</pre>
</pre>
</div>
<h2><span style="font-family:Verdana,sans-serif; font-size:small">3)How to bind SQLite &nbsp;data to listbox?</span></h2>
</div>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">In above&nbsp;<strong>step 2.1</strong>&nbsp;i created one Database helper class name is &quot;<strong>DatabaseHelperClass.cs</strong>&quot; which is main head for this sample to perform all SQlite operations.Lets
 first see my project&nbsp;hierarchy&nbsp;like this</span></p>
</div>
<p class="separator">&nbsp;</p>
<p class="separator">&nbsp;</p>
<p class="separator"><span style="font-size:small"><a href="http://2.bp.blogspot.com/-Llj1lDw4p7A/VL5C7bDnOhI/AAAAAAAABjw/-4oJGKI37ao/s1600/References.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F2.bp.blogspot.com%2F-Llj1lDw4p7A%2FVL5C7bDnOhI%2FAAAAAAAABjw%2F-4oJGKI37ao%2Fs1600%2FReferences.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="332" height="400"></a></span></p>
<p class="separator">&nbsp;</p>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">In the app.xaml class lets create a database. &nbsp;In the constructor we check if the database exists and if it does not we create it. &nbsp;Since if there is no file exists ,it will get an exception.&nbsp;</span></p>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><br>
</span></p>
</div>
<div>
<div class="title">
<p><span style="font-size:small">C#</span></p>
</div>
<div class="pluginLinkHolder">
<p>&nbsp;</p>
</div>
<div class="preview">
<pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;partial&nbsp;<span class="cs__keyword" style="color:#3a3aff">class</span>&nbsp;App&nbsp;:&nbsp;Application&nbsp;
{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">static</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">string</span>&nbsp;DB_PATH&nbsp;=&nbsp;Path.Combine(Path.Combine(ApplicationData.Current.LocalFolder.Path,&nbsp;<span class="cs__string" style="color:#800000">&quot;ContactsManager.sqlite&quot;</span>));<span class="cs__com" style="color:#008000">//DataBase&nbsp;Name</span>&nbsp;
<span class="cs__keyword" style="color:#3a3aff">public</span>&nbsp;App()&nbsp;
&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">if</span>&nbsp;(!CheckFileExists(<span class="cs__string" style="color:#800000">&quot;ContactsManager.sqlite&quot;</span>).Result)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">using</span>&nbsp;(var&nbsp;db&nbsp;=&nbsp;<span class="cs__keyword" style="color:#3a3aff">new</span>&nbsp;SQLiteConnection(DB_PATH))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;db.CreateTable&lt;Contacts&gt;();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;
&nbsp;&nbsp;}&nbsp;
&nbsp;
<span class="cs__keyword" style="color:#3a3aff">private</span>&nbsp;async&nbsp;Task&lt;<span class="cs__keyword" style="color:#3a3aff">bool</span>&gt;&nbsp;CheckFileExists(<span class="cs__keyword" style="color:#3a3aff">string</span>&nbsp;fileName)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">try</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var&nbsp;store&nbsp;=&nbsp;await&nbsp;Windows.Storage.ApplicationData.Current.LocalFolder.GetFileAsync(fileName);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">return</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">true</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">catch</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword" style="color:#3a3aff">return</span>&nbsp;<span class="cs__keyword" style="color:#3a3aff">false</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
</div>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">Next I divided my project into MVVM pattern for simplicity.So in Model folder i placed table class name is &quot;Contacts.cs&quot;.In ViewModels i placed DB helpers classes(DatabaseHelperClass.cs &amp;
 ReadAllContactsList.cs).And finally Views folder i placed All my three UI related pages</span></p>
</div>
<div>
<ul>
<li><span style="font-family:Verdana,sans-serif; font-size:small"><strong>AddConatct.xaml:</strong>This page for adding contact to database,when click on &quot;Add Contact&quot; button it will be add contact in database like this
<p class="separator"><a href="http://3.bp.blogspot.com/-tmG0Pq5FGtw/VL5DIYvzFSI/AAAAAAAABj4/dB_HIZf8oQ8/s1600/Intial.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F3.bp.blogspot.com%2F-tmG0Pq5FGtw%2FVL5DIYvzFSI%2FAAAAAAAABj4%2FdB_HIZf8oQ8%2Fs1600%2FIntial.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="223" height="400"></a></p>
<p class="separator">&nbsp;</p>
</span></li></ul>
</div>
<div>
<div class="title"><span style="font-size:small">C#</span></div>
<div class="pluginLinkHolder"></div>
<div class="preview">
<pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__keyword">private</span>&nbsp;async&nbsp;<span class="cs__keyword">void</span>&nbsp;AddContact_Click(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;RoutedEventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DatabaseHelperClass&nbsp;Db_Helper&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;DatabaseHelperClass();<span class="cs__com">//Creating&nbsp;object&nbsp;for&nbsp;DatabaseHelperClass.cs&nbsp;from&nbsp;ViewModel/DatabaseHelperClass.cs&nbsp;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(NametxtBx.Text&nbsp;!=&nbsp;<span class="cs__string">&quot;&quot;</span>&nbsp;&amp;&nbsp;PhonetxtBx.Text&nbsp;!=&nbsp;<span class="cs__string">&quot;&quot;</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Db_Helper.Insert(<span class="cs__keyword">new</span>&nbsp;Contacts(NametxtBx.Text,&nbsp;PhonetxtBx.Text));&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Frame.Navigate(<span class="cs__keyword">typeof</span>(ReadContactList));<span class="cs__com">//after&nbsp;add&nbsp;contact&nbsp;redirect&nbsp;to&nbsp;contact&nbsp;listbox&nbsp;page&nbsp;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">else</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MessageDialog&nbsp;messageDialog&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;MessageDialog(<span class="cs__string">&quot;Please&nbsp;fill&nbsp;two&nbsp;fields&quot;</span>);<span class="cs__com">//Text&nbsp;should&nbsp;not&nbsp;be&nbsp;empty&nbsp;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;await&nbsp;messageDialog.ShowAsync();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
</div>
</div>
<div>
<ul>
<li><span style="font-size:small"><strong>ReadContactList.xaml:</strong><span style="font-family:Verdana,sans-serif">This page for displaying all DB contact list with listbox.And in this screen there is two buttons(Add Contact &amp; DeleteAll) for correspondingly
 add contact to DB / Delete entire table data.</span><span style="font-family:Verdana,sans-serif">Firstly i made following listbox datatemplate for binding database contacts<br>
</span></span></li></ul>
<div class="title"><span style="font-size:small">XAML</span></div>
<div class="pluginLinkHolder"></div>
<div class="preview">
<pre class="xaml"><pre class="xaml"><span style="font-size:small"><span class="xaml__tag_start">&lt;Grid</span>&nbsp;x:<span class="xaml__attr_name">Name</span>=<span class="xaml__attr_value">&quot;ContentPanel&quot;</span>&nbsp;Grid.<span class="xaml__attr_name">Row</span>=<span class="xaml__attr_value">&quot;1&quot;</span>&nbsp;<span class="xaml__attr_name">Margin</span>=<span class="xaml__attr_value">&quot;12,0,12,0&quot;</span><span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;Grid</span>.RowDefinitions<span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;RowDefinition</span>&nbsp;<span class="xaml__attr_name">Height</span>=<span class="xaml__attr_value">&quot;auto&quot;</span><span class="xaml__tag_start">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;RowDefinition</span>&nbsp;<span class="xaml__attr_name">Height</span>=<span class="xaml__attr_value">&quot;*&quot;</span><span class="xaml__tag_start">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/Grid.RowDefinitions&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;StackPanel</span>&nbsp;<span class="xaml__attr_name">Width</span>=<span class="xaml__attr_value">&quot;400&quot;</span>&nbsp;<span class="xaml__attr_name">Orientation</span>=<span class="xaml__attr_value">&quot;Horizontal&quot;</span>&nbsp;Grid.<span class="xaml__attr_name">Row</span>=<span class="xaml__attr_value">&quot;0&quot;</span><span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;Button</span>&nbsp;&nbsp;<span class="xaml__attr_name">Margin</span>=<span class="xaml__attr_value">&quot;20,0,0,0&quot;</span>&nbsp;<span class="xaml__attr_name">Content</span>=<span class="xaml__attr_value">&quot;Add&nbsp;Contact&quot;</span>&nbsp;&nbsp;<span class="xaml__attr_name">Click</span>=<span class="xaml__attr_value">&quot;AddContact_Click&quot;</span><span class="xaml__tag_start">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;Button</span>&nbsp;<span class="xaml__attr_name">Name</span>=<span class="xaml__attr_value">&quot;Btn_Delete&quot;</span>&nbsp;<span class="xaml__attr_name">Margin</span>=<span class="xaml__attr_value">&quot;100,0,0,0&quot;</span>&nbsp;<span class="xaml__attr_name">Content</span>=<span class="xaml__attr_value">&quot;DeleteAll&quot;</span>&nbsp;<span class="xaml__attr_name">Click</span>=<span class="xaml__attr_value">&quot;DeleteAll_Click&quot;</span><span class="xaml__tag_start">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_end">&lt;/StackPanel&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;ListBox</span>&nbsp;<span class="xaml__attr_name">Background</span>=<span class="xaml__attr_value">&quot;Transparent&quot;</span>&nbsp;<span class="xaml__attr_name">Margin</span>=<span class="xaml__attr_value">&quot;6&quot;</span>&nbsp;<span class="xaml__attr_name">Height</span>=<span class="xaml__attr_value">&quot;auto&quot;</span>&nbsp;<span class="xaml__attr_name">BorderThickness</span>=<span class="xaml__attr_value">&quot;2&quot;</span>&nbsp;<span class="xaml__attr_name">MaxHeight</span>=<span class="xaml__attr_value">&quot;580&quot;</span>&nbsp;Grid.<span class="xaml__attr_name">Row</span>=<span class="xaml__attr_value">&quot;1&quot;</span>&nbsp;x:<span class="xaml__attr_name">Name</span>=<span class="xaml__attr_value">&quot;listBoxobj&quot;</span>&nbsp;<span class="xaml__attr_name">SelectionChanged</span>=<span class="xaml__attr_value">&quot;listBoxobj_SelectionChanged&quot;</span><span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;ListBox</span>.ItemTemplate<span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;DataTemplate</span><span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;Grid</span>&nbsp;<span class="xaml__attr_name">Width</span>=<span class="xaml__attr_value">&quot;350&quot;</span>&nbsp;<span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;Border</span>&nbsp;<span class="xaml__attr_name">Margin</span>=<span class="xaml__attr_value">&quot;5&quot;</span>&nbsp;<span class="xaml__attr_name">BorderBrush</span>=<span class="xaml__attr_value">&quot;White&quot;</span>&nbsp;<span class="xaml__attr_name">BorderThickness</span>=<span class="xaml__attr_value">&quot;1&quot;</span><span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;Grid</span><span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;Grid</span>.RowDefinitions<span class="xaml__tag_start">&gt;&nbsp;
</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;RowDefinition</span>&nbsp;<span class="xaml__attr_name">Height</span>=<span class="xaml__attr_value">&quot;Auto&quot;</span><span class="xaml__tag_start">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;RowDefinition</span>&nbsp;<span class="xaml__attr_name">Height</span>=<span class="xaml__attr_value">&quot;Auto&quot;</span><span class="xaml__tag_start">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/Grid.RowDefinitions&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;TextBlock</span>&nbsp;<span class="xaml__attr_name">Margin</span>=<span class="xaml__attr_value">&quot;5,0,0,0&quot;</span>&nbsp;Grid.<span class="xaml__attr_name">Row</span>=<span class="xaml__attr_value">&quot;0&quot;</span>&nbsp;x:<span class="xaml__attr_name">Name</span>=<span class="xaml__attr_value">&quot;NameTxt&quot;</span>&nbsp;<span class="xaml__attr_name">TextWrapping</span>=<span class="xaml__attr_value">&quot;Wrap&quot;</span>&nbsp;<span class="xaml__attr_name">Text</span>=<span class="xaml__attr_value">&quot;{Binding&nbsp;Name}&quot;</span>&nbsp;<span class="xaml__attr_name">FontSize</span>=<span class="xaml__attr_value">&quot;28&quot;</span>&nbsp;<span class="xaml__attr_name">Foreground</span>=<span class="xaml__attr_value">&quot;White&quot;</span><span class="xaml__tag_start">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;TextBlock</span>&nbsp;Grid.<span class="xaml__attr_name">Row</span>=<span class="xaml__attr_value">&quot;0&quot;</span>&nbsp;Text=&quot;<span class="xaml__tag_start">&gt;</span>&quot;&nbsp;FontSize=&quot;28&quot;&nbsp;&nbsp;HorizontalAlignment=&quot;Right&quot;&nbsp;VerticalAlignment=&quot;Center&quot;&nbsp;Foreground=&quot;White&quot;<span class="xaml__tag_end">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;TextBlock</span>&nbsp;<span class="xaml__attr_name">Margin</span>=<span class="xaml__attr_value">&quot;5,0,0,0&quot;</span>&nbsp;Grid.<span class="xaml__attr_name">Row</span>=<span class="xaml__attr_value">&quot;1&quot;</span>&nbsp;x:<span class="xaml__attr_name">Name</span>=<span class="xaml__attr_value">&quot;PhoneTxt&quot;</span>&nbsp;&nbsp;<span class="xaml__attr_name">TextWrapping</span>=<span class="xaml__attr_value">&quot;Wrap&quot;</span>&nbsp;<span class="xaml__attr_name">Foreground</span>=<span class="xaml__attr_value">&quot;White&quot;</span>&nbsp;<span class="xaml__attr_name">FontSize</span>=<span class="xaml__attr_value">&quot;18&quot;</span>&nbsp;<span class="xaml__attr_name">Text</span>=<span class="xaml__attr_value">&quot;{Binding&nbsp;PhoneNumber}&quot;</span>&nbsp;<span class="xaml__tag_start">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_start">&lt;TextBlock</span>&nbsp;<span class="xaml__attr_name">HorizontalAlignment</span>=<span class="xaml__attr_value">&quot;Right&quot;</span>&nbsp;<span class="xaml__attr_name">Margin</span>=<span class="xaml__attr_value">&quot;0,0,35,0&quot;</span>&nbsp;Grid.<span class="xaml__attr_name">Row</span>=<span class="xaml__attr_value">&quot;3&quot;</span>&nbsp;x:<span class="xaml__attr_name">Name</span>=<span class="xaml__attr_value">&quot;CreateddateTxt&quot;</span>&nbsp;<span class="xaml__attr_name">Foreground</span>=<span class="xaml__attr_value">&quot;White&quot;</span>&nbsp;<span class="xaml__attr_name">FontSize</span>=<span class="xaml__attr_value">&quot;18&quot;</span>&nbsp;<span class="xaml__attr_name">TextWrapping</span>=<span class="xaml__attr_value">&quot;Wrap&quot;</span>&nbsp;<span class="xaml__attr_name">Text</span>=<span class="xaml__attr_value">&quot;{Binding&nbsp;CreationDate}&quot;</span>&nbsp;<span class="xaml__tag_start">/&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_end">&lt;/Grid&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_end">&lt;/Border&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_end">&lt;/Grid&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_end">&lt;/DataTemplate&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/ListBox.ItemTemplate&gt;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_end">&lt;/ListBox&gt;</span>&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="xaml__tag_end">&lt;/Grid&gt;</span></span></pre>
</pre>
</div>
<div class="preview"></div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<p class="separator">&nbsp;</p>
<p class="separator"><span style="font-size:small"><a href="http://4.bp.blogspot.com/-h5EdDGdA2Zs/VL5FH_jnlpI/AAAAAAAABkE/D4h2zPUmOAg/s1600/Simple.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F4.bp.blogspot.com%2F-h5EdDGdA2Zs%2FVL5FH_jnlpI%2FAAAAAAAABkE%2FD4h2zPUmOAg%2Fs1600%2FSimple.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="223" height="400"></a></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><br>
</span></p>
<p class="separator"><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<p><span style="font-size:small"><span style="font-family:Verdana,sans-serif">&nbsp;</span><span style="font-family:Verdana,sans-serif">So when page is loaded ,i done like this</span>&nbsp;</span></p>
</div>
<div>
<p>&nbsp;</p>
<div class="title"><span style="font-size:small">C#</span></div>
<div class="pluginLinkHolder"></div>
<div class="preview">
<pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;ReadContactList_Loaded(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;RoutedEventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ReadAllContactsList&nbsp;dbcontacts&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;ReadAllContactsList();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DB_ContactList&nbsp;=&nbsp;dbcontacts.GetAllContacts();<span class="cs__com">//Get&nbsp;all&nbsp;DB&nbsp;contacts&nbsp;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(DB_ContactList.Count&nbsp;&gt;&nbsp;<span class="cs__number">0</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Btn_Delete.IsEnabled&nbsp;=&nbsp;<span class="cs__keyword">true</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;listBoxobj.ItemsSource&nbsp;=&nbsp;DB_ContactList.OrderByDescending(i&nbsp;=&gt;&nbsp;i.Id).ToList();<span class="cs__com">//Binding&nbsp;DB&nbsp;data&nbsp;to&nbsp;LISTBOX&nbsp;and&nbsp;Latest&nbsp;contact&nbsp;ID&nbsp;can&nbsp;Display&nbsp;first.&nbsp;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
</div>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">When &quot;Add Contact&quot; button is clicked is navigated to &quot;<strong>AddConatct.xaml</strong>&quot; page to add contact in DB.</span></p>
<p><span style="font-size:small"><br>
</span></p>
<div class="title"><span style="font-size:small">C#</span></div>
<div class="pluginLinkHolder"></div>
<div class="preview">
<pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;AddContact_Click(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;RoutedEventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Frame.Navigate(<span class="cs__keyword">typeof</span>(AddConatct));&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
</div>
<p><span style="font-size:small">When &quot;DeleteAll&quot; button is clicked ,i done like this</span></p>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><br>
</span></p>
<div class="title"><span style="font-size:small">C#</span></div>
<div class="pluginLinkHolder"></div>
<div class="preview">
<pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__keyword">private</span>&nbsp;async&nbsp;<span class="cs__keyword">void</span>&nbsp;DeleteAll_Click(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;RoutedEventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var&nbsp;dialog&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;MessageDialog(<span class="cs__string">&quot;Are&nbsp;you&nbsp;sure&nbsp;you&nbsp;want&nbsp;to&nbsp;remove&nbsp;all&nbsp;your&nbsp;data&nbsp;?&quot;</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dialog.Commands.Add(<span class="cs__keyword">new</span>&nbsp;UICommand(<span class="cs__string">&quot;No&quot;</span>,&nbsp;<span class="cs__keyword">new</span>&nbsp;UICommandInvokedHandler(Command)));&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dialog.Commands.Add(<span class="cs__keyword">new</span>&nbsp;UICommand(<span class="cs__string">&quot;Yes&quot;</span>,&nbsp;<span class="cs__keyword">new</span>&nbsp;UICommandInvokedHandler(Command)));&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;await&nbsp;dialog.ShowAsync();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
<pre class="csharp"><span style="font-size:small">&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;Command(IUICommand&nbsp;command)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(command.Label.Equals(<span class="cs__string">&quot;Yes&quot;</span>))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DatabaseHelperClass&nbsp;Db_Helper&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;DatabaseHelperClass();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Db_Helper.DeleteAllContact();<span class="cs__com">//delete&nbsp;all&nbsp;DB&nbsp;contacts&nbsp;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DB_ContactList.Clear();<span class="cs__com">//Clear&nbsp;collections&nbsp;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Btn_Delete.IsEnabled&nbsp;=&nbsp;<span class="cs__keyword">false</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;listBoxobj.ItemsSource&nbsp;=&nbsp;DB_ContactList;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
</div>
<p><span style="font-size:small"><span style="font-family:Verdana,sans-serif">When selected listbox item ,i navigate to &quot;<strong>Delete_UpdateContacts.xaml</strong>&quot; page for delete/update corresponding contact details&nbsp;on listbox&nbsp;<strong>SelectionChanged</strong>&nbsp;event&nbsp;</span><span style="font-family:Verdana,sans-serif">&nbsp;like
 this.</span></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><br>
</span></p>
<div class="title"><span style="font-size:small">C#</span></div>
<div class="pluginLinkHolder"></div>
<div class="preview">
<pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;listBoxobj_SelectionChanged(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;SelectionChangedEventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">int</span>&nbsp;SelectedContactID&nbsp;=&nbsp;<span class="cs__number">0</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(listBoxobj.SelectedIndex&nbsp;!=&nbsp;-<span class="cs__number">1</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Contacts&nbsp;listitem&nbsp;=&nbsp;listBoxobj.SelectedItem&nbsp;<span class="cs__keyword">as</span>&nbsp;Contacts;<span class="cs__com">//Get&nbsp;slected&nbsp;listbox&nbsp;item&nbsp;contact&nbsp;ID&nbsp;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Frame.Navigate(<span class="cs__keyword">typeof</span>(Delete_UpdateContacts),SelectedContactID=listitem.Id);&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
</div>
</div>
<div>
<ul>
<li><span style="font-size:small"><strong>Delete_UpdateContacts.xaml:</strong><span style="font-family:Verdana,sans-serif">This page is for updating/delete selected contact details
<p class="separator">&nbsp;</p>
</span></span></li></ul>
<span style="font-size:small"><a href="http://3.bp.blogspot.com/-FWCQ2xr0dQo/VL5GyJZFI1I/AAAAAAAABkQ/hs8fqCuBLw4/s1600/C%23.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F3.bp.blogspot.com%2F-FWCQ2xr0dQo%2FVL5GyJZFI1I%2FAAAAAAAABkQ%2Fhs8fqCuBLw4%2Fs1600%2FC%2523.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="223" height="400"></a><span style="font-family:Verdana,sans-serif"><br>
</span></span>
<p><span style="font-family:Verdana,sans-serif; font-size:small">See in above when listbox item is selected ,i passed selected&nbsp;contact&nbsp;Id as query&nbsp;string,so in this i get that id in &quot;<strong>OnNavigatedTo</strong>&quot; method like this<br>
</span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><br>
</span></p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span style="font-size:small">C#</span></div>
<div class="pluginLinkHolder"></div>
<div class="preview">
<pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__keyword">protected</span>&nbsp;<span class="cs__keyword">override</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;OnNavigatedTo(NavigationEventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Selected_ContactId&nbsp;=&nbsp;<span class="cs__keyword">int</span>.Parse(e.Parameter.ToString());&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;currentcontact&nbsp;=&nbsp;Db_Helper.ReadContact(Selected_ContactId);<span class="cs__com">//Read&nbsp;selected&nbsp;DB&nbsp;contact</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;NametxtBx.Text&nbsp;=&nbsp;currentcontact.Name;<span class="cs__com">//get&nbsp;contact&nbsp;Name</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;PhonetxtBx.Text&nbsp;=&nbsp;currentcontact.PhoneNumber;<span class="cs__com">//get&nbsp;contact&nbsp;PhoneNumber</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
<div></div>
</div>
</div>
</div>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">When &quot;Delete&quot; button is pressed i done like this.</span></p>
<p><span style="font-size:small"><br>
</span></p>
<div class="title"><span style="font-size:small">C#</span></div>
<div class="pluginLinkHolder"></div>
<div class="preview">
<pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;DeleteContact_Click(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;RoutedEventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Db_Helper.DeleteContact(Selected_ContactId);<span class="cs__com">//Delete&nbsp;selected&nbsp;DB&nbsp;contact&nbsp;Id.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Frame.Navigate(<span class="cs__keyword">typeof</span>(ReadContactList));&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
</div>
<p><span style="font-size:small">When &quot;Update&quot; button is pressed i done like this.</span></p>
<p><span style="font-size:small"><br>
</span></p>
<div class="title"><span style="font-size:small">C#</span></div>
<div class="pluginLinkHolder"></div>
<div class="preview">
<pre class="csharp"><pre class="csharp"><span style="font-size:small"><span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;UpdateContact_Click(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;RoutedEventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;currentcontact.Name&nbsp;=&nbsp;NametxtBx.Text;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;currentcontact.PhoneNumber&nbsp;=&nbsp;PhonetxtBx.Text;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Db_Helper.UpdateContact(currentcontact);<span class="cs__com">//Update&nbsp;selected&nbsp;DB&nbsp;contact&nbsp;Id</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Frame.Navigate(<span class="cs__keyword">typeof</span>(ReadContactList));&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</span></pre>
</pre>
</div>
</div>
<div>
<h2><span style="font-family:Verdana,sans-serif; font-size:small">4)How to explore my SQLite &nbsp;database data?</span></h2>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">Isolated Storage Explorer tool to get the database file.This tool is installed under folder path is&nbsp;<strong>Program Files (x86)\Microsoft SDKs\Windows Phone\v8.1\Tools\IsolatedStorageExplorerTool</strong></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><strong><br>
</strong></span></p>
</div>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">To use Isolated Storage Explorer, the following things must be true:</span></p>
</div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<div>
<ul>
<span style="font-family:Verdana,sans-serif">
<li><span style="font-size:small">The app that you want to test must be installed on the emulator or device.</span>
</li><li><span style="font-size:small">The emulator or device must be running, but the app doesn&rsquo;t have to be running.</span>
</span></li></ul>
</div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">You cannot do the following things with Isolated Storage Explorer:</span></p>
</div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span></p>
<div>
<ul>
<span style="font-family:Verdana,sans-serif">
<li><span style="font-size:small">You can&rsquo;t view isolated storage for apps that you&rsquo;ve installed from the Windows Phone Store.</span>
</li><li><span style="font-size:small">You can&rsquo;t view app settings that are stored in the local folder in Isolated Storage Explorer. These are settings that the app saved by using the IsolatedStorageSettings class.</span>
</span></li></ul>
</div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">&nbsp;</span><span style="font-family:Verdana,sans-serif; font-size:small">After that&nbsp;execute&nbsp;following commands from command prompt.</span></p>
</div>
<div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">1)First change command prompt&nbsp;directory&nbsp;path to&nbsp;<strong>Program Files (x86)\Microsoft&nbsp;SDKs\Windows Phone\v8.1\Tools\IsolatedStorageExplorerTool</strong></span></p>
<p class="separator"><span style="font-size:small"><a href="http://2.bp.blogspot.com/-3iSRb-b1Zo0/VL5L130Q5eI/AAAAAAAABkg/TdOr8LFOf-c/s1600/Cmd1.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F2.bp.blogspot.com%2F-3iSRb-b1Zo0%2FVL5L130Q5eI%2FAAAAAAAABkg%2FTdOr8LFOf-c%2Fs1600%2FCmd1.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="96"></a></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><strong>&nbsp;</strong></span><span style="font-family:Verdana,sans-serif">2)Get Product Id from project&nbsp;Package.appxmanifest&nbsp;file Packaging Tab under Package name attribute&nbsp;(i.e&nbsp;</span><span style="font-family:Verdana,sans-serif">9f68177c-0add-437b-8b43-95ec429ee5b5)</span></p>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">3)if your app is run on emulator excute this command:&nbsp;<strong>ISETool.exe ts xd&nbsp;9f68177c-0add-437b-8b43-95ec429ee5b5&nbsp;c:\data\myfiles</strong></span></p>
</div>
<div>
<p class="separator"><span style="font-size:small"><a href="http://2.bp.blogspot.com/-vuiI4CFff4s/VL5M9tT3itI/AAAAAAAABk0/UQt0vlZ5rTU/s1600/Cmd2.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F2.bp.blogspot.com%2F-vuiI4CFff4s%2FVL5M9tT3itI%2FAAAAAAAABk0%2FUQt0vlZ5rTU%2Fs1600%2FCmd2.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt="" width="640" height="130"></a></span></p>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><strong><br>
</strong></span></p>
</div>
<div>
<p><span style="font-size:small"><span style="font-family:Verdana,sans-serif">4)if your app is run on device excute this command:&nbsp;<strong>ISETool.exe ts de&nbsp;</strong></span><strong>9f68177c-0add-437b-8b43-95ec429ee5b5</strong><span style="font-family:Verdana,sans-serif"><strong>&nbsp;c:\data\myfiles</strong></span></span></p>
</div>
</div>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small">Now we will be found&nbsp;DB content in your computer at c:\data\myfiles like this.</span></p>
</div>
<p class="separator"><span style="font-size:small"><a href="http://4.bp.blogspot.com/-w6rcwZwDndU/U99sN_WZGyI/AAAAAAAABGw/mhuy4iLCoZs/s1600/DBExplore.PNG"><img src="https://images-blogger-opensocial.googleusercontent.com/gadgets/proxy?url=http%3A%2F%2F4.bp.blogspot.com%2F-w6rcwZwDndU%2FU99sN_WZGyI%2FAAAAAAAABGw%2Fmhuy4iLCoZs%2Fs1600%2FDBExplore.PNG&container=blogger&gadget=a&rewriteMime=image%2F*" border="0" alt=""></a></span></p>
<div>
<p><span style="font-family:Verdana,sans-serif; font-size:small"><br>
</span></p>
</div>
<div>
<p><span style="font-size:small"><span style="font-family:Verdana,sans-serif"><strong>Note:</strong></span><span style="font-family:Verdana,sans-serif">This content may be change in future.</span></span></p>
</div>
<div>
<p><span style="font-size:small"><strong>Summary:</strong></span></p>
<p class="separator"><span style="font-size:small">In this first part, we have seen the basics of Sqlite, how to install the engine, the library Sqlite-net, and saw the most common operations (also known as code first), such as inserting, updating, and deleting
 data from a table of a database.</span></p>
<pre class="csharp"><p><span style="font-size:small"><strong>Help me with feedback:</strong></span></p><p><span style="font-size:small">Thank you for reading my article. Drop all your questions/comments in QA tab give me your feedback with&nbsp;<img id="67168" src="http://i1.code.msdn.s-msft.com/oops-principles-solid-7a4e69bf/image/file/67168/1/ratings.png" alt="" width="74" height="15">&nbsp;star rating (1 Star - Very Poor, 5&nbsp;Star -&nbsp;Very Nice). &nbsp;</span></p></pre>
<p class="separator"><span style="color:#666666; font-family:Verdana,sans-serif"><span style="color:#000000">Follow me always at &nbsp;</span></span><a class="account-group x_x_x_x_js-account-group x_x_x_x_js-action-profile x_x_x_x_js-user-profile-link x_x_x_x_js-nav" href="https://twitter.com/Subramanyam_B" style="font-size:small"><span class="username js-action-profile-name"><span style="color:#b1bbc3">@</span>Subramanyam_B</span>&nbsp;</a></p>
<p class="separator"><a class="account-group x_x_x_x_js-account-group x_x_x_x_js-action-profile x_x_x_x_js-user-profile-link x_x_x_x_js-nav" href="https://twitter.com/Subramanyam_B" style="font-size:small"></a><span style="font-size:small">Have a nice day
 by</span><span style="color:#000000">&nbsp;</span><a href="http://bsubramanyamraju.blogspot.in/p/about-me.html" style="font-size:small">Subramanyam Raju</a><span style="color:#000000">&nbsp;:)</span></p>
</div>
