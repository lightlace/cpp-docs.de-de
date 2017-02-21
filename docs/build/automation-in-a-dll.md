---
title: "Automatisierung in einer DLL | Microsoft Docs"
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
  - "Automatisierung [C++], DLLs"
  - "DLLs [C++], Automatisierung"
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Automatisierung in einer DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie im MFC\-DLL\-Assistenten die Automatisierungsoption auswählen, stellt der Assistent folgende Objekte bereit:  
  
-   Eine ODL\-Startdatei \(Object Description Language\)  
  
-   Eine include\-Direktive für Afxole.h in der Datei STDAFX.h  
  
-   Eine Implementierung der `DllGetClassObject`\-Funktion, durch die die **AfxDllGetClassObject**\-Funktion aufgerufen wird  
  
-   Eine Implementierung der `DllCanUnloadNow`\-Funktion, durch die die **AfxDllCanUnloadNow**\-Funktion aufgerufen wird  
  
-   Eine Implementierung der `DllRegisterServer`\-Funktion, durch die die [COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md)\-Funktion aufgerufen wird  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Automatisierungsserver](../mfc/automation-servers.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)