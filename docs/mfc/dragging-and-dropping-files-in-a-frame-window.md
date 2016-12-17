---
title: "Ziehen und Fallenlassen von Dateien in einem Rahmenfenster"
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
  - "Drag & Drop [C++], Datei-Manager"
  - "Drag & Drop [C++], Dateien"
  - "Drag & Drop [C++], Windows Explorer"
  - "Drag & Drop-Unterstützung (Datei-Manager)"
  - "Dateien [C++], Drag & Drop"
  - "Rahmenfenster [C++], Ziehen und Ablegen von Dateien in"
  - "Windows Explorer [C++]"
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Ziehen und Fallenlassen von Dateien in einem Rahmenfenster
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Rahmenfenster verwaltet eine Beziehung mit Datei\-Explorer oder Datei\-Manager.  
  
 Mit einigen initialisierenden Aufrufen in der Überschreibung der `CWinApp`\-Memberfunktion `InitInstance` hinzufügen, wie in [CWinApp: Die Application\-Klasse](../mfc/cwinapp-the-application-class.md) beschrieben, können Sie die Dateien öffnen gezogener von Datei\-Explorer oder Datei\-Manager indirekt haben des Rahmenfensters und abgelegt im Rahmenfenster.  Siehe [Datei\-Manager\-Drag & Drop](../mfc/special-cwinapp-services.md).  
  
## Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)