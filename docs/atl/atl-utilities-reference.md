---
title: Referenz zu ATL-Hilfsprogrammen
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: b5365ddc2924955fbdcf694065c4d4041a38eb01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62251862"
---
# <a name="atl-utilities-reference"></a>Referenz zu ATL-Hilfsprogrammen

ATL stellt Code bereit, für die Bearbeitung von Pfade und URLs in Form von [CPathT](../atl/reference/cpatht-class.md) und [CUrl](../atl/reference/curl-class.md). Einen Threadpool [CThreadPool](../atl/reference/cthreadpool-class.md), in Ihren Anwendungen verwendet werden kann. Dieser Code finden Sie in "atlpath.h" und "atlutil.h".

### <a name="classes"></a>Klassen

|||
|-|-|
|[CPathT-Klasse](../atl/reference/cpatht-class.md)|Diese Klasse stellt einen Pfad an.|
|[CDebugReportHook-Klasse](../atl/reference/cdebugreporthook-class.md)|Verwenden Sie diese Klasse zum Senden von debugberichten und einer named Pipe an.|
|[CNonStatelessWorker-Klasse](../atl/reference/cnonstatelessworker-class.md)|Empfängt Anforderungen aus dem Threadpool und übergibt sie an eine Worker-Objekt, das erstellt und zerstört wird bei jeder Anforderung.|
|[CNoWorkerThread-Klasse](../atl/reference/cnoworkerthread-class.md)|Verwenden Sie diese Klasse als Argument für die `MonitorClass` Vorlagenparameter für Cacheklassen, wenn Sie dynamische Cache Wartung deaktivieren möchten.|
|[CThreadPool-Klasse](../atl/reference/cthreadpool-class.md)|Diese Klasse stellt einen Pool von Arbeitsthreads, die eine Warteschlange von Arbeitsaufgaben zu verarbeiten.|
|[CUrl-Klasse](../atl/reference/curl-class.md)|Diese Klasse stellt eine URL an. Sie können jedes Element der unabhängig von den anderen-URL ändern, ob eine vorhandene URL analysieren Zeichenfolge oder eine Zeichenfolge von Grund auf neu erstellen.|
|[CWorkerThread-Klasse](../atl/reference/cworkerthread-class.md)|Diese Klasse einen Arbeitsthread erstellt oder verwendet eine vorhandene, wartet auf eine oder mehrere Kernel-Objekt-Handles und führt eine angegebene Client-Funktion aus, wenn einem der Handles signalisiert wird.|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[CPath](../atl/reference/atl-typedefs.md#cpath)|Eine Spezialisierung der [CPathT](../atl/reference/cpatht-class.md) mit `CString`.|
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|Eine Spezialisierung der [CPathT](../atl/reference/cpatht-class.md) mit `CStringA`.|
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|Eine Spezialisierung der [CPathT](../atl/reference/cpatht-class.md) mit `CStringW`.|
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|Der Typ, der von verwendeten [CUrl](../atl/reference/curl-class.md) für Sie keine Portnummer angeben.|

### <a name="enums"></a>Enumerationen

|||
|-|-|
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|Geben Sie die Member dieser Enumeration Konstanten für die Schemas, die von verstanden [CUrl](../atl/reference/curl-class.md).|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|Mit dieser Funktion wird eine URL kanonisiert, wobei unsichere Zeichen und Leerzeichen in Escapesequenzen konvertiert werden.|
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|Mit dieser Funktion wird eine Basis-URL und eine relative URL zu einer einzelnen kanonischen URL zusammengefasst.|
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|Mit dieser Funktion werden alle unsicheren Zeichen in Escapesequenzen konvertiert.|
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|Rufen Sie diese Funktion zum Abrufen der Standard-Portnummer, die einem bestimmten Internetprotokoll oder-Schema zugeordnet.|
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.|
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|Mit dieser Funktion finden Sie heraus, ob die Verwendung eines bestimmten Zeichens in einer URL sicher ist.|
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|Mit dieser Funktion können Sie Escapezeichen zurück in ihre ursprünglichen Werte konvertieren.|
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|Mit dieser Funktion konvertieren Sie die Systemzeit in eine Zeichenfolge, deren Format sich für die Verwendung in HTTP-Headern eignet.|

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| Diese Funktion ist ein überladener Wrapper für [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha
). | |[ ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| Diese Funktion ist ein überladener Wrapper für [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona). | |[ ATLPath::Append](../atl/reference/atl-path-functions.md#append)| Diese Funktion ist ein überladener Wrapper für [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda). | |[ ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| Diese Funktion ist ein überladener Wrapper für [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota). | |[ ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| Diese Funktion ist ein überladener Wrapper für [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea). | |[ ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| Diese Funktion ist ein überladener Wrapper für [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea). | |[ ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| Diese Funktion ist ein überladener Wrapper für [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa). | |[ ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| Diese Funktion ist ein überladener Wrapper für [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha). | |[ ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| Diese Funktion ist ein überladener Wrapper für [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa). | |[ ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| Diese Funktion ist ein überladener Wrapper für [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa). | |[ ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| Diese Funktion ist ein überladener Wrapper für [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona). | |[ ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| Diese Funktion ist ein überladener Wrapper für [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea). | |[ ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| Diese Funktion ist ein überladener Wrapper für [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera). | |[ ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| Diese Funktion ist ein überladener Wrapper für [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya). | |[ ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| Diese Funktion ist ein überladener Wrapper für [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca). | |[ ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| Diese Funktion ist ein überladener Wrapper für [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa). | |[ ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| Diese Funktion ist ein überladener Wrapper für [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea). | |[ ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| Diese Funktion ist ein überladener Wrapper für [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota). | |[ ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| Diese Funktion ist ein überladener Wrapper für [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota). | |[ ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| Diese Funktion ist ein überladener Wrapper für [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca). | |[ ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| Diese Funktion ist ein überladener Wrapper für [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera). | |[ ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| Diese Funktion ist ein überladener Wrapper für [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).| |[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)|This function is an overloaded wrapper for [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).| |[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)|This function is an overloaded wrapper for [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).| |[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)|This function is an overloaded wrapper for [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).| |[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)|This function is an overloaded wrapper for [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).| |[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)|This function is an overloaded wrapper for [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).| |[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)|This function is an overloaded wrapper for [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).| |[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)|This function is an overloaded wrapper for [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).| |[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)|This function is an overloaded wrapper for [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).| |[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)|This function is an overloaded wrapper for [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).| |[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)|This function is an overloaded wrapper for [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).| |[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)|This function is an overloaded wrapper for [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).| |[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)|This function is an overloaded wrapper for [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).| |[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)|This function is an overloaded wrapper for [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).| |[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)|This function is an overloaded wrapper for [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).|

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)<br/>
[ATL-COM-Desktop-Komponenten](../atl/atl-com-desktop-components.md)
