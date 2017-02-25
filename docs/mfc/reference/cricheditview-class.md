---
title: "CRichEditView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRichEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditView class"
  - "document/view architecture, Rich-Edit-Steuerelemente"
  - "OLE containers, rich edit"
  - "Rich-Edit-Steuerelemente, OLE container"
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CRichEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) und [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) stellt die Funktionalität des Rich\-Edit\-Steuerelements im Kontext Dokumenten\-Ansichtsarchitektur MFC bereit.  
  
## Syntax  
  
```  
  
class CRichEditView : public CCtrlView  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditView::CRichEditView](../Topic/CRichEditView::CRichEditView.md)|Erstellt ein `CRichEditView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditView::AdjustDialogPosition](../Topic/CRichEditView::AdjustDialogPosition.md)|Verschiebt ein Dialogfeld, sodass es nicht die aktuelle Auswahl verdeckt.|  
|[CRichEditView::CanPaste](../Topic/CRichEditView::CanPaste.md)|Teilt mit, ob die Zwischenablage Daten enthält, die in die Rich\-Edit\-Ansicht eingefügt werden können.|  
|[CRichEditView::DoPaste](../Topic/CRichEditView::DoPaste.md)|Fügt ein OLE\-Element in diese Rich\-Edit\-Ansicht ein.|  
|[CRichEditView::FindText](../Topic/CRichEditView::FindText.md)|Sucht den angegebenen Text und ruft den Wartecursor auf.|  
|[CRichEditView::FindTextSimple](../Topic/CRichEditView::FindTextSimple.md)|Sucht den angegebenen Text.|  
|[CRichEditView::GetCharFormatSelection](../Topic/CRichEditView::GetCharFormatSelection.md)|Ruft die Zeichenformatierungsattribute für die aktuelle Auswahl ab.|  
|[CRichEditView::GetDocument](../Topic/CRichEditView::GetDocument.md)|Ruft einen Zeiger auf zugehörigen [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) ab.|  
|[CRichEditView::GetInPlaceActiveItem](../Topic/CRichEditView::GetInPlaceActiveItem.md)|Ruft das OLE\-Element ab, das in der Rich\-Edit\-Ansicht nur direkt aktiviert ist.|  
|[CRichEditView::GetMargins](../Topic/CRichEditView::GetMargins.md)|Ruft die Ränder für diese Rich\-Edit\-Ansicht ab.|  
|[CRichEditView::GetPageRect](../Topic/CRichEditView::GetPageRect.md)|Ruft das Seitenrechteck für diese Rich\-Edit\-Ansicht ab.|  
|[CRichEditView::GetPaperSize](../Topic/CRichEditView::GetPaperSize.md)|Ruft das Papierformat für diese Rich\-Edit\-Ansicht ab.|  
|[CRichEditView::GetParaFormatSelection](../Topic/CRichEditView::GetParaFormatSelection.md)|Ruft die Absatzformatierungsattribute für die aktuelle Auswahl ab.|  
|[CRichEditView::GetPrintRect](../Topic/CRichEditView::GetPrintRect.md)|Ruft das Drucksrechteck für diese Rich\-Edit\-Ansicht ab.|  
|[CRichEditView::GetPrintWidth](../Topic/CRichEditView::GetPrintWidth.md)|Ruft die Druckbreite für diese Rich\-Edit\-Ansicht ab.|  
|[CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md)|Ruft das RichEdit\-Steuerelement ab.|  
|[CRichEditView::GetSelectedItem](../Topic/CRichEditView::GetSelectedItem.md)|Ruft das ausgewählte Element aus der Rich\-Edit\-Ansicht ab.|  
|[CRichEditView::GetTextLength](../Topic/CRichEditView::GetTextLength.md)|Ruft die Länge des Texts in der Rich\-Edit\-Ansicht ab.|  
|[CRichEditView::GetTextLengthEx](../Topic/CRichEditView::GetTextLengthEx.md)|Ruft die Anzahl von Zeichen oder Bytes in der Rich\-Edit\-Ansicht ab.  Erweiterte Flagsliste für Methode zum Bestimmen der Länge.|  
|[CRichEditView::InsertFileAsObject](../Topic/CRichEditView::InsertFileAsObject.md)|Fügt eine Datei als ein OLE\-Element.|  
|[CRichEditView::InsertItem](../Topic/CRichEditView::InsertItem.md)|Fügt ein neues Element als ein OLE\-Element.|  
|[CRichEditView::IsRichEditFormat](../Topic/CRichEditView::IsRichEditFormat.md)|Teilt mit, ob die Zwischenablage Daten in einem umfangreichen Bearbeitungs\- oder Textformat enthält.|  
|[CRichEditView::OnCharEffect](../Topic/CRichEditView::OnCharEffect.md)|Schaltet die Zeichenformatierung für die aktuelle Auswahl um.|  
|[CRichEditView::OnParaAlign](../Topic/CRichEditView::OnParaAlign.md)|Ändert die Ausrichtung der Absätze.|  
|[CRichEditView::OnUpdateCharEffect](../Topic/CRichEditView::OnUpdateCharEffect.md)|Aktualisiert die Befehlsbenutzeroberfläche für Funktionen des Zeichenöffentlichen members.|  
|[CRichEditView::OnUpdateParaAlign](../Topic/CRichEditView::OnUpdateParaAlign.md)|Aktualisiert die Befehlsbenutzeroberfläche für Funktionen des Absatzöffentlichen members.|  
|[CRichEditView::PrintInsideRect](../Topic/CRichEditView::PrintInsideRect.md)|Formatiert den angegebenen Text im angegebenen Rechtecks.|  
|[CRichEditView::PrintPage](../Topic/CRichEditView::PrintPage.md)|Formatiert den angegebenen Text innerhalb der angegebenen Seite.|  
|[CRichEditView::SetCharFormat](../Topic/CRichEditView::SetCharFormat.md)|Legt die Zeichenformatierungsattribute für die aktuelle Auswahl fest.|  
|[CRichEditView::SetMargins](../Topic/CRichEditView::SetMargins.md)|Legt die Ränder für diese Rich\-Edit\-Ansicht fest.|  
|[CRichEditView::SetPaperSize](../Topic/CRichEditView::SetPaperSize.md)|Legt das Papierformat für diese Rich\-Edit\-Ansicht fest.|  
|[CRichEditView::SetParaFormat](../Topic/CRichEditView::SetParaFormat.md)|Legt die Absatzformatierungsattribute für die aktuelle Auswahl fest.|  
|[CRichEditView::TextNotFound](../Topic/CRichEditView::TextNotFound.md)|Setzt den internen Suchenzustand des Steuerelements zurück.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditView::GetClipboardData](../Topic/CRichEditView::GetClipboardData.md)|Ruft ein Zwischenablageobjekt für einen Bereich in dieser Rich\-Edit\-Ansicht ab.|  
|[CRichEditView::GetContextMenu](../Topic/CRichEditView::GetContextMenu.md)|Ruft ein Kontextmenü ab, um auf einer rechten Maustaste unten zu verwenden.|  
|[CRichEditView::IsSelected](../Topic/CRichEditView::IsSelected.md)|Gibt an, ob das angegebene OLE\-Element oder nicht aktiviert ist.|  
|[CRichEditView::OnFindNext](../Topic/CRichEditView::OnFindNext.md)|Sucht das nächste Vorkommen einer Teilzeichenfolge.|  
|[CRichEditView::OnInitialUpdate](../Topic/CRichEditView::OnInitialUpdate.md)|Aktualisiert eine Ansicht, bei der ersten angefügt zu einem Dokument ist.|  
|[CRichEditView::OnPasteNativeObject](../Topic/CRichEditView::OnPasteNativeObject.md)|Ruft systemeigene Daten von einem OLE\-Element ab.|  
|[CRichEditView::OnPrinterChanged](../Topic/CRichEditView::OnPrinterChanged.md)|Legt die Druckseigenschaften zum angegebenen Gerät fest.|  
|[CRichEditView::OnReplaceAll](../Topic/CRichEditView::OnReplaceAll.md)|Ersetzt alle Vorkommen einer angegebenen Zeichenfolge durch eine neue Zeichenfolge.|  
|[CRichEditView::OnReplaceSel](../Topic/CRichEditView::OnReplaceSel.md)|Ersetzt die aktuelle Auswahl.|  
|[CRichEditView::OnTextNotFound](../Topic/CRichEditView::OnTextNotFound.md)|Bearbeitet Benutzerbenachrichtigung, die der angeforderte Text nicht gefunden wurde.|  
|[CRichEditView::QueryAcceptData](../Topic/CRichEditView::QueryAcceptData.md)|Abfragen, um über die Daten auf `IDataObject` anzuzeigen.|  
|[CRichEditView::WrapChanged](../Topic/CRichEditView::WrapChanged.md)|Stellt den Zielausgabe\-Ausgabemechanismus auf diese Rich\-Edit\-Ansicht, abhängig vom Wert von `m_nWordWrap` ein.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditView::m\_nBulletIndent](../Topic/CRichEditView::m_nBulletIndent.md)|Gibt die Menge des Einzugs für Aufzählungszeichenlisten an.|  
|[CRichEditView::m\_nWordWrap](../Topic/CRichEditView::m_nWordWrap.md)|Gibt die Zeilenumbrucheinschränkungen an.|  
  
## Hinweise  
 Ein "RichEdit\-Steuerelement" ist ein Fenster, in dem der Benutzer Text eingeben und bearbeiten kann.  Der Text kann Zeichen und Absatzformatierung zugewiesen und kann eingebettete OLE\-Objekte einschließen.  derzeit stellen eine Programmierschnittstelle zum Formatieren von Text bereit.  muss jedoch eine Anwendung alle Benutzeroberflächenkomponenten implementieren, die erforderlich sind, Formatierungsvorgänge zu machen für den Benutzer.  
  
 `CRichEditView` verwaltet das Text\- und Formatierungseigenschaft des Texts bei.  `CRichEditDoc` führt die Liste der OLE\-Clientelementen, die in der Ansicht sind.  `CRichEditCntrItem` ContainerSeite bietet Zugriff auf OLE\-Clientelement.  
  
 Dieses allgemeine Windows\-Steuerelement \(und daher [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und die zugehörigen Klassen\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT\-Versionen 3,51 und höher ausgeführt werden.  
  
 Ein Beispiel für die Verwendung einer Rich\-Edit\-Ansicht in einer MFC\-Anwendung, finden Sie die [WORDPAD](../../top/visual-cpp-samples.md) Beispielanwendung.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## Anforderungen  
 **Header:**  afxrich.h  
  
## Siehe auch  
 [MFC Sampling WORDPAD](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc Class](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem Class](../../mfc/reference/cricheditcntritem-class.md)