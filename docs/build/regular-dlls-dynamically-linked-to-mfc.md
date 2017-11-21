---
title: "Dynamisch mit MFC verknüpfte reguläre MFC-DLLs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- AFX_MANAGE_STATE macro
- DLLs [C++], regular
- shared DLL versions [C++]
- dynamically linked DLLs [C++]
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9c1835ad660c9dbb9f8e4b43dbf697ea960f82ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="regular-mfc-dlls-dynamically-linked-to-mfc"></a>Dynamisch mit MFC verknüpfte reguläre MFC-DLLs
Eine reguläre MFC-DLL dynamisch mit MFC verknüpft wird, eine DLL, die MFC intern verwendet und von ausführbaren MFC oder MFC-Dateien können in der DLL exportierten Funktionen aufgerufen werden. Wie der Name beschrieben wird, wird diese Art von DLL über die Dynamic Link Library-Version von MFC (auch bekannt als die freigegebene Version von MFC) erstellt. Funktionen sind in der Regel über reguläre MFC-DLL über die standard-C-Schnittstelle exportiert.  
  
 Sie müssen Hinzufügen der `AFX_MANAGE_STATE` Makro am Anfang der exportierten Funktionen in regulären MFC-DLLs, die dynamisch mit MFC für den aktuellen Zustand des Moduls festzulegen, für die DLL verknüpft sind. Dies erfolgt durch die folgende Codezeile am Anfang des aus der DLL exportierten Funktionen hinzufügen:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 Dynamisch mit MFC verknüpfte reguläre MFC-DLL hat die folgenden Funktionen:  
  
-   Dies ist eine neue Art von DLL, die von Visual C++ 4.0 eingeführt.  
  
-   Die ausführbare Clientdatei kann in einer beliebigen Sprache geschrieben werden, die unterstützt die Verwendung von DLLs (C, C++, Pascal, Visual Basic, usw.); Es muss sich nicht in einer MFC-Anwendung sein.  
  
-   Im Gegensatz zu der statisch verknüpften regulären MFC-DLL ist diese Art von DLL dynamisch mit MFC-DLL (auch bekannt als die gemeinsam genutzte MFC-DLL) verknüpft.  
  
-   Die MFC-Importbibliothek verknüpft werden, um diese Art von DLL ist der gleiche für MFC-Erweiterungs-DLLs oder Anwendungen, die mit der MFC-DLL verwendet: lib MFCxx (D).  
  
 Dynamisch mit MFC verknüpfte reguläre MFC-DLL hat die folgenden Anforderungen:  
  
-   Diese DLLs mit kompiliert **_AFXDLL** definiert, wie eine ausführbare Datei, die dynamisch mit MFC-DLL verknüpft ist. Aber **_USRDLL** wird auch definiert, wie eine reguläre MFC-DLL, die statisch mit MFC verknüpft wird.  
  
-   Diese Art von DLL muss Instanziieren einer `CWinApp`-Klasse abgeleitet.  
  
-   Diese Art von DLL verwendet die `DllMain` von MFC bereitgestellt. Platzieren Sie alle DLL-spezifische Initialisierungscode in der `InitInstance` Elementcode-Funktion und Beendigung in `ExitInstance` wie bei einer normalen MFC-Anwendung.  
  
 Da diese Art von DLL über die Dynamic Link Library-Version von MFC verwendet, müssen Sie explizit den aktuellen Zustand des Moduls mit der für die DLL festlegen. Verwenden Sie hierzu die [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) Makro am Anfang jeder Funktion aus der DLL exportierten.  
  
 Reguläre MFC-DLLs benötigen eine `CWinApp`-Klasse und ein einzelnes Objekt dieser Anwendungsklasse abgeleitet, wie eine MFC-Anwendung. Allerdings die `CWinApp` Objekt der DLL keine Haupt-Meldungsverteilschleife, wie die `CWinApp` Objekt einer Anwendung.  
  
 Beachten Sie, dass die `CWinApp::Run` Mechanismus selbst gilt nicht für eine DLL, da die Anwendung die Haupt-Meldungsverteilschleife besitzt. Wenn die DLL nicht modale Dialogfelder öffnet oder ein Hauptrahmenfenster eigene, Haupt-Meldungsverteilschleife für Ihre Anwendung muss eine DLL exportiert Routine aufrufen, die Aufrufe `CWinApp::PreTranslateMessage`.  
  
 Platzieren Sie alle DLL-spezifische Initialisierung in den `CWinApp::InitInstance` Memberfunktion wie bei einer normalen MFC-Anwendung. Die `CWinApp::ExitInstance` Memberfunktion von Ihrem `CWinApp` abgeleiteten Klasse aufgerufen wird, über die MFC-Bibliothek bereitgestellt `DllMain` Funktion, bevor die DLL entladen wird.  
  
 Sie müssen die gemeinsam genutzten DLLs, nämlich MFCx0.dll und 0.dll (oder ähnliche Dateien) mit der Anwendung verteilen.  
  
 Eine DLL, die dynamisch mit MFC verknüpft wird, kann nicht auch statisch mit MFC verknüpft. Anwendungen-Link, um reguläre MFC-DLLs verknüpften dynamisch mit MFC ihn genau wie jede andere DLL.  
  
 Symbole werden in der Regel über reguläre MFC-DLL über die standard-C-Schnittstelle exportiert. Die Deklaration einer aus einer regulären MFC-DLL exportierten Funktion sieht etwa wie folgt:  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 Alle speicherbelegungen innerhalb einer regulären MFC DLL sollte innerhalb der DLL bleiben. die DLL sollten nicht an übergeben oder Empfangen von der aufrufenden ausführbaren Datei die folgenden:  
  
-   Zeiger auf MFC-Objekte  
  
-   Zeiger auf von MFC belegten Arbeitsspeicher  
  
 Wenn Sie einen der oben genannten Schritte ausführen müssen oder MFC abgeleitete Objekte zwischen der aufrufenden ausführbaren Datei und DLL übergeben werden müssen, müssen Sie eine MFC-Erweiterungs-DLL erstellen.  
  
 Sie können ruhig Zeiger in den Arbeitsspeicher, die zugewiesen wurden durch Übergeben der C-Laufzeitbibliotheken zwischen einer Anwendung und eine DLL-Datei nur dann, wenn eine Kopie der Daten erstellt. Sie müssen nicht löschen oder ändern diese Zeiger oder verwenden, ohne dass eine Kopie des Arbeitsspeichers.  
  
 Beim Erstellen einer regulären MFC-DLL, die dynamisch mit MFC verknüpft ist, müssen Sie das Makro verwenden [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) MFC-Modulstatus ordnungsgemäß zu wechseln. Dies erfolgt durch die folgende Codezeile am Anfang des aus der DLL exportierten Funktionen hinzufügen:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 Die **AFX_MANAGE_STATE** Makro sollte nicht in regulären MFC-DLLs, die statisch mit MFC verknüpft oder in MFC-Erweiterungs-DLLs verwendet werden. Weitere Informationen finden Sie unter [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md).  
  
 Ein Beispiel zu schreiben, erstellen und eine reguläre MFC-DLL verwenden, finden Sie im Beispiel [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap). Weitere Informationen zu regulären MFC-DLLs, die dynamisch mit MFC verknüpft sind, finden Sie unter im Abschnitt "Konvertieren DLLScreenCap auf dynamische Verknüpfung mit der MFC-DLL" in der Zusammenfassung für das Beispiel.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Reguläre MFC-DLLs initialisieren](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Die Modulzustände einer regulären MFC-DLL verknüpften dynamisch mit MFC](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
  
-   [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [Using Database, OLE, and Sockets MFC extension DLLs in regular MFC DLLs (Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs)](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Arten von DLLs](../build/kinds-of-dlls.md)