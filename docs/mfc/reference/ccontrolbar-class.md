---
title: "CControlBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CControlBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlBar class"
  - "control bars [C++], Basisklasse"
  - "dialog bars, Basisklasse"
  - "OLE resize bars"
  - "OLE resize bars, Basisklasse"
  - "Statusleisten, Basisklasse"
  - "Symbolleisten [C++], Basisklasse"
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CControlBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse für die Steuerleisteklassen [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md) und [COleResizeBar](../../mfc/reference/coleresizebar-class.md).  
  
## Syntax  
  
```  
class CControlBar : public CWnd  
```  
  
## Member  
  
### Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CControlBar::CControlBar](../Topic/CControlBar::CControlBar.md)|Erstellt ein `CControlBar`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CControlBar::CalcDynamicLayout](../Topic/CControlBar::CalcDynamicLayout.md)|Gibt die Größe einer dynamischen Steuerleiste als ein [CSize](../../atl-mfc-shared/reference/csize-class.md)\-Objekt zurück.|  
|[CControlBar::CalcFixedLayout](../Topic/CControlBar::CalcFixedLayout.md)|Gibt die Größe der Steuerleiste als ein [CSize](../../atl-mfc-shared/reference/csize-class.md)\-Objekt zurück.|  
|[CControlBar::CalcInsideRect](../Topic/CControlBar::CalcInsideRect.md)|Gibt die aktuellen Maße des Steuerleistenbereichs, einschließlich der Rahmen, zurück.|  
|[CControlBar::DoPaint](../Topic/CControlBar::DoPaint.md)|Rendert die Rahmen und das Ziehelement der Steuerleiste.|  
|[CControlBar::DrawBorders](../Topic/CControlBar::DrawBorders.md)|Rendert die Rahmen der Steuerleiste.|  
|[CControlBar::DrawGripper](../Topic/CControlBar::DrawGripper.md)|Rendert das Ziehelement der Steuerleiste.|  
|[CControlBar::EnableDocking](../Topic/CControlBar::EnableDocking.md)|Ermöglicht das Andocken bzw. eine unverankerte Steuerleiste.|  
|[CControlBar::GetBarStyle](../Topic/CControlBar::GetBarStyle.md)|Ruft die Formatvorlagen der Steuerleiste ab.|  
|[CControlBar::GetBorders](../Topic/CControlBar::GetBorders.md)|Ruft die Rahmenwerte der Steuerleiste ab.|  
|[CControlBar::GetCount](../Topic/CControlBar::GetCount.md)|Gibt die Anzahl von nicht `HWND`\-Elementen in der Steuerleiste zurück.|  
|[CControlBar::GetDockingFrame](../Topic/CControlBar::GetDockingFrame.md)|Gibt einen Zeiger auf den Frame zurück, an den eine Steuerleiste angedockt ist.|  
|[CControlBar::IsFloating](../Topic/CControlBar::IsFloating.md)|Gibt einen Wert ungleich 0 \(null\) zurück, wenn die fragliche Steuerleiste unverankert ist.|  
|[CControlBar::OnUpdateCmdUI](../Topic/CControlBar::OnUpdateCmdUI.md)|Ruft die Befehlshandler der Benutzeroberfläche ab.|  
|[CControlBar::SetBarStyle](../Topic/CControlBar::SetBarStyle.md)|Ändert die Formatvorlagen der Steuerleiste.|  
|[CControlBar::SetBorders](../Topic/CControlBar::SetBorders.md)|Legt die Rahmenwerte der Steuerleiste fest.|  
|[CControlBar::SetInPlaceOwner](../Topic/CControlBar::SetInPlaceOwner.md)|Ändert den direkten Besitzer einer Steuerleiste.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CControlBar::m\_bAutoDelete](../Topic/CControlBar::m_bAutoDelete.md)|Wenn der Wert ungleich 0 \(null\) ist, wird das `CControlBar`\-Objekt gelöscht, sobald die Windows\-Steuerleiste beschädigt wird.|  
|[CControlBar::m\_pInPlaceOwner](../Topic/CControlBar::m_pInPlaceOwner.md)|Der direkte Besitzer der Steuerleiste.|  
  
## Hinweise  
 Eine Steuerleiste ist ein Fenster, das normalerweise am linken oder rechten Rand eines Rahmenfensters ausgerichtet wird.  Es enthält möglicherweise untergeordnete Elemente, die alle `HWND`\-basierte Steuerelemente sind, also Fenster, die Windows\-Meldungen generieren oder darauf reagieren, oder es handelt sich um nicht\-`HWND`\-basierte Elemente. Das sind keine Fenster und diese Elemente werden mithilfe von Anwendungs\- oder Frameworkcode verwaltet.  Beispiele für `HWND`\-basierte Steuerelemente sind Listenfelder und Bearbeitungssteuerelemente. Hingegen sind Statusleistenbereiche und Bitmapschaltflächen Beispiele für nicht `HWND`\-basierte Steuerelemente.  
  
 Bei Steuerleistenfenstern handelt es sich normalerweise um untergeordnete Fenster eines übergeordneten Rahmenfensters, und es sind normalerweise nebengeordnete Elemente der Clientansicht oder des MDI\-Clients des Rahmenfensters.  Ein `CControlBar`\-Objekt verwendet zum eigenen Positionieren Informationen über das Clientrechteck des übergeordneten Fensters.  Dem übergeordneten Fenster wird dann die Menge des Speicherplatzes im Clientbereich des übergeordneten Fensters mitgeteilt, die unzugeordnet bleibt.  
  
 Weitere Informationen zu `CControlBar` finden Sie unter:  
  
-   [Steuerleisten](../../mfc/control-bars.md)  
  
-   [Technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).  
  
-   Knowledge Base\-Artikel Q242577: PRB: Update\-Befehlshandler für Benutzeroberflächen funktionieren für das an ein Dialogfeld angefügte Menü nicht mehr  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## Anforderungen  
 **Header:** afxext.h  
  
## Siehe auch  
 [MFC\-Muster CTRLBARS](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar Class](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar Class](../../mfc/reference/cstatusbar-class.md)   
 [CReBar Class](../../mfc/reference/crebar-class.md)