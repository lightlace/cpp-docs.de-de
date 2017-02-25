---
title: "CButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "button control [MFC]"
  - "button objects (CButton)"
  - "CButton class"
  - "Kontrollkästchen, button controls"
  - "checkbox buttons"
  - "pushbuttons"
  - "Optionsfelder, CButton class"
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität von Windows\-Schaltflächen\-Steuerelementen bereit.  
  
## Syntax  
  
```  
class CButton : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CButton::CButton](../Topic/CButton::CButton.md)|Erstellt ein `CButton`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CButton::Create](../Topic/CButton::Create.md)|Erstellt das Schaltflächen\-Steuerelement von Windows und fügt es dem `CButton`\-Objekt.|  
|[CButton::DrawItem](../Topic/CButton::DrawItem.md)|Überschreiben Sie, um ein Ownerdrawn\-`CButton`\-Objekt zu zeichnen.|  
|[CButton::GetBitmap](../Topic/CButton::GetBitmap.md)|Ruft das Handle der Bitmap ab, die zuvor mit [SetBitmap](../Topic/CButton::SetBitmap.md) festgelegt ist.|  
|[CButton::GetButtonStyle](../Topic/CButton::GetButtonStyle.md)|Ruft Informationen zum Schaltflächen\-Steuerelement\-Format ab.|  
|[CButton::GetCheck](../Topic/CButton::GetCheck.md)|Ruft den Aktivierungszustand eines Button\-Steuerelements ab.|  
|[CButton::GetCursor](../Topic/CButton::GetCursor.md)|Ruft das Handle des Cursorbilder ab, die zuvor mit [SetCursor](../Topic/CButton::SetCursor.md) festgelegt ist.|  
|[CButton::GetIcon](../Topic/CButton::GetIcon.md)|Ruft das Handle des Symbols ab, die zuvor mit [SetIcon](../Topic/CButton::SetIcon.md) festgelegt ist.|  
|[CButton::GetIdealSize](../Topic/CButton::GetIdealSize.md)|Ruft die ideale Größe des Button\-Steuerelements ab.|  
|[CButton::GetImageList](../Topic/CButton::GetImageList.md)|Ruft die Bildliste des Button\-Steuerelements ab.|  
|[CButton::GetNote](../Topic/CButton::GetNote.md)|Ruft die Hinweiskomponente des aktuellen Befehlslink\-steuerelements ab.|  
|[CButton::GetNoteLength](../Topic/CButton::GetNoteLength.md)|Ruft die Länge des Hinweistexts für das aktuelle Befehlslink\-steuerelement ab.|  
|[CButton::GetSplitGlyph](../Topic/CButton::GetSplitGlyph.md)|Ruft das Symbol ab, das dem aktuellen SplitButton\-Steuerelement zugeordnet ist.|  
|[CButton::GetSplitImageList](../Topic/CButton::GetSplitImageList.md)|Ruft die Bildliste für das aktuelle SplitButton\-Steuerelement ab.|  
|[CButton::GetSplitInfo](../Topic/CButton::GetSplitInfo.md)|Ruft Informationen ab, die das aktuelle SplitButton\-Steuerelement definiert.|  
|[CButton::GetSplitSize](../Topic/CButton::GetSplitSize.md)|Ruft das umschließende Rechteck der Dropdown\-Komponente des aktuellen Steuerelements der Auswahlschaltfläche ab.|  
|[CButton::GetSplitStyle](../Topic/CButton::GetSplitStyle.md)|Ruft die Formate der Auswahlschaltfläche ab, die das aktuelle SplitButton\-Steuerelement definieren.|  
|[CButton::GetState](../Topic/CButton::GetState.md)|Ruft den Aktivierungszustand, den Hervorhebungszustand und den Fokusenzustand eines Button\-Steuerelements ab.|  
|[CButton::GetTextMargin](../Topic/CButton::GetTextMargin.md)|Ruft den Textrand des Button\-Steuerelements ab.|  
|[CButton::SetBitmap](../Topic/CButton::SetBitmap.md)|Gibt eine auf an der Schaltfläche angezeigt werden Bitmap.|  
|[CButton::SetButtonStyle](../Topic/CButton::SetButtonStyle.md)|Ändert das Format einer Schaltfläche.|  
|[CButton::SetCheck](../Topic/CButton::SetCheck.md)|Legt den Aktivierungszustand eines Button\-Steuerelements fest.|  
|[CButton::SetCursor](../Topic/CButton::SetCursor.md)|Gibt ein auf der Schaltfläche an angezeigt werden Cursor\-Image.|  
|[CButton::SetDropDownState](../Topic/CButton::SetDropDownState.md)|Legt den Dropdown\-Zustand des aktuellen Steuerelements der Auswahlschaltfläche fest.|  
|[CButton::SetIcon](../Topic/CButton::SetIcon.md)|Gibt ein auf an der Schaltfläche angezeigt werden Symbol.|  
|[CButton::SetImageList](../Topic/CButton::SetImageList.md)|Legt die Bildliste des Button\-Steuerelements fest.|  
|[CButton::SetNote](../Topic/CButton::SetNote.md)|Legt den Hinweis über das aktuelle Befehlslink\-steuerelement fest.|  
|[CButton::SetSplitGlyph](../Topic/CButton::SetSplitGlyph.md)|Ordnet ein bestimmtes Symbol mit dem aktuellen SplitButton\-Steuerelement zu.|  
|[CButton::SetSplitImageList](../Topic/CButton::SetSplitImageList.md)|Ordnet eine Bildliste mit dem aktuellen SplitButton\-Steuerelement zu.|  
|[CButton::SetSplitInfo](../Topic/CButton::SetSplitInfo.md)|Gibt Informationen an, die das aktuelle SplitButton\-Steuerelement definiert.|  
|[CButton::SetSplitSize](../Topic/CButton::SetSplitSize.md)|Legt das umschließende Rechteck der Dropdown\-Komponente des aktuellen Steuerelements der Auswahlschaltfläche fest.|  
|[CButton::SetSplitStyle](../Topic/CButton::SetSplitStyle.md)|Legt das Format des aktuellen Steuerelements der Auswahlschaltfläche fest.|  
|[CButton::SetState](../Topic/CButton::SetState.md)|Legt den Hervorhebungszustand eines Button\-Steuerelements fest.|  
|[CButton::SetTextMargin](../Topic/CButton::SetTextMargin.md)|Legt den Textrand des Button\-Steuerelements fest.|  
  
## Hinweise  
 Ein Schaltflächen\-Steuerelement ist ein kleines, rechteckiges untergeordnetes Fenster, auf das an und weg geklickt werden kann.  Schaltflächen können in Gruppen allein oder verwendet werden und entweder beschriftet sind oder ohne Text angezeigt werden.  Eine Schaltfläche ändert in der Regel Darstellung, wenn der Benutzer darauf klickt.  
  
 Typische Schaltflächen sind das Kontrollkästchen, das Optionsfeld und der Pushbutton.  Ein Objekt `CButton` kann diese, entsprechend [Schaltflächenformat](../../mfc/reference/button-styles.md) werden, das an der Initialisierung von der [Erstellen Sie](../Topic/CButton::Create.md)\-Memberfunktion angegeben wird.  
  
 Darüber hinaus unterstützt die [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)\-Klasse, die von abgeleitet ist, `CButton` Erstellung von Schaltflächen\-Steuerelemente, die mit Bitmap\-Bildern anstelle von Text bezeichnet werden.  `CBitmapButton` kann separate Bitmaps für eine Schaltfläche oben, unten liegt und deaktivierte Status haben.  
  
 Sie können ein Schaltflächen\-Steuerelement entweder einer Dialogfeldvorlage oder direkt im Code erstellen.  In beiden Fällen zunächst der Konstruktor `CButton`, um `CButton` des Objekts zu erstellen; Rufen Sie dann die **Create**\-Memberfunktion auf, um das Schaltflächen\-Steuerelement von Windows zu erstellen und auf `CButton`\-Objekt anzufügen.  
  
 Konstruktion kann ein nur einen Schritt umfassender Prozess in einer Klasse sein, die von `CButton` abgeleitet wird.  Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen Sie **Create** aus dem Konstruktor auf.  
  
 Wenn Sie Windows\-Benachrichtigungsmeldungen bearbeiten möchten, die durch ein Schaltflächen\-Steuerelement zu seinem übergeordneten Element gesendet werden \(normalerweise eine Klasse wird von abgeleitet [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)\), fügen Sie eine Meldungszuordnungseintrags\- und Meldungshandlermemberfunktion der übergeordneten Klasse für jede Meldung hinzu.  
  
 Jeder Eintrag in der Meldungszuordnung weist folgende Form auf:  
  
 **ON\_** Benachrichtigung **\(**`id`, `memberFxn`**\)**  
  
 wobei `id` die ID des untergeordneten Fensters sendenden des Steuerelements, ist die Benachrichtigungen und `memberFxn` der Name der übergeordneten Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu bearbeiten.  
  
 Der Funktionsprototyp des übergeordneten Elements ist, wie folgt:  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 Mögliche Meldungszuordnungseinträge sind, wie folgt:  
  
|Zuordnungseintrag|Gesendet, um zum übergeordneten Element, wenn...|  
|-----------------------|------------------------------------------------------|  
|**ON\_BN\_CLICKED**|Der Benutzer klickt auf eine Schaltfläche.|  
|**ON\_BN\_DOUBLECLICKED**|Der Benutzer doppelklickt auf eine Schaltfläche.|  
  
 Wenn Sie ein `CButton`\-Objekt aus einer Dialogfeldressource erstellen, wird das Objekt `CButton` automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie ein `CButton`\-Objekt innerhalb eines Fensters erstellen, müssen Sie es zerstören.  Wenn Sie das `CButton`\-Objekt auf dem Heap erstellen, indem Sie die **new**\-Funktion verwenden, müssen Sie **delete** für das Objekt aufrufen, um es zu zerstören, wenn der Benutzer das Schaltflächen\-Steuerelement von Windows enthält.  Wenn Sie das `CButton`\-Objekt auf dem Stapel erstellen oder er im übergeordneten Dialogfeldobjekt eingebettet wird, wird er automatisch zerstört.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CBitmapButton Class](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)