---
layout: post
title: How to edit Erb files using Notepad++
date: 2011-10-21 14:10:28.000000000 +01:00
---
If you're one of the tiny band of people developing Ruby or Rails code on Windows, then you might have tried editing <code>.erb</code> files with Notepad++. In general, Notepad++ is a very nice little text editor. It's my only IDE. But it's not very good at <code>.erb</code> files. Here's an example:
<p style="text-align: center;"><a href="https://res.cloudinary.com/dominicsayers/image/upload/v1399584836/without-scilexer_baivrq.png"><img class="aligncenter size-full wp-image-687" title="Without SciLexer" src="https://res.cloudinary.com/dominicsayers/image/upload/v1399584836/without-scilexer_baivrq.png" alt="Without SciLexer" width="480" height="360" /></a>Yuk.</p>
There's two problems here. One is the godawful color scheme. But other is more serious: Notepad++ fails to recognise the quoted text within a pair of <code>&lt;% ... %&gt;</code> braces.

The cause of this is the parsing engine built into Notepad++: Scintilla. Scintilla thinks that <code>&lt;% ... %&gt;</code> braces indicate ASP code, and therefore a single quote indicates the start of a comment. The "comment" includes the closing brace at the end of the line, so the rest of the document is parsed as an ASP comment.

I'm using Notepad++ 5.9.3, the latest version at the time of writing. This uses the Scintilla <code>SciLexer.dll</code> version 2.2.7. More recent versions of the dll don't have this problem, so the solution is straightforward: replace Notepad++'s dll with a more recent one. Here's how to do it step by step:
<ol>
	<li>Close Notepad++</li>
	<li>Download the Scintilla text editor, SciTE. The latest version at the time of writing is here: <a href="https://sourceforge.net/projects/scintilla/files/SciTE/2.29/">https://sourceforge.net/projects/scintilla/files/SciTE/2.29/</a> and the file you want is <code><a title="wscite229.zip" href="https://sourceforge.net/projects/scintilla/files/SciTE/2.29/wscite229.zip/download" target="_blank">wscite229.zip</a></code>.</li>
	<li>Extract the <code>.zip</code> file somewhere handy.</li>
	<li>Navigate to the Notepad++ installation folder. Mine is at <code>C:Program Files (x86)Notepad++</code> but you may have installed it somewhere else.</li>
	<li>Rename <code>SciLexer.dll</code> as <code>SciLexer.bak</code></li>
	<li>Copy <code>SciLexer.dll</code> from your SciTE package to your Notepad++ folder</li>
	<li>Restart Notepad++</li>
</ol>
You will be asked by Windows if you really want to mess around in the Program Files folder. Yes, you do.

Hurrah! Now the <code>.erb</code> braces are parsed correctly:
<p style="text-align: center;"><a href="https://res.cloudinary.com/dominicsayers/image/upload/v1399584835/with_scilexer_wzhj8p.png"><img class="aligncenter  wp-image-688" title="With updated SciLexer.dll" src="https://res.cloudinary.com/dominicsayers/image/upload/v1399584835/with_scilexer_wzhj8p.png" alt="" width="480" height="360" /></a>But it's still a naff colour scheme.</p>
If you look in Notepad++'s Style Configurator, you won't find anything in Global Styles or HTML to change this. There isn't an Erb language specification. So how do we change the colour of the braces?

Notepad still thinks they are ASP braces. The style it is rendering is the <code>ASPSYBOL</code> style in the <code>asp</code> language configuration. Here's how to change it:
<ol>
	<li>Settings &gt; Style Configurator</li>
	<li>In the Language selector, choose <code>asp</code></li>
	<li>In the Style selector, choose <code>ASPSYBOL</code></li>
	<li>Change the <em>Foreground color</em> and <em>Background color</em> to a cool new style.</li>
	<li>Save &amp; Close</li>
</ol>
<p style="text-align: center;"><a href="https://res.cloudinary.com/dominicsayers/image/upload/v1399584834/style_configurator_h8lxlt.png"><img class="aligncenter size-full wp-image-689" title="Style Configurator" src="https://res.cloudinary.com/dominicsayers/image/upload/v1399584834/style_configurator_h8lxlt.png" alt="" width="480" height="360" /></a>Now your <code>.erb</code> file looks like this:</p>
<p style="text-align: center;"><a href="https://blog-dominicsayers.rhcloud.com/wp-content/uploads/2011/10/final.png"><img class="aligncenter  wp-image-690" title="Final" src="https://blog-dominicsayers.rhcloud.com/wp-content/uploads/2011/10/final.png" alt="" width="480" height="360" /></a>Win!</p>
Go and write some nice Rails code and ignore all those dudes telling you to get a Mac.
