---
title: "CScrollBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CScrollBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelemente [MFC], Bildlaufleiste"
  - "CScrollBar class"
  - "Bildlaufleisten"
  - "SCROLLBAR window class"
  - "Windows common controls [C++], CScrollBar"
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CScrollBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines Windows\-Bildlaufleisten\-Steuerelements bereit.  
  
## Syntax  
  
```  
class CScrollBar : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CScrollBar::CScrollBar](../Topic/CScrollBar::CScrollBar.md)|Erstellt ein `CScrollBar`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CScrollBar::Create](../Topic/CScrollBar::Create.md)|Erstellt die Windows\-Bildlaufleiste und fügt sie dem `CScrollBar`\-Objekt.|  
|[CScrollBar::EnableScrollBar](../Topic/CScrollBar::EnableScrollBar.md)|Aktiviert oder deaktiviert eine oder beide Pfeile einer Bildlaufleiste.|  
|[CScrollBar::GetScrollBarInfo](../Topic/CScrollBar::GetScrollBarInfo.md)|Ruft Informationen über die Bildlaufleiste unter Verwendung einer `SCROLLBARINFO`\-Struktur ab.|  
|[CScrollBar::GetScrollInfo](../Topic/CScrollBar::GetScrollInfo.md)|Ruft Informationen über die Bildlaufleiste ab.|  
|[CScrollBar::GetScrollLimit](../Topic/CScrollBar::GetScrollLimit.md)|Ruft die Begrenzung der Bildlaufleiste ab|  
|[CScrollBar::GetScrollPos](../Topic/CScrollBar::GetScrollPos.md)|Ruft die aktuelle Position eines Bildlauffelds ab.|  
|[CScrollBar::GetScrollRange](../Topic/CScrollBar::GetScrollRange.md)|Ruft die aktuellen minimalen und maximalen Bildlaufleistenpositionen für die angegebene Bildlaufleiste ab.|  
|[CScrollBar::SetScrollInfo](../Topic/CScrollBar::SetScrollInfo.md)|Enthält Informationen über die Bildlaufleiste fest.|  
|[CScrollBar::SetScrollPos](../Topic/CScrollBar::SetScrollPos.md)|Legt die aktuelle Position eines Bildlauffelds fest.|  
|[CScrollBar::SetScrollRange](../Topic/CScrollBar::SetScrollRange.md)|Legt minimale und maximale Positionswerte für die angegebene Bildlaufleiste fest.|  
|[CScrollBar::ShowScrollBar](../Topic/CScrollBar::ShowScrollBar.md)|In oder aus ein Bildlaufleiste.|  
  
## Hinweise  
 Sie erstellen ein ScrollBar\-Steuerelement in zwei Schritten erstellt.  Zuerst rufen Sie den Konstruktor `CScrollBar` auf, um das `CScrollBar`\-Objekt zu erstellen, und rufen Sie dann die [Erstellen Sie](../Topic/CScrollBar::Create.md)\-Memberfunktion auf, um das Windows\-Bildlaufleisten\-Steuerelement zu erstellen und auf den `CScrollBar`\-Objekt anzufügen.  
  
 Wenn Sie ein `CScrollBar`\-Objekt innerhalb eines Dialogfelds \(durch eine Dialogfeldressource\) erstellen, wird `CScrollBar` automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie ein `CScrollBar`\-Objekt innerhalb eines Fensters erstellen, müssen Sie möglicherweise auch es zerstören.  
  
 Wenn Sie das `CScrollBar`\-Objekt auf dem Stapel erstellen, wird er automatisch zerstört.  Wenn Sie das `CScrollBar`\-Objekt auf dem Heap erstellen, indem Sie die **new**\-Funktion verwenden, müssen Sie **delete** für das Objekt aufrufen, um es zu zerstören, wenn der Benutzer die Windows\-Bildlaufleiste beendet.  
  
 Wenn Sie einen Arbeitsspeicher im `CScrollBar`\-Objekt zuordnen, überschreiben Sie den `CScrollBar` Destruktor, um die Zuordnungen freizugeben.  
  
 Weitere Informationen zur Verwendung von `CScrollBar`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CScrollBar`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)