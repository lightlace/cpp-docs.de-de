---
title: "_U_RECT Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::_U_RECT"
  - "_U_RECT"
  - "ATL._U_RECT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_RECT class"
  - "U_RECT class"
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# _U_RECT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Argumentadapterklasse können entweder an eine Funktion übergeben werden `RECT` Zeiger oder Verweise, die im Hinblick auf Zeiger implementiert wird.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class _U_RECT  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[\_U\_RECT::\_U\_RECT](../Topic/_U_RECT::_U_RECT.md)|Der \-Konstruktor.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[\_U\_RECT::m\_lpRect](../Topic/_U_RECT::m_lpRect.md)|Zeiger auf `RECT`.|  
  
## Hinweise  
 Die Klasse definiert zwei Konstruktorüberladungen: Sie akzeptiert ein **RECT&**\-Argument und der andere akzeptiert ein `LPRECT`\-Argument.  Der erste Konstruktor speichert die Adresse des Bezugsarguments im Einzelnen Datenmember der Klasse, [m\_lpRect](../Topic/_U_RECT::m_lpRect.md).  Das Argument in Zeigerkonstruktor wird direkt ohne Konvertierung gespeichert.  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)