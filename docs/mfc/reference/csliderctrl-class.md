---
title: "CSliderCtrl Class"
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
  - "CSliderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSliderCtrl class"
  - "CSliderCtrl class, Allgemeine Steuerelemente"
  - "Schieberegler-Steuerelemente, CSliderCtrl class"
  - "Windows common controls [C++], CSliderCtrl"
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CSliderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des allgemeinen Schieberegler\-Steuerelements Windows bereit.  
  
## Syntax  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSliderCtrl::CSliderCtrl](../Topic/CSliderCtrl::CSliderCtrl.md)|Erstellt ein `CSliderCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSliderCtrl::ClearSel](../Topic/CSliderCtrl::ClearSel.md)|Löscht die aktuelle Auswahl in einem Schieberegler\-Steuerelement.|  
|[CSliderCtrl::ClearTics](../Topic/CSliderCtrl::ClearTics.md)|Entfernt die aktuellen Teilstriche aus einem Schieberegler\-Steuerelement.|  
|[CSliderCtrl::Create](../Topic/CSliderCtrl::Create.md)|Erstellt ein Schieberegler\-Steuerelement und fügt es zu einem `CSliderCtrl`\-Objekt.|  
|[CSliderCtrl::CreateEx](../Topic/CSliderCtrl::CreateEx.md)|Erstellt ein Schieberegler\-Steuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CSliderCtrl`\-Objekt.|  
|[CSliderCtrl::GetBuddy](../Topic/CSliderCtrl::GetBuddy.md)|Ruft das Handle für ein Schieberegler\-Steuerelement\-Buddyfenster an einem angegebenen Speicherort ab.|  
|[CSliderCtrl::GetChannelRect](../Topic/CSliderCtrl::GetChannelRect.md)|Ruft die Größe des Steuerkanals des Schieberegler\-Steuerelements ab.|  
|[CSliderCtrl::GetLineSize](../Topic/CSliderCtrl::GetLineSize.md)|Ruft die Zeilengröße eines Schieberegler\-Steuerelements ab.|  
|[CSliderCtrl::GetNumTics](../Topic/CSliderCtrl::GetNumTics.md)|Ruft die Anzahl der Teilstriche in einem Schieberegler\-Steuerelement ab.|  
|[CSliderCtrl::GetPageSize](../Topic/CSliderCtrl::GetPageSize.md)|Ruft die Seitengröße eines Schieberegler\-Steuerelements ab.|  
|[CSliderCtrl::GetPos](../Topic/CSliderCtrl::GetPos.md)|Ruft die aktuelle Position des Schiebereglers ab.|  
|[CSliderCtrl::GetRange](../Topic/CSliderCtrl::GetRange.md)|Ruft die minimale und maximale Positionen für einen Schieberegler ab.|  
|[CSliderCtrl::GetRangeMax](../Topic/CSliderCtrl::GetRangeMax.md)|Ruft die maximale Position für einen Schieberegler ab.|  
|[CSliderCtrl::GetRangeMin](../Topic/CSliderCtrl::GetRangeMin.md)|Ruft die minimale Position für einen Schieberegler ab.|  
|[CSliderCtrl::GetSelection](../Topic/CSliderCtrl::GetSelection.md)|Ruft den Bereich der aktuellen Auswahl ab.|  
|[CSliderCtrl::GetThumbLength](../Topic/CSliderCtrl::GetThumbLength.md)|Ruft die Länge des Schiebereglers im aktuellen Trackleisten\-Steuerelement ab.|  
|[CSliderCtrl::GetThumbRect](../Topic/CSliderCtrl::GetThumbRect.md)|Ruft die Größe des Ziehpunkts des Schieberegler\-Steuerelements ab.|  
|[CSliderCtrl::GetTic](../Topic/CSliderCtrl::GetTic.md)|Ruft die Position des angegebenen Teilstrichs ab.|  
|[CSliderCtrl::GetTicArray](../Topic/CSliderCtrl::GetTicArray.md)|Ruft das Array von Teilstrichpositionen für ein Schieberegler\-Steuerelement ab.|  
|[CSliderCtrl::GetTicPos](../Topic/CSliderCtrl::GetTicPos.md)|Ruft die Position des angegebenen Teilstrichs, in Clientkoordinaten ab.|  
|[CSliderCtrl::GetToolTips](../Topic/CSliderCtrl::GetToolTips.md)|Ruft das Handle für QuickInfosteuerelement ab, das dem Slider\-Steuerelement, sofern zugewiesen wird.|  
|[CSliderCtrl::SetBuddy](../Topic/CSliderCtrl::SetBuddy.md)|Weist ein Fenster als das Buddyfenster für ein Schieberegler\-Steuerelement zu.|  
|[CSliderCtrl::SetLineSize](../Topic/CSliderCtrl::SetLineSize.md)|Legt die Zeilengröße eines Schieberegler\-Steuerelements fest.|  
|[CSliderCtrl::SetPageSize](../Topic/CSliderCtrl::SetPageSize.md)|Legt die Seitengröße eines Schieberegler\-Steuerelements fest.|  
|[CSliderCtrl::SetPos](../Topic/CSliderCtrl::SetPos.md)|Legt die aktuelle Position des Schiebereglers fest.|  
|[CSliderCtrl::SetRange](../Topic/CSliderCtrl::SetRange.md)|Legt die minimalen und maximalen Positionen für einen Schieberegler fest.|  
|[CSliderCtrl::SetRangeMax](../Topic/CSliderCtrl::SetRangeMax.md)|Legt die maximale Position für einen Schieberegler fest.|  
|[CSliderCtrl::SetRangeMin](../Topic/CSliderCtrl::SetRangeMin.md)|Legt die minimale Position für einen Schieberegler fest.|  
|[CSliderCtrl::SetSelection](../Topic/CSliderCtrl::SetSelection.md)|Legt den Bereich der aktuellen Auswahl fest.|  
|[CSliderCtrl::SetThumbLength](../Topic/CSliderCtrl::SetThumbLength.md)|Legt die Länge des Schiebereglers im aktuellen Trackleisten\-Steuerelement fest.|  
|[CSliderCtrl::SetTic](../Topic/CSliderCtrl::SetTic.md)|Legt die Position des angegebenen Teilstrichs fest.|  
|[CSliderCtrl::SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md)|Legt die Häufigkeit von Ticks pro Schieberegler\-Steuerelement\-Inkrement fest.|  
|[CSliderCtrl::SetTipSide](../Topic/CSliderCtrl::SetTipSide.md)|Positioniert ein QuickInfosteuerelement, das von einem Trackleisten\-Steuerelement verwendet wird.|  
|[CSliderCtrl::SetToolTips](../Topic/CSliderCtrl::SetToolTips.md)|Weist ein QuickInfosteuerelement zu einem Schieberegler\-Steuerelement zu.|  
  
## Hinweise  
 Ein "Schieberegler\-Steuerelement" \(auch als Trackleiste\) ist ein Fenster, das einen Schieberegler und optionalen Teilstriche enthält.  Wenn der Benutzer den Schieberegler, entweder mit bewegt, die Maus oder die Pfeiltasten, das Steuerelement sendet Benachrichtigungsmeldungen, um die Änderung anzugeben.  
  
 Schieberegler\-Steuerelemente sind nützlich, wenn der Benutzer einen einzelnen Wert oder einem Satz von nachfolgende Werte in einem Bereich aus.  Beispielsweise können Sie ein Schieberegler\-Steuerelement, um dem Benutzer zu ermöglichen, die Wiederholungskinetik der Tastatur festzulegen, indem Sie den Schieberegler zu einem angegebenen Teilstrich verschieben.  
  
 Dieses Steuerelement \(und daher die `CSliderCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT 3,51 und höher ausgeführt werden.  
  
 Der Schieberegler bewegt sich in Inkremente, die Sie angeben, wenn Sie es erstellen.  Wenn Sie beispielsweise angeben, dass der Schieberegler einen Bereich von fünf haben soll, kann der Schieberegler sechs Positionen nur einnehmen: eine Position auf der linken Seite des Schieberegler\-Steuerelements und eine Position für jedes Inkrement im Bereich.  In der Regel wird jede dieser Positionen durch einen Teilstrich identifiziert.  
  
 Sie erstellen einen Schieberegler erstellt, indem Sie den Konstruktor und die **Create**\-Memberfunktion der `CSliderCtrl` verwenden.  Nachdem Sie ein Schieberegler\-Steuerelement erstellt haben, können Sie Memberfunktionen in `CSliderCtrl` verwenden, um viele seiner Eigenschaften zu ändern.  Änderungen, die Sie die Include ausführen können, das die minimalen und maximalen Positionen für den Schieberegler festlegt, Teilstriche zeichnet, einen Auswahlbereich festgelegt wird und den Schieberegler neu angeordnet werden.  
  
 Weitere Informationen zur Verwendung von `CSliderCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSliderCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [MFC Sampling CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl Class](../../mfc/reference/cprogressctrl-class.md)