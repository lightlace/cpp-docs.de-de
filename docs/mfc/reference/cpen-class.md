---
title: "CPen Class"
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
  - "HPEN"
  - "CPen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPen class"
  - "HPEN"
  - "Stifte, MFC"
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: 20
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CPen Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt einen Stift des Windows GDI \(Graphics Device Interface\).  
  
## Syntax  
  
```  
class CPen : public CGdiObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPen::CPen](../Topic/CPen::CPen.md)|Erstellt ein `CPen`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPen::CreatePen](../Topic/CPen::CreatePen.md)|Stellt eine logische Kosmetik oder eines geometrischen Stift mit dem angegebenen Format, Breite und den Pinselattributen erstellt und fügt ihn dem `CPen`\-Objekt.|  
|[CPen::CreatePenIndirect](../Topic/CPen::CreatePenIndirect.md)|Stellt einen Stift mit dem Format, Breite und Farbe, die in einer [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)\-Struktur angegeben wird, und fügt ihn dem `CPen`\-Objekt.|  
|[CPen::FromHandle](../Topic/CPen::FromHandle.md)|Gibt einen Zeiger auf ein Objekt zurück `CPen`, wenn Sie Windows `HPEN` angegeben werden.|  
|[CPen::GetExtLogPen](../Topic/CPen::GetExtLogPen.md)|Ruft eine zugrunde liegende Struktur [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) ab.|  
|[CPen::GetLogPen](../Topic/CPen::GetLogPen.md)|Ruft eine zugrunde liegende Struktur [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) ab.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPen::operator HPEN](../Topic/CPen::operator%20HPEN.md)|Gibt das Windows\-Handles zurück, das dem Objekt `CPen` angefügt wird.|  
  
## Hinweise  
 Weitere Informationen zur Verwendung von `CPen`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBrush Class](../../mfc/reference/cbrush-class.md)