---
title: Statisch mit MFC verknüpfte reguläre MFC-DLLs
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++]
- DLLs [C++], regular
- USRDLLs
- USRDLLs, statically linked to MFC
- statically linked DLLs [C++]
- regular MFC DLLs [C++], statically linked to MFC
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
ms.openlocfilehash: 1f05b5e3c268935cf3161fb7184e04b3e3ea1446
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815800"
---
# <a name="regular-mfc-dlls-statically-linked-to-mfc"></a>Statisch mit MFC verknüpfte reguläre MFC-DLLs

Eine, die MFC-DLL statisch mit MFC verknüpfte reguläre ist eine DLL, die MFC intern verwendet, und die exportierten Funktionen in der DLL können von entweder MFC oder MFC-fremde ausführbare Dateien aufgerufen werden. Wie der Name beschrieben wird, wird die mit der static Link Library-Version von MFC diese Art von DLL erstellt werden. Funktionen werden in der Regel über reguläre MFC-DLL über die standard-C-Schnittstelle exportiert. Ein Beispiel zum Schreiben, erstellen und Verwenden einer regulären MFC DLL finden Sie im Beispiel [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap).

Beachten Sie, die den Begriff USRDLL nicht mehr in der Dokumentation zu Visual C++ verwendet wird. Eine reguläre MFC-DLL, die statisch mit MFC verknüpfte hat dieselben Merkmale wie die frühere USRDLL.

Eine reguläre, statisch mit MFC verknüpfte MFC DLL hat die folgenden Funktionen:

- Die ausführbare Clientdatei kann in einer beliebigen Sprache geschrieben werden, die die Verwendung von DLLs (C, C++, Pascal, Visual Basic, usw.); unterstützt. Es ist keiner MFC-Anwendung sein.

- Die DLL kann auf die gleichen MFC static Link Libraries, die von Anwendungen verwendeten verknüpfen. Es ist nicht mehr eine separate Version der statischen DLLs für DLL-Dateien.

- Vor Version 4.0 von MFC bereitgestellten USRDLLs die gleiche Art von Funktionalität wie reguläre, statisch mit MFC verknüpfte MFC-DLLs. Ab Visual C++-ist Version 4.0, der Begriff USRDLL überholt.

Eine reguläre, statisch mit MFC verknüpfte MFC DLL hat die folgenden Anforderungen:

- Die DLL muss eine Klasse, die von abgeleiteten instanziieren `CWinApp`.

- Diese Art von DLL verwendet die `DllMain` von MFC bereitgestellt. Platzieren Sie alle DLL-spezifische Initialisierungscode in der `InitInstance` Elementcode-Funktion und Beendigung in `ExitInstance` wie bei einer normalen MFC-Anwendung.

- Obwohl der Begriff USRDLL veraltet ist, müssen Sie immer noch definieren "**_USRDLL**" auf der Befehlszeile des Compilers. Diese Definition wird bestimmt, welche Deklarationen aus den MFC-Headerdateien.

reguläre MFC-DLLs müssen eine `CWinApp`-Klasse und ein einzelnes Objekt der Anwendungsklasse abgeleitet, wie eine MFC-Anwendung. Allerdings die `CWinApp` Objekt der DLL keine Haupt-Meldungsverteilschleife, wie die `CWinApp` Objekt einer Anwendung.

Beachten Sie, dass die `CWinApp::Run` Mechanismus selbst gilt nicht für eine DLL, da die Anwendung die Haupt-Meldungsverteilschleife besitzt. Wenn die DLL nicht modale Dialogfelder geöffnet oder eine eigene Hauptrahmenfenster, muss die Haupt-Meldungsverteilschleife der Anwendung eine Routine, die von der DLL, die wiederum ruft exportierten Aufrufen der `CWinApp::PreTranslateMessage` Memberfunktion des DLL Application-Objekt.

Ein Beispiel dieser Funktion finden Sie im DLLScreenCap-Beispiel.

Symbole werden in der Regel über reguläre MFC-DLL über die standard-C-Schnittstelle exportiert. Die Deklaration einer Funktion, die aus einer regulären MFC-DLL exportiert würde etwa wie folgt aussehen:

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

Alle speicherbelegungen innerhalb einer regulären MFC DLL sollten in der DLL bleiben; die DLL sollte nicht zu übergeben oder erhalten Sie eine der folgenden von der aufrufenden ausführbaren Datei:

- Zeiger auf MFC-Objekte

- Zeiger auf die speicherbelegung von MFC

Wenn Sie eine der oben genannten oder MFC abgeleitete Objekte zwischen der aufrufende ausführbare Datei und DLL übergeben müssen, müssen Sie eine MFC-Erweiterungs-DLL erstellen.

Es ist sicher Zeiger auf den Speicher, die zugeordnet wurden durch Übergeben der C-Laufzeitbibliotheken zwischen einer Anwendung und eine DLL-Datei nur dann, wenn Sie eine Kopie der Daten erstellen. Sie müssen nicht löschen oder Ändern der Größe diese Zeiger oder diese verwenden, ohne dass eine Kopie des Speichers.

Eine DLL, die statisch mit MFC verknüpfte kann nicht mit der gemeinsam genutzte MFC-DLLs auch dynamisch verknüpfen. Eine DLL, die statisch mit MFC verknüpfte wird dynamisch an eine Anwendung wie jede andere DLL gebunden; Anwendungen verknüpfen, genau wie jede andere DLL.

Standard statischen MFC-DLLs werden gemäß der Konvention, die in beschriebenen benannt [Namenskonventionen für MFC-DLLs](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions). Mit MFC, Version 3.0 und höher ist es jedoch nicht mehr erforderlich, manuell die Version der MFC-Bibliothek für den Linker anzugeben, die eingebunden werden soll. Stattdessen wird er automatisch die MFC-Headerdateien bestimmt die richtige Version der MFC-Bibliothek zur Verknüpfung von basierend auf Präprozessor definiert, wie z. B.  **\_DEBUGGEN** oder **_UNICODE**. Die MFC-Headerdateien DEFAULTLIB fügen-Direktiven hinzu, des Linkers in einer bestimmten Version der MFC-Bibliothek zu verknüpfen.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Reguläre MFC-DLLs initialisieren](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [Using Database, OLE, and Sockets MFC extension DLLs in regular MFC DLLs (Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs)](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [Erstellen eine MFC-DLL](../mfc/reference/mfc-dll-wizard.md)

- [Regular MFC DLLs Dynamically Linked to MFC (Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs)](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC extension DLLs (MFC-Erweiterungs-DLLs)](extension-dlls-overview.md)

## <a name="see-also"></a>Siehe auch

[Arten von DLLs](kinds-of-dlls.md)
