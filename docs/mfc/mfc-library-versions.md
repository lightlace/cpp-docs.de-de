---
title: MFC-Bibliotheksversionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- class libraries [MFC], building versions
- version information [MFC], MFC library
- MFC class library
- MFC class library, building
- MFC libraries
- MFC, library versions
- libraries [MFC], versions
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a077cd90055a17f9aff71d67d2cb9a511a1caf0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078036"
---
# <a name="mfc-library-versions"></a>MFC-Bibliotheksversionen

Die MFC-Bibliothek steht in Versionen, die Einzelbyte-ANSI unterstützen, und multibyte-Zeichensatz (MBCS)-Code als auch Versionen, die Unterstützung für Unicode (codiert als UTF-16LE den nativen Windows-Zeichensatz). Jedes MFC-Version ist verfügbar, als eine statische Bibliothek oder einer gemeinsam genutzten DLL. Es gibt auch eine kleinere Version des Typs MFC statische Bibliothek, die MFC-Steuerelemente für Dialoge, die für Anwendungen, die sehr empfindlich, Größe und die Steuerelemente nicht erforderlich, zu verlassen. Die MFC-Bibliotheken stehen in sowohl für Debug- und Releaseversionen für unterstützte Architektur, die X86 X64 und ARM-Prozessoren enthalten. Sie können beide Anwendungen (.exe-Dateien) erstellen und DLL-Dateien mit einer Version von MFC-Bibliotheken. Es gibt auch eine Reihe von MFC-Bibliotheken, die für die Interaktion mit verwaltetem Code kompiliert. Die MFC-Bibliothek freigegebene DLLs enthalten eine Versionsnummer, um binäre Kompatibilität anzugeben.

## <a name="automatic-linking-of-mfc-library-versions"></a>Automatisches Verlinken der MFC-Bibliotheksversionen

Die MFC-Headerdateien bestimmt automatisch die richtige Version der MFC-Bibliothek zu verknüpfen basierend auf Werten in der aktuellen Buildumgebung definiert wird. Die MFC-Headerdateien fügen Sie Compiler-Direktiven der Linker zur Verknüpfung von einer bestimmten Version der MFC-Bibliothek hinzu.

Beispiel: die AFX. H-Headerdatei weist den Linker an, in der vollständig statischen, begrenzte statisch oder gemeinsam genutzten DLL-Version von MFC verknüpfen; ANSI/MBCS oder Unicode-version und Debug- oder Retailmodus-Version, abhängig von der Buildkonfiguration:

```cpp
#ifndef _AFXDLL
    #ifdef _AFX_NO_MFC_CONTROLS_IN_DIALOGS
        #ifdef _DEBUG
            #pragma comment(lib, "afxnmcdd.lib")
        #else
            #pragma comment(lib, "afxnmcd.lib")
        #endif
        #pragma comment(linker, "/include:__afxNoMFCControlSupportInDialogs")
        #pragma comment(linker, "/include:__afxNoMFCControlContainerInDialogs")
    #endif
    #ifndef _UNICODE
        #ifdef _DEBUG
            #pragma comment(lib, "nafxcwd.lib")
        #else
            #pragma comment(lib, "nafxcw.lib")
        #endif
    #else
        #ifdef _DEBUG
            #pragma comment(lib, "uafxcwd.lib")
        #else
            #pragma comment(lib, "uafxcw.lib")
        #endif
    #endif
#else
    #ifndef _UNICODE
        #ifdef _DEBUG
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "d.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "d.lib")
        #else
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER ".lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER ".lib")
        #endif
    #else
        #ifdef _DEBUG
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "ud.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "ud.lib")
        #else
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "u.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "u.lib")
        #endif
    #endif
#endif
```

MFC-Headerdateien umfassen auch Anweisungen, um alle erforderlichen Bibliotheken wie MFC-Bibliotheken, Win32-Bibliotheken, OLE-Bibliotheken, OLE-Bibliotheken, die aus Beispielen erstellt, ODBC-Bibliotheken und So weiter zu verknüpfen.

## <a name="ansi-mbcs-and-unicode"></a>ANSI, MBCS und Unicode

Die Versionen der MFC ANSI-/MBCS-Bibliothek unterstützen beide Einzelbyte-Zeichensätze wie ASCII und Mehrbyte-Zeichensätzen wie z. B. Shift-JIS. Die Unicode-MFC-Bibliotheksversionen unterstützt Unicode in UTF-16LE Breitzeichen-codierte Form. Verwenden Sie die ANSI-/MBCS-Bibliothek Produktversionen von MFC für UTF-8 Unicode-Unterstützung codiert.

Um die Projektkonfiguration mit Einzelbyte-Multibytezeichen oder Breitzeichen-Unicode-Zeichenfolgen und Unterstützung in der IDE festzulegen, verwenden die **Projekteigenschaften** Dialogfeld. In der **Konfigurationseigenschaften** > **allgemeine** Seite der **Zeichensatz** Eigenschaft **nicht festgelegt** verwenden ein Einzelbyte-Zeichensatz. Legen Sie die Eigenschaft auf **Multi-Byte-Zeichensatz verwenden** einen multibyte-Zeichensatz verwenden oder **Unicode-Zeichensatz verwenden** Unicode codiert als UTF-16 verwendet.

MFC-Projekte verwenden das Präprozessorsymbol \_UNICODE UTF-16 Breitzeichen-Unicode-Unterstützung, an und \_MBCS an, dass MBCS-Unterstützung. Diese Optionen schließen sich in einem Projekt gegenseitig aus.

## <a name="mfc-static-library-naming-conventions"></a>Namenskonventionen für MFC-statische Bibliothek

Statische Bibliotheken für die MFC verwenden Sie die folgenden Benennungskonventionen. Die Namen von Typbibliotheken aufweisen Form.

> <em>u</em>AFX<em>cd</em>. LIB

in dem die Buchstaben kursiv dargestellten Kleinbuchstaben Platzhalter für Bezeichner, dessen Bedeutung in der folgenden Tabelle angezeigt werden:

|Bezeichner|Werte und Bedeutung|
|---------------|-------------------------|
|*n*|(N) ANSI-/MBCS oder Unicode (U); Lassen Sie für die Version ohne MFC-Steuerelemente in Dialogfeldern|
|*c*|Version mit der MFC-Steuerelemente in Dialogfeldern (CW) oder ohne (NMCD)|
|*d*|Debug oder Release: D = Debuggen; kein Bezeichner für Release|

Alle Bibliotheken, die in der folgenden Tabelle aufgeführt sind, enthalten vordefinierte im Verzeichnis \atlmfc\lib unterstützten Build-Architekturen.

|Bibliothek|Beschreibung|
|-------------|-----------------|
|NAFXCW.LIB|MFC-Bibliothek Static Link Releaseversion|
|NAFXCWD.LIB|MFC-Bibliothek Static Link Debugversion|
|UAFXCW.LIB|MFC-Static Link-Bibliothek mit Unicode-Unterstützung, Releaseversion|
|UAFXCWD.LIB|Static Link Library mit Unicode-Unterstützung, die Debugversion von MFC|
|AFXNMCD.LIB|MFC-Static Link Library ohne MFC-Dialogfeld-Steuerelemente, Releaseversion|
|AFXNMCDD.LIB|Static Link Library ohne MFC-Dialogfeld-Steuerelemente, Debugversion von MFC|

Außerdem stehen Debugger Dateien mit den gleichen Basisnamen und einer .pdb-Erweiterung für jede der statischen Bibliotheken zur Verfügung.

## <a name="mfc-shared-dll-naming-conventions"></a>Gemeinsam genutzte MFC-DLL-Benennungskonventionen

Die MFC-Bibliothek freigegebene DLLs auch führen Sie eine strukturierte-Namenskonvention gilt. Dies erleichtert es wissen, welche DLL oder eine Bibliothek Sie für welche Zwecke verwenden sollten.

Die MFC-DLLs haben *Version* Zahlen, die binäre Kompatibilität angeben. Verwenden Sie die MFC-DLLs, die die gleiche Version wie Ihre anderen Bibliotheken und Compiler-Toolset, um die Kompatibilität innerhalb eines Projekts zu gewährleisten.

|DLL|Beschreibung|
|---------|-----------------|
|MFC*Version*. DLL|Version von MFC-DLL, ANSI- oder MBCS-Version|
|MFC*Version*U.DLL|MFC-DLL, Unicode-Releaseversion|
|MFC*Version*D.DLL|MFC-DLL "," ANSI "oder" Debuggen von MBCS-version|
|MFC*Version*UD. DLL|MFC-DLL, Unicode-Debug-version|
|MFCM*Version*. DLL|MFC-DLL mit Windows Forms-Steuerelementen, ANSI- oder MBCS-Version-Version|
|MFCM*Version*U.DLL|MFC-DLL mit Windows Forms-Steuerelementen, Unicode-Releaseversion|
|MFCM*Version*D.DLL|MFC-DLL mit Windows Forms-Steuerelementen, ANSI- oder Debuggen der MBCS-Version|
|MFCM*Version*UD. DLL|MFC-DLL mit Windows Forms-Steuerelementen, Unicode-Debug-version|

Die Importbibliotheken, die zum Erstellen von Anwendungen oder MFC-Erweiterungs-DLLs, mit denen diese gemeinsam genutzte DLLs benötigt den gleichen Basisnamen wie die DLL haben aber eine LIB-Dateinamenerweiterung. Wenn Sie die freigegebene DLLs verwenden, muss eine kleine statische Bibliothek immer noch mit dem Code verknüpft sein; Diese Bibliothek heißt MFCS*Version*{U} {D} lib.

Wenn Sie dynamisch die gemeinsam genutzte DLL-Version von MFC, verknüpfen möchten, ob es sich um aus einer Anwendung oder aus einer MFC-Erweiterungs-DLL handelt, müssen Sie die entsprechende MFC-Bibliothek einschließen*Version*. DLL-Datei oder MFC*Version*U.DLL, wenn Sie Ihr Produkt bereitstellen.

Eine Liste der Visual C++-DLLs, die mit Ihren Anwendungen verteilt werden können, finden Sie unter [verteilbarer Code für Microsoft Visual Studio 2017 und Microsoft Visual Studio 2017 SDK (enthält Dienstprogramme und BuildServer-Dateien)](http://go.microsoft.com/fwlink/p/?LinkId=823098).

Weitere Informationen zur MBCS und Unicode-Unterstützung in MFC finden Sie unter [Unicode- und Multibyte-Zeichensatz (MBCS) Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

## <a name="dynamic-link-library-support"></a>Dynamic Link Library-Unterstützung

Sie können entweder statischen oder freigegebenen dynamische MFC-Bibliotheken verwenden, zum Erstellen von DLLs, die von ausführbaren MFC- und MFC-fremde Dateien verwendet werden kann. Diese werden als "reguläre DLLs" oder "regulären MFC-DLLs" bezeichnet, verwendet, um sie von MFC-Erweiterungs-DLLs zu unterscheiden, die nur können mithilfe von MFC-apps und MFC-DLLs. Eine DLL, die mithilfe der statischen MFC-Bibliotheken erstellt bezeichnet ein USRDLL in älteren verweisen, da MFC-DLL-Projekten das Präprozessorsymbol definieren  **\_USRDLL**. Eine DLL, die gemeinsam genutzte verwendet die MFC-DLLs bezeichnet AFXDLL in älteren verweisen, da sie das Präprozessorsymbol definiert  **\_AFXDLL**.

Wenn Sie Ihre DLL-Projekt erstellen, indem Sie mit der statischen MFC-Bibliotheken verknüpfen, kann die DLL bereitgestellt werden, ohne gemeinsam MFC-DLLs genutzte. Wenn Ihre DLL-Projekt verknüpft mit Importbibliotheken MFC*Version*. LIB oder MFC*Version*U.LIB, Sie müssen bereitstellen, den entsprechenden gemeinsam genutzte MFC-DLL MFC*Version*. DLL-Datei oder MFC*Version*U.DLL zusammen mit der DLL. Weitere Informationen finden Sie unter [DLLs](../build/dlls-in-visual-cpp.md).

## <a name="see-also"></a>Siehe auch

[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)
