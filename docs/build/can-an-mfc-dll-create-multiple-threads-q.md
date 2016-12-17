---
title: "Kann eine MFC-DLL mehrere Threads erstellen?"
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
  - "DLLs [C++], Multithreading"
  - "MFC-DLLs [C++], Multithreading"
  - "Multithreading [C++], DLLs"
  - "Threading [MFC], DLLs"
ms.assetid: 41d5b5e6-a7d3-42bf-b641-f1245abd1c59
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Kann eine MFC-DLL mehrere Threads erstellen?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Außer während der Initialisierung können problemlos mehrere Threads von einer MFC\-DLL erstellt werden, solange die DLL die Win32\-Funktionen für lokalen Threadspeicher \(Thread Local Storage, TLS\), z. B. **TlsAlloc**, zur Reservierung von lokalem Threadspeicher verwendet.  Wenn eine MFC\-DLL jedoch **\_\_declspec\(thread\)** verwendet, um lokalen Threadspeicher zu reservieren, muss die Clientanwendung implizit mit der DLL verknüpft werden.  Im Fall einer expliziten Verknüpfung wird die DLL durch den Aufruf von **LoadLibrary** nicht erfolgreich geladen.  Weitere Informationen über das Erstellen mehrerer Threads innerhalb von MFC\-DLLs finden Sie im Knowledge Base\-Artikel "PRB: Calling LoadLibrary\(\) to Load a DLL That Has Static TLS" \(Q118816, nur auf Englisch verfügbar\).  
  
 Eine MFC\-DLL, die während des Starts einen neuen MFC\-Thread erstellt, antwortet nicht mehr, wenn sie von einer Anwendung geladen wird.  Dies tritt ein, sobald ein Thread durch Aufrufen von `AfxBeginThread` oder `CWinThread::CreateThread` in einer der folgenden Funktionen erstellt wird:  
  
-   Einer `InitInstance` eines von `CWinApp` abgeleiteten Objekts in einer regulären DLL.  
  
-   Einer bereitgestellten `DllMain`\-Funktion oder **RawDllMain**\-Funktion in einer regulären DLL.  
  
-   Einer bereitgestellten `DllMain`\-Funktion oder **RawDllMain**\-Funktion in einer Erweiterungs\-DLL.  
  
 Weitere Informationen über das Erstellen von Threads während der Initialisierung finden Sie im Knowledge Base\-Artikel "PRB: Cannot Create an MFC Thread During DLL Startup" \(Q142243, nur auf Englisch verfügbar\).  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zu DLLs](../build/dll-frequently-asked-questions.md)