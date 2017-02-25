---
title: "CReBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBar class"
  - "Internet Explorer 4.0 common controls"
  - "rebar controls, control bar"
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CReBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Steuerleiste, die Layout, Persistenz\- und Zustandsinformationen für Infoleistensteuerelemente bereitstellt.  
  
## Syntax  
  
```  
  
class CReBar : public CControlBar  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CReBar::AddBar](../Topic/CReBar::AddBar.md)|Fügt ein Band einer Infoleiste hinzu.|  
|[CReBar::Create](../Topic/CReBar::Create.md)|Erstellt das Grundleistensteuerelement und fügt es dem `CReBar`\-Objekt.|  
|[CReBar::GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md)|Ermöglicht Zugriff auf die zugrunde liegenden allgemeine Steuerelemente.|  
  
## Hinweise  
 Ein Infoleistenobjekt kann eine Vielzahl von untergeordneten Fenstern, normalerweise weitere Steuerelemente enthalten, einschließlich Eingabefelder, Symbolleisten und Listenfelder.  Ein Infoleistenobjekt kann untergeordneten Fenster über einer angegebenen Bitmap anzeigen.  Die Anwendung kann die Infoleiste automatisch ändern, oder der Benutzer kann die Infoleiste manuell Größe ändern, indem er auf die Ziehpunktleiste klickt oder ziehen.  
  
 ![Beispiel eines Grundleistenmenüs](../../mfc/reference/media/vc4sc61.png "vc4SC61")  
  
## Grundleistensteuerelement  
 Ein Infoleistenobjekt verhält sich wie ein Symbolleistenobjekt.  Eine Infoleiste verwendet den Klick\-undZieh Mechanismus, um die Bänder Größe zu ändern.  Ein Grundleistensteuerelement kann eine oder mehrere Bänder enthalten, wenn jedes Band jede Kombination verfügt, einer Ziehpunktleiste, der Bitmaps, der Beschriftung und untergeordneten Fensters.  Sie können jedoch Bänder mehr als ein untergeordnetes Fenster nicht enthalten.  
  
 **CReBar** verwendet die [CReBarCtrl](../../mfc/reference/crebarctrl-class.md)\-Klasse, um seine Implementierung bereitzustellen.  Sie können auf das Grundleistensteuerelement durch [GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md) zugreifen, um die Anpassungsoptionen des Steuerelements zu nutzen.  Weitere Informationen zu Infoleistensteuerelemente, finden Sie unter `CReBarCtrl`.  Weitere Informationen zur Verwendung von Infoleiste\-Steuerelementen, finden Sie unter [Verwenden CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
> [!CAUTION]
>  Infoleisten\- und Infoleiste\-Steuerelement\-Objekte unterstützen keine MFC\-Steuerleistenandocken.  Wenn **CRebar::EnableDocking** aufgerufen wird, werden die Anwendung.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## Anforderungen  
 **Header:**  afxext.h  
  
## Siehe auch  
 [MFC\-Beispiel MFCIE](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)