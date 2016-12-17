---
title: "Referenz zu ATL-Hilfsprogrammen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
caps.latest.revision: 8
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# Referenz zu ATL-Hilfsprogrammen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL stellt Code für das Bearbeiten von Pfaden und von URLs in Form von [CPathT](../atl/reference/cpatht-class.md) und [Rotation](../atl/reference/curl-class.md) bereit.  Ein Threadpool, [CThreadPool](../atl/reference/cthreadpool-class.md), kann in Anwendungen verwendet werden.  Dieser Code kann in atlpath.h und in atlutil.h gefunden werden.  
  
### Klassen  
  
|||  
|-|-|  
|[CPathT\-Klasse](../atl/reference/cpatht-class.md)|Diese Klasse stellt einen Pfad dar.|  
|[CDebugReportHook\-Klasse](../atl/reference/cdebugreporthook-class.md)|Verwenden Sie diese Klasse, um Debugberichte zu einer benannten Pipe zu senden.|  
|[CNonStatelessWorker\-Klasse](../atl/reference/cnonstatelessworker-class.md)|Empfängt Anforderungen aus einem Threadpool und leitet sie an ein Workerobjekt weiter, die bei jeder Anforderung erstellt und zerstört wird.|  
|[CNoWorkerThread\-Klasse](../atl/reference/cnoworkerthread-class.md)|Verwenden Sie diese Klasse als Argument, damit der `MonitorClass` Vorlagenparameter Klassen zwischengespeichert werden, wenn Sie dynamische Cacheverwaltung deaktivieren möchten.|  
|[CThreadPool\-Klasse](../atl/reference/cthreadpool-class.md)|Diese Klasse stellt einen Pool von Arbeitsthreads, die eine Warteschlange von Arbeitsaufgaben verarbeiten.|  
|[Rotations\-Klasse](../atl/reference/curl-class.md)|Diese Klasse stellt eine URL dar.  Sie ermöglicht es Ihnen, um jedes Element des URL unabhängig von anderen zu bearbeiten, ob, eine vorhandene URL\-Zeichenfolge analysieren oder eine Zeichenfolge von Grund auf neu erstellen.|  
|[CWorkerThread\-Klasse](../atl/reference/cworkerthread-class.md)|Diese Klasse erstellt einen Arbeitsthread oder verwendet eine vorhandene, wartet auf eine oder mehrere Kernelobjekthandles und führt eine angegebene Clientfunktion aus, wenn eines der Handles signalisiert wird.|  
  
### Typedefs  
  
|||  
|-|-|  
|[CPath](../Topic/CPath.md)|Eine Spezialisierung von [CPathT](../atl/reference/cpatht-class.md) mithilfe `CString`.|  
|[CPathA](../Topic/CPathA.md)|Eine Spezialisierung von [CPathT](../atl/reference/cpatht-class.md) mithilfe `CStringA`.|  
|[CPathW](../Topic/CPathW.md)|Eine Spezialisierung von [CPathT](../atl/reference/cpatht-class.md) mithilfe `CStringW`.|  
|[ATL\_URL\_PORT](../Topic/ATL_URL_PORT.md)|Der Typ wird von [Rotation](../atl/reference/curl-class.md) zum Angeben einer Portnummer.|  
  
### Enumerationen  
  
|||  
|-|-|  
|[ATL\_URL\_SCHEME](../Topic/ATL_URL_SCHEME.md)|Die Mitglieder dieser Enumeration stellen Konstanten für die Schemas bereit, die von [Rotation](../atl/reference/curl-class.md) verstanden werden.|  
  
### Funktionen  
  
|||  
|-|-|  
|[AtlCanonicalizeUrl](../Topic/AtlCanonicalizeUrl.md)|Rufen Sie diese Funktion, um eine URL zu kanonisieren, das das Konvertieren von unsicheren Zeichen und der Leerzeichen in Escapesequenzen einschließt.|  
|[AtlCombineUrl](../Topic/AtlCombineUrl.md)|Rufen Sie diese Funktion auf, um eine Basis\-URL und eine relative URL in ein einzelnes, kanonisches URL zu kombinieren.|  
|[AtlEscapeUrl](../Topic/AtlEscapeUrl.md)|Rufen Sie diese Funktion auf, um alle unsicheren Zeichen zu den Escapesequenzen zu konvertieren.|  
|[AtlGetDefaultUrlPort](../Topic/AtlGetDefaultUrlPort.md)|Rufen Sie diese Funktion auf, um die Standardportnummer abzurufen, die einem bestimmten Internetprotokoll oder einem Schema zugeordnet ist.|  
|[AtlHexValue](../Topic/AtlHexValue.md)|Rufen Sie diese Funktion auf, um den numerischen Wert einer Hexadezimalziffer abzurufen.|  
|[AtlIsUnsafeUrlChar](../Topic/AtlIsUnsafeUrlChar.md)|Rufen Sie diese Funktion, um zu ermitteln, ob ein Zeichen zur Verwendung in einer URL sicher ist.|  
|[AtlUnescapeUrl](../Topic/AtlUnescapeUrl.md)|Rufen Sie diese Funktion, um Escapezeichen zurück auf ihre ursprünglichen Werte zu konvertieren.|  
|[SystemTimeToHttpDate](../Topic/SystemTimeToHttpDate.md)|Rufen Sie diese Funktion auf, um eine Systemzeit zu einer Zeichenfolge in ein Format konvertiert, das für die Anwendung in HTTP\-Headern geeignet ist.|  
|[ATLPath::AddBackslash](../Topic/ATLPath::AddBackslash.md)|Diese Funktion ist ein überladener Wrapper für [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561).|  
|[ATLPath::AddExtension](../Topic/ATLPath::AddExtension.md)|Diese Funktion ist ein überladener Wrapper für [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).|  
|[ATLPath::Append](../Topic/ATLPath::Append.md)|Diese Funktion ist ein überladener Wrapper für [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).|  
|[ATLPath::BuildRoot](../Topic/ATLPath::BuildRoot.md)|Diese Funktion ist ein überladener Wrapper für [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).|  
|[ATLPath::Canonicalize](../Topic/ATLPath::Canonicalize.md)|Diese Funktion ist ein überladener Wrapper für [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).|  
|[ATLPath::Combine](../Topic/ATLPath::Combine.md)|Diese Funktion ist ein überladener Wrapper für [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571).|  
|[ATLPath::CommonPrefix](../Topic/ATLPath::CommonPrefix.md)|Diese Funktion ist ein überladener Wrapper für [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).|  
|[ATLPath::CompactPath](../Topic/ATLPath::CompactPath.md)|Diese Funktion ist ein überladener Wrapper für [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).|  
|[ATLPath::CompactPathEx](../Topic/ATLPath::CompactPathEx.md)|Diese Funktion ist ein überladener Wrapper für [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).|  
|[ATLPath::FileExists](../Topic/ATLPath::FileExists.md)|Diese Funktion ist ein überladener Wrapper für [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).|  
|[ATLPath::FindExtension](../Topic/ATLPath::FindExtension.md)|Diese Funktion ist ein überladener Wrapper für [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).|  
|[ATLPath::FindFileName](../Topic/ATLPath::FindFileName.md)|Diese Funktion ist ein überladener Wrapper für [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).|  
|[ATLPath::GetDriveNumber](../Topic/ATLPath::GetDriveNumber.md)|Diese Funktion ist ein überladener Wrapper für [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).|  
|[ATLPath::IsDirectory](../Topic/ATLPath::IsDirectory.md)|Diese Funktion ist ein überladener Wrapper für [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).|  
|[ATLPath::IsFileSpec](../Topic/ATLPath::IsFileSpec.md)|Diese Funktion ist ein überladener Wrapper für [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).|  
|[ATLPath::IsPrefix](../Topic/ATLPath::IsPrefix.md)|Diese Funktion ist ein überladener Wrapper für [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).|  
|[ATLPath::IsRelative](../Topic/ATLPath::IsRelative.md)|Diese Funktion ist ein überladener Wrapper für [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).|  
|[ATLPath::IsRoot](../Topic/ATLPath::IsRoot.md)|Diese Funktion ist ein überladener Wrapper für [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).|  
|[ATLPath::IsSameRoot](../Topic/ATLPath::IsSameRoot.md)|Diese Funktion ist ein überladener Wrapper für [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).|  
|[ATLPath::IsUNC](../Topic/ATLPath::IsUNC.md)|Diese Funktion ist ein überladener Wrapper für [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).|  
|[ATLPath::IsUNCServer](../Topic/ATLPath::IsUNCServer.md)|Diese Funktion ist ein überladener Wrapper für [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).|  
|[ATLPath::IsUNCServerShare](../Topic/ATLPath::IsUNCServerShare.md)|Diese Funktion ist ein überladener Wrapper für [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).|  
|[ATLPath::MakePretty](../Topic/ATLPath::MakePretty.md)|Diese Funktion ist ein überladener Wrapper für [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).|  
|[ATLPath::MatchSpec](../Topic/ATLPath::MatchSpec.md)|Diese Funktion ist ein überladener Wrapper für [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).|  
|[ATLPath::QuoteSpaces](../Topic/ATLPath::QuoteSpaces.md)|Diese Funktion ist ein überladener Wrapper für [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).|  
|[ATLPath::RelativePathTo](../Topic/ATLPath::RelativePathTo.md)|Diese Funktion ist ein überladener Wrapper für [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).|  
|[ATLPath::RemoveArgs](../Topic/ATLPath::RemoveArgs.md)|Diese Funktion ist ein überladener Wrapper für [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).|  
|[ATLPath::RemoveBackslash](../Topic/ATLPath::RemoveBackslash.md)|Diese Funktion ist ein überladener Wrapper für [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).|  
|[ATLPath::RemoveBlanks](../Topic/ATLPath::RemoveBlanks.md)|Diese Funktion ist ein überladener Wrapper für [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).|  
|[ATLPath::RemoveExtension](../Topic/ATLPath::RemoveExtension.md)|Diese Funktion ist ein überladener Wrapper für [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).|  
|[ATLPath::RemoveFileSpec](../Topic/ATLPath::RemoveFileSpec.md)|Diese Funktion ist ein überladener Wrapper für [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).|  
|[ATLPath::RenameExtension](../Topic/ATLPath::RenameExtension.md)|Diese Funktion ist ein überladener Wrapper für [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).|  
|[ATLPath::SkipRoot](../Topic/ATLPath::SkipRoot.md)|Diese Funktion ist ein überladener Wrapper für [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).|  
|[ATLPath::StripPath](../Topic/ATLPath::StripPath.md)|Diese Funktion ist ein überladener Wrapper für [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).|  
|[ATLPath::StripToRoot](../Topic/ATLPath::StripToRoot.md)|Diese Funktion ist ein überladener Wrapper für [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).|  
|[ATLPath::UnquoteSpaces](../Topic/ATLPath::UnquoteSpaces.md)|Diese Funktion ist ein überladener Wrapper für [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).|  
  
### Makros  
  
|||  
|-|-|  
|[ATL\_URL\-Flags](../Topic/ATL_URL%20Flags.md)|Diese Flags ändern das Verhalten von [AtlEscapeUrl](../Topic/AtlEscapeUrl.md) und von [AtlCanonicalizeUrl](../Topic/AtlCanonicalizeUrl.md).|  
|[ATL\_WORKER\_THREAD\_WAIT](../Topic/ATL_WORKER_THREAD_WAIT.md)|Dieses Makro definiert den Standardwert in Millisekunden, die [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md) auf den Arbeitsthread wartet, um herunterzufahren.|  
|[ATLS\_DEFAULT\_THREADPOOLSHUTDOWNTIMEOUT](../Topic/ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT.md)|Dieses Makro wird die standardmäßige Zeit in Millisekunden, dass [CThreadPool](../atl/reference/cthreadpool-class.md) auf einen Thread wartet, um herunterzufahren.|  
|[ATLS\_DEFAULT\_THREADSPERPROC](../Topic/ATLS_DEFAULT_THREADSPERPROC.md)|Dieses Makro wird die standardmäßige Anzahl von Threads pro Prozessor, der von [CThreadPool](../atl/reference/cthreadpool-class.md) verwendet wird.|  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)