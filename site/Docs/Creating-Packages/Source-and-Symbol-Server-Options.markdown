# Source And Symbol Server Options

## Introduction
NuGet supports creating [symbol/source packages](~/docs/creating-and-publishing-a-symbol-package) and publishing them to a symbol/source 
server. Visual Studio can be configured to use any number of symbol/source servers to download associated PDB files and enable step into 
debugging of packages.

There are a number of services and products available to easily support symbol/source serving. Symbol/source servers can be public or private. 

Note that for non-Open Source projects symbol files contain 
[sensitive information](http://www.wintellect.com/CS/blogs/jrobbins/archive/2009/05/11/pdb-files-what-every-developer-must-know.aspx) and 
caution should be taken when publishing them to ensure proper security.

## Public Servers

### [SymbolSource.org](http://symbolsource.org)
The default symbol/source server that NuGet uses is [SymbolSource.org](http://symbolsource.org). 
This is a publicly available server and contains symbols/source packages for many [NuGet packages](http://www.symbolsource.org/Public/Metadata/NuGet). 

See the [instructions](http://www.symbolsource.org/Public/Home/VisualStudio) for how to integrate the public SymbolSource.org server into 
Visual Studio. The default symbol server URL for SymbolSource.org is 
	http://srv.symbolsource.org/pdb/Public
 
## Private Servers

### TFS
Microsoft Team Foundation Server 2010 and higher provide integrated symbol and source serving when using Team Build. 
You can set your build to support [symbol and source serving](http://www.edsquared.com/2011/02/12/Source+Server+And+Symbol+Server+Support+In+TFS+2010.aspx) 
at build time.

### SymSrv
Microsoft provides a free set of tools to [create](http://msdn.microsoft.com/en-us/library/ms681416(v=vs.85).aspx) and 
[populate](http://msdn.microsoft.com/en-us/library/ms681417(v=vs.85).aspx) an internal symbol server. 

### ProGet
ProGet is a product that includes both an enhanced NuGet compatible server as well as the ability to host 
[symbol/source packages](http://inedo.com/support/documentation/proget/feeds/symbol-and-source-server). ProGet supports the NuGet convention of separating 
the implementation files from the symbols and source code files, it also supports the option to include all files in a single package which the server will separate. 

Setting up debugging of ProGet hosted symbol/source packages is described in the 
[instructions](http://inedo.com/support/kb/1036/using-progets-symbol-server).
