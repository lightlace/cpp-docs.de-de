---
title: "CBrush Class"
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
  - "CBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Pinsel, CBrush class"
  - "CBrush class"
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CBrush Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt einen Pinsel des Windows GDI \(Graphics Device Interface\).  
  
## Syntax  
  
```  
class CBrush : public CGdiObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CBrush::CBrush](../Topic/CBrush::CBrush.md)|Erstellt ein `CBrush`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](../Topic/CBrush::CreateBrushIndirect.md)|Initialisiert ein Pinsel mit dem Format, der Farbe und dem Muster, das in einer [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)\-Struktur angegeben wird.|  
|[CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)|Initialisiert ein Pinsel mit einem Muster, das von einer Bitmap geräteunabhängige \(DIBs\) angegeben wird.|  
|[CBrush::CreateHatchBrush](../Topic/CBrush::CreateHatchBrush.md)|Initialisiert ein Pinsel mit der angegebenen Schraffur und Farbe.|  
|[CBrush::CreatePatternBrush](../Topic/CBrush::CreatePatternBrush.md)|Initialisiert ein Pinsel mit einem Muster, das von einer Bitmap angegeben wird.|  
|[CBrush::CreateSolidBrush](../Topic/CBrush::CreateSolidBrush.md)|Initialisiert ein Pinsel mit der angegebenen Volltonfarbe.|  
|[CBrush::CreateSysColorBrush](../Topic/CBrush::CreateSysColorBrush.md)|Stellt einen Pinsel erstellt, der die Standardsystemfarbe ist.|  
|[CBrush::FromHandle](../Topic/CBrush::FromHandle.md)|Gibt einen Zeiger auf ein Objekt zurück `CBrush`, wenn Sie ein Handle für ein Objekt Windows `HBRUSH` angegeben werden.|  
|[CBrush::GetLogBrush](../Topic/CBrush::GetLogBrush.md)|Ruft eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)\-Struktur ab.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CBrush::operator HBRUSH](../Topic/CBrush::operator%20HBRUSH.md)|Gibt das Windows\-Handles zurück, das dem Objekt `CBrush` angefügt wird.|  
  
## Hinweise  
 Um ein `CBrush`\-Objekt zu verwenden, erstellen Sie ein `CBrush`\-Objekt und führen Sie es zu jeder `CDC`\-Memberfunktion die einen Pinsel erfordert.  
  
 Pinsel können der Vollton\- sein, schraffiert, oder kopiert.  
  
 Weitere Informationen zu `CBrush`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [Bei MFC Sampling](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBitmap Class](../../mfc/reference/cbitmap-class.md)   
 [CDC\-Klasse](../../mfc/reference/cdc-class.md)