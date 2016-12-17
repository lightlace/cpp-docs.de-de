---
title: "Regul&#228;re, statisch mit MFC verkn&#252;pfte DLLs"
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
helpviewer_keywords: 
  - "DLLs [C++], Reguläre"
  - "Reguläre DLLs [C++]"
  - "Reguläre DLLs [C++], Statisch gebunden mit MFC"
  - "Statisch gebunden mit DLLs [C++]"
  - "USRDLLs"
  - "USRDLLs, Statisch gebunden mit MFC"
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Regul&#228;re, statisch mit MFC verkn&#252;pfte DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine reguläre DLL, die statisch mit MFC verknüpft ist, ist eine DLL, die MFC intern verwendet. Die exportierten Funktionen in der DLL können sowohl von ausführbaren MFC\- als auch von ausführbaren MFC\-fremden Dateien aufgerufen werden.  Wie der Name bereits vermuten lässt, wird dieser DLL\-Typ mithilfe der Static Link Library\-Version von MFC erstellt.  Die Funktionen werden in der Regel aus einer regulären DLL über die Standard\-C\-Schnittstelle exportiert.  Ein Beispiel dafür, wie eine reguläre DLL geschrieben, erstellt und verwendet wird, finden Sie unter [DLLScreenCap](assetId:///2171291d-3a50-403b-90a1-d93c2acb4f4a).  
  
 Beachten Sie, dass der Begriff "USRDLL" in der Visual C\+\+\-Dokumentation nicht mehr verwendet wird.  Eine reguläre DLL, die statisch mit MFC verknüpft ist, hat dieselben Merkmale wie die frühere USRDLL.  
  
 Eine statisch mit MFC verknüpfte reguläre DLL hat die folgenden Merkmale:  
  
-   Die ausführbare Clientdatei kann in jeder Sprache geschrieben werden, die die Verwendung von DLLs unterstützt \(C, C\+\+, Pascal, Visual Basic usw.\); sie muss keine MFC\-Anwendung sein.  
  
-   Die DLL kann mit denselben MFC\-Static Link Libraries verknüpft werden, die auch von Anwendungen verwendet werden.  Eine separate Version von Static Link Libraries für DLLs ist nicht mehr verfügbar.  
  
-   Vor Version 4.0 von MFC hatten USRDLLs dieselbe Art von Funktionalität wie reguläre, statisch mit MFC verknüpfte DLLs.  Seit Version 4.0 von Visual C\+\+ ist der Ausdruck USRDLL überholt.  
  
 Für eine statisch mit MFC verknüpfte reguläre DLL bestehen folgende Anforderungen:  
  
-   Dieser DLL\-Typ muss eine von `CWinApp` abgeleitete Klasse instanziieren.  
  
-   Die DLL verwendet die von MFC bereitgestellte `DllMain`\-Funktion.  Legen Sie den gesamten DLL\-spezifischen Initialisierungscode, wie bei einer normalen MFC\-Anwendung, in der Memberfunktion `InitInstance` sowie den Terminierungscode in `ExitInstance` ab.  
  
-   Auch wenn der Ausdruck USRDLL veraltet ist, müssen Sie in der Compilerbefehlszeile "**\_USRDLL**" definieren.  Dadurch wird festgelegt, welche Deklarationen aus den MFC\-Headerdateien übernommen werden.  
  
 Reguläre DLLs müssen über eine von `CWinApp` abgeleitete Klasse sowie über ein einzelnes Objekt dieser Anwendungsklasse verfügen, wie dies auch bei einer MFC\-Anwendung der Fall ist.  Das `CWinApp`\-Objekt der DLL hat jedoch keine Haupt\-Meldungsverteilschleife wie das **CWinApp**\-Objekt einer Anwendung.  
  
 Beachten Sie, dass der `CWinApp::Run`\-Mechanismus nicht auf eine DLL angewendet werden kann, da die Haupt\-Meldungsverteilschleife im Besitz der Anwendung ist.  Wenn die DLL keine modalen Dialogfelder öffnet oder ein eigenes Hauptrahmenfenster hat, muss die Haupt\-Meldungsverteilschleife der Anwendung eine von der DLL exportierte Routine aufrufen, die wiederum die `CWinApp::PreTranslateMessage`\-Memberfunktion des DLL\-Anwendungsobjekts aufruft.  
  
 Ein Beispiel für diese Funktion finden Sie unter dem Beispiel "DLLScreenCap".  
  
 Symbole werden in der Regel aus einer regulären DLL über die Standard\-C\-Schnittstelle exportiert.  Die Deklaration einer aus einer regulären DLL exportierten Funktion würde etwa so aussehen:  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 Alle Speicherbelegungen innerhalb einer regulären DLL sollten in der DLL verbleiben. Folgende Elemente sollten weder an die aufrufende ausführbare Datei übergeben noch von dieser empfangen werden:  
  
-   Zeiger auf MFC\-Objekte  
  
-   Zeiger auf von MFC belegten Speicher  
  
 Falls eine der oben genannten Aktionen oder eine Übergabe der von MFC abgeleiteten Objekte zwischen der aufrufenden ausführbaren Datei und der DLL erforderlich ist, müssen Sie eine Erweiterungs\-DLL erstellen.  
  
 Zeiger auf Speicherbereiche, die von den C\-Laufzeitbibliotheken belegt wurden, lassen sich nur dann bedenkenlos zwischen einer Anwendung und einer DLL austauschen, wenn Sie von den Daten eine Kopie anlegen.  Sie dürfen diese Zeiger nicht löschen, neu dimensionieren oder verwenden, ohne eine Kopie des Speichers angefertigt zu haben.  
  
 Eine statisch mit MFC verknüpfte DLL kann nicht zusätzlich mit den gemeinsam genutzten MFC\-DLLs dynamisch verknüpft werden.  Eine statisch mit MFC verknüpfte DLL wird, wie jede andere DLL, dynamisch an eine Anwendung gebunden. Dieser DLL\-Typ wird nach demselben Verfahren wie alle anderen DLLs mit Anwendungen verknüpft.  
  
 Die standardmäßigen MFC\-Static Link Libraries werden gemäß den unter [Namenskonventionen für MFC\-DLLs](../build/naming-conventions-for-mfc-dlls.md) beschriebenen Konventionen benannt.  Ab MFC, Version 3.0, müssen Sie die Version der MFC\-Bibliothek, die eingebunden werden soll, nicht mehr manuell für den Linker angeben.  Die korrekte Version der MFC\-Bibliothek, die auf der Grundlage von Präprozessordefinitionen, wie **\_DEBUG** oder **\_UNICODE**, eingebunden werden soll, wird automatisch durch die MFC\-Headerdateien ermittelt.  Die MFC\-Headerdateien fügen **\/DEFAULTLIB**\-Direktiven hinzu, wodurch der Linker angewiesen wird, eine spezifische Version der MFC\-Bibliothek einzubinden.  
  
## Was möchten Sie tun?  
  
-   [Reguläre DLLs initialisieren](../build/initializing-regular-dlls.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [Verwenden von Datenbank\-, OLE\- und Sockets\-Erweiterungs\-DLLs in regulären DLLs](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [MFC\-DLL\-Assistent](../mfc/reference/mfc-dll-wizard.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Erweiterungs\-DLLs](../build/extension-dlls-overview.md)  
  
## Siehe auch  
 [Arten von DLLs](../build/kinds-of-dlls.md)