---
title: "CDialogEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogEx class"
  - "CDialogEx::PreTranslateMessage method"
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CDialogEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDialogEx`\-Klasse gibt die Hintergrundfarbe und das Hintergrundbild eines Dialogfelds an.  
  
## Syntax  
  
```  
class CDialogEx : public CDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDialogEx::CDialogEx](../Topic/CDialogEx::CDialogEx.md)|Erstellt ein `CDialogEx`\-Objekt.|  
|`CDialogEx::~CDialogEx`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDialogEx::SetBackgroundColor](../Topic/CDialogEx::SetBackgroundColor.md)|Legt die Hintergrundfarbe des Dialogfelds fest.|  
|[CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md)|Legt das Hintergrundbild des Dialogfelds fest.|  
  
## Hinweise  
 Zum Verwenden der `CDialogEx`\-Klasse müssen Sie Ihre Dialogfeldklasse von der `CDialogEx`\-Klasse statt der `CDialog`\-Klasse ableiten.  
  
 Dialogfeldbilder werden in einer Ressourcendatei gespeichert.  Das Framework löscht automatisch jedes Bild, das aus der Ressourcendatei geladen wird.  Um das aktuelle Hintergrundbild programmgesteuert zu löschen, rufen Sie die [CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md)\-Methode auf, oder implementieren Sie einen `OnDestroy`\-Ereignishandler.  Beim Aufrufen der [CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md)\-Methode übergeben Sie einen `HBITMAP`\-Parameter als Bild\-Handle.  Das `CDialogEx`\-Objekt übernimmt den Besitz des Bilds und löscht es, wenn das `m_bAutoDestroyBmp` \-Flag `TRUE` ist.  
  
 Ein `CDialogEx`\-Objekt kann ein übergeordnetes Element eines [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)\-Objekts sein.  Das [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) \-Objekt ruft beim Öffnen des [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)\-Objekts die `CDialogEx::SetActiveMenu` Methode auf.  Danach verarbeitet das `CDialogEx`\-Objekt alle Menüereignisse, bis das [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)\-Objekt geschlossen ist.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## Anforderungen  
 **Header:** afxdialogex.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)   
 [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md)