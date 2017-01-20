---
title: "CDragListBox Class"
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
  - "CDragListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDragListBox class"
  - "drag list box [C++]"
  - "dragging list items"
  - "Listenfelder"
  - "Windows [C++], Listenfelder"
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: 24
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CDragListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Neben der Funktionalität eines Windows\-Listenfelds, ermöglicht die `CDragListBox`\-Klasse der Benutzer den Verschiebungslistenfeldelementen, wie Dateinamen, innerhalb des Listenfelds.  
  
## Syntax  
  
```  
class CDragListBox : public CListBox  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](../Topic/CDragListBox::CDragListBox.md)|Erstellt ein `CDragListBox`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](../Topic/CDragListBox::BeginDrag.md)|Aufgerufen vom Framework beim Start eines Ziehvorgangs.|  
|[CDragListBox::CancelDrag](../Topic/CDragListBox::CancelDrag.md)|Aufgerufen vom Framework ausgelöst, wenn ein Ziehvorgang abgebrochen wurde.|  
|[CDragListBox::Dragging](../Topic/CDragListBox::Dragging.md)|Aufgerufen vom Framework während eines Ziehvorgangs.|  
|[CDragListBox::DrawInsert](../Topic/CDragListBox::DrawInsert.md)|Zeichnet das Einfügungshandbuch des Ziehlistenfelds.|  
|[CDragListBox::Dropped](../Topic/CDragListBox::Dropped.md)|Aufgerufen vom Framework, nachdem das Element gelöscht wurde.|  
|[CDragListBox::ItemFromPt](../Topic/CDragListBox::ItemFromPt.md)|Gibt die Koordinaten des Elements zurück, das gezogen wird.|  
  
## Hinweise  
 Listenfelder mit dieser Funktion können Benutzer, um die Elemente in einer Liste in zu sortieren, was Weise zu ihnen geeignet ist.  Standardmäßig wird das Listenfeld das Element auf die neue Position in der Liste.  Sie können jedoch `CDragListBox`\-Objekte angepasst werden, um Elemente zu kopieren, statt sie zu verschieben.  
  
 Das Listenfeld\-Steuerelement, das der `CDragListBox`\-Klasse zugeordnet ist, darf **LBS\_SORT** oder das **LBS\_MULTIPLESELECT** Format aufweisen.  Eine Beschreibung der Listenfeldformaten, finden Sie unter [Listenfeld\-Formate](../../mfc/reference/list-box-styles.md).  
  
 Um ein Ziehlistenfeld in einem vorhandenen Dialogfeld der Anwendung zu verwenden, fügen Sie ein Listenfeld\-Steuerelement der Dialogfeldvorlage mithilfe des Dialog\-Editors hinzu und anschließend eine Membervariable \(der Kategorie `Control` und des Variablentyps `CDragListBox`\) nach dem Listenfeld\-Steuerelement in der Dialogfeldvorlage zu.  
  
 Weitere Informationen zum Zuweisen von Steuerelementen auf Membervariablen, finden Sie unter [Verknüpfung zum Definieren von Membervariablen für Dialogfeld\-Steuerelementen](../../mfc/defining-member-variables-for-dialog-controls.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [MFC Sampling TSTCON](../../top/visual-cpp-samples.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)