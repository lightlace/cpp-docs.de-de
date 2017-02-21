---
title: "Zugreifen auf die Typbibliothek | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Typbibliotheken, Aufrufen"
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Zugreifen auf die Typbibliothek
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typbibliotheken stellen den Schnittstellen eines OLE\-Steuerelements anderen OLE\-bewussten Anwendungen aus.  Jedes OLE\-Steuerelement muss eine Typbibliothek haben, wenn eine oder mehrere Schnittstellen verfügbar gemacht werden sollen.  
  
 Die folgenden Makros ermöglichen einem OLE\-Steuerelement, um Zugriff an seine eigene Typbibliothek zu ermöglichen:  
  
### Typbibliotheks\-Zugriff  
  
|||  
|-|-|  
|[DECLARE\_OLETYPELIB](../Topic/DECLARE_OLETYPELIB.md)|Deklariert eine `GetTypeLib`\-Memberfunktion eines OLE\-Steuerelements \(muss in der Klassendeklaration verwendet werden\).|  
|[IMPLEMENT\_OLETYPELIB](../Topic/IMPLEMENT_OLETYPELIB.md)|Implementiert eine `GetTypeLib`\-Memberfunktion eines OLE\-Steuerelements \(muss in die Klassenimplementierung verwendet werden\).|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)