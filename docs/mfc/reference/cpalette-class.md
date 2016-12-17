---
title: "CPalette Class"
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
  - "CPalette"
  - "HPALETTE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Farbpaletten, MFC"
  - "CPalette class"
  - "HPALETTE"
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CPalette Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt eine Windows\-Farbpalette.  
  
## Syntax  
  
```  
class CPalette : public CGdiObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPalette::CPalette](../Topic/CPalette::CPalette.md)|Erstellt ein Objekt `CPalette` ohne angefügte Windows\-Palette.  Sie müssen das `CPalette`\-Objekt mit einer der Initialisierungsmemberfunktionen initialisieren, bevor sie verwendet werden kann.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPalette::AnimatePalette](../Topic/CPalette::AnimatePalette.md)|Ersetzt Einträge in der Logischen Palette, die vom `CPalette`\-Objekt identifiziert wird.  Die Anwendung muss den Clientbereich nicht aktualisieren, da Windows die neue Einträge in die Systempalette sofort zuordnet.|  
|[CPalette::CreateHalftonePalette](../Topic/CPalette::CreateHalftonePalette.md)|Stellt eine Halbtonpalette für den Gerätekontext erstellt und fügt sie dem `CPalette`\-Objekt.|  
|[CPalette::CreatePalette](../Topic/CPalette::CreatePalette.md)|Stellt eine Windows\-Farbpalette erstellt und fügt sie dem `CPalette`\-Objekt.|  
|[CPalette::FromHandle](../Topic/CPalette::FromHandle.md)|Gibt einen Zeiger auf ein Objekt zurück `CPalette`, wenn Sie ein Handle für ein Windows\-Palettenobjekt angegeben werden.|  
|[CPalette::GetEntryCount](../Topic/CPalette::GetEntryCount.md)|Ruft die Anzahl der Paletteneinträgen in einer Logischen Palette ab.|  
|[CPalette::GetNearestPaletteIndex](../Topic/CPalette::GetNearestPaletteIndex.md)|Gibt den Index des Eintrags in der Palette Logischen zurück, die am nächsten einen Wert übereinstimmt.|  
|[CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)|Ruft einen Bereich von Paletteneinträgen in einer Logischen Palette ab.|  
|[CPalette::ResizePalette](../Topic/CPalette::ResizePalette.md)|Ändert die Größe der Logischen Palette, die vom `CPalette`\-Objekt der angegebenen Anzahl von Einträgen angegeben wird.|  
|[CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)|Legt RGB\-Farbwerte und \-Flags in einem Bereich von Einträgen in einer Logischen Palette fest.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPalette::operator HPALETTE](../Topic/CPalette::operator%20HPALETTE.md)|Gibt `HPALETTE` zurück, das in `CPalette` angefügt wird.|  
  
## Hinweise  
 Eine Palette stellt eine Schnittstelle zwischen einer Anwendung und einer Farbenausgabegerät \(wie einem Anzeigegerät\).  Die Schnittstelle ermöglicht der Anwendung, vollem Umfang den Farbenfunktionen des Ausgabegeräts zu ziehen, ohne die Farben erheblich zu beeinträchtigen, die von anderen Anwendungen angezeigt werden.  Windows verwendet die Logische Palette der Anwendung \(eine Liste der erforderlichen Farben\) und die Systempalette \(die verfügbaren Farben definiert\), um die verwendeten Farben zu bestimmen.  
  
 Ein Objekt `CPalette` enthält Memberfunktionen zum Bearbeiten der Palette bereit, die vom Objekt verwiesen wird.  Erstellen Sie ein `CPalette`\-Objekt und verwenden Sie die Memberfunktionen, um die tatsächliche Palette, ein Objekt des GDI \(Graphics Device Interface\) zu erstellen, und die Einträge und andere Eigenschaften zu bearbeiten.  
  
 Weitere Informationen zur Verwendung von `CPalette`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC Sampling DIBLOOK](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)   
 [CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)