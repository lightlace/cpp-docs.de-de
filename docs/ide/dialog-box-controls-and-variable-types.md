---
title: Dialogfeld-Steuerelemente und Variablentypen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2fbae37072f50898181334a9059a7dc9c6a83a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dialog-box-controls-and-variable-types"></a>Dialogfeld-Steuerelemente und Variablentypen
Können Sie die [Assistenten zum Hinzufügen von Variablen](../ide/add-member-variable-wizard.md) ein Dialogfeld-Steuerelement mit MFC erstellt eine Membervariable hinzu. Der Typ des Steuerelements für die Sie die Membervariable hinzufügen, bestimmt die Optionen, die Sie im Dialogfeld angezeigt werden.  
  
 Die folgende Tabelle beschreibt alle Typen von Dialogfeld-Steuerelementen, die von in MFC unterstützt und die [Dialog-Editor](../windows/dialog-editor.md), den verfügbaren Typen und Werten.  
  
|Steuerelement|Steuerelementtyp|Variable-Steuerelementtyp|Variable Werttyp|Min/Max-Werte (nur Werttyp)|  
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|  
|Animationssteuerelement|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|None; nur-Steuerelement|Nicht zutreffend|  
|Schaltfläche|SCHALTFLÄCHE|[CButton](../mfc/reference/cbutton-class.md)|None; nur-Steuerelement|Nicht zutreffend|  
|Kontrollkästchen|KONTROLLKÄSTCHEN|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|Min-Wert oder ' max '-Wert|  
|Kombinationsfeld|KOMBINATIONSFELD-STEUERELEMENT|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|Maximale Anzahl von Zeichen|  
|Datums-/ Zeitauswahl-Steuerelement|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|Min-Wert oder ' max '-Wert|  
|Eingabefeld|BEARBEITEN|[CEdit](../mfc/reference/cedit-class.md)|`CString`, Int, UINT, long, DWORD, float, double, BYTE, short, BOOL, `COleDateTime`, oder **COleCurrency**|Min-Wert oder ' max '-Wert; Einige unterstützen Max. Zeichen|  
|Abkürzungstaste-Steuerelement|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|None; nur-Steuerelement|Nicht zutreffend|  
|Listenfeld|LISTBOX|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|Maximale Anzahl von Zeichen|  
|Listensteuerelement|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|None; nur-Steuerelement|Nicht zutreffend|  
|Monatskalender-Steuerelement|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|Min-Wert oder ' max '-Wert|  
|Statuskontrolle|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|None; nur-Steuerelement|Nicht zutreffend|  
|Bearbeiten Sie Rich-2-Steuerelement|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|Maximale Anzahl von Zeichen|  
|Rich-Edit-Steuerelement|RICHEDIT|`CRichEditCtrl`|`CString`|Maximale Anzahl von Zeichen|  
|Bildlaufleiste (vertikal oder horizontal|BILDLAUFLEISTE|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|Min-Wert oder ' max '-Wert|  
|Schiebereglersteuerung|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|Min-Wert oder ' max '-Wert|  
|Drehfeld-Steuerelement|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|None; nur-Steuerelement|Nicht zutreffend|  
|Registersteuerelement|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|None; nur-Steuerelement|Nicht zutreffend|  
|Struktursteuerelement|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|None; nur-Steuerelement|Nicht zutreffend|  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)