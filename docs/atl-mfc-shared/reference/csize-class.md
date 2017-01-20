---
title: "CSize Class"
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
  - "CSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSize class"
  - "Dimensionen"
  - "Dimensionen, MFC"
  - "SIZE"
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CSize Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ähnlich der Struktur Windows [GRÖSSE](http://msdn.microsoft.com/library/windows/desktop/dd145106), die eine relative Koordinate oder Position implementiert.  
  
## Syntax  
  
```  
class CSize : public tagSIZE  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CSize::CSize](../Topic/CSize::CSize.md)|Erstellt ein `CSize`\-Objekt.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CSize::operator \-](../Topic/CSize::operator%20-.md)|Subtrahiert zwei Größen.|  
|[CSize::operator \!\=](../Topic/CSize::operator%20!=.md)|Überprüfungen für Ungleichheit zwischen `CSize` und einer Größe.|  
|[CSize::operator \+](../Topic/CSize::operator%20+.md)|Addiert zwei Größen hinzu.|  
|[CSize::operator \+\=](../Topic/CSize::operator%20+=.md)|Fügt eine Größe `CSize` hinzu.|  
|[CSize::operator \-\=](../Topic/CSize::operator%20-=.md)|Subtrahiert eine Größe von `CSize`.|  
|[CSize::operator \=\=](../Topic/CSize::operator%20==.md)|Überprüft die Gleichheit zwischen `CSize` und einer Größe.|  
  
## Hinweise  
 Diese Klasse wird von **SIZE**\-Struktur abgeleitet.  Dies bedeutet, dass Sie `CSize` in einem Parameter übergeben können, der für **SIZE** aufruft und den die Datenmember der **SIZE**\-Struktur zugreifbare Datenmember von `CSize` sind.  
  
 Die **cx** und **cy**\-Member von **SIZE** \(und von `CSize`\) sind öffentlich.  Außerdem implementiert `CSize`\-Memberfunktionen, um die **SIZE**\-Struktur zu bearbeiten.  
  
> [!NOTE]
>  Weitere Informationen zu freigegebenen Hilfsklassen \(z `CSize`\), finden Sie unter [Freigegebene Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## Vererbungshierarchie  
 `tagSIZE`  
  
 `CSize`  
  
## Anforderungen  
 **Header:** atltypes.h  
  
## Siehe auch  
 [MFC\-Beispiel\-MDI](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint Class](../../atl-mfc-shared/reference/cpoint-class.md)