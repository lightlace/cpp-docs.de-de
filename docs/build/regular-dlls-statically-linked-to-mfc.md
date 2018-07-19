---
title: Statisch mit MFC verknüpfte reguläre MFC-DLLs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++]
- DLLs [C++], regular
- USRDLLs
- USRDLLs, statically linked to MFC
- statically linked DLLs [C++]
- regular MFC DLLs [C++], statically linked to MFC
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c48fdfb0b10541c1643ec49038e29cfa60c633d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383747"
---
# <a name="regular-mfc-dlls-statically-linked-to-mfc"></a>Statisch mit MFC verknüpfte reguläre MFC-DLLs
Eine reguläre MFC-DLL statisch mit MFC verknüpft wird, eine DLL, die MFC intern verwendet und von ausführbaren MFC oder MFC-Dateien können in der DLL exportierten Funktionen aufgerufen werden. Wie der Name beschrieben wird, wird diese Art von DLL erstellt mithilfe der static Link Library-Version von MFC. Funktionen sind in der Regel über reguläre MFC-DLL über die standard-C-Schnittstelle exportiert. Ein Beispiel zu schreiben, erstellen und eine reguläre MFC-DLL verwenden, finden Sie im Beispiel [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap).  
  
 Beachten Sie, die den Begriff USRDLL nicht mehr in der Dokumentation zu Visual C++ verwendet wird. Eine reguläre MFC-DLL, die statisch mit MFC verknüpft wird, hat dieselben Merkmale wie die frühere USRDLL.  
  
 Eine reguläre, statisch mit MFC verknüpfte MFC DLL hat die folgenden Funktionen:  
  
-   Die ausführbare Clientdatei kann in einer beliebigen Sprache geschrieben werden, die unterstützt die Verwendung von DLLs (C, C++, Pascal, Visual Basic, usw.); Es muss sich nicht in einer MFC-Anwendung sein.  
  
-   Die DLL kann die gleichen MFC static Link Libraries, die von Clientanwendungen genutzt verknüpfen. Es ist nicht mehr eine separate Version der static Link Libraries für DLLs.  
  
-   Vor Version 4.0 von MFC bereitgestellten USRDLLs dieselbe Art von Funktionalität wie reguläre, statisch mit MFC verknüpfte MFC-DLLs. Ab Visual C++ ist als Version 4.0 des Begriffs USRDLL veraltet.  
  
 Eine reguläre, statisch mit MFC verknüpfte MFC DLL hat die folgenden Anforderungen:  
  
-   Diese Art von DLL muss instanziieren eine Klasse abgeleitet `CWinApp`.  
  
-   Diese Art von DLL verwendet die `DllMain` von MFC bereitgestellt. Platzieren Sie alle DLL-spezifische Initialisierungscode in der `InitInstance` Elementcode-Funktion und Beendigung in `ExitInstance` wie bei einer normalen MFC-Anwendung.  
  
-   Obwohl der Begriff USRDLL veraltet ist, müssen Sie dennoch definieren "**_USRDLL**" auf der Befehlszeile des Compilers. Diese Definition wird bestimmt, welche Deklarationen aus den MFC-Headerdateien per Pull abgerufen wird.  
  
 Reguläre MFC-DLLs benötigen eine `CWinApp`-Klasse und ein einzelnes Objekt dieser Anwendungsklasse abgeleitet, wie eine MFC-Anwendung. Allerdings die `CWinApp` Objekt der DLL keine Haupt-Meldungsverteilschleife, wie die `CWinApp` Objekt einer Anwendung.  
  
 Beachten Sie, dass die `CWinApp::Run` Mechanismus selbst gilt nicht für eine DLL, da die Anwendung die Haupt-Meldungsverteilschleife besitzt. Wenn die DLL nicht modale Dialogfelder öffnet oder ein Hauptrahmenfenster eigene, muss die Haupt-Meldungsverteilschleife der Anwendung eine Routine, die von der DLL, die wiederum ruft exportierten Aufrufen der `CWinApp::PreTranslateMessage` Memberfunktion von der DLL-Application-Objekt.  
  
 Ein Beispiel dieser Funktion finden Sie im DLLScreenCap-Beispiel.  
  
 Symbole werden in der Regel über reguläre MFC-DLL über die standard-C-Schnittstelle exportiert. Die Deklaration einer aus einer regulären MFC-DLL exportierten Funktion würde etwa wie folgt aussehen:  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 Alle speicherbelegungen innerhalb einer regulären MFC DLL sollte innerhalb der DLL bleiben. die DLL sollten nicht an übergeben oder Empfangen von der aufrufenden ausführbaren Datei die folgenden:  
  
-   Zeiger auf MFC-Objekte  
  
-   Zeiger auf von MFC belegten Arbeitsspeicher  
  
 Wenn Sie eine der oben genannten Kriterien oder MFC abgeleitete Objekte zwischen der aufrufenden ausführbaren Datei und DLL übergeben müssen, müssen Sie eine MFC-Erweiterungs-DLL erstellen.  
  
 Sie können ruhig Zeiger in den Arbeitsspeicher, die zugewiesen wurden durch Übergeben der C-Laufzeitbibliotheken zwischen einer Anwendung und eine DLL-Datei nur dann, wenn eine Kopie der Daten erstellt. Sie müssen nicht löschen oder ändern diese Zeiger oder verwenden, ohne dass eine Kopie des Arbeitsspeichers.  
  
 Eine, die statisch mit MFC verknüpften DLL kann nicht mit der gemeinsam genutzten MFC-DLLs auch dynamisch verknüpfen. Eine DLL, die statisch mit MFC verknüpften ist dynamisch zu einer Anwendung genau wie jede andere DLL gebunden. Anwendungen, die mit es genau wie jede andere DLL verknüpft wird.  
  
 Die standardmäßigen MFC-static Link Libraries heißen gemäß der Konvention, die in beschriebenen [Namenskonventionen für MFC-DLLs](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions). Mit MFC, Version 3.0 und höher ist es jedoch nicht mehr erforderlich, manuell an den Linker geben die Version der MFC-Bibliothek, die eingebunden werden soll. Stattdessen automatisch die MFC-Headerdateien bestimmt die richtige Version der MFC-Bibliothek zur Verknüpfung von basierend auf Präprozessor definiert, wie z. B.  **\_DEBUGGEN** oder **_UNICODE**. Die MFC-Headerdateien hinzufügen Option Direktiven den Linker angewiesen wird, um in einer bestimmten Version der MFC-Bibliothek zu verknüpfen.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Reguläre MFC-DLLs initialisieren](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [Using Database, OLE, and Sockets MFC extension DLLs in regular MFC DLLs (Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs)](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [Erstellen einer MFC-DLL](../mfc/reference/mfc-dll-wizard.md)  
  
-   [Regular MFC DLLs Dynamically Linked to MFC (Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs)](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC extension DLLs (MFC-Erweiterungs-DLLs)](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Arten von DLLs](../build/kinds-of-dlls.md)