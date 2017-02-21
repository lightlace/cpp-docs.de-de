---
title: "Dynamische Objekterstellung | Microsoft Docs"
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
  - "CObject-Klasse, dynamische Objekterstellung"
  - "dynamische Objekterstellung"
  - "Objekterstellung, dynamisch zur Laufzeit"
  - "Objekte [C++], dynamisches Erstellen zur Laufzeit"
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Dynamische Objekterstellung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird beschrieben, wie ein Objekt zur Laufzeit dynamisch erstellt.  Die Prozedur verwendet Ablaufklasseninformationen, wie im Artikel [Zugreifen auf Ablaufklasseninformationen](../mfc/accessing-run-time-class-information.md) erläutert.  
  
#### Um ein Objekt dynamisch erstellen die Laufzeitklasse angegeben  
  
1.  Verwenden Sie den folgenden Code, um ein Objekt dynamisch erstellen, indem Sie die `CreateObject`\-Funktion `CRuntimeClass` verwenden.  Beachten Sie die auf Fehler, `CreateObject` gibt **NULL**, anstatt eine Ausnahme auszulösen:  
  
     [!CODE [NVC_MFCCObjectSample#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCObjectSample#6)]  
  
## Siehe auch  
 [Verwenden von CObject](../mfc/using-cobject.md)