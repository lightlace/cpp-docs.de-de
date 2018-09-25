---
title: Dialogfeld-Steuerelemente und Variablentypen | Microsoft-Dokumentation
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
ms.openlocfilehash: 6914ab8b5838ee6bc5bb7a74004ed986efe2fcda
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373986"
---
# <a name="dialog-box-controls-and-variable-types"></a>Dialogfeld-Steuerelemente und Variablentypen

Sie können den [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) verwenden, um einem mit MFC erstellten Dialogfeld-Steuerelement eine Membervariable hinzuzufügen. Der Typ des Steuerelements, dem Sie die Membervariable hinzufügen, bestimmt die Optionen, die im Dialogfeld angezeigt werden.

In der folgenden Tabelle werden alle Steuerelementtypen der Dialogfelder und deren verfügbare Typen und Werte beschrieben, die in MFC und dem [Dialog-Editor](../windows/dialog-editor.md) unterstützt werden.

|Steuerelement|Steuerelementtyp|Variable für den Steuerelementtyp|Variable für den Werttyp|Min/Max-Werte (nur der Werttyp)|
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|
|Animationssteuerelement|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|Keiner, nur Steuerelement|Nicht zutreffend|
|Schaltfläche|SCHALTFLÄCHE|[CButton](../mfc/reference/cbutton-class.md)|Keiner, nur Steuerelement|Nicht zutreffend|
|Kontrollkästchen|KONTROLLKÄSTCHEN|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|Minimalwert/Maximalwert|
|Kombinationsfeld|KOMBINATIONSFELD|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|Maximale Zeichenanzahl|
|Datums-/Zeitauswahl-Steuerelement|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|Minimalwert/Maximalwert|
|Bearbeitungsfeld|BEARBEITEN|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, long, DWORD, float, double, BYTE, short, BOOL, `COleDateTime`, oder **COleCurrency**|Minimalwert/Maximalwert, einige unterstützen die maximale Zeichenanzahl|
|Hotkey-Steuerelement|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|Keiner, nur Steuerelement|Nicht zutreffend|
|Listenfeld|LISTENFELD|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|Maximale Zeichenanzahl|
|Listensteuerelement|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|Keiner, nur Steuerelement|Nicht zutreffend|
|Monatskalender-Steuerelement|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|Minimalwert/Maximalwert|
|Statuskontrolle|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Keiner, nur Steuerelement|Nicht zutreffend|
|Rich Edit 2-Steuerelement|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|Maximale Zeichenanzahl|
|Rich Edit-Steuerelement|RICHEDIT|`CRichEditCtrl`|`CString`|Maximale Zeichenanzahl|
|Scrollleiste (vertikal oder horizontal)|SCROLLLEISTE|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|Minimalwert/Maximalwert|
|Schiebereglersteuerung|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|Minimalwert/Maximalwert|
|Drehfeld-Steuerelement|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Keiner, nur Steuerelement|Nicht zutreffend|
|Registersteuerelement|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|Keiner, nur Steuerelement|Nicht zutreffend|
|Struktursteuerelement|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Keiner, nur Steuerelement|Nicht zutreffend|

## <a name="see-also"></a>Siehe auch

[Adding a Member Variable (Hinzufügen einer Membervariablen)](../ide/adding-a-member-variable-visual-cpp.md)