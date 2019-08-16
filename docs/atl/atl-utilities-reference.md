---
title: Referenz zu ATL-Hilfsprogrammen
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: 6c1481929f832e6f810ce46773f328f278b503fa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491702"
---
# <a name="atl-utilities-reference"></a>Referenz zu ATL-Hilfsprogrammen

ATL stellt Code zum Bearbeiten von Pfaden und URLs in Form von [cpatht](../atl/reference/cpatht-class.md) und [CUrl](../atl/reference/curl-class.md)bereit. Ein Thread Pool, [CThreadPool](../atl/reference/cthreadpool-class.md), kann in Ihren Anwendungen verwendet werden. Diesen Code finden Sie in „atlpath.h“ und „atlutil.h“.

### <a name="classes"></a>Klassen

|||
|-|-|
|[CPathT-Klasse](../atl/reference/cpatht-class.md)|Diese Klasse stellt einen Pfad dar.|
|[CDebugReportHook-Klasse](../atl/reference/cdebugreporthook-class.md)|Verwenden Sie diese Klasse, um Debugberichte an einen Named Pipe zu senden.|
|[CNonStatelessWorker-Klasse](../atl/reference/cnonstatelessworker-class.md)|Empfängt Anforderungen von einem Thread Pool und übergibt sie an ein Worker-Objekt, das bei jeder Anforderung erstellt und zerstört wird.|
|[CNoWorkerThread-Klasse](../atl/reference/cnoworkerthread-class.md)|Verwenden Sie diese Klasse als Argument für den `MonitorClass` Vorlagen Parameter, um Klassen zwischenzuspeichern, wenn Sie die dynamische Cache Wartung deaktivieren möchten.|
|[CThreadPool-Klasse](../atl/reference/cthreadpool-class.md)|Diese Klasse stellt einen Pool von Arbeitsthreads bereit, die eine Warteschlange von Arbeits Elementen verarbeiten.|
|[CUrl-Klasse](../atl/reference/curl-class.md)|Diese Klasse stellt eine URL dar. Sie ermöglicht es Ihnen, jedes Element der URL unabhängig von den anderen zu bearbeiten, unabhängig davon, ob Sie eine vorhandene URL-Zeichenfolge oder eine Zeichenfolge von Grund auf erstellen.|
|[CWorkerThread-Klasse](../atl/reference/cworkerthread-class.md)|Diese Klasse erstellt einen Arbeits Thread oder verwendet einen vorhandenen Thread, wartet auf ein oder mehrere Kernel Objekt Handles und führt eine angegebene Client Funktion aus, wenn eines der Handles signalisiert wird.|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[CPath](../atl/reference/atl-typedefs.md#cpath)|Eine Spezialisierung von [cpatht](../atl/reference/cpatht-class.md) mithilfe `CString`von.|
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|Eine Spezialisierung von [cpatht](../atl/reference/cpatht-class.md) mithilfe `CStringA`von.|
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|Eine Spezialisierung von [cpatht](../atl/reference/cpatht-class.md) mithilfe `CStringW`von.|
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|Der Typ, der von [CUrl](../atl/reference/curl-class.md) zum Angeben einer Portnummer verwendet wird.|

### <a name="enums"></a>Enumerationen

|||
|-|-|
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|Die Member dieser Enumeration stellen Konstanten für die Schemas bereit, die von [CUrl](../atl/reference/curl-class.md)verstanden werden.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|Mit dieser Funktion wird eine URL kanonisiert, wobei unsichere Zeichen und Leerzeichen in Escapesequenzen konvertiert werden.|
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|Mit dieser Funktion wird eine Basis-URL und eine relative URL zu einer einzelnen kanonischen URL zusammengefasst.|
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|Mit dieser Funktion werden alle unsicheren Zeichen in Escapesequenzen konvertiert.|
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|Mit dieser Funktion können Sie die Standard Portnummer abrufen, die einem bestimmten Internetprotokoll oder-Schema zugeordnet ist.|
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.|
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|Mit dieser Funktion finden Sie heraus, ob die Verwendung eines bestimmten Zeichens in einer URL sicher ist.|
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|Mit dieser Funktion können Sie Escapezeichen zurück in ihre ursprünglichen Werte konvertieren.|
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|Mit dieser Funktion konvertieren Sie die Systemzeit in eine Zeichenfolge, deren Format sich für die Verwendung in HTTP-Headern eignet.|

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| Diese Funktion ist ein überladener Wrapper für [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha
). | |[ ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| Diese Funktion ist ein überladener Wrapper für [PathAddExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw). | |[ ATLPath::Append](../atl/reference/atl-path-functions.md#append)| Diese Funktion ist ein überladener Wrapper für [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw). | |[ ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| Diese Funktion ist ein überladener Wrapper für [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw). | |[ ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| Diese Funktion ist ein überladener Wrapper für [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew). | |[ ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| Diese Funktion ist ein überladener Wrapper für [PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew). | |[ ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| Diese Funktion ist ein überladener Wrapper für [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw). | |[ ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| Diese Funktion ist ein überladener Wrapper für [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw). | |[ ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| Diese Funktion ist ein überladener Wrapper für [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw). | |[ ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| Diese Funktion ist ein überladener Wrapper für [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw). | |[ ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| Diese Funktion ist ein überladener Wrapper für [PathFindExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw). | |[ ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| Diese Funktion ist ein überladener Wrapper für [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew). | |[ ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| Diese Funktion ist ein überladener Wrapper für [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw). | |[ ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| Diese Funktion ist ein überladener Wrapper für [PathIsDirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw). | |[ ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| Diese Funktion ist ein überladener Wrapper für [PathIsFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw). | |[ ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| Diese Funktion ist ein überladener Wrapper für [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw). | |[ ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| Diese Funktion ist ein überladener Wrapper für [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew). | |[ ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| Diese Funktion ist ein überladener Wrapper für [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw). | |[ ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| Diese Funktion ist ein überladener Wrapper für [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw). | |[ ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| Diese Funktion ist ein überladener Wrapper für [PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw). | |[ ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| Diese Funktion ist ein überladener Wrapper für [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw). | |[ ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| Diese Funktion ist ein überladener Wrapper für [PathIsUNCServerShare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew).| |[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)|This function is an overloaded wrapper for [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw).| |[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)|This function is an overloaded wrapper for [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw).| |[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)|This function is an overloaded wrapper for [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw).| |[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)|This function is an overloaded wrapper for [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow).| |[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)|This function is an overloaded wrapper for [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw).| |[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)|This function is an overloaded wrapper for [PathRemoveBackslash](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw).| |[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)|This function is an overloaded wrapper for [PathRemoveBlanks](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw).| |[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)|This function is an overloaded wrapper for [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw).| |[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)|This function is an overloaded wrapper for [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw).| |[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)|This function is an overloaded wrapper for [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw).| |[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)|This function is an overloaded wrapper for [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw).| |[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)|This function is an overloaded wrapper for [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw).| |[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)|This function is an overloaded wrapper for [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw).| |[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)|This function is an overloaded wrapper for [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw).|

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)<br/>
[ATL-COM-Desktop-Komponenten](../atl/atl-com-desktop-components.md)
