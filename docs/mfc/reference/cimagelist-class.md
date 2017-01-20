---
title: "CImageList Class"
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
  - "CImageList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList class"
  - "image lists [C++], CImageList class"
  - "Windows common controls [C++], CImageList"
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CImageList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des allgemeinen Bildlistensteuerelements Windows bereit.  
  
## Syntax  
  
```  
class CImageList : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CImageList::CImageList](../Topic/CImageList::CImageList.md)|Erstellt ein `CImageList`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CImageList::Add](../Topic/CImageList::Add.md)|Fügt ein Bild oder einer Bildliste Bilder hinzu.|  
|[CImageList::Attach](../Topic/CImageList::Attach.md)|Fügt eine Bildliste zu einem `CImageList`\-Objekt bei.|  
|[CImageList::BeginDrag](../Topic/CImageList::BeginDrag.md)|Startet, ein Bild zu ziehen.|  
|[CImageList::Copy](../Topic/CImageList::Copy.md)|Kopiert ein Bild innerhalb eines `CImageList`\-Objekts.|  
|[CImageList::Create](../Topic/CImageList::Create.md)|Initialisiert eine Bildliste und fügt sie zu einem `CImageList`\-Objekt.|  
|[CImageList::DeleteImageList](../Topic/CImageList::DeleteImageList.md)|Löscht eine Bildliste.|  
|[CImageList::DeleteTempMap](../Topic/CImageList::DeleteTempMap.md)|Aufgerufen durch den [CWinApp](../../mfc/reference/cwinapp-class.md) Leerlaufhandler, entweder `CImageList` temporäres Objekt gelöscht erstellt durch `FromHandle`.|  
|[CImageList::Detach](../Topic/CImageList::Detach.md)|Trennt ein Bildlistenobjekt von einem `CImageList`\-Objekt und gibt ein Handle einer Bildliste zurück.|  
|[CImageList::DragEnter](../Topic/CImageList::DragEnter.md)|Sperrenupdates während eines Ziehvorgangs und das Anzeigen der Ziehbild an einer angegebenen Position.|  
|[CImageList::DragLeave](../Topic/CImageList::DragLeave.md)|Entsperrt das und blendet das Ziehbild aus, damit das Fenster aktualisiert werden kann.|  
|[CImageList::DragMove](../Topic/CImageList::DragMove.md)|Verschiebt das Bild, das während eines Drag & Drop\-Vorgangs gezogen wird.|  
|[CImageList::DragShowNolock](../Topic/CImageList::DragShowNolock.md)|In oder aus das Ziehbild während eines Ziehvorgangs, ohne das Fenster zu sperren.|  
|[CImageList::Draw](../Topic/CImageList::Draw.md)|Zeichnet das Bild, das während eines Drag & Drop\-Vorgangs gezogen wird.|  
|[CImageList::DrawEx](../Topic/CImageList::DrawEx.md)|Zeichnet ein Bildlistenelement im angegebenen Gerätekontext.  Die Funktion verwendet das angegebene Zeichnungsformat und mischt das Bild mit der angegebenen Farbe.|  
|[CImageList::DrawIndirect](../Topic/CImageList::DrawIndirect.md)|Zeichnet ein Bild aus einer Bildliste.|  
|[CImageList::EndDrag](../Topic/CImageList::EndDrag.md)|Beendet einen Ziehvorgang.|  
|[CImageList::ExtractIcon](../Topic/CImageList::ExtractIcon.md)|Erstellt ein Symbol auf einem Bild und Maske in einer Bildliste.|  
|[CImageList::FromHandle](../Topic/CImageList::FromHandle.md)|Gibt einen Zeiger auf ein Objekt `CImageList` zurück, wenn Sie ein Handle einer Bildliste angegeben werden.  Wenn ein `CImageList`\-Objekt nicht in Anspruch angefügt wird, wird ein temporäres Objekt erstellt und `CImageList` angefügt.|  
|[CImageList::FromHandlePermanent](../Topic/CImageList::FromHandlePermanent.md)|Gibt einen Zeiger auf ein Objekt `CImageList` zurück, wenn Sie ein Handle einer Bildliste angegeben werden.  Wenn ein `CImageList`\-Objekt nicht in Anspruch angefügt wird, wird **NULL** zurückgegeben.|  
|[CImageList::GetBkColor](../Topic/CImageList::GetBkColor.md)|Ruft die aktuelle Hintergrundfarbe für eine Bildliste ab.|  
|[CImageList::GetDragImage](../Topic/CImageList::GetDragImage.md)|Ruft die temporäre Bildliste ab, die für das Ziehen verwendet wird.|  
|[CImageList::GetImageCount](../Topic/CImageList::GetImageCount.md)|Ruft die Anzahl von Bildern in einer Bildliste ab.|  
|[CImageList::GetImageInfo](../Topic/CImageList::GetImageInfo.md)|Ruft Informationen über ein Bild ab.|  
|[CImageList::GetSafeHandle](../Topic/CImageList::GetSafeHandle.md)|Ruft **m\_hImageList** ab.|  
|[CImageList::Read](../Topic/CImageList::Read.md)|Liest eine Bildliste aus einem Archiv.|  
|[CImageList::Remove](../Topic/CImageList::Remove.md)|Entfernt ein Bild aus einer Bildliste.|  
|[CImageList::Replace](../Topic/CImageList::Replace.md)|Ersetzt ein Bild in einer Bildliste durch ein neues Bild.|  
|[CImageList::SetBkColor](../Topic/CImageList::SetBkColor.md)|Legt die Hintergrundfarbe für eine Bildliste fest.|  
|[CImageList::SetDragCursorImage](../Topic/CImageList::SetDragCursorImage.md)|Erstellt ein neues Ziehbild.|  
|[CImageList::SetImageCount](../Topic/CImageList::SetImageCount.md)|Setzt die Anzahl von Bildern in einer Bildliste zurück.|  
|[CImageList::SetOverlayImage](../Topic/CImageList::SetOverlayImage.md)|Fügt den nullbasierten Index eines Bilds der Liste der als hinzu Overlaymasken verwendet werden Bilder.|  
|[CImageList::Write](../Topic/CImageList::Write.md)|Schreibt eine Bildliste zu einem Archiv.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CImageList::operator HIMAGELIST](../Topic/CImageList::operator%20HIMAGELIST.md)|Gibt `HIMAGELIST` zurück, das in `CImageList` angefügt wird.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CImageList::m\_hImageList](../Topic/CImageList::m_hImageList.md)|Ein Handle, das die Bildliste angefügt auf dieses Objekt enthält.|  
  
## Hinweise  
 Eine "Bildliste" ist eine Auflistung gleich\-groß Bilder, von denen jedes über seinen nullbasierten Index verwiesen werden kann.  Bildlisten werden verwendet, um große Mengen von Symbole oder Bitmaps effizient zu verwalten.  Alle Bilder in einer Bildliste werden in einer einzelnen, Anordnen Bitmap im Bildschirmgerätenformat enthalten.  Eine Bildliste enthält möglicherweise auch eine monochrome Bitmap, die die Masken enthält, die verwendet werden, um Bildes transparent zu zeichnen \(Symbolformat\).  Die Microsoft Win32\-Fensters Anwendungsprogrammierschnittstelle \(API\) stellt Bildlistenfunktionen, die es Ihnen ermöglichen, Bildern zu zeichnen, Bildlisten zu erstellen und zu zerstören, Bilder hinzufügen und entfernen, ersetzen Bilder, Zusammenführungsimages und Ziehbilder.  
  
 Dieses Steuerelement \(und daher die `CImageList`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT 3,51 und höher ausgeführt werden.  
  
 Weitere Informationen zur Verwendung von `CImageList`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CImageList](../../mfc/using-cimagelist.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl Class](../../mfc/reference/ctabctrl-class.md)