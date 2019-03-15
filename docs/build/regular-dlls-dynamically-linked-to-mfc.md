---
title: Dynamisch mit MFC verknüpfte reguläre MFC-DLLs
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- AFX_MANAGE_STATE macro
- DLLs [C++], regular
- shared DLL versions [C++]
- dynamically linked DLLs [C++]
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
ms.openlocfilehash: 3bfed5f75dab4c501708950fdb99f53c40ec142c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821299"
---
# <a name="regular-mfc-dlls-dynamically-linked-to-mfc"></a>Dynamisch mit MFC verknüpfte reguläre MFC-DLLs

Eine, die MFC-DLL dynamisch mit MFC verknüpfte reguläre ist eine DLL, die MFC intern verwendet, und die exportierten Funktionen in der DLL können von entweder MFC oder MFC-fremde ausführbare Dateien aufgerufen werden. Wie der Name beschrieben wird, wird die mit der Dynamic Link Library-Version von MFC (auch bekannt als die freigegebene Version von MFC) diese Art von DLL erstellt werden. Funktionen werden in der Regel über reguläre MFC-DLL über die standard-C-Schnittstelle exportiert.

Sie müssen hinzufügen, die `AFX_MANAGE_STATE` Makro am Anfang die exportierten Funktionen in regulären MFC-DLLs, die dynamisch mit MFC für den aktuellen Zustand festzulegen, für die DLL verknüpfen. Dies erfolgt durch die folgende Codezeile am Anfang des aus der DLL exportierten Funktionen hinzufügen:

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

Eine reguläre MFC-DLL dynamisch mit MFC verknüpfte bietet die folgenden Features:

- Dies ist eine neue Art von DLL, die von Visual C++ 4.0 eingeführt.

- Die ausführbare Clientdatei kann in einer beliebigen Sprache geschrieben werden, die die Verwendung von DLLs (C, C++, Pascal, Visual Basic, usw.); unterstützt. Es ist keiner MFC-Anwendung sein.

- Im Gegensatz zu der statisch verknüpften regulären MFC-DLL wird die DLL dynamisch mit der MFC-DLL (auch bekannt als die gemeinsam genutzten MFC-DLL) verknüpft.

- Die MFC-Importbibliothek verknüpft werden, um die DLL ist der gleiche für MFC-Erweiterungs-DLLs oder Anwendungen, die mit der MFC-DLL: MFCxx(D).lib.

Eine reguläre MFC-DLL dynamisch mit MFC verknüpfte gelten die folgenden Anforderungen:

- Mit dieser DLL kompiliert **_AFXDLL** definiert, wie eine ausführbare Datei, die dynamisch mit MFC-DLL verknüpft ist. Aber **_USRDLL** wird auch definiert, wie eine reguläre MFC-DLL, die statisch mit MFC verknüpft wird.

- Diese Art von DLL muss Instanziieren einer `CWinApp`-abgeleitete Klasse.

- Diese Art von DLL verwendet die `DllMain` von MFC bereitgestellt. Platzieren Sie alle DLL-spezifische Initialisierungscode in der `InitInstance` Elementcode-Funktion und Beendigung in `ExitInstance` wie bei einer normalen MFC-Anwendung.

Da diese Art von DLL über die Dynamic Link Library-Version von MFC verwendet, müssen Sie explizit den aktuellen Modulstatus, die für die DLL festlegen. Verwenden Sie hierzu die [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) Makro am Anfang jeder Funktion, die aus der DLL exportiert.

reguläre MFC-DLLs müssen eine `CWinApp`-Klasse und ein einzelnes Objekt der Anwendungsklasse abgeleitet, wie eine MFC-Anwendung. Allerdings die `CWinApp` Objekt der DLL keine Haupt-Meldungsverteilschleife, wie die `CWinApp` Objekt einer Anwendung.

Beachten Sie, dass die `CWinApp::Run` Mechanismus selbst gilt nicht für eine DLL, da die Anwendung die Haupt-Meldungsverteilschleife besitzt. Wenn die DLL nicht modale Dialogfelder öffnet oder eine eigene Hauptrahmenfenster, Haupt-Meldungsverteilschleife Ihrer Anwendung muss eine DLL exportierte Routine aufrufen, die Aufrufe `CWinApp::PreTranslateMessage`.

Platzieren Sie alle DLL-spezifische-Initialisierung in der `CWinApp::InitInstance` Memberfunktion in einer normalen MFC-Anwendung. Die `CWinApp::ExitInstance` Memberfunktion Ihre `CWinApp` abgeleiteten Klasse wird aufgerufen, durch die von MFC bereitgestellten `DllMain` -Funktion die DLL entladen wird.

Sie müssen die freigegebene DLLs, nämlich MFCx0.dll und 0.dll (oder ähnliche Dateien) mit Ihrer Anwendung verteilen.

Eine DLL, die dynamisch mit MFC verknüpft wird, kann nicht auch statisch mit MFC verknüpft. Anwendungen, die mit regulären MFC-DLLs verknüpfen verknüpften dynamisch mit MFC es genau wie jede andere DLL.

Symbole werden in der Regel über reguläre MFC-DLL über die standard-C-Schnittstelle exportiert. Die Deklaration einer aus einer regulären MFC DLL exportierten Funktion sieht etwa folgendermaßen aus:

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

Alle speicherbelegungen innerhalb einer regulären MFC DLL sollten in der DLL bleiben; die DLL sollte nicht zu übergeben oder erhalten Sie eine der folgenden von der aufrufenden ausführbaren Datei:

- Zeiger auf MFC-Objekte

- Zeiger auf die speicherbelegung von MFC

Wenn Sie einen der oben genannten Schritte müssen oder wenn Sie MFC abgeleitete Objekte zwischen der aufrufende ausführbare Datei und DLL übergeben müssen, müssen Sie eine MFC-Erweiterungs-DLL erstellen.

Es ist sicher Zeiger auf den Speicher, die zugeordnet wurden durch Übergeben der C-Laufzeitbibliotheken zwischen einer Anwendung und eine DLL-Datei nur dann, wenn Sie eine Kopie der Daten erstellen. Sie müssen nicht löschen oder Ändern der Größe diese Zeiger oder diese verwenden, ohne dass eine Kopie des Speichers.

Beim Erstellen einer regulären MFC-DLL, die dynamisch mit MFC verknüpft ist, müssen Sie das Makro verwenden [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) MFC-Modulstatus ordnungsgemäß zu wechseln. Dies erfolgt durch die folgende Codezeile am Anfang des aus der DLL exportierten Funktionen hinzufügen:

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

Die **AFX_MANAGE_STATE** Makro sollte nicht verwendet werden, in regulären MFC-DLLs, die statisch mit MFC verknüpft oder in MFC-Erweiterungs-DLLs. Weitere Informationen finden Sie unter [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md).

Ein Beispiel zum Schreiben, erstellen und Verwenden einer regulären MFC DLL finden Sie im Beispiel [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap). Weitere Informationen zu regulären MFC-DLLs, die dynamisch mit MFC verknüpfen, finden Sie unter im Abschnitt "Konvertieren von DLLScreenCap auf dynamische Verknüpfung mit der MFC-DLL" in der Zusammenfassung für das Beispiel.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Reguläre MFC-DLLs initialisieren](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Modulzustände einer regulären MFC DLL verknüpften dynamisch mit MFC](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)

- [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)

- [Using Database, OLE, and Sockets MFC extension DLLs in regular MFC DLLs (Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs)](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

## <a name="see-also"></a>Siehe auch

[Arten von DLLs](kinds-of-dlls.md)
