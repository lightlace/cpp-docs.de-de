---
title: "CEditView Class"
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
  - "CEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEditView class"
  - "edit controls, Klassen"
  - "text editors"
  - "text editors, CEditView class"
  - "Ansichten, Klassen"
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
caps.latest.revision: 25
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Typ Ansichtsklasse, die die Funktionalität eines Windows\-Bearbeitungssteuerelements stellt und verwendet werden kann, um einfache Text\-Editor\-Funktionalität zu implementieren.  
  
## Syntax  
  
```  
class CEditView : public CCtrlView  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CEditView::CEditView](../Topic/CEditView::CEditView.md)|Erstellt ein Objekt vom Typ `CEditView`.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CEditView::FindText](../Topic/CEditView::FindText.md)|Sucht eine Zeichenfolge innerhalb des Texts.|  
|[CEditView::GetBufferLength](../Topic/CEditView::GetBufferLength.md)|Ruft die Länge des Zeichenpuffers.|  
|[CEditView::GetEditCtrl](../Topic/CEditView::GetEditCtrl.md)|Bietet Zugriff auf den `CEdit` Teil eines Objekts `CEditView` \(das Windows\-Bearbeitungssteuerelement\).|  
|[CEditView::GetPrinterFont](../Topic/CEditView::GetPrinterFont.md)|Ruft die aktuelle Druckerschriftart ab.|  
|[CEditView::GetSelectedText](../Topic/CEditView::GetSelectedText.md)|Ruft die aktuelle Textauswahl ab.|  
|[CEditView::LockBuffer](../Topic/CEditView::LockBuffer.md)|Sperrt den Puffer.|  
|[CEditView::PrintInsideRect](../Topic/CEditView::PrintInsideRect.md)|Macht Textinnere ein bestimmtes Rechteck.|  
|[CEditView::SerializeRaw](../Topic/CEditView::SerializeRaw.md)|Serialisiert ein `CEditView`\-Objekt auf dem Datenträger als unformatierter Text.|  
|[CEditView::SetPrinterFont](../Topic/CEditView::SetPrinterFont.md)|Legt eine neue Druckerschriftart fest.|  
|[CEditView::SetTabStops](../Topic/CEditView::SetTabStops.md)|Legt Tabstopps für Bildschirmanzeige und Drucken fest.|  
|[CEditView::UnlockBuffer](../Topic/CEditView::UnlockBuffer.md)|Setzt den Puffer frei.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CEditView::OnFindNext](../Topic/CEditView::OnFindNext.md)|Folgendes Vorkommen der Suchen einer Textzeichenfolge.|  
|[CEditView::OnReplaceAll](../Topic/CEditView::OnReplaceAll.md)|Ersetzt alle Vorkommen einer angegebenen Zeichenfolge durch eine neue Zeichenfolge.|  
|[CEditView::OnReplaceSel](../Topic/CEditView::OnReplaceSel.md)|Ersetzt aktuelle Auswahl.|  
|[CEditView::OnTextNotFound](../Topic/CEditView::OnTextNotFound.md)|Aufgerufen, wenn ein Suchvorgang Text keine weiteren kann nicht übereinstimmen.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CEditView::dwStyleDefault](../Topic/CEditView::dwStyleDefault.md)|Standardstil für Objekte des Typs **CEditView.**|  
  
## Hinweise  
 Die `CEditView`\-Klasse stellt die folgenden Optionen:  
  
-   Drucken.  
  
-   Suchen und Ersetzen Sie.  
  
 Da Klasse `CEditView` eine Ableitung der Klasse `CView` ist, können Objekte der Klasse `CEditView` mit Dokumenten und Dokumentvorlagen verwendet werden.  
  
 Der Text `CEditView` jedes Steuerelements wird in einem eigenen globalen Arbeitsspeicherobjekt übernommen.  Die Anwendung kann eine beliebige Anzahl `CEditView`\-Objekte verfügen.  
  
 Erstellen Sie Objekte des Typs `CEditView`, wenn Sie ein Bearbeitungsfenster mit der zusätzlichen Funktionen benötigen, die oben aufgeführten wird oder wenn Sie einfache Text\-Editor\-Funktionalität soll.  Ein Objekt `CEditView` kann den gesamten Clientbereich eines Fensters einnehmen.  Leiten Sie eigene Klassen von `CEditView`, um die grundlegende Funktionalität hinzuzufügen oder zu ändern, oder Klassen deklarieren, die einer Normal\-Vorlage hinzugefügt werden können.  
  
 Die Standardimplementierung der Klasse `CEditView` behandelt die folgenden Befehle: **ID\_EDIT\_SELECT\_ALL**, **ID\_EDIT\_FIND**, **ID\_EDIT\_REPLACE**, **ID\_EDIT\_REPEAT** und **ID\_FILE\_PRINT**.  
  
 Die standardmäßige Zeichengrenze für `CEditView` ist \(1024 \* 1024 \- 1 \= 1048575\).  Dies kann geändert werden, indem die **EM\_LIMITTEXT**\-Funktion des zugrunde liegenden Bearbeitungssteuerelements aufruft.  Allerdings sind die Grenzen abhängig vom Betriebssystem und Typ des Bearbeitungssteuerelements unterschiedlich \(einzeln oder mehrzeilig\).  Weitere Informationen über diese Grenzen, finden Sie unter [EM\_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607).  
  
 Um diese Beschränkungen in dem Steuerelement zu ändern, überschreiben Sie die `OnCreate()`\-Funktion für die `CEditView`\-Klasse und fügen Sie die folgende Codezeile ein:  
  
 [!CODE [NVC_MFCDocView#65](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#65)]  
  
 Objekte des Typs `CEditView` \(oder der Typen abgeleitet von `CEditView`\) gelten folgende Einschränkungen:  
  
-   `CEditView` implementiert nicht true Bearbeiten What you see is what you get \(WYSIWYG\).  Wo es eine Auswahl zwischen Lesbarkeit auf dem Bildschirm und entsprechender Druckausgabe gibt, wählt `CEditView` Bildschirmlesbarkeit.  
  
-   `CEditView` kann Text in nur einem Schriftfamilie anzeigen.  Keine Sonderzeichenformatierung wird unterstützt.  Siehe Klasse [CRichEditView](../../mfc/reference/cricheditview-class.md) für größere Funktionen.  
  
-   Die Menge des Texts, den `CEditView` enthalten kann, ist eingeschränkt.  Die Grenzen sind die gleichen wie für das `CEdit`\-Steuerelement.  
  
 Weitere Informationen zu `CEditView`, finden Sie unter [Abgeleitete Ansichtsklassen verfügbar in MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CEditView`  
  
## Anforderungen  
 **Header:** afxext.h  
  
## Siehe auch  
 [SUPERPAD MFC\-Beispiel](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)