---
title: "CGdiObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGdiObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Pinsel, base class for"
  - "CGdiObject class"
  - "Schriftarten, base class for"
  - "GDI-Objekte, base class for"
  - "Paletten, base class for"
  - "Stifte, base class for"
  - "Bereiche, base class for"
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CGdiObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Basisklasse für verschiedene Arten von Objekten des Windows GDI \(Graphics Device Interface\) wie Bitmaps, Bereichen, Pinsel, Stiften, Paletten und Schriftarten bereit.  
  
## Syntax  
  
```  
class CGdiObject : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CGdiObject::CGdiObject](../Topic/CGdiObject::CGdiObject.md)|Erstellt ein `CGdiObject`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CGdiObject::Attach](../Topic/CGdiObject::Attach.md)|Fügt ein Windows GDI\-Objekt zu einem `CGdiObject`\-Objekt.|  
|[CGdiObject::CreateStockObject](../Topic/CGdiObject::CreateStockObject.md)|Ruft ein Handle auf eine der Windows vordefinierten vordefinierten Stifte, der Pinsel oder der Schriftart ab.|  
|[CGdiObject::DeleteObject](../Topic/CGdiObject::DeleteObject.md)|Löscht das Windows GDI\-Objekt, das dem `CGdiObject`\-Objekt aus dem Speicher mit Freigeben alle Systemspeichers angefügt wird, der dem Objekt zugeordnet ist.|  
|[CGdiObject::DeleteTempMap](../Topic/CGdiObject::DeleteTempMap.md)|Löscht alle temporären `CGdiObject`\-Objekte, die von `FromHandle` erstellt werden.|  
|[CGdiObject::Detach](../Topic/CGdiObject::Detach.md)|Trennt ein Windows GDI\-Objekt von einem `CGdiObject`\-Objekt und gibt ein Handle für Windows GDI\-Objekt zurück.|  
|[CGdiObject::FromHandle](../Topic/CGdiObject::FromHandle.md)|Gibt einen Zeiger auf einen `CGdiObject`\-Objekt zurück, das ein Handle für ein Windows GDI\-Objekt angegeben ist.|  
|[CGdiObject::GetObject](../Topic/CGdiObject::GetObject.md)|Füllt einen Puffer mit Daten, die das Windows GDI\-Objekt beschreibt, das dem `CGdiObject`\-Objekt angefügt wird.|  
|[CGdiObject::GetObjectType](../Topic/CGdiObject::GetObjectType.md)|Ruft den Typ des GDI\-Objekts ab.|  
|[CGdiObject::GetSafeHandle](../Topic/CGdiObject::GetSafeHandle.md)|Gibt `m_hObject` zurück, es sei denn, `this``NULL` ist, in diesem Fall `NULL` zurückgegeben wird.|  
|[CGdiObject::UnrealizeObject](../Topic/CGdiObject::UnrealizeObject.md)|Setzt den Ursprung eines Pinsels zurück oder legt eine Logische Palette zurück.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CGdiObject::operator \!\=](../Topic/CGdiObject::operator%20!=.md)|Bestimmt, ob zwei GDI\-Objekte logisch nicht gleich sind.|  
|[CGdiObject::operator \=\=](../Topic/CGdiObject::operator%20==.md)|Bestimmt, ob zwei GDI\-Objekte logisch gleich sind.|  
|[CGdiObject::operator HGDIOBJ](../Topic/CGdiObject::operator%20HGDIOBJ.md)|Ruft `HANDLE` das verknüpfte Windows GDI\-Objekt ab.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CGdiObject::m\_hObject](../Topic/CGdiObject::m_hObject.md)|`HANDLE`, das `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN` oder `HFONT` angefügt auf dieses Objekt enthält.|  
  
## Hinweise  
 Sie erstellen `CGdiObject` nie direkt.  Stattdessen erstellen Sie ein Objekt von einer ihrer abgeleiteten Klassen, wie `CPen` oder `CBrush`.  
  
 Weitere Informationen zu `CGdiObject`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBitmap Class](../../mfc/reference/cbitmap-class.md)   
 [CBrush Class](../../mfc/reference/cbrush-class.md)   
 [CFont Class](../../mfc/reference/cfont-class.md)   
 [CPalette Class](../../mfc/reference/cpalette-class.md)   
 [CPen Class](../../mfc/reference/cpen-class.md)   
 [CRgn\-Klasse](../../mfc/reference/crgn-class.md)