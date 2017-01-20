---
title: "Zugreifen auf die Typbibliothek"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Typbibliotheken, Aufrufen"
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
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