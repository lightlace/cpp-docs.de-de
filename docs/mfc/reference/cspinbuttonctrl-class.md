---
title: "CSpinButtonCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSpinButtonCtrl class"
  - "CSpinButtonCtrl class, Allgemeine Steuerelemente"
  - "Drehfeld-Steuerelement"
  - "Auf-Ab-Steuerelemente, Drehfeld-Steuerelement"
  - "Windows common controls [C++], CSpinButtonCtrl"
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSpinButtonCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des allgemeinen Drehfelds Windows bereit.  
  
## Syntax  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](../Topic/CSpinButtonCtrl::CSpinButtonCtrl.md)|Erstellt ein `CSpinButtonCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](../Topic/CSpinButtonCtrl::Create.md)|Erstellt ein Drehfeldsteuerelement und fügt es zu einem `CSpinButtonCtrl`\-Objekt.|  
|[CSpinButtonCtrl::CreateEx](../Topic/CSpinButtonCtrl::CreateEx.md)|Erstellt ein Drehfeldsteuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CSpinButtonCtrl`\-Objekt.|  
|[CSpinButtonCtrl::GetAccel](../Topic/CSpinButtonCtrl::GetAccel.md)|Ruft Beschleunigungsinformationen für ein Drehfeldsteuerelement ab.|  
|[CSpinButtonCtrl::GetBase](../Topic/CSpinButtonCtrl::GetBase.md)|Ruft die aktuelle Basis für ein Drehfeldsteuerelement ab.|  
|[CSpinButtonCtrl::GetBuddy](../Topic/CSpinButtonCtrl::GetBuddy.md)|Ruft einen Zeiger auf das aktuelle Buddyfenster ab.|  
|[CSpinButtonCtrl::GetPos](../Topic/CSpinButtonCtrl::GetPos.md)|Ruft die aktuelle Position eines Drehfeld\-Steuerelements ab.|  
|[CSpinButtonCtrl::GetRange](../Topic/CSpinButtonCtrl::GetRange.md)|Ruft das der Ober\- und Untergrenze \(Bereich\) für ein Drehfeldsteuerelement ab.|  
|[CSpinButtonCtrl::SetAccel](../Topic/CSpinButtonCtrl::SetAccel.md)|Legt die Beschleunigung für ein Drehfeldsteuerelement fest.|  
|[CSpinButtonCtrl::SetBase](../Topic/CSpinButtonCtrl::SetBase.md)|Legt die Basis für ein Drehfeldsteuerelement fest.|  
|[CSpinButtonCtrl::SetBuddy](../Topic/CSpinButtonCtrl::SetBuddy.md)|Legt das Buddyfenster für ein Drehfeldsteuerelement fest.|  
|[CSpinButtonCtrl::SetPos](../Topic/CSpinButtonCtrl::SetPos.md)|Legt die aktuelle Position für das Steuerelement fest.|  
|[CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md)|Setzt das der Ober\- und Untergrenze \(Bereich\) für ein Drehfeldsteuerelement fest.|  
  
## Hinweise  
 Ein "Spinner\-Steuerelement" \(auch als Auf\-Ab\-Steuerelement\) ist ein Paar auf Pfeilschaltflächen, die der Benutzer klicken kann, um einen Wert zu erhöhen oder zu verringern, wie eine Bildlaufposition oder eine Zahl, die in einem Begleitsteuerelement angezeigt werden.  Der Wert, der einem Drehfeld\-Steuerelement zugeordnet ist, wird die aktuelle Position aufgerufen.  Ein Drehfeld\-Steuerelement ist mit einem Begleitsteuerelement meist verwendet, aufgerufen Buddyfenster ein "."  
  
 Dieses Steuerelement \(und daher die `CSpinButtonCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT 3,51 und höher ausgeführt werden.  
  
 Wenn Benutzer wird ein Drehfeldsteuerelement und sein Buddyfenster häufig wie ein einzelnes Steuerelement aus.  Sie können angeben, dass ein Drehfeldsteuerelement sich automatisch neben dem Buddyfenster positionieren und dass es automatisch die Beschriftung des Buddyfensters an der aktuellen Position fest.  Sie können ein Drehfeldsteuerelement mit einem Bearbeitungssteuerelement verwenden, um den Benutzer für numerische Eingabe aufzufordern.  
  
 Auf den Aufwärtspfeil klicken, wird die aktuelle Position zum Maximum, und auf den Pfeil nach unten klicken, wird die aktuelle Position zum Mindestregeln.  Standardmäßig ist das Minimum und das Maximum 100 ist 0.  Immer wenn die minimale Einstellung größer als die maximale Einstellung ist \(beispielsweise, wenn die Standardeinstellungen verwendet werden\), auf den Aufwärtspfeil klicken senkt den Positionswert und Klicken auf den Pfeil nach unten erhöht sie.  
  
 Ein Drehfeld\-Steuerelement ohne Funktionen eines Buddyfensters als Sortierung der vereinfachten Bildlaufleiste.  Beispielsweise wird ein Tab\-Steuerelement manchmal ein Drehfeldsteuerelement an, um dem Benutzer zu ermöglichen, um zusätzliche Registerkarten in einblenden.  
  
 Weitere Informationen zur Verwendung von `CSpinButtonCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [MFC Sampling CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Class](../../mfc/reference/csliderctrl-class.md)