---
title: "Initialisieren regul&#228;rer DLLs"
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
  - "Initialisieren von DLLs"
  - "Reguläre DLLs [C++], Initialisieren"
ms.assetid: f1f091d1-bb91-468a-94f4-3c554657b8fc
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Initialisieren regul&#228;rer DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Da reguläre DLLs über ein `CWinApp`\-Objekt verfügen, sollten sie ihre Initialisierungs\- und Terminierungsaufgaben an derselben Stelle ausführen wie eine MFC\-Anwendung: in den Memberfunktionen `InitInstance` und **ExitInstance** der von `CWinApp` abgeleiteten Klasse der DLL.  MFC umfasst eine `DllMain`\-Funktion, die von **\_DllMainCRTStartup** für **PROCESS\_ATTACH** und **PROCESS\_DETACH** aufgerufen wird. Folglich sollten Sie keine eigene `DllMain`\-Funktion schreiben.  Die von MFC bereitgestellte `DllMain`\-Funktion ruft `InitInstance` beim Laden der DLL und `ExitInstance` vor dem Entladen der DLL auf.  
  
 Eine reguläre DLL kann mehrere Threads verfolgen, indem sie in ihrer `InitInstance`\-Funktion die Funktionen [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) und [TlsGetValue](http://msdn.microsoft.com/library/windows/desktop/ms686812) aufruft.  Mit diesen Funktionen kann die DLL threadspezifische Daten verfolgen.  
  
 Wenn Sie die MFC\-Unterstützung für OLE, Datenbanken \(bzw. DAO\) oder Sockets in einer regulären, dynamisch mit MFC verknüpften DLL verwenden, dann werden die MFC\-Debugbuilds der Erweiterungs\-DLLs MFCOxxD.dll, MFCDxxD.dll und MFCNxxD.dll automatisch eingebunden \(wobei xx für die Versionsnummer steht\).  Sie müssen eine der folgenden vordefinierten Initialisierungsfunktionen für jede dieser DLLs aufrufen, die Sie in `CWinApp::InitInstance` der regulären DLL verwenden.  
  
|Art der MFC\-Unterstützung|Aufzurufende Initialisierungsfunktion|  
|--------------------------------|-------------------------------------------|  
|MFC\-OLE \(MFCOxxD.dll\)|`AfxOleInitModule`|  
|MFC\-Datenbank \(MFCDxxD.dll\)|`AfxDbInitModule`|  
|MFC\-Sockets \(MFCNxxD.dll\)|`AfxNetInitModule`|  
  
## Was möchten Sie tun?  
  
-   [Erweiterungs\-DLLs initialisieren](../build/initializing-extension-dlls.md)  
  
-   [MFC\-fremde DLLs initialisieren](../build/initializing-non-mfc-dlls.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Das Verhalten der C\-Laufzeitbibliothek und \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [Verwenden von Datenbank\-, OLE\- und Sockets\-Erweiterungs\-DLLs in regulären DLLs](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [\<caps:sentence id\="tgt22" sentenceid\="704731be78a1b2b43311fed62656e454" class\="tgtSentence"\>Prozesse und Threads \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
-   [Thread local storage wrappers \(MFC Technical Note 58, nur auf Englisch verfügbar\)](../mfc/tn058-mfc-module-state-implementation.md)  
  
## Siehe auch  
 [Initialisieren einer DLL](../build/initializing-a-dll.md)