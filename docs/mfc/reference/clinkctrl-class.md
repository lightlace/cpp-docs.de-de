---
title: "CLinkCtrl Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinkCtrl class"
  - "Steuerelemente [MFC], Verknüpfungen"
  - "Links [C++], link control"
  - "SysLink control"
  - "Webseiten, link control"
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
caps.latest.revision: 23
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CLinkCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des allgemeinen SysLink Steuerelements Windows bereit.  
  
## Syntax  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CLinkCtrl::CLinkCtrl](../Topic/CLinkCtrl::CLinkCtrl.md)|Erstellt ein `CLinkCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CLinkCtrl::Create](../Topic/CLinkCtrl::Create.md)|Erstellt ein Linksteuerelement und fügt es zu einem `CLinkCtrl`\-Objekt.|  
|[CLinkCtrl::CreateEx](../Topic/CLinkCtrl::CreateEx.md)|Erstellt ein Linksteuerelement mit erweiterten Formaten und fügt es zu einem `CLinkCtrl`\-Objekt.|  
|[CLinkCtrl::GetIdealHeight](../Topic/CLinkCtrl::GetIdealHeight.md)|Ruft die ideale Höhe des Link\-Steuerelements ab.|  
|[CLinkCtrl::GetIdealSize](../Topic/CLinkCtrl::GetIdealSize.md)|Berechnet die bevorzugte Höhe des Linktexts für das aktuelle Linksteuerelement, abhängig von der angegebenen Breite des Links.|  
|[CLinkCtrl::GetItem](../Topic/CLinkCtrl::GetItem.md)|Ruft die Zustände und die Attribute eines Verknüpfungssteuerelements ab.|  
|[CLinkCtrl::GetItemID](../Topic/CLinkCtrl::GetItemID.md)|Ruft die ID eines Verknüpfungssteuerelements ab.|  
|[CLinkCtrl::GetItemState](../Topic/CLinkCtrl::GetItemState.md)|Ruft den Zustand des Verknüpfungssteuerelements ab.|  
|[CLinkCtrl::GetItemUrl](../Topic/CLinkCtrl::GetItemUrl.md)|Ruft die URL ab, das vom Verknüpfungssteuerelement dargestellt wird.|  
|[CLinkCtrl::HitTest](../Topic/CLinkCtrl::HitTest.md)|Bestimmt, ob der Benutzer auf den angegebenen Link.|  
|[CLinkCtrl::SetItem](../Topic/CLinkCtrl::SetItem.md)|Legt die Zustände und die Attribute eines Verknüpfungssteuerelements fest.|  
|[CLinkCtrl::SetItemID](../Topic/CLinkCtrl::SetItemID.md)|Legt die ID eines Verknüpfungssteuerelements fest.|  
|[CLinkCtrl::SetItemState](../Topic/CLinkCtrl::SetItemState.md)|Legt den Zustand des Verknüpfungssteuerelements fest.|  
|[CLinkCtrl::SetItemUrl](../Topic/CLinkCtrl::SetItemUrl.md)|Legt die URL fest, das vom Verknüpfungssteuerelement dargestellt wird.|  
  
## Hinweise  
 Ein "Linksteuerelement" bietet eine einfache Möglichkeit, Hypertextlinks in einem Fenster einzubetten.  Das tatsächliche Steuerelement ist ein Fenster, das markierten Text rendert und entsprechende Anwendungen automatisch gestartet, wenn der Benutzer auf einen eingebetteten Link klickt.  Auf mehrere Links werden innerhalb eines Steuerelements unterstützt und können durch einen nullbasierten Index zugegriffen werden.  
  
 Dieses Steuerelement \(und daher die `CLinkCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die später unter Windows XP und ausgeführt werden.  
  
 Weitere Informationen finden Sie unter [SysLink\-Steuerelement](http://msdn.microsoft.com/library/windows/desktop/bb760706) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## Anforderungen  
 **Header:** afxcmn.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)