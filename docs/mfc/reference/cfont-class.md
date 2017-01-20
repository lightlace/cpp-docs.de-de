---
title: "CFont Class"
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
  - "CFont"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFont class"
  - "Schriftarten, MFC-Klassen"
  - "GDI, font classes"
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CFont Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt eine Schriftart des Windows GDI \(Graphics Device Interface\) und bietet Memberfunktionen zum Bearbeiten der Schriftarten bereit.  
  
## Syntax  
  
```  
class CFont : public CGdiObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFont::CFont](../Topic/CFont::CFont.md)|Erstellt ein `CFont`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFont::CreateFont](../Topic/CFont::CreateFont.md)|Initialisiert `CFont` mit den angegebenen Eigenschaften.|  
|[CFont::CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md)|Initialisiert `CFont` ein Objekt mit den Eigenschaften, die in einer `LOGFONT`\-Struktur angegeben werden.|  
|[CFont::CreatePointFont](../Topic/CFont::CreatePointFont.md)|Initialisiert `CFont` mit der angegebenen Höhe, gemessen in den Zehnteln eines Punkts und Schriftart.|  
|[CFont::CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md)|Wie das `CreateFontIndirect` nur die Schriftarthöhe wird in den Zehnteln eines Punkts anstatt logische Einheiten gemessen.|  
|[CFont::FromHandle](../Topic/CFont::FromHandle.md)|Gibt einen Zeiger auf ein Objekt zurück `CFont`, wenn Sie Windows **HFONT** angegeben werden.|  
|[CFont::GetLogFont](../Topic/CFont::GetLogFont.md)|Füllt `LOGFONT` mit Informationen über die logische Schriftart aus, die dem `CFont`\-Objekt angefügt wird.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFont::operator HFONT](../Topic/CFont::operator%20HFONT.md)|Gibt das Windows GDI\-Schriftarthandle zurück, das dem Objekt `CFont` angefügt wird.|  
  
## Hinweise  
 So fügen Sie ein Objekt `CFont` verwenden, ein `CFont`\-Objekt und eine Windows\-Schriftart anfügen mit [CreateFont](../Topic/CFont::CreateFont.md), [CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md), [CreatePointFont](../Topic/CFont::CreatePointFont.md) oder [CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md) erstellen, und die Memberfunktionen des Objekts dann verwenden, um die Schriftart zu bearbeiten.  
  
 Die `CreatePointFont` und `CreatePointFontIndirect`\-Funktionen sind häufig einfacher als `CreateFont` oder `CreateFontIndirect` zu verwenden, da diese die Konvertierung für die Höhe der Schriftart aus einem Schriftgrad zu logischen Einheiten automatisch erstellen.  
  
 Weitere Informationen zu `CFont`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel HIERSVR](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)