---
title: "CProgressCtrl Class"
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
  - "CProgressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProgressCtrl class"
  - "Internet Explorer 4.0 common controls"
  - "progress controls [C++], CProgressCtrl class"
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
caps.latest.revision: 25
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CProgressCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des Windows\-Common\-Statusanzeige\-Steuerelements bereit.  
  
## Syntax  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CProgressCtrl::CProgressCtrl](../Topic/CProgressCtrl::CProgressCtrl.md)|Erstellt ein `CProgressCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CProgressCtrl::Create](../Topic/CProgressCtrl::Create.md)|Erstellt ein und fügt es Statusanzeige\-Steuerelement zu einem `CProgressCtrl`\-Objekt.|  
|[CProgressCtrl::CreateEx](../Topic/CProgressCtrl::CreateEx.md)|Erstellt ein Statussteuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CProgressCtrl`\-Objekt.|  
|[CProgressCtrl::GetBarColor](../Topic/CProgressCtrl::GetBarColor.md)|Ruft die Farbe der Statusanzeigeleiste für das aktuelle Statusanzeige\-Steuerelement ab.|  
|[CProgressCtrl::GetBkColor](../Topic/CProgressCtrl::GetBkColor.md)|Ruft die Hintergrundfarbe der aktuellen Statusanzeige ab.|  
|[CProgressCtrl::GetPos](../Topic/CProgressCtrl::GetPos.md)|Ruft die aktuelle Position der Statusanzeige ab.|  
|[CProgressCtrl::GetRange](../Topic/CProgressCtrl::GetRange.md)|Ruft das niedrigere und die Untergrenze des Bereichs des Statusanzeige\-Steuerelements ab.|  
|[CProgressCtrl::GetState](../Topic/CProgressCtrl::GetState.md)|Ruft den Zustand des aktuellen Statusanzeige\-Steuerelements ab.|  
|[CProgressCtrl::GetStep](../Topic/CProgressCtrl::GetStep.md)|Ruft die Schrittweite für die Statusanzeige des aktuellen Statusanzeige\-Steuerelements ab.|  
|[CProgressCtrl::OffsetPos](../Topic/CProgressCtrl::OffsetPos.md)|Setzt die aktuelle Position eines Statusanzeige\-Steuerelements vom angegebenen Inkrement und zeichnet die Leiste neu, um die neue Lage widerzuspiegeln.|  
|[CProgressCtrl::SetBarColor](../Topic/CProgressCtrl::SetBarColor.md)|Legt die Farbe der Statusanzeigeleiste im aktuellen Statusanzeige\-Steuerelement fest.|  
|[CProgressCtrl::SetBkColor](../Topic/CProgressCtrl::SetBkColor.md)|Legt die Hintergrundfarbe der Statusanzeige fest.|  
|[CProgressCtrl::SetMarquee](../Topic/CProgressCtrl::SetMarquee.md)|Aktiviert oder deaktiviert Laufschriftmodus für das aktuelle Statusanzeige\-Steuerelement.|  
|[CProgressCtrl::SetPos](../Topic/CProgressCtrl::SetPos.md)|Legt die aktuelle Position für ein Statusanzeige\-Steuerelement fest und zeichnet die Leiste neu, um die neue Lage widerzuspiegeln.|  
|[CProgressCtrl::SetRange](../Topic/CProgressCtrl::SetRange.md)|Legt die minimalen und maximalen Bereiche für ein Statusanzeige\-Steuerelement fest und zeichnet die Leiste neu, um die neuen Bereiche wiederzugeben.|  
|[CProgressCtrl::SetState](../Topic/CProgressCtrl::SetState.md)|Legt den Zustand des aktuellen Statusanzeige\-Steuerelements fest.|  
|[CProgressCtrl::SetStep](../Topic/CProgressCtrl::SetStep.md)|Gibt die Schrittweite für ein Statusanzeige\-Steuerelement an.|  
|[CProgressCtrl::StepIt](../Topic/CProgressCtrl::StepIt.md)|Setzt die aktuelle Position für ein Statusanzeige\-Steuerelement durch die Schrittweite \(siehe [SetStep](../Topic/CProgressCtrl::SetStep.md)\) und zeichnet die Leiste neu, um die neue Lage widerzuspiegeln.|  
  
## Hinweise  
 Ein Statusanzeige\-Steuerelement ist ein Fenster, das eine Anwendung verwenden kann, um den Status eines längeren Vorgangs anzugeben.  Es besteht aus einem Rechteck, das sich von links nach rechts gefüllt wird mit der Hervorhebungsfarbe des Systems Status eines Vorgangs.  
  
 Ein Statusanzeige\-Steuerelement hat einen Bereich und eine aktuelle Position.  Der Bereich stellt die gesamte Dauer des Vorgangs dar, und die aktuelle Position stellt den Status dar, den die Anwendung beim Abschließen des Vorgangs ausgeführt hat.  Die Fensterprozedur verwendet den Bereich und die aktuelle Position, den Prozentsatz der Statusanzeige zu bestimmen, die mit der Hervorhebungsfarbe auszufüllen.  Da die Bereichs\- und Positionswerte als Zahlen mit Vorzeichen ausgedrückt werden, ist der mögliche Bereich von Werten der aktuellen Position von 2.147.483.648 bis 2.147.483.647 liegt.  
  
 Weitere Informationen zur Verwendung von `CProgressCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden CProgressCtrl](../../mfc/using-cprogressctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [Das MFC\-Beispiel](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)