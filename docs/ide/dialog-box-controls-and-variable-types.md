---
title: "Dialogfeld-Steuerelemente und Variablentypen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dialogfeldsteuerelemente, Membervariablen"
  - "Dialogfeldsteuerelemente, Variablentypen"
  - "Variablen, Membervariablen für Dialogfeld-Steuerelemente"
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Dialogfeld-Steuerelemente und Variablentypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) können Sie einem Dialogfeld\-Steuerelement, das unter Verwendung von MFC erstellt wurde, eine Membervariable hinzufügen.  Die im Dialogfeld angezeigten Optionen hängen vom Steuerelementtyp ab, für den Sie die Membervariable hinzufügen.  
  
 In der folgenden Tabelle werden alle Typen von Dialogfeld\-Steuerelementen, die von MFC und dem [Dialog\-Editor](../mfc/dialog-editor.md) unterstützt werden, zusammen mit den verfügbaren Typen und Werten beschrieben.  
  
|Steuerelement|Steuerelementtyp|Steuerelementvariablen\-Typ|Wertvariablentyp|Min. Wert\/Max. Wert \(nur Werttypen\)|  
|-------------------|----------------------|---------------------------------|----------------------|--------------------------------------------|  
|Animationssteuerelement|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|Keiner; nur Steuerelement|Nicht zutreffend|  
|Button|BUTTON|[CButton](../mfc/reference/cbutton-class.md)|Keiner; nur Steuerelement|Nicht zutreffend|  
|Kontrollkästchen|CHECK|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|Min. Wert\/Max. Wert|  
|Kombinationsfeld|COMBOBOX|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|Max. Zeichen|  
|Datums\-\/Zeitauswahl\-Steuerelement|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|Min. Wert\/Max. Wert|  
|Eingabefeld|EDIT|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, long, DWORD, float, double, BYTE, short, BOOL, `COleDateTime` oder **COleCurrency**|Min. Wert\/Max. Wert; einige unterstützen Max. Zeichen|  
|Abkürzungstaste\-Steuerelement|msctls\_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|Keiner; nur Steuerelement|Nicht zutreffend|  
|Listenfeld|LISTBOX|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|Max. Zeichen|  
|Listen\-Steuerelement|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|Keiner; nur Steuerelement|Nicht zutreffend|  
|Monatskalender\-Steuerelement|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|Min. Wert\/Max. Wert|  
|Statuskontrolle|msctls\_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Keiner; nur Steuerelement|Nicht zutreffend|  
|Rich\-Edit\-2\-Steuerelement|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|Max. Zeichen|  
|RichEdit\-Steuerelement|RICHEDIT|`CRichEditCtrl`|`CString`|Max. Zeichen|  
|Schiebeleiste \(vertikal oder horizontal\)|SCROLLBAR|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|Min. Wert\/Max. Wert|  
|Schieberegler\-Steuerelement|msctls\_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|Min. Wert\/Max. Wert|  
|Drehfeld\-Steuerelement|msctls\_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Keiner; nur Steuerelement|Nicht zutreffend|  
|Registersteuerelement|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|Keiner; nur Steuerelement|Nicht zutreffend|  
|Strukturansicht\-Steuerelement|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Keiner; nur Steuerelement|Nicht zutreffend|  
  
## Siehe auch  
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)