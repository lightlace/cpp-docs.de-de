---
title: "Active Technology und DLLs | Microsoft Docs"
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
  - "Active Technology [C++]"
  - "Automatisierung [C++], DLLs"
  - "DLLs [C++], Active Technology"
  - "Prozessinterne Server-DLLs"
  - "MFC-DLLs [C++], Active Technology"
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Active Technology und DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active Technology bietet die Möglichkeit, Objektserver vollständig innerhalb einer DLL zu implementieren.  Dieser Servertyp wird "prozessinterner Server" genannt.  MFC unterstützt bei prozessinternen Servern nicht alle Features der visuellen Bearbeitung. Dies liegt hauptsächlich daran, dass Active Technology keine Möglichkeit bietet, einen Server mit der Hauptmeldungsschleife des Containers zu verknüpfen.  MFC benötigt Zugriff auf die Meldungsschleife der Containeranwendung, um Zugriffstasten und Leerlaufsituationen verarbeiten zu können.  
  
 Wenn Sie einen Automatisierungsserver programmieren und der Server keine Benutzeroberfläche aufweist, können Sie den Server als prozessinternen Server konfigurieren und ihn vollständig in eine DLL integrieren.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Automatisierungsserver](../mfc/automation-servers.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)