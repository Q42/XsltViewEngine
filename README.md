XsltViewEngine
==============

An XSLT view engine for asp.net mvc that comes with a plugin architecture.

# Add to global.asax

	ViewEngines.Engines.Clear();
	var xlsEngine = new XsltViewEngine();
	xlsEngine.AddExtension("urn:myplugin", (v, c) => new Plugin());
	ViewEngines.Engines.Add(xlsEngine);

# Use plugins

	<xsl:stylesheet version="1.0"
                xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:Html="urn:HtmlHelper"
                xmlns:ext="http://exslt.org/common"
                xmlns:ArtObject="urn:myplugin">
     .... SNAP

     <xsl:value-of select="myplugin:MyMethod(.)"/><br/>

# LICENSE

MIT see `LICENSE.txt`