---
title: "CStatic Class"
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
  - "CStatic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bitmaps, Anzeigen"
  - "Steuerelemente [MFC], Statische"
  - "CStatic class"
  - "Cursor, Anzeigen"
  - "enhanced metafiles"
  - "enhanced metafiles, Anzeigen"
  - "Symbole, Anzeigen"
  - "static controls"
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CStatic Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines Windows\-statischenSteuerelements bereit.  
  
## Syntax  
  
```  
class CStatic : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CStatic::CStatic](../Topic/CStatic::CStatic.md)|Erstellt ein `CStatic`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CStatic::Create](../Topic/CStatic::Create.md)|Erstellt das Windows\-statischeSteuerelement und fügt es dem `CStatic`\-Objekt.|  
|[CStatic::DrawItem](../Topic/CStatic::DrawItem.md)|Überschreiben Sie, um eines Ownerdrawnstatischen Kartensteuerelements zu zeichnen.|  
|[CStatic::GetBitmap](../Topic/CStatic::GetBitmap.md)|Ruft das Handle der Bitmap ab, die zuvor mit [SetBitmap](../Topic/CStatic::SetBitmap.md) festgelegt ist.|  
|[CStatic::GetCursor](../Topic/CStatic::GetCursor.md)|Ruft das Handle des Cursorbilder ab, die zuvor mit [SetCursor](../Topic/CStatic::SetCursor.md) festgelegt ist.|  
|[CStatic::GetEnhMetaFile](../Topic/CStatic::GetEnhMetaFile.md)|Ruft das Handle der erweiterten Metadatei ab, die zuvor mit [SetEnhMetaFile](../Topic/CStatic::SetEnhMetaFile.md) festgelegt ist.|  
|[CStatic::GetIcon](../Topic/CStatic::GetIcon.md)|Ruft das Handle des Symbols ab, die zuvor mit [SetIcon](../Topic/CStatic::SetIcon.md) festgelegt ist.|  
|[CStatic::SetBitmap](../Topic/CStatic::SetBitmap.md)|Gibt eine an im statischen Steuerelement angezeigt werden, Bitmap.|  
|[CStatic::SetCursor](../Topic/CStatic::SetCursor.md)|Gibt ein im an statischen Steuerelement angezeigt werden Cursor\-Image.|  
|[CStatic::SetEnhMetaFile](../Topic/CStatic::SetEnhMetaFile.md)|Gibt eine an im statischen Steuerelement angezeigt werden erweiterte Metadatei.|  
|[CStatic::SetIcon](../Topic/CStatic::SetIcon.md)|Gibt ein an im statischen Steuerelement angezeigt werden, Symbol.|  
  
## Hinweise  
 Ein statisches Steuerelement zeigt eine Textzeichenfolge, ein Feld, ein Rechteck, ein Symbol, einen Cursor, eine Bitmap oder eine erweiterte Metadatei.  Es kann verwendet werden, um andere zu bezeichnen, entfällt oder trennen können Steuerelemente.  Ein statisches Steuerelement normalerweise akzeptiert keine Eingabe und stellt keine Ausgabe; kann jedoch es das übergeordnete Element von Mausklicks benachrichtigen, wenn es mit **SS\_NOTIFY** Format erstellt hat.  
  
 Erstellen Sie ein statisches Steuerelement in zwei Schritten.  Zuerst rufen Sie den Konstruktor auf, um das `CStatic`\-Objekt zu erstellen, und rufen Sie dann die [Erstellen Sie](../Topic/CStatic::Create.md)\-Memberfunktion auf, um das statische Steuerelement zu erstellen und auf `CStatic`\-Objekt anzufügen.  
  
 Wenn Sie ein `CStatic`\-Objekt innerhalb eines Dialogfelds \(durch eine Dialogfeldressource\) erstellen, wird das Objekt `CStatic` automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie ein `CStatic`\-Objekt innerhalb eines Fensters erstellen, müssen Sie möglicherweise auch es zerstören.  Ein `CStatic`\-Objekt, das auf dem Stapel innerhalb eines Fensters erstellt wird, wird automatisch zerstört.  Wenn Sie das `CStatic`\-Objekt auf dem Heap erstellen, indem Sie die **new**\-Funktion verwenden, müssen Sie **delete** für das Objekt aufrufen, um es zu zerstören, wenn Sie damit fertig sind.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
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
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)