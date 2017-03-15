---
title: "Regul&#228;re, dynamisch mit MFC verkn&#252;pfte DLLs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_MANAGE_STATE-Makro"
  - "DLLs [C++], Reguläre"
  - "Dynamisch verknüpfte DLLs [C++]"
  - "Reguläre DLLs [C++], Dynamisch verknüpft mit MFC"
  - "Gemeinsam genutzte DLL-Versionen [C++]"
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Regul&#228;re, dynamisch mit MFC verkn&#252;pfte DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine reguläre DLL, die dynamisch mit MFC verknüpft ist, ist eine DLL, die MFC intern verwendet und deren exportierte Funktionen entweder von ausführbaren MFC\- oder von ausführbaren MFC\-fremden Dateien aufgerufen werden können.  Wie der Name bereits vermuten lässt, wird dieser DLL\-Typ unter Verwendung der Dynamic Link Library\-Version von MFC \(auch bekannt als die gemeinsam genutzte Version von MFC\) erstellt.  Die Funktionen werden in der Regel aus einer regulären DLL über die Standard\-C\-Schnittstelle exportiert.  
  
 Das `AFX_MANAGE_STATE`\-Makro muss vor allen exportierten Funktionen in reguläre DLLs eingefügt werden, die dynamisch mit MFC verknüpft sind, um den Zustand der DLL als aktuellen Modulzustand festzulegen.  Fügen Sie zu diesem Zweck die folgende Codezeile am Anfang der aus der DLL exportierten Funktionen ein:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 Eine reguläre, dynamisch mit MFC verknüpfte DLL hat die folgenden Features:  
  
-   Dies ist ein neuer DLL\-Typ, der mit Visual C\+\+ 4.0 eingeführt wurde.  
  
-   Die ausführbare Clientdatei kann in jeder Sprache geschrieben werden, die die Verwendung von DLLs unterstützt \(C, C\+\+, Pascal, Visual Basic usw.\); sie muss keine MFC\-Anwendung sein.  
  
-   Im Gegensatz zur statisch verknüpften regulären DLL wird dieser DLL\-Typ dynamisch mit der MFC\-DLL \(auch als gemeinsam genutzte MFC\-DLL bekannt\) verknüpft.  
  
-   Die MFC\-Importbibliothek, die mit diesem DLL\-Typ verknüpft wird, ist dieselbe, die auch für Erweiterungs\-DLLs oder Anwendungen genutzt wird, die die MFC\-DLL MFCxx\(D\).lib verwenden.  
  
 Eine reguläre, dynamisch mit MFC verknüpfte DLL stellt folgende Anforderungen:  
  
-   Dieser DLL\-Typ wird mit definiertem **\_AFXDLL** kompiliert, genau wie eine dynamisch mit der MFC\-DLL verknüpfte ausführbare Datei.  Außerdem wird auch **\_USRDLL** definiert, wie bei einer statisch mit MFC verknüpften regulären DLL.  
  
-   Dieser DLL\-Typ muss eine von `CWinApp` abgeleitete Klasse instanziieren.  
  
-   Die DLL verwendet die von MFC bereitgestellte `DllMain`\-Funktion.  Legen Sie den gesamten DLL\-spezifischen Initialisierungscode, wie bei einer normalen MFC\-Anwendung, in der Memberfunktion `InitInstance` sowie den Terminierungscode in `ExitInstance` ab.  
  
 Da dieser DLL\-Typ die Dynamic Link Library\-Version von MFC verwendet, müssen Sie den Zustand der DLL explizit als aktuellen Modulzustand festlegen.  Zu diesem Zweck verwenden Sie zu Beginn jeder aus der DLL exportierten Funktion das [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md)\-Makro.  
  
 Reguläre DLLs müssen über eine von `CWinApp` abgeleitete Klasse sowie über ein einzelnes Objekt dieser Anwendungsklasse verfügen, wie dies auch bei einer MFC\-Anwendung der Fall ist.  Das `CWinApp`\-Objekt der DLL hat jedoch keine Haupt\-Meldungsverteilschleife wie das **CWinApp**\-Objekt einer Anwendung.  
  
 Beachten Sie, dass der `CWinApp::Run`\-Mechanismus nicht auf eine DLL angewendet werden kann, da die Haupt\-Meldungsverteilschleife im Besitz der Anwendung ist.  Wenn die DLL nicht modale Dialogfelder öffnet oder ein eigenes Hauptrahmenfenster hat, muss die Haupt\-Meldungsverteilschleife der Anwendung eine aus der DLL exportierte Routine aufrufen, die `CWinApp::PreTranslateMessage` aufruft.  
  
 Legen Sie alle DLL\-spezifischen Initialisierungen, wie bei einer normalen MFC\-Anwendung, in der Memberfunktion `CWinApp::InitInstance` ab.  Die `CWinApp::ExitInstance`\-Memberfunktion der von `CWinApp` abgeleiteten Klasse wird durch die von MFC bereitgestellte `DllMain`\-Funktion aufgerufen, bevor die DLL entladen wird.  
  
 Die gemeinsam genutzten DLLs MFCx0.dll und Msvcr\*0.dll \(oder ähnliche Dateien\) müssen zusammen mit der Anwendung verteilt werden.  
  
 Eine dynamisch mit MFC verknüpfte DLL kann nicht zusätzlich statisch mit MFC verknüpft werden.  Reguläre, dynamisch mit MFC verknüpfte DLLs werden nach demselben Verfahren wie andere DLLs mit Anwendungen verknüpft.  
  
 Symbole werden in der Regel aus einer regulären DLL über die Standard\-C\-Schnittstelle exportiert.  Die Deklaration einer aus einer regulären DLL exportierten Funktion sieht ungefähr folgendermaßen aus:  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 Alle Speicherbelegungen innerhalb einer regulären DLL sollten in der DLL verbleiben. Folgende Elemente sollten weder an die aufrufende ausführbare Datei übergeben noch von dieser empfangen werden:  
  
-   Zeiger auf MFC\-Objekte.  
  
-   Zeiger auf Speicherbereiche, die von MFC belegt wurden.  
  
 Falls eine der oben genannten Aktionen erforderlich ist oder Sie von MFC abgeleitete Objekte zwischen der aufrufenden ausführbaren Datei und der DLL austauschen müssen, müssen Sie eine Erweiterungs\-DLL erstellen.  
  
 Zeiger auf Speicherbereiche, die von den C\-Laufzeitbibliotheken belegt wurden, lassen sich nur dann bedenkenlos zwischen einer Anwendung und einer DLL austauschen, wenn Sie von den Daten eine Kopie anlegen.  Sie dürfen diese Zeiger nicht löschen, neu dimensionieren oder verwenden, ohne eine Kopie des Speichers angefertigt zu haben.  
  
 Beim Erstellen einer regulären, dynamisch mit MFC verknüpften DLL müssen Sie das [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md)\-Makro ausführen, um zum richtigen MFC\-Modulstatus zu wechseln.  Fügen Sie zu diesem Zweck die folgende Codezeile am Anfang der aus der DLL exportierten Funktionen ein:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 Das `AFX_MANAGE_STATE`\-Makro sollte in regulären, statisch mit MFC verknüpften DLLs oder in Erweiterungs\-DLLs nicht verwendet werden.  Weitere Informationen finden Sie unter [Verwalten der Statusdaten von MFC\-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md).  
  
 Ein Beispiel dafür, wie eine reguläre DLL geschrieben, erstellt und verwendet wird, finden Sie unter [DLLScreenCap](assetId:///2171291d-3a50-403b-90a1-d93c2acb4f4a).  Weitere Informationen über reguläre DLLs, die dynamisch mit MFC verknüpft werden, finden Sie im Abschnitt "Konvertieren von DLLScreenCap, sodass eine dynamische Verknüpfung mit MFC DLL hergestellt wird" in der Kurzbeschreibung des Beispiels.  
  
## Was möchten Sie tun?  
  
-   [Reguläre DLLs initialisieren](../build/initializing-regular-dlls.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Modulzustände einer regulären, dynamisch mit MFC verknüpften DLL](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
  
-   [Verwalten der Statusdaten von MFC\-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [Verwenden von Datenbank\-, OLE\- und Sockets\-Erweiterungs\-DLLs in regulären DLLs](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
## Siehe auch  
 [Arten von DLLs](../build/kinds-of-dlls.md)