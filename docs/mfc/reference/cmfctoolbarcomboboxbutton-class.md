---
title: CMFCToolBarComboBoxButton Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddSortedItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::Compare
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CreateEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::DeleteItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::FindItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetByCmd
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetComboBox
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCount
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCountAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSel
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSelAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetEditCtrl
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemData
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataPtrAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetText
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetTextAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsFlatMode
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::RemoveAllItems
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetDropDownHeight
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetFlatMode
dev_langs: C++
helpviewer_keywords:
- CMFCToolBarComboBoxButton [MFC], CMFCToolBarComboBoxButton
- CMFCToolBarComboBoxButton [MFC], AddItem
- CMFCToolBarComboBoxButton [MFC], AddSortedItem
- CMFCToolBarComboBoxButton [MFC], Compare
- CMFCToolBarComboBoxButton [MFC], CreateEdit
- CMFCToolBarComboBoxButton [MFC], DeleteItem
- CMFCToolBarComboBoxButton [MFC], FindItem
- CMFCToolBarComboBoxButton [MFC], GetByCmd
- CMFCToolBarComboBoxButton [MFC], GetComboBox
- CMFCToolBarComboBoxButton [MFC], GetCount
- CMFCToolBarComboBoxButton [MFC], GetCountAll
- CMFCToolBarComboBoxButton [MFC], GetCurSel
- CMFCToolBarComboBoxButton [MFC], GetCurSelAll
- CMFCToolBarComboBoxButton [MFC], GetEditCtrl
- CMFCToolBarComboBoxButton [MFC], GetItem
- CMFCToolBarComboBoxButton [MFC], GetItemAll
- CMFCToolBarComboBoxButton [MFC], GetItemData
- CMFCToolBarComboBoxButton [MFC], GetItemDataAll
- CMFCToolBarComboBoxButton [MFC], GetItemDataPtrAll
- CMFCToolBarComboBoxButton [MFC], GetText
- CMFCToolBarComboBoxButton [MFC], GetTextAll
- CMFCToolBarComboBoxButton [MFC], IsCenterVert
- CMFCToolBarComboBoxButton [MFC], IsFlatMode
- CMFCToolBarComboBoxButton [MFC], RemoveAllItems
- CMFCToolBarComboBoxButton [MFC], SelectItem
- CMFCToolBarComboBoxButton [MFC], SelectItemAll
- CMFCToolBarComboBoxButton [MFC], SetCenterVert
- CMFCToolBarComboBoxButton [MFC], SetDropDownHeight
- CMFCToolBarComboBoxButton [MFC], SetFlatMode
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 18fafd4fece0047a8dcb95e50f8d4e5133ca3760
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton-Klasse
Eine Symbolleisten-Schaltfläche, die ein Kombinationsfeld-Steuerelement enthält ( [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarComboBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|Erstellt ein Objekt vom Typ `CMFCToolBarComboBoxButton`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarComboBoxButton::AddItem](#additem)|Fügt ein Element am Ende der Liste des Kombinationsfelds.|  
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|Fügt ein Element auf der Liste des Kombinationsfelds. Die Reihenfolge der Elemente in der Liste wird angegeben, indem Sie `Compare`.|  
|[CMFCToolBarComboBoxButton::Compare](#compare)|Vergleicht zwei Elemente. Wird aufgerufen, sortiert die Elemente an, `AddSortedItems` fügt der Liste des Kombinationsfelds hinzu.|  
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|Erstellt ein neue Edit-Steuerelement für die Kombinationsfelds-Schaltfläche.|  
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|Löscht ein Element aus der Liste des Kombinationsfelds.|  
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|Gibt den Index des Elements, das eine angegebene Zeichenfolge enthält.|  
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|Gibt einen Zeiger auf die kombinationsfeldschaltfläche mit einer angegebenen Befehls-ID.|  
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|Gibt einen Zeiger auf ein Kombinationsfeld-Steuerelement, das in der kombinationsfeldschaltfläche eingebettet ist.|  
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|Gibt die Anzahl der Elemente im Kombinationsfeld Liste zurück.|  
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|Sucht nach des Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID. Gibt die Anzahl der Elemente im Kombinationsfeld Listenfeld der Schaltfläche zurück.|  
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|Gibt den Index des ausgewählten Elements im Kombinationsfeld Liste zurück.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene Befehls-ID und gibt den Index des ausgewählten Elements im Kombinationsfeld Listenfeld der Schaltfläche.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|Gibt einen Zeiger auf das Steuerelement zum Bearbeiten, das in der kombinationsfeldschaltfläche eingebettet ist.|  
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Gibt die Zeichenfolge, die mit einem angegebenen Index in das Kombinationsfeld für den zugeordneten Liste zurück.|  
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene Befehls-ID und gibt die Zeichenfolge, die einen Index in der Liste des Kombinationsfelds der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|Gibt die 32-Bit-Wert, der mit einem angegebenen Index in das Kombinationsfeld für den zugeordneten ist Liste zurück.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene Befehls-ID und gibt den 32-Bit-Wert, der mit einem Index in der Liste des Kombinationsfelds der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Sucht nach des Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID. Ruft der 32-Bit-Wert, der zugeordnete eines Indexes in der Liste des Kombinationsfelds dieser Schaltfläche, und gibt die 32-Bit-Wert als Zeiger.|  
|[CMFCToolBarComboBoxButton::GetText](#gettext)|Gibt den Text in das Bearbeitungssteuerelement des Kombinationsfelds.|  
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene Befehls-ID und gibt den Text aus der Schaltfläche Edit-Steuerelement.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|Bestimmt, ob Schaltflächen in der Anwendung zentriert oder am oberen Rand der Symbolleiste ausgerichtet sind.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|Bestimmt, ob Schaltflächen in der Anwendung eine flache Darstellung haben.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Entfernt, die alle Elemente aus der Liste ein und Bearbeitungssteuerelement des Kombinationsfelds.|  
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|Wählt ein Element im Kombinationsfeld gemäß dessen Index, 32-Bit-Wert oder eine Zeichenfolge, und benachrichtigt das Kombinationsfeld-Steuerelement zur Auswahl.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|Sucht nach des Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID. Aufrufe `SelectItem` Auswahl ein Elements im Kombinationsfeld der Schaltfläche gemäß seiner Zeichenfolge, den Index oder die 32-Bit-Wert.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|Gibt an, ob Schaltflächen in der Anwendung vertikal zentriert oder am oberen Rand der Symbolleiste ausgerichtet sind.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Legt die Höhe der im Dropdown-Listenfeld an.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Gibt an, ob Schaltflächen in der Anwendung eine flache Darstellung haben.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine kombinationsfeldschaltfläche eine Symbolleiste hinzugefügt haben, gehen Sie folgendermaßen vor:  
  
 1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2. Konstruieren Sie ein `CMFCToolBarComboBoxButton`-Objekt.  
  
 3. In der Message-Handler, der verarbeitet die `AFX_WM_RESETTOOLBAR` angezeigt wird, ersetzen Sie die Schaltfläche "dummy" mit der neuen kombinationsfeldschaltfläche mit [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md). Ein Beispiel für eine Symbolleiste kombinationsfeldschaltfläche finden Sie in diesem Beispielprojekt VisualStudioDemo.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCToolBarComboBoxButton` Klasse. Das Beispiel zeigt, wie die bearbeiten und Kombinationsfelder Kontrollkästchen aktivieren, legen Sie die vertikale Position des Kombinationsfelds Schaltflächen in der Anwendung, legen Sie die Höhe des Listenfelds aus, wenn es, nach unten gelöscht wird, die flache Darstellung von Schaltflächen in der Anwendung festgelegt , und legen Sie den Text in das Bearbeitungsfeld des Kombinationsfeld-Schaltfläche. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarcomboboxbutton.h  
  
##  <a name="additem"></a>CMFCToolBarComboBoxButton::AddItem  
 Fügt ein eindeutiges Element in das Listenfeld.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszItem`  
 Der Text des Elements zum Listenfeld hinzugefügt werden soll.  
  
 [in] `dwData`  
 Die Daten, die Verbindung mit den Elementen im Listenfeld hinzu.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des letzten Elements im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nicht, wenn die Knotenart Liste sortiert wird.  
  
 Wenn der Elementtext bereits in der Liste enthalten ist, werden die neuen Daten mit dem vorhandenen Element gespeichert. Die Suche für das Element wird Groß-/Kleinschreibung beachtet.  
  
##  <a name="addsorteditem"></a>CMFCToolBarComboBoxButton::AddSortedItem  
 Fügt ein Element in das Listenfeld in der Reihenfolge, die von definiert ist die [vergleichen](#compare) Methode.  
  
```  
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszItem`  
 Der Text des Elements zum Listenfeld hinzugefügt werden soll.  
  
 [in] `dwData`  
 Die Daten, die Verbindung mit den Elementen im Listenfeld hinzu.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Elements, das im Listenfeld hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um das Listenfeld in einer bestimmten Reihenfolge Elemente hinzuzufügen.  
  
##  <a name="canbestretched"></a>CMFCToolBarComboBoxButton::CanBeStretched  
 Gibt an, ob die Größe des Kombinationsfelds Schaltfläche ändern kann.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE`zurück.  
  
##  <a name="cmfctoolbarcomboboxbutton"></a>CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton  
 Erstellt eine [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) Objekt.  
  
```  
CMFCToolBarComboBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=CBS_DROPDOWNLIST,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Die Befehls-ID von der Schaltfläche "Neu".  
  
 [in] `iImage`  
 Der Image-Index des Bilds der Schaltfläche "Neu" zugeordnet werden soll.  
  
 [in] `dwStyle`  
 Der Stil der mit der Schaltfläche "Neu".  
  
 [in] `iWidth`  
 Die Breite in Pixel der Schaltfläche "Neu".  
  
### <a name="remarks"></a>Hinweise  
 Die Standardbreite beträgt 150 Pixel.  
  
 Eine Liste der Formatvorlagen für Symbolleistenschaltflächen finden Sie unter [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="cleardata"></a>CMFCToolBarComboBoxButton::ClearData  
 Löscht eine benutzerdefinierte Daten.  
  
```  
virtual void ClearData();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Methode keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn eine benutzerdefinierte Daten gelöscht werden sollen.  
  
##  <a name="compare"></a>CMFCToolBarComboBoxButton::Compare  
 Vergleicht zwei Zeichenfolgen.  
  
```  
virtual int Compare(
    LPCTSTR lpszItem1,  
    LPCTSTR lpszItem2);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszItem1`  
 Die erste zu vergleichende Zeichenfolge.  
  
 [in] `lpszItem2`  
 Die zweite zu vergleichende Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der die Groß-/Kleinschreibung lexikografische Beziehung zwischen den Zeichenfolgen angibt. In der folgenden Tabelle sind die möglichen Werte aufgeführt:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|\<0|Die erste Zeichenfolge ist kleiner als der zweite.|  
|0|Die erste Zeichenfolge gleich der zweiten ist.|  
|>0|Die erste Zeichenfolge ist größer als das zweite.|  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode zum Ändern der Sortierung der Elemente im Listenfeld ein.  
  
 Der Vergleich wird die Groß-/Kleinschreibung beachtet.  
  
 Diese Methode wird aufgerufen, nur über die [AddSortedItem](#addsorteditem) Methode.  
  
##  <a name="copyfrom"></a>CMFCToolBarComboBoxButton::CopyFrom  
 Kopiert den Status des angegebenen `CMFCToolBarComboBoxButton` auf das aktuelle Objekt.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Das `CMFCToolBarComboBoxButton`-Quellobjekt.  
  
##  <a name="createcombo"></a>CMFCToolBarComboBoxButton::CreateCombo  
 Erstellt ein neues Kombinationsfeld für den Kombinationsfelds-Schaltfläche.  
  
```  
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster der Schaltfläche.  
  
 [in] `rect`  
 Umschließende Rechteck des Kombinationsfelds.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neue Kombinationsfeld, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
##  <a name="createedit"></a>CMFCToolBarComboBoxButton::CreateEdit  
 Erstellt eine neue Bearbeitungsfeld für die Kombinationsfelds-Schaltfläche.  
  
```  
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster der Schaltfläche.  
  
 [in] `rect`  
 Das umgebende Rechteck neben dem neuen Bearbeitungsfeld.  
  
 [in] `dwEditStyle`  
 Das Format des neuen Steuerelements Eingabefeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neue Eingabefeld zurück, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn es sich um ein neues Eingabefeld für eine kombinationsfeldschaltfläche erstellt. Überschreiben Sie diese Methode ändern wie [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) wird erstellt.  
  
##  <a name="deleteitem"></a>CMFCToolBarComboBoxButton::DeleteItem  
 Löscht ein angegebenes Element aus dem Listenfeld aus.  
  
```  
BOOL DeleteItem(int iIndex);  
BOOL DeleteItem(DWORD_PTR dwData);  
  BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index des Elements gelöscht werden soll.  
  
 [in] `dwData`  
 Die Daten, die Verbindung mit den Elementen gelöscht werden soll.  
  
 [in] `lpszText`  
 Der Text des Elements gelöscht werden soll. Wenn mehrere Elemente mit demselben Text vorhanden sind, wird das erste Element gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Element gefunden und erfolgreich gelöscht wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="duplicatedata"></a>CMFCToolBarComboBoxButton::DuplicateData  
 Duplikate benutzerdefinierten Daten.  
  
```  
virtual void DuplicateData();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Methode keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie eine benutzerdefinierte Daten kopieren möchten.  
  
##  <a name="enablewindow"></a>CMFCToolBarComboBoxButton::EnableWindow  
 Aktiviert oder deaktiviert die Felder bearbeiten und Kombinationsfelder.  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die Felder bearbeiten und Kombinationsfelder; `FALSE` So deaktivieren Sie die Felder bearbeiten und Kombinationsfelder.  
  
### <a name="remarks"></a>Hinweise  
 Wenn deaktiviert, werden die Steuerelemente können nicht aktiv und können keine Benutzereingaben akzeptieren.  
  
##  <a name="exporttomenubutton"></a>CMFCToolBarComboBoxButton::ExportToMenuButton  
 Kopiert eine Zeichenfolge aus der Anwendung Zeichenfolgentabelle zum angegebenen Menü mithilfe des Kombinationsfelds Feld Schaltfläche-Befehls-ID.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `menuButton`  
 Verweis auf eine Menüschaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
##  <a name="finditem"></a>CMFCToolBarComboBoxButton::FindItem  
 Gibt den Index des ersten Elements in der Liste, die eine angegebene Zeichenfolge enthält.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
 Der Text für die Suche im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Elements; oder `CB_ERR` , wenn das Element nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getbycmd"></a>CMFCToolBarComboBoxButton::GetByCmd  
 Ruft einen Zeiger auf die Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID  
  
```  
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,  
    BOOL bIsFocus=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID des Kombinationsfelds-Schaltfläche.  
  
 [in] `bIsFocus`  
 `TRUE`mit Fokus Schaltflächen, um nur zu suchen; `FALSE` , alle Schaltflächen gesucht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine kombinationsfeldschaltfläche; oder `NULL` , wenn die Schaltfläche "" nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcombobox"></a>CMFCToolBarComboBoxButton::GetComboBox  
 Gibt der einen Zeiger auf das Kombinationsfeld in des Kombinationsfelds-Schaltfläche.  
  
```  
CComboBox* GetComboBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md) Objekt, wenn die Methode erfolgreich, andernfalls war `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcontextmenuid"></a>CMFCToolBarComboBoxButton::GetContextMenuID  
 Ruft die Verknüpfung im Menü-Ressourcen-ID für die kombinationsfeldschaltfläche ab.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Verknüpfung im Menü-Ressourcen-ID.  
  
##  <a name="getcount"></a>CMFCToolBarComboBoxButton::GetCount  
 Gibt die Anzahl der Elemente in der Liste zurück.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcountall"></a>CMFCToolBarComboBoxButton::GetCountAll  
 Ruft die Anzahl der Elemente im Listenfeld von einer Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID  
  
```  
static int GetCountAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID des Kombinationsfelds-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Listenfeld; andernfalls `CB_ERR` Wenn der kombinationsfeldschaltfläche nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcursel"></a>CMFCToolBarComboBoxButton::GetCurSel  
 Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des derzeit ausgewählten Elements im Listenfeld; oder `CB_ERR` , wenn kein Element ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
 Die listenfeldindex ist nullbasiert.  
  
##  <a name="getcurselall"></a>CMFCToolBarComboBoxButton::GetCurSelAll  
 Gibt den Index des derzeit ausgewählten Elements im Listenfeld eines Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID.  
  
```  
static int GetCurSelAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID des Kombinationsfelds-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des derzeit ausgewählten Elements im Listenfeld; andernfalls `CB_ERR` Wenn kein Element ausgewählt ist, oder eine kombinationsfeldschaltfläche wurde nicht gefunden.  
  
### <a name="remarks"></a>Hinweise  
 Die listenfeldindex ist nullbasiert.  
  
##  <a name="geteditctrl"></a>CMFCToolBarComboBoxButton::GetEditCtrl  
 Gibt einen Zeiger zurück in das Bearbeitungsfeld in des Kombinationsfelds-Schaltfläche.  
  
```  
virtual CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Eingabefeld ein, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethwnd"></a>CMFCToolBarComboBoxButton::GetHwnd  
 Gibt das Fensterhandle für das Kombinationsfeld zurück.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fensterhandle oder `NULL` , wenn das Kombinationsfeld das nicht mit einem Fensterobjekt verknüpft ist.  
  
##  <a name="getitem"></a>CMFCToolBarComboBoxButton::GetItem  
 Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld zugeordnet.  
  
```  
LPCTSTR GetItem(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Nullbasierten Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Zeichenfolge, die dem Element zugeordnet ist; andernfalls `NULL` Wenn Indexparameter ungültig ist oder wenn Indexparameter ist-1, und es ist kein Element ausgewählt im Kombinationsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Ein Indexparameter "-1" gibt die Zeichenfolge des Elements, das derzeit ausgewählt ist.  
  
##  <a name="getitemall"></a>CMFCToolBarComboBoxButton::GetItemAll  
 Gibt die Zeichenfolge, die ein Element am angegebenen Index im Listenfeld von einer Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID zugeordnet  
  
```  
static LPCTSTR GetItemAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID des Kombinationsfelds-Schaltfläche.  
  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Element-Zeichenfolge, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL` , wenn der Index ungültig ist, wird eine kombinationsfeldschaltfläche nicht gefunden, oder wenn der Index ist-1, und es ist kein Element ausgewählt im Kombinationsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Ein Indexwert-1 gibt die Zeichenfolge des Elements, das derzeit ausgewählt ist.  
  
##  <a name="getitemdata"></a>CMFCToolBarComboBoxButton::GetItemData  
 Gibt ein Element am angegebenen Index in das Listenfeld zugeordneten Daten zurück.  
  
```  
DWORD_PTR GetItemData(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Daten, die dem Element zugeordnet; oder 0, wenn das Element nicht vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Ein Indexparameter "-1" gibt das aktuell ausgewählte Element zugeordneten Daten zurück.  
  
##  <a name="getitemdataall"></a>CMFCToolBarComboBoxButton::GetItemDataAll  
 Gibt ein Element am angegebenen Index in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine bestimmte Befehls-ID wurde zugeordneten Daten  
  
```  
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID des Kombinationsfelds-Schaltfläche.  
  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Daten, die dem Element zugeordnet, wenn die Methode erfolgreich ausgeführt wurde; andernfalls 0, wenn der angegebene Index nicht gültig ist oder CB_ERR, wenn das Kombinationsfeld für den Schaltfläche Feld wurde nicht gefunden.  
  
### <a name="remarks"></a>Hinweise  
 Ein Indexparameter "-1" gibt das aktuell ausgewählte Element zugeordneten Daten zurück.  
  
##  <a name="getitemdataptrall"></a>CMFCToolBarComboBoxButton::GetItemDataPtrAll  
 Gibt ein Element am angegebenen Index in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine bestimmte Befehls-ID wurde zugeordneten Daten Diese Daten werden als Zeiger zurückgegeben.  
  
```  
static void* GetItemDataPtrAll(
    UINT uiCmd,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID des Kombinationsfelds-Schaltfläche.  
  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger, der dem Element zugeordnet, wenn die Methode erfolgreich ausgeführt wurde; Wenn ein Fehler auftritt, andernfalls -1 oder `NULL` , wenn der kombinationsfeldschaltfläche nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getprompt"></a>CMFCToolBarComboBoxButton::GetPrompt  
 Gibt die eingabeaufforderungs-Zeichenfolge für das Kombinationsfeld-Schaltfläche zurück.  
  
```  
virtual CString GetPrompt() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die eingabeaufforderungs-Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird derzeit nicht implementiert.  
  
##  <a name="gettext"></a>CMFCToolBarComboBoxButton::GetText  
 Ruft den Text im Bearbeitungsfeld.  
  
```  
LPCTSTR GetText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Text in das Bearbeitungsfeld.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettextall"></a>CMFCToolBarComboBoxButton::GetTextAll  
 Ruft den Text im Eingabefeld für eine Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID.  
  
```  
static LPCTSTR GetTextAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID von einer bestimmten Kombinationsfelds-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Text im Bearbeitungsfeld, wenn die Methode erfolgreich ausgeführt wurde. andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasfocus"></a>CMFCToolBarComboBoxButton::HasFocus  
 Gibt an, ob das Kombinationsfeld das aktuell den Fokus besitzt.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Kombinationsfeld das aktuell den Fokus besitzt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt auch zurück `TRUE` Wenn beliebige untergeordnete Fenster des Kombinationsfelds aktuell den Fokus besitzt.  
  
##  <a name="iscentervert"></a>CMFCToolBarComboBoxButton::IsCenterVert  
 Gibt die vertikale Position der Schaltflächen in der Anwendung zurück.  
  
```  
static BOOL IsCenterVert();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltflächen zentriert werden; `FALSE` , wenn die Schaltflächen oben ausgerichtet sind.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isflatmode"></a>CMFCToolBarComboBoxButton::IsFlatMode  
 Gibt die flache Darstellung von Schaltflächen in der Anwendung zurück.  
  
```  
static BOOL IsFlatMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltflächen flach verfügen; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Flatfile Standardformat für Schaltflächen ist`FALSE.`  
  
##  <a name="isownerof"></a>CMFCToolBarComboBoxButton::IsOwnerOf  
 Gibt an, ob das angegebene Handle Kombinationsfelds-Schaltfläche oder eines seiner untergeordneten Elemente zugeordnet ist.  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hwnd`  
 Ein Fensterhandle.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Handle Assocated mit dem Kombinationsfelds-Schaltfläche oder eines seiner untergeordneten Elemente ist. andernfalls `FALSE`.  
  
##  <a name="isribbonbutton"></a>CMFCToolBarComboBoxButton::IsRibbonButton  
 Gibt an, ob der kombinationsfeldschaltfläche in einem Menübandbereich befindet.  
  
```  
BOOL IsRibbonButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `FALSE`, womit des Kombinationsfelds-Schaltfläche in einem Menübandbereich nie angezeigt wird.  
  
##  <a name="iswindowvisible"></a>CMFCToolBarComboBoxButton::IsWindowVisible  
 Gibt den Sichtbarkeitszustand des Kombinationsfeld-Schaltfläche.  
  
```  
virtual BOOL IsWindowVisible();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Sichtbarkeitszustand des Kombinationsfelds-Schaltfläche.  
  
##  <a name="notifycommand"></a>CMFCToolBarComboBoxButton::NotifyCommand  
 Gibt an, ob der kombinationsfeldschaltfläche die Nachricht verarbeitet.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iNotifyCode`  
 Die Benachrichtigung, die dem Befehl zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob der kombinationsfeldschaltfläche die Nachricht verarbeitet.  
  
##  <a name="onaddtocustomizepage"></a>CMFCToolBarComboBoxButton::OnAddToCustomizePage  
 Vom Framework aufgerufen, wenn die Schaltfläche "" hinzugefügt wird die **anpassen** (Dialogfeld).  
  
```  
virtual void OnAddToCustomizePage();
```  
  
##  <a name="oncalculatesize"></a>CMFCToolBarComboBoxButton::OnCalculateSize  
 Vom Framework aufgerufen, die Größe der Schaltfläche zu berechnen.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, in dem der kombinationsfeldschaltfläche angezeigt.  
  
 [in] `sizeDefault`  
 Die Standardgröße des Kombinationsfelds-Schaltfläche.  
  
 [in] `bHorz`  
 Der Status der Andocken der übergeordneten Symbolleiste. `TRUE`Wenn die Symbolleiste horizontal angedockt und `FALSE` Wenn die Symbolleiste vertikal verankert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `SIZE` -Struktur, die die Dimensionen der kombinationsfeldschaltfläche in Pixel enthält.  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarComboBoxButton::OnChangeParentWnd  
 Vom Framework aufgerufen, wenn der kombinationsfeldschaltfläche in eine neue Symbolleiste eingefügt wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf den neuen übergeordneten Symbolleiste.  
  
##  <a name="onclick"></a>CMFCToolBarComboBoxButton::OnClick  
 Vom Framework aufgerufen, wenn der Benutzer die Kombinationsfelds-Schaltfläche klickt.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf das übergeordnete Fenster eines Kombinationsfelds-Schaltfläche.  
  
 [in] `bDelay`  
 Reserviert für die Verwendung in einer abgeleiteten Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode mit das Ereignis verarbeitet andernfalls `FALSE`.  
  
##  <a name="onctlcolor"></a>CMFCToolBarComboBoxButton::OnCtlColor  
 Vom Framework aufgerufen, wenn der Benutzer der übergeordneten Symbolleistenfarbe an, die das Kombinationsfeld für den Schaltflächenfarbe festgelegt ändert.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, in dem der kombinationsfeldschaltfläche angezeigt.  
  
 [in] `nCtlColor`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für den Pinsel, den das Framework verwendet, um den Hintergrund des Kombinationsfelds-Schaltfläche zu zeichnen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt auch die Textfarbe für Kombinationsfeld Feld Schaltfläche fest.  
  
##  <a name="ondraw"></a>CMFCToolBarComboBoxButton::OnDraw  
 Wird aufgerufen, durch das Framework der kombinationsfeldschaltfläche gezeichnet werden soll, mithilfe des angegebenen Stile und Optionen.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Pdc`  
 Der Gerätekontext, in dem die Schaltfläche angezeigt.  
  
 [in] `rect`  
 Das umschließende Rechteck der Schaltfläche.  
  
 [in] `pImages`  
 Die Auflistung der Bilder, die die Schaltfläche zugeordnet ist.  
  
 [in] `bHorz`  
 Der Status der Andocken der übergeordneten Symbolleiste. `TRUE`Wenn die Symbolleiste horizontal angedockt und `FALSE` Wenn die Symbolleiste vertikal verankert ist.  
  
 [in] `bCustomizeMode`  
 Gibt an, ob die Anwendung im Anpassungsmodus ist.  
  
 [in] `bHighlight`  
 Ob der kombinationsfeldschaltfläche hervorgehoben gezeichnet werden soll.  
  
 [in] `bDrawBorder`  
 Ob der kombinationsfeldschaltfläche mit einem Rahmen gezeichnet werden soll.  
  
 [in] `bGrayDisabledButtons`  
 `TRUE`schattierte deaktivierte Schaltflächen gezeichnet werden soll; `FALSE` verwenden Sie die deaktivierten Bilder Auflistung.  
  
##  <a name="ondrawoncustomizelist"></a>CMFCToolBarComboBoxButton::OnDrawOnCustomizeList  
 Wird aufgerufen, durch das Framework der kombinationsfeldschaltfläche gezeichnet werden soll, der **Befehle** im Bereich der **anpassen** (Dialogfeld).  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, in dem der kombinationsfeldschaltfläche angezeigt.  
  
 [in] `rect`  
 Das umschließende Rechteck des Kombinationsfelds-Schaltfläche.  
  
 [in] `bSelected`  
 `TRUE`Wenn das Kombinationsfeld für den Schaltfläche Feld ausgewählt ist; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite des Kombinationsfelds-Schaltfläche in Pixel.  
  
##  <a name="onglobalfontschanged"></a>CMFCToolBarComboBoxButton::OnGlobalFontsChanged  
 Wird aufgerufen, durch das Framework das Kombinationsfeld für den Schaltfläche Schriftart festlegen, wenn die Anwendungsschriftart geändert wird.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
##  <a name="onmove"></a>CMFCToolBarComboBoxButton::OnMove  
 Vom Framework aufgerufen wird, ändern den Speicherort des Kombinationsfelds-Schaltfläche, wenn die übergeordneten Symbolleiste verschoben.  
  
```  
virtual void OnMove();
```  
  
##  <a name="onshow"></a>CMFCToolBarComboBoxButton::OnShow  
 Vom Framework aufgerufen, wenn der kombinationsfeldschaltfläche angezeigt oder ausgeblendet wird.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Ob der kombinationsfeldschaltfläche anzeigen oder ausblenden.  
  
##  <a name="onsize"></a>CMFCToolBarComboBoxButton::OnSize  
 Vom Framework aufgerufen wird, ändern die Größe des Kombinationsfelds-Schaltfläche, wenn die übergeordneten Symbolleiste Größe ändert.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iSize`  
 Die neue Breite des Kombinationsfelds-Schaltfläche.  
  
##  <a name="onupdatetooltip"></a>CMFCToolBarComboBoxButton::OnUpdateToolTip  
 Vom Framework aufgerufen, wenn der Benutzer die QuickInfo für die kombinationsfeldschaltfläche ändert.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster für die Kombinationsfelds-Schaltfläche.  
  
 [in] `iButtonIndex`  
 ID des Kombinationsfelds-Schaltfläche.  
  
 [in] `wndToolTip`  
 Die QuickInfo der kombinationsfeldschaltfläche zugeordnet werden soll.  
  
 [in] `str`  
 Der QuickInfo-Text.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode mit das Ereignis verarbeitet andernfalls `FALSE`.  
  
##  <a name="removeallitems"></a>CMFCToolBarComboBoxButton::RemoveAllItems  
 Löscht alle Elemente aus den Dropdownfeldern Liste und zu bearbeiten.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt, die alle Elemente aus der Liste ein und Bearbeitungssteuerelement des Kombinationsfelds.  
  
##  <a name="selectitem"></a>CMFCToolBarComboBoxButton::SelectItem  
 Wählt ein Element im Listenfeld aus.  
  
```  
BOOL SelectItem(
    int iIndex,  
    BOOL bNotify=TRUE);  
  
BOOL SelectItem(DWORD_PTR dwData);  
BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
 [in] `bNotify`  
 `TRUE`Um der Auswahl der kombinationsfeldschaltfläche benachrichtigen; andernfalls `FALSE`.  
  
 [in] `dwData`  
 Die Daten, die einem Element im Listenfeld zugeordnet.  
  
 [in] `lpszText`  
 Der Text eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ausgeführt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="selectitemall"></a>CMFCToolBarComboBoxButton::SelectItemAll  
 Wählt ein Element im Listenfeld von einer Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID  
  
```  
static BOOL SelectItemAll(
    UINT uiCmd,  
    int iIndex);

 
static BOOL SelectItemAll(
    UINT uiCmd,  
    DWORD_PTR dwData);

 
static BOOL SelectItemAll(
    UINT uiCmd,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID der kombinationsfeldschaltfläche an, die im Listenfeld enthält.  
  
 [in] `iIndex`  
 Der nullbasierte Index des Elements im Listenfeld. Der Wert-1 entfernt alle aktuellen Auswahl im Listenfeld und löscht im Bearbeitungsfeld.  
  
 [in] `dwData`  
 Die Daten eines Elements im Listenfeld.  
  
 [in] `lpszText`  
 Der Text eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ausgeführt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="serialize"></a>CMFCToolBarComboBoxButton::Serialize  
 Dieses Objekt aus einem Archiv liest oder schreibt sie in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `ar`  
 Die `CArchive` zu serialisierende Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Einstellungen in der `CArchive` Objekt zu ermitteln, ob diese Methode liest oder schreibt in das Archiv.  
  
##  <a name="setaccdata"></a>CMFCToolBarComboBoxButton::SetACCData  
 Füllt das angegebene `CAccessibilityData` Objekt mithilfe von barrierefreiheitsdaten aus dem Kombinationsfelds-Schaltfläche.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParent`  
 Das übergeordnete Fenster des Kombinationsfelds-Schaltfläche.  
  
 [out] `data`  
 Ein `CAccessibilityData` Objekt, das die barrierefreiheitsdaten aus der kombinationsfeldschaltfläche empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ausgeführt wurde; andernfalls `FALSE`.  
  
##  <a name="setcentervert"></a>CMFCToolBarComboBoxButton::SetCenterVert  
 Legt die vertikale Position der Schaltflächen in der Anwendung fest.  
  
```  
static void SetCenterVert(BOOL bCenterVert=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCenterVert`  
 `TRUE`Um Centers Kombinationsfelds-Schaltfläche auf der Symbolleiste. `FALSE` zum Ausrichten der Kombinationsfelds-Schaltfläche am oberen Rand der Symbolleiste.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig werden die Schaltflächen nach oben ausgerichtet.  
  
##  <a name="setcontextmenuid"></a>CMFCToolBarComboBoxButton::SetContextMenuID  
 Legt die Verknüpfung im Menü-Ressourcen-ID für das Kombinationsfeld-Schaltfläche fest.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiResID`  
 Die Verknüpfung im Menü-Ressourcen-ID.  
  
##  <a name="setdropdownheight"></a>CMFCToolBarComboBoxButton::SetDropDownHeight  
 Legt die Höhe des Listenfelds fest, wenn sie nach unten gelöscht wird.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHeight`  
 Die Höhe in Pixel, der im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardhöhe beträgt 150 Pixel.  
  
##  <a name="setflatmode"></a>CMFCToolBarComboBoxButton::SetFlatMode  
 Legt die flache Darstellung von Schaltflächen in der Anwendung fest.  
  
```  
static void SetFlatMode(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bFlat`  
 `TRUE`für eine flache Darstellung; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Flatfile Standardformat für Schaltflächen ist `FALSE`.  
  
##  <a name="setstyle"></a>CMFCToolBarComboBoxButton::SetStyle  
 Legt das angegebene Format für das Kombinationsfeld-Schaltfläche und zeichnet das Steuerelement neu, wenn er nicht deaktiviert ist.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nStyle`  
 Eine bitweise Kombination (OR) von Toolbar-Stile.  
  
### <a name="remarks"></a>Hinweise  
 Eine Liste der Formatvorlagen für Symbolleistenschaltflächen finden Sie unter [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="settext"></a>CMFCToolBarComboBoxButton::SetText  
 Legt den Text in das Bearbeitungsfeld des Kombinationsfeld-Schaltfläche fest.  
  
```  
void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
 Ein Zeiger auf eine Zeichenfolge, die den Text für das Eingabefeld enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)



