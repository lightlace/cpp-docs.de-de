---
title: Referenz zu ATL-Hilfsprogrammen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69f085df8b5dadbd0ba9d20596d37cb6313bb3f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="atl-utilities-reference"></a>Referenz zu ATL-Hilfsprogrammen
ATL stellt Code zum Bearbeiten von Pfaden und URLs in Form von [CPathT](../atl/reference/cpatht-class.md) und [CUrl](../atl/reference/curl-class.md). Ein Threadpool [CThreadPool](../atl/reference/cthreadpool-class.md), können in Anwendungen verwendet werden. Dieser Code kann in atlpath.h und atlutil.h gefunden werden.  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[CPathT-Klasse](../atl/reference/cpatht-class.md)|Diese Klasse stellt einen Pfad an.|  
|[CDebugReportHook-Klasse](../atl/reference/cdebugreporthook-class.md)|Verwenden Sie diese Klasse wird zum Senden von debugberichten einer named Pipe.|  
|[CNonStatelessWorker-Klasse](../atl/reference/cnonstatelessworker-class.md)|Empfang von Anforderungen von einem Threadpool und übergibt sie bei jeder Anforderung an einen Worker-Objekt, das erstellt und zerstört wird.|  
|[CNoWorkerThread-Klasse](../atl/reference/cnoworkerthread-class.md)|Verwenden Sie diese Klasse als Argument für die `MonitorClass` Vorlagenparameter Cacheklassen, wenn Sie dynamische Cache Wartung deaktivieren möchten.|  
|[CThreadPool-Klasse](../atl/reference/cthreadpool-class.md)|Diese Klasse stellt einen Pool von Arbeitsthreads, die eine Warteschlange von Arbeitsaufgaben zu verarbeiten.|  
|[CUrl-Klasse](../atl/reference/curl-class.md)|Diese Klasse stellt eine URL an. Dadurch können Sie jedes Element der URL unabhängig von den anderen bearbeiten, ob eine vorhandene URL analysieren Zeichenfolge oder eine Zeichenfolge von Grund auf neu erstellen.|  
|[CWorkerThread-Klasse](../atl/reference/cworkerthread-class.md)|Diese Klasse wird ein Arbeitsthread erstellt oder verwendet eine vorhandene, wartet auf eine oder mehrere Kernel-Objekt-Handles und führt eine angegebene Client-Funktion aus, wenn Sie einen der Ziehpunkte signalisiert wird.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[CPath](../atl/reference/atl-typedefs.md#cpath)|Eine Spezialisierung der [CPathT](../atl/reference/cpatht-class.md) mit `CString`.|  
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|Eine Spezialisierung der [CPathT](../atl/reference/cpatht-class.md) mit `CStringA`.|  
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|Eine Spezialisierung der [CPathT](../atl/reference/cpatht-class.md) mit `CStringW`.|  
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|Vom verwendeten [CUrl](../atl/reference/curl-class.md) für keine Portnummer angeben.|  
  
### <a name="enums"></a>Enumerationen  
  
|||  
|-|-|  
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|Der Member dieser Enumeration angeben Konstanten für die Schemas verständlich [CUrl](../atl/reference/curl-class.md).|  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|Mit dieser Funktion wird eine URL kanonisiert, wobei unsichere Zeichen und Leerzeichen in Escapesequenzen konvertiert werden.|  
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|Mit dieser Funktion wird eine Basis-URL und eine relative URL zu einer einzelnen kanonischen URL zusammengefasst.|  
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|Mit dieser Funktion werden alle unsicheren Zeichen in Escapesequenzen konvertiert.|  
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|Mit dieser Funktion wird zum Abrufen der Standard-Portnummer, die einem bestimmten Internetprotokoll oder-Schema zugeordnet.|  
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.|  
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|Mit dieser Funktion finden Sie heraus, ob die Verwendung eines bestimmten Zeichens in einer URL sicher ist.|  
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|Mit dieser Funktion können Sie Escapezeichen zurück in ihre ursprünglichen Werte konvertieren.|  
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|Mit dieser Funktion konvertieren Sie die Systemzeit in eine Zeichenfolge, deren Format sich für die Verwendung in HTTP-Headern eignet.|  

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| Diese Funktion ist ein überladener Wrapper für [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561). |  
|[ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| Diese Funktion ist ein überladener Wrapper für [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563). |  
|[ATLPath::Append](../atl/reference/atl-path-functions.md#append)| Diese Funktion ist ein überladener Wrapper für [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565). |  
|[ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| Diese Funktion ist ein überladener Wrapper für [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567). |  
|[ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| Diese Funktion ist ein überladener Wrapper für [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569). |  
|[ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| Diese Funktion ist ein überladener Wrapper für [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571). |  
|[ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| Diese Funktion ist ein überladener Wrapper für [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574). |  
|[ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| Diese Funktion ist ein überladener Wrapper für [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575). |  
|[ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| Diese Funktion ist ein überladener Wrapper für [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578). |  
|[ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| Diese Funktion ist ein überladener Wrapper für [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584). |  
|[ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| Diese Funktion ist ein überladener Wrapper für [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587). |  
|[ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| Diese Funktion ist ein überladener Wrapper für [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589). |  
|[ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| Diese Funktion ist ein überladener Wrapper für [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612). |  
|[ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| Diese Funktion ist ein überladener Wrapper für [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621). |  
|[ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| Diese Funktion ist ein überladener Wrapper für [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627). |  
|[ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| Diese Funktion ist ein überladener Wrapper für [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650). |  
|[ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| Diese Funktion ist ein überladener Wrapper für [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660). |  
|[ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| Diese Funktion ist ein überladener Wrapper für [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674). |  
|[ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| Diese Funktion ist ein überladener Wrapper für [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687). |  
|[ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| Diese Funktion ist ein überladener Wrapper für [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712). |  
|[ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| Diese Funktion ist ein überladener Wrapper für [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722). |  
|[ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| Diese Funktion ist ein überladener Wrapper für [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723). |  
|[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)| Diese Funktion ist ein überladener Wrapper für [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725). |  
|[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)| Diese Funktion ist ein überladener Wrapper für [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727). |  
|[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)| Diese Funktion ist ein überladener Wrapper für [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739). |  
|[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)| Diese Funktion ist ein überladener Wrapper für [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740). |  
|[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)| Diese Funktion ist ein überladener Wrapper für [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742). |  
|[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)| Diese Funktion ist ein überladener Wrapper für [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743). |  
|[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)| Diese Funktion ist ein überladener Wrapper für [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745). |  
|[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)| Diese Funktion ist ein überladener Wrapper für [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746). |  
|[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)| Diese Funktion ist ein überladener Wrapper für [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748). |  
|[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)| Diese Funktion ist ein überladener Wrapper für [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749). |  
|[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)| Diese Funktion ist ein überladener Wrapper für [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754). |  
|[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)| Diese Funktion ist ein überladener Wrapper für [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756). |  
|[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)| Diese Funktion ist ein überladener Wrapper für [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757). |  
|[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)| Diese Funktion ist ein überladener Wrapper für [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763). |  
  

## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [ATL-COM-Desktop-Komponenten](../atl/atl-com-desktop-components.md)
