---
title: "Erweiterungs-DLLs: &#220;bersicht"
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
  - "AFXDLL-Bibliothek"
  - "DLLs [C++], Erweiterung"
  - "Erweiterungs-DLLs [C++], Informationen über Erweiterungs-DLLs"
  - "MFC-DLLs [C++], Erweiterungs-DLLs"
  - "Gemeinsam genutzte DLL-Versionen [C++]"
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Erweiterungs-DLLs: &#220;bersicht
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine MFC\-Erweiterungs\-DLL ist eine DLL, die in der Regel wiederverwendbare, von bestehenden Microsoft Foundation Class Library\-Klassen abgeleitete Klassen implementiert.  Erweiterungs\-DLLs werden über die Dynamic Link Library\-Version von MFC \(auch als gemeinsam genutzte MFC\-Version bekannt\) erstellt.  Eine Erweiterungs\-DLL kann ausschließlich von ausführbaren MFC\-Dateien \(entweder Anwendungen oder regulären DLLs\) verwendet werden, die mit der gemeinsam genutzten MFC\-Version erstellt wurden.  Mit einer Erweiterungs\-DLL können Sie neue benutzerdefinierte Klassen von MFC ableiten und diese erweiterte MFC\-Version anschließend Anwendungen zur Verfügung stellen, die die DLL aufrufen.  
  
 Erweiterungs\-DLLs können auch dazu verwendet werden, von MFC abgeleitete Objekte zwischen Anwendung und DLL zu übergeben.  Die dem übergebenen Objekt zugeordneten Memberfunktionen befinden sich in dem Modul, in dem das Objekt erstellt wurde.  Da diese Funktionen bei Verwendung der gemeinsam genutzten DLL\-Version von MFC ordnungsgemäß exportiert werden, können problemlos Zeiger auf MFC\-Objekte oder auf von MFC abgeleitete Objekte zwischen einer Anwendung und den von ihr geladenen Erweiterungs\-DLLs übergeben werden.  
  
 Ein Beispiel für eine DLL, die die Grundanforderungen an eine Erweiterungs\-DLL erfüllt, finden Sie im MFC\-Beispiel [DLLHUSK](assetId:///dfcaa6ff-b8e2-4efd-8100-ee3650071f90).  Achten Sie insbesondere auf die Dateien Testdll1.cpp und Testdll2.cpp.  
  
 Beachten Sie, dass der Begriff "AFXDLL" nicht mehr in der Visual C\+\+\-Dokumentation verwendet wird.  Eine Erweiterungs\-DLL hat dieselben Merkmale wie die frühere AFXDLL.  
  
## Was möchten Sie tun?  
  
-   [Erweiterungs\-DLLs initialisieren](../build/initializing-extension-dlls.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Erweiterungs\-DLLs](../build/extension-dlls.md)  
  
-   [Verwenden von Datenbank\-, OLE\- und Sockets\-Erweiterungs\-DLLs in regulären DLLs](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [MFC\-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC\-DLL\-Assistent](../mfc/reference/mfc-dll-wizard.md)  
  
## Siehe auch  
 [Arten von DLLs](../build/kinds-of-dlls.md)