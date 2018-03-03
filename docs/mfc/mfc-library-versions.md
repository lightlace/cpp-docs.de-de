---
title: MFC-Bibliotheksversionen | Microsoft Docs
ms.custom: 
ms.date: 1/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7641a970c747576fa3cfd8cd1c00602edb3541e2
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2018
---
# <a name="mfc-library-versions"></a>MFC-Bibliotheksversionen

Die MFC-Bibliothek ist in Versionen, die ANSI-Einzelbyte-Unterstützung verfügbar und Mehrbyte-Zeichensatz (MBCS) Code sowie die Versionen, die Unicode (codiert als UTF-16LE der systemeigenen Windows-Zeichensatz) unterstützen. Jedes MFC-Version ist verfügbar, als statische Bibliothek oder als eine freigegebene DLL. Zudem besteht eine kleinere MFC statischen Bibliotheksversion, die MFC-Steuerelemente für Dialogfelder, für die Anwendungen verlassen, die sind sehr empfindlich gegenüber Größe und die Steuerelemente nicht erforderlich. Die MFC-Bibliotheken stehen in sowohl Debug-als auch Releaseversionen unterstützten Architekturen, die X86 X64 und ARM-Prozessoren enthalten. Sie können beide Anwendungen (.exe-Dateien) erstellen und DLLs mit einer Version von MFC-Bibliotheken. Es gibt auch einen Satz von MFC-Bibliotheken, die für eine Schnittstelle mit verwaltetem Code kompiliert. Die MFC-Bibliothek gemeinsam genutzte DLLs enthalten eine Versionsnummer, um die Binärkompatibilität Bibliothek anzugeben.

## <a name="automatic-linking-of-mfc-library-versions"></a>Automatisches Verlinken der MFC-Bibliotheksversionen

Die MFC-Headerdateien bestimmt automatisch die richtige Version der MFC-Bibliothek zu verknüpfen, basierend auf Werten, die in der Buildumgebung definiert. Die MFC-Headerdateien hinzufügen Compilerdirektiven den Linker angewiesen wird, um in einer bestimmten Version der MFC-Bibliothek zu verknüpfen.

Beispiel: die AFX. H-Headerdatei weist den Linker an, in die vollständige statische, beschränkt statisch oder gemeinsam genutzten DLL-Version von MFC verknüpfen; ANSI-/MBCS oder Unicode-Version. und Debuggen "oder" Retail-Version, abhängig von der Buildkonfiguration:

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

MFC-Headerdateien umfassen auch Anweisungen zur Verknüpfung von alle erforderlichen Bibliotheken, einschließlich der MFC-Bibliotheken, Win32-Bibliotheken, OLE-Bibliotheken, OLE-Bibliotheken, die aus Beispielen erstellt, ODBC-Bibliotheken und So weiter. 

## <a name="ansi-mbcs-and-unicode"></a>ANSI, MBCS und Unicode

Die MFC-ANSI-/MBCS-Bibliotheksversionen unterstützen beide Einzelbyte-Zeichensätze, z. B. ASCII und Mehrbyte-Zeichensätzen wie Shift-JIS. In UTF-16LE Breitzeichen-codierte Form, die Unicode-MFC-Bibliotheksversionen wird Unicode unterstützt. Verwenden Sie die ANSI-/MBCS-Bibliotheksversionen von MFC für UTF-8-Unterstützung für Unicode codierte.

Um die Projektkonfiguration Einzelbyte-Multibytezeichen oder Breitzeichen-Unicode-Zeichenfolgen und Unterstützung für in der IDE festzulegen, verwenden die **Projekteigenschaften** Dialogfeld. In der **Konfigurationseigenschaften** > **allgemeine** Seite der **Zeichensatz** Eigenschaft **nicht festgelegt** verwenden eine Einzelbyte-Zeichensatz. Legen Sie die Eigenschaft auf **verwenden Multi-Byte Character Set** Mehrbyte-Zeichensatz verwenden oder **Unicode-Zeichensatz verwenden** Unicode codiert als UTF-16 verwendet.

MFC-Projekten verwenden das Präprozessorsymbol  **\_UNICODE** an, dass UTF-16 Breitzeichen-Unicode-Unterstützung und  **\_MBCS** an, dass MBCS-Unterstützung. Diese Optionen sind sich gegenseitig ausschließende in einem Projekt.

## <a name="mfc-static-library-naming-conventions"></a>Namenskonventionen für MFC-statische Bibliothek

Statische Bibliotheken für MFC verwenden Sie die folgenden Benennungskonventionen. Die Bibliotheksnamen haben das Format

> *u*AFX*c ** d*. LIB

die Buchstaben kursiv dargestellten Kleinbuchstaben Platzhalter für Bezeichner gegangenem, dessen Bedeutung in der folgenden Tabelle angezeigt werden:

|Bezeichner|Werte und Bedeutung|
|---------------|-------------------------|
|*u*|(N) ANSI-/MBCS oder Unicode (U); für Version ohne MFC-Steuerelemente in Dialogfeldern auslassen|
|*c*|Die Version mit MFC-Steuerelementen in Dialogfeldern (WINS, CW) oder ohne (NMCD)|
|*d*|Debug- oder Release: D = Debug; Spezifizierer für Version auslassen|

Alle Bibliotheken, die in der folgenden Tabelle aufgeführt sind, enthalten im Verzeichnis \atlmfc\lib unterstützten Build Architekturen vorgefertigten.

|Bibliothek|Beschreibung|
|-------------|-----------------|
|NAFXCW.LIB|MFC-Static Link Library, Originalversion|
|NAFXCWD.LIB|MFC-Static Link Library Debugversion|
|UAFXCW.LIB|MFC-Static Link Library mit Unicode-Unterstützung, Releaseversion|
|UAFXCWD.LIB|Static Link Library mit Unicode-Unterstützung, die Debugversion von MFC|
|AFXNMCD. LIB|MFC-Static Link Library ohne MFC-Dialogfeld-Steuerelemente, Originalversion|
|AFXNMCDD. LIB|Static Link Library ohne MFC-Dialogfeld-Steuerelemente, Debugversion von MFC|

Debugger-Dateien, die den gleichen Basisnamen und eine Erweiterung ".pdb" verfügen, sind auch verfügbar, für jede der statischen Bibliotheken.

## <a name="mfc-shared-dll-naming-conventions"></a>Gemeinsam genutzte MFC-DLL-Benennungskonventionen

Die MFC-Bibliothek für freigegebene DLLs außerdem gilt eine strukturierten Namenskonvention gilt. Dies erleichtert es, wissen, welche DLL-Datei oder Bibliothek Sie für welchen Zweck verwendet werden soll.

Die MFC-DLLs haben *Version* Zahlen, die Binärkompatibilität angeben. Verwenden Sie die MFC-DLLs, die die gleiche Version wie die andere Bibliotheken und Compilertoolset zum Gewährleisten der Kompatibilität innerhalb eines Projekts haben.

|DLL|Beschreibung|
|---------|-----------------|
|MFC*Version*. DLL|Version von MFC-DLL, ANSI oder MBCS-Version|
|MFC*Version*U.DLL|MFC-DLL, Unicode-Release-version|
|MFC*Version*D.DLL|MFC-DLL, ANSI oder Debuggen von MBCS-version|
|MFC*Version*UD. DLL|MFC-DLL, Unicode-Debugversion|
|MFCM*Version*. DLL|MFC-DLL mit Windows Forms-Steuerelemente ANSI- oder MBCS-Release-Version|
|MFCM*Version*U.DLL|MFC-DLL mit Unicode-Release-Version Windows Forms-Steuerelemente|
|MFCM*Version*D.DLL|MFC-DLL mit Windows Forms-Steuerelemente ANSI- oder Debuggen von MBCS-Version|
|MFCM*Version*UD. DLL|MFC-DLL mit Unicode-Debugversion Windows Forms-Steuerelemente|

Die Importbibliotheken zum Erstellen von Anwendungen oder MFC-Erweiterungs-DLLs, die diese gemeinsam genutzte DLLs verwenden den gleichen Basisnamen wie die DLL haben aber eine LIB-Dateinamenerweiterung. Bei Verwendung der gemeinsam genutzte DLLs muss eine kleine statische Bibliothek mit Ihrem Code weiterhin verknüpft sein; Diese Bibliothek heißt MFCS*Version*lib {U} {D}.

Wenn Sie dynamisch der gemeinsam genutzten DLL-Version von MFC verknüpfen möchten, ob sie eine Anwendung oder eine MFC-Erweiterungs-DLL ist, müssen Sie die entsprechende MFC-Bibliothek einschließen*Version*. DLL-Datei oder MFC*Version*U.DLL, wenn Sie Ihr Produkt bereitstellen.

Eine Liste der Visual C++-DLLs, die mit Ihren Anwendungen verteilt werden können, finden Sie unter [verteilbarer Code für Microsoft Visual Studio 2017 und Microsoft Visual Studio 2017 SDK (enthält Dienstprogramme und BuildServer-Dateien)](http://go.microsoft.com/fwlink/p/?LinkId=823098).

Weitere Informationen zur MBCS und Unicode-Unterstützung in MFC finden Sie unter [Unicode- und Multibyte-Zeichensätzen (MBCS)-Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

## <a name="dynamic-link-library-support"></a>Dynamic Link Library-Unterstützung

Sie können entweder statischen oder gemeinsam genutzten dynamic MFC-Bibliotheken verwenden, zum Erstellen von DLLs, die von MFC und MFC-fremde ausführbare Dateien verwendet werden kann. Diese heißen "reguläre DLLs" oder "regulären MFC-DLLs", verwendet, um sie von MFC-Erweiterungs-DLLs zu unterscheiden, die nur können von MFC-apps und MFC-DLLs. Eine DLL erstellt mithilfe der statischen MFC-Bibliotheken wird eine USRDLL manchmal in älteren verweisen bezeichnet werden, da MFC-DLL-Projekten das Präprozessorsymbol definieren  **\_USRDLL**. Eine DLL, die gemeinsam genutzte verwendet die MFC-DLLs wird AFXDLL manchmal in älteren verweisen bezeichnet werden, da es das Präprozessorsymbol definiert  **\_AFXDLL**.

Wenn Sie das DLL-Projekt erstellen, indem Sie mit der statischen MFC-Bibliotheken verknüpfen, kann die DLL bereitgestellt werden, ohne gemeinsam MFC-DLLs genutzte. Wenn Ihre DLL-Projekt verknüpft mit Importbibliotheken MFC*Version*. LIB oder MFC*Version*U.LIB, Sie müssen bereitstellen, die entsprechenden gemeinsam genutzte MFC-DLL MFC*Version*. DLL-Datei oder MFC*Version*U.DLL zusammen mit der DLL. Weitere Informationen finden Sie unter [DLLs](../build/dlls-in-visual-cpp.md).

## <a name="see-also"></a>Siehe auch

[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)  
