---
title: Klasse CMFCToolBarComboBoxButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarComboBoxButton class
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
caps.latest.revision: 30
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 43369e8869f9dd58543016bd74547b24fbe183a5
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|Fügt ein Element auf der Liste des Kombinationsfelds. Die Reihenfolge der Elemente in der Liste wird anhand des `Compare`.|  
|[CMFCToolBarComboBoxButton::Compare](#compare)|Vergleicht zwei Elemente. Namens sortieren Elemente `AddSortedItems` fügt der Liste des Kombinationsfelds hinzu.|  
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|Erstellt ein neues Edit-Steuerelement für die Kombinationsfelds-Schaltfläche.|  
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|Löscht ein Element aus der Liste des Kombinationsfelds.|  
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|Gibt den Index des Elements, das eine angegebene Zeichenfolge enthält.|  
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|Gibt einen Zeiger auf die Kombinationsfelds-Schaltfläche mit einem angegebenen Befehls-ID.|  
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|Gibt einen Zeiger auf das Kombinationsfeld-Steuerelement, das in der kombinationsfeldschaltfläche eingebettet ist.|  
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|Gibt die Anzahl der Elemente im Kombinationsfeld Liste zurück.|  
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene ID verfügt. Gibt die Anzahl der Elemente im Kombinationsfeld Liste dieser Schaltfläche zurück.|  
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|Gibt den Index des ausgewählten Elements im Kombinationsfeld Liste zurück.|  
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene Befehls-ID und gibt den Index des ausgewählten Elements im Kombinationsfeld Liste dieser Schaltfläche.|  
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|Gibt einen Zeiger auf das Steuerelement zum Bearbeiten, das in der kombinationsfeldschaltfläche eingebettet ist.|  
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Gibt die Zeichenfolge mit einem angegebenen Index in das Kombinationsfeld für den zugeordneten Liste zurück.|  
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene Befehls-ID und gibt die Zeichenfolge zurück, die einen Index in der Liste des Kombinationsfelds dieser Schaltfläche zugeordnet ist.|  
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|32-Bit-Wert zurück, der mit einem angegebenen Index in das Kombinationsfeld verknüpft ist Listenfeld.|  
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene Befehls-ID und 32-Bit-Wert zurück, der einen Index in der Liste des Kombinationsfelds dieser Schaltfläche zugeordnet ist.|  
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene ID verfügt. Ruft verknüpft der 32-Bit-Wert, der einen Index in der Liste des Kombinationsfelds dieser Schaltfläche, und gibt die 32-Bit-Wert als Zeiger zurück.|  
|[CMFCToolBarComboBoxButton::GetText](#gettext)|Gibt den Text in das Steuerelement zum Bearbeiten des Kombinationsfelds.|  
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene Befehls-ID und gibt den Text aus dieser Schaltfläche Edit-Steuerelement.|  
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|Bestimmt, ob Schaltflächen in der Anwendung zentriert oder am oberen Rand der Symbolleiste ausgerichtet sind.|  
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|Bestimmt, ob Schaltflächen in der Anwendung eine flache Darstellung haben.|  
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Entfernt, die alle Elemente aus der Liste im Feld und edit-Steuerelement des Kombinationsfelds.|  
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|Wählt ein Element im Kombinationsfeld gemäß den Index, eine 32-Bit-Wert oder eine Zeichenfolge, und benachrichtigt das Kombinationsfeld-Steuerelement zur Auswahl.|  
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|Sucht das Kombinationsfeld-Schaltfläche, die eine angegebene ID verfügt. Aufrufe `SelectItem` Auswahl ein Elements im Kombinationsfeld dieser Schaltfläche entsprechend der Zeichenfolge, Index oder 32-Bit-Wert.|  
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|Gibt an, ob Schaltflächen in der Anwendung vertikal zentriert oder am oberen Rand der Symbolleiste ausgerichtet werden.|  
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Legt die Höhe der im Dropdown-Listenfeld.|  
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Gibt an, ob Schaltflächen in der Anwendung flach dargestellt.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Kombinationsfelds-Schaltfläche zu einer Symbolleiste hinzuzufügen, gehen Sie folgendermaßen vor:  
  
 1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2. Konstruieren Sie ein `CMFCToolBarComboBoxButton`-Objekt.  
  
 3. In den Message-Handler, verarbeitet die `AFX_WM_RESETTOOLBAR` angezeigt wird, ersetzen Sie die platzhalterschaltfläche mithilfe von mit der neuen kombinationsfeldschaltfläche [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md). Ein Beispiel für eine Symbolleiste kombinationsfeldschaltfläche finden Sie das Beispielprojekt VisualStudioDemo.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCToolBarComboBoxButton` Klasse. Das Beispiel zeigt, wie die Felder bearbeiten und Kombinationsfeld aktivieren, legen Sie die vertikale Position des Kombinationsfelds Schaltflächen in der Anwendung, legen Sie die Höhe des Listenfelds beim Löschen, die flache Darstellung von Schaltflächen in der Anwendung festgelegt, und legen den Text in das Bearbeitungsfeld des Kombinationsfelds-Schaltfläche. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo Nr.&36;](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#37;](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 Der Text des Elements im Listenfeld hinzu.  
  
 [in] `dwData`  
 Die Daten, die Verbindung mit den Elementen im Listenfeld hinzu.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des letzten Elements im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nicht, wenn die Knotenart Liste sortiert wird.  
  
 Wenn der Elementtext bereits im Listenfeld ist, werden die neuen Daten mit vorhandenen Elements gespeichert. Die Suche für den Artikel ist die Groß-/Kleinschreibung beachtet.  
  
##  <a name="addsorteditem"></a>CMFCToolBarComboBoxButton::AddSortedItem  
 Fügt ein Element in die Liste in der Reihenfolge, die durch definiert ist die [vergleichen](#compare) Methode.  
  
```  
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszItem`  
 Der Text des Elements im Listenfeld hinzu.  
  
 [in] `dwData`  
 Die Daten, die Verbindung mit den Elementen im Listenfeld hinzu.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Elements, das im Listenfeld hinzugefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um Elemente in die Liste in einer bestimmten Reihenfolge hinzufügen.  
  
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
 Die Befehls-ID, der die neue Schaltfläche.  
  
 [in] `iImage`  
 Der Index des Bildes von der die neue Schaltfläche zugeordnete Bild.  
  
 [in] `dwStyle`  
 Der Stil der Schaltfläche neu.  
  
 [in] `iWidth`  
 Die Breite in Pixel, der die neue Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardbreite beträgt 150 Pixel.  
  
 Eine Liste der Formatvorlagen für Schaltflächen der Symbolleiste finden Sie unter [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="cleardata"></a>CMFCToolBarComboBoxButton::ClearData  
 Löscht den benutzerdefinierten Daten.  
  
```  
virtual void ClearData();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig bewirkt diese Methode nichts. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn benutzerdefinierte Daten gelöscht werden sollen.  
  
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
|>0|Die erste Zeichenfolge ist größer als der zweite.|  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die ändern, wie die Elemente im Listenfeld sortiert werden.  
  
 Der Vergleich wird die Groß-/Kleinschreibung beachtet.  
  
 Diese Methode wird aufgerufen, nur über die [AddSortedItem](#addsorteditem) Methode.  
  
##  <a name="copyfrom"></a>CMFCToolBarComboBoxButton::CopyFrom  
 Kopiert den Zustand des angegebenen `CMFCToolBarComboBoxButton` auf das aktuelle Objekt.  
  
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
 Ein Zeiger auf die neue Kombinationsfeld, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
##  <a name="createedit"></a>CMFCToolBarComboBoxButton::CreateEdit  
 Erstellt ein neues Eingabefeld für den Kombinationsfelds-Schaltfläche.  
  
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
 Umschließende Rechteck für das neue bearbeiten.  
  
 [in] `dwEditStyle`  
 Das Format des neuen Steuerelements Bearbeitungsfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neue Bearbeitungsfeld, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
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
 Der nullbasierte Index des Elements, das gelöscht werden.  
  
 [in] `dwData`  
 Die Daten, die zu löschenden Element zugeordnet.  
  
 [in] `lpszText`  
 Der Text des Elements, das gelöscht werden. Wenn mehrere Elemente mit demselben Text vorhanden sind, wird das erste Element gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Element gefunden und erfolgreich gelöscht wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="duplicatedata"></a>CMFCToolBarComboBoxButton::DuplicateData  
 Duplikate benutzerdefinierten Daten.  
  
```  
virtual void DuplicateData();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig bewirkt diese Methode nichts. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie benutzerdefinierte Daten kopieren möchten.  
  
##  <a name="enablewindow"></a>CMFCToolBarComboBoxButton::EnableWindow  
 Aktiviert oder deaktiviert die Felder bearbeiten und Kombinationsfeld.  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die Felder bearbeiten und Kombinationsfeld; `FALSE` So deaktivieren Sie die Felder bearbeiten und Kombinationsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Wenn deaktiviert, werden die Steuerelemente können nicht aktiv und können nicht Benutzereingaben akzeptieren.  
  
##  <a name="exporttomenubutton"></a>CMFCToolBarComboBoxButton::ExportToMenuButton  
 Kopiert eine Zeichenfolge in der Tabelle für die Anwendung, die das angegebene Menü mit dem Kombinationsfeld ein schaltflächenbefehl-ID.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `menuButton`  
 Verweis auf eine Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
##  <a name="finditem"></a>CMFCToolBarComboBoxButton::FindItem  
 Gibt den Index des ersten Elements im Listenfeld, das eine angegebene Zeichenfolge enthält.  
  
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
 Ruft einen Zeiger auf die Kombinationsfelds-Schaltfläche, die eine angegebene ID verfügt.  
  
```  
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,  
    BOOL bIsFocus=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID des Kombinationsfelds-Schaltfläche.  
  
 [in] `bIsFocus`  
 `TRUE`konzentrieren Schaltflächen, um nur zu suchen; `FALSE` alle Schaltflächen zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine kombinationsfeldschaltfläche; oder `NULL` , wenn die Schaltfläche nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcombobox"></a>CMFCToolBarComboBoxButton::GetComboBox  
 Gibt einen Zeiger zurück an das Kombinationsfeld im Kombinationsfeld-Schaltfläche.  
  
```  
CComboBox* GetComboBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md) Objekt, wenn die Methode erfolgreich, andernfalls war `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcontextmenuid"></a>CMFCToolBarComboBoxButton::GetContextMenuID  
 Ruft die Verknüpfung im Menü Ressourcen-ID für die Kombinationsfelds-Schaltfläche.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Verknüpfung im Menü Ressourcen-ID.  
  
##  <a name="getcount"></a>CMFCToolBarComboBoxButton::GetCount  
 Gibt die Anzahl der Elemente im Listenfeld.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcountall"></a>CMFCToolBarComboBoxButton::GetCountAll  
 Ruft die Anzahl der Elemente in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine angegebene ID verfügt.  
  
```  
static int GetCountAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID des Kombinationsfelds-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Listenfeld; andernfalls `CB_ERR` wird der kombinationsfeldschaltfläche nicht gefunden.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcursel"></a>CMFCToolBarComboBoxButton::GetCurSel  
 Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des derzeit ausgewählten Elements im Listenfeld; oder `CB_ERR` , wenn kein Element ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste im Feld Index ist nullbasiert.  
  
##  <a name="getcurselall"></a>CMFCToolBarComboBoxButton::GetCurSelAll  
 Gibt den Index des derzeit ausgewählten Elements im Listenfeld eines Kombinationsfelds-Schaltfläche, die eine angegebene ID verfügt.  
  
```  
static int GetCurSelAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID des Kombinationsfelds-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des derzeit ausgewählten Elements im Listenfeld; andernfalls `CB_ERR` , wenn kein Element ausgewählt ist, oder eine Kombinationsfelds-Schaltfläche wurde nicht gefunden.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste im Feld Index ist nullbasiert.  
  
##  <a name="geteditctrl"></a>CMFCToolBarComboBoxButton::GetEditCtrl  
 Gibt einen Zeiger zurück in das Bearbeitungsfeld im Kombinationsfeld-Schaltfläche.  
  
```  
virtual CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Bearbeitungsfeld, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethwnd"></a>CMFCToolBarComboBoxButton::GetHwnd  
 Gibt das Fensterhandle für das Kombinationsfeld zurück.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fensterhandle oder `NULL` Wenn das Kombinationsfeld kein Window-Objekt zugeordnet ist.  
  
##  <a name="getitem"></a>CMFCToolBarComboBoxButton::GetItem  
 Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld zugeordnet.  
  
```  
LPCTSTR GetItem(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Nullbasierten Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Zeichenfolge, die dem Element zugeordnet ist; andernfalls `NULL` , wenn der Indexparameter ungültig ist oder wenn der Indexparameter ist-1 und gibt es kein Element ausgewählt ist, im Kombinationsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Ein Indexparameter-1 gibt die Zeichenfolge des Elements, das derzeit ausgewählt ist.  
  
##  <a name="getitemall"></a>CMFCToolBarComboBoxButton::GetItemAll  
 Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine angegebene Befehls-ID zugeordnet  
  
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
 Ein Zeiger auf das Element-Zeichenfolge, wenn die Methode erfolgreich war; andernfalls `NULL` Wenn der Index ungültig ist, ist eine Kombinationsfelds-Schaltfläche nicht gefunden, oder wenn der Index-1 und gibt es kein Element ausgewählt ist, im Kombinationsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Ein Indexwert von-1 gibt die Zeichenfolge des Elements, das derzeit ausgewählt ist.  
  
##  <a name="getitemdata"></a>CMFCToolBarComboBoxButton::GetItemData  
 Gibt ein Element am angegebenen Index in das Listenfeld zugeordneten Daten zurück.  
  
```  
DWORD_PTR GetItemData(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Daten, die dem Element zugeordnete; oder 0, wenn das Element nicht vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Ein Indexparameter-1 gibt das aktuell ausgewählte Element zugeordneten Daten zurück.  
  
##  <a name="getitemdataall"></a>CMFCToolBarComboBoxButton::GetItemDataAll  
 Gibt ein Element am angegebenen Index in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine bestimmten Befehls-ID zugeordneten Daten  
  
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
 Die Daten, die dem Element zugeordnet ist, wenn die Methode erfolgreich war. andernfalls 0, wenn der angegebene Index nicht gültig ist oder CB_ERR, wenn das Kombinationsfeld Schaltfläche Feld wurde nicht gefunden.  
  
### <a name="remarks"></a>Hinweise  
 Ein Indexparameter-1 gibt das aktuell ausgewählte Element zugeordneten Daten zurück.  
  
##  <a name="getitemdataptrall"></a>CMFCToolBarComboBoxButton::GetItemDataPtrAll  
 Gibt ein Element am angegebenen Index in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine bestimmten Befehls-ID zugeordneten Daten Diese Daten werden als Zeiger zurückgegeben.  
  
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
 Ein Zeiger, der dem Element zugeordnet ist, wenn die Methode erfolgreich war; Wenn ein Fehler auftritt, andernfalls -1 oder `NULL` wird der kombinationsfeldschaltfläche nicht gefunden.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getprompt"></a>CMFCToolBarComboBoxButton::GetPrompt  
 Gibt die eingabeaufforderungs-Zeichenfolge für das Kombinationsfeld-Schaltfläche zurück.  
  
```  
virtual CString GetPrompt() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die eingabeaufforderungs-Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist derzeit nicht implementiert.  
  
##  <a name="gettext"></a>CMFCToolBarComboBoxButton::GetText  
 Ruft den Text im Bearbeitungsfeld.  
  
```  
LPCTSTR GetText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Text im Bearbeitungsfeld.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettextall"></a>CMFCToolBarComboBoxButton::GetTextAll  
 Ruft den Text im Eingabefeld für eine Kombinationsfelds-Schaltfläche, die eine angegebene ID verfügt.  
  
```  
static LPCTSTR GetTextAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID von einem bestimmten Kombinationsfelds-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Text im Bearbeitungsfeld, wenn die Methode erfolgreich war. andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasfocus"></a>CMFCToolBarComboBoxButton::HasFocus  
 Gibt an, ob das Kombinationsfeld gegenwärtig den Fokus besitzt.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Kombinationsfeld gegenwärtig den Fokus besitzt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt auch `TRUE` , wenn untergeordneten Fenster des Kombinationsfelds derzeit den Fokus besitzt.  
  
##  <a name="iscentervert"></a>CMFCToolBarComboBoxButton::IsCenterVert  
 Gibt die vertikale Position der Schaltflächen in der Anwendung zurück.  
  
```  
static BOOL IsCenterVert();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltflächen zentriert werden; `FALSE` Wenn die Schaltflächen oben ausgerichtet sind.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isflatmode"></a>CMFCToolBarComboBoxButton::IsFlatMode  
 Gibt die flache Darstellung von Schaltflächen in der Anwendung zurück.  
  
```  
static BOOL IsFlatMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn alle Schaltflächen flach sind; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wird von der flachen Standardstil für Schaltflächen`FALSE.`  
  
##  <a name="isownerof"></a>CMFCToolBarComboBoxButton::IsOwnerOf  
 Gibt an, ob das angegebene Handle der Kombinationsfelds-Schaltfläche oder eines seiner untergeordneten Elemente zugeordnet ist.  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hwnd`  
 Ein Fensterhandle.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Handle Assocated mit der Kombinationsfelds-Schaltfläche oder eines seiner untergeordneten Elemente ist. andernfalls `FALSE`.  
  
##  <a name="isribbonbutton"></a>CMFCToolBarComboBoxButton::IsRibbonButton  
 Gibt an, ob die Kombinationsfelds-Schaltfläche in einem Menübandbereich befindet.  
  
```  
BOOL IsRibbonButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `FALSE`, womit das Kombinationsfeld-Schaltfläche wird nie in einem Menübandbereich angezeigt.  
  
##  <a name="iswindowvisible"></a>CMFCToolBarComboBoxButton::IsWindowVisible  
 Gibt den Sichtbarkeitsstatus des Kombinationsfeld-Schaltfläche.  
  
```  
virtual BOOL IsWindowVisible();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den Sichtbarkeitszustand des Kombinationsfelds-Schaltfläche.  
  
##  <a name="notifycommand"></a>CMFCToolBarComboBoxButton::NotifyCommand  
 Gibt an, ob der kombinationsfeldschaltfläche die Nachricht verarbeitet.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iNotifyCode`  
 Die Nachricht, die mit dem Befehl zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob der kombinationsfeldschaltfläche die Nachricht verarbeitet.  
  
##  <a name="onaddtocustomizepage"></a>CMFCToolBarComboBoxButton::OnAddToCustomizePage  
 Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird die **anpassen** Dialogfeld.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
##  <a name="oncalculatesize"></a>CMFCToolBarComboBoxButton::OnCalculateSize  
 Aufgerufen, um die Größe der Schaltfläche zu berechnen.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, in dem die Kombinationsfelds-Schaltfläche angezeigt.  
  
 [in] `sizeDefault`  
 Die Standardgröße des Kombinationsfelds-Schaltfläche.  
  
 [in] `bHorz`  
 Der Status der Andocken der übergeordneten Symbolleiste. `TRUE`Wenn die Symbolleiste horizontal verankert ist und `FALSE` Wenn die Symbolleiste vertikal verankert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `SIZE` -Struktur, die Dimensionen der kombinationsfeldschaltfläche in Pixel enthält.  
  
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
 Ein Zeiger auf das übergeordnete Fenster des Kombinationsfelds-Schaltfläche.  
  
 [in] `bDelay`  
 Reserviert für die Verwendung in einer abgeleiteten Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode das Ereignis behandelt. andernfalls `FALSE`.  
  
##  <a name="onctlcolor"></a>CMFCToolBarComboBoxButton::OnCtlColor  
 Wird vom Framework aufgerufen, wenn der Benutzer der übergeordneten Symbolleistenfarbe an, die das Kombinationsfeld Schaltflächenfarbe festgelegt wird.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, in dem die Kombinationsfelds-Schaltfläche angezeigt.  
  
 [in] `nCtlColor`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für den Pinsel aus, dem das Framework zum Zeichnen des Hintergrunds der kombinationsfeldschaltfläche verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt außerdem die Textfarbe der Kombinationsfeld-Feld-Schaltfläche.  
  
##  <a name="ondraw"></a>CMFCToolBarComboBoxButton::OnDraw  
 Aufgerufen, die Kombinationsfelds-Schaltfläche zeichnen, mithilfe der angegebenen Formate und -Optionen.  
  
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
 Der Gerätekontext, der die Schaltfläche angezeigt.  
  
 [in] `rect`  
 Das umschließende Rechteck der Schaltfläche.  
  
 [in] `pImages`  
 Die Auflistung der Bilder, die der Schaltfläche zugeordnet ist.  
  
 [in] `bHorz`  
 Der Status der Andocken der übergeordneten Symbolleiste. `TRUE`Wenn die Symbolleiste horizontal verankert ist und `FALSE` Wenn die Symbolleiste vertikal verankert ist.  
  
 [in] `bCustomizeMode`  
 Gibt an, ob die Anwendung im Anpassungsmodus ist.  
  
 [in] `bHighlight`  
 Ob die hervorgehobenen Kombinationsfelds-Schaltfläche gezeichnet werden soll.  
  
 [in] `bDrawBorder`  
 Ob die Kombinationsfelds-Schaltfläche mit einem Rahmen gezeichnet werden soll.  
  
 [in] `bGrayDisabledButtons`  
 `TRUE`schattierte deaktivierte Schaltflächen gezeichnet; `FALSE` verwenden die deaktivierten images Auflistung.  
  
##  <a name="ondrawoncustomizelist"></a>CMFCToolBarComboBoxButton::OnDrawOnCustomizeList  
 Aufgerufen, die Kombinationsfelds-Schaltfläche zeichnen, der **Befehle** im Bereich der **anpassen** im Dialogfeld.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, in dem die Kombinationsfelds-Schaltfläche angezeigt.  
  
 [in] `rect`  
 Das umschließende Rechteck des Kombinationsfelds-Schaltfläche.  
  
 [in] `bSelected`  
 `TRUE`Wenn das Kombinationsfeld Schaltfläche Feld ausgewählt ist. andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite des Kombinationsfelds-Schaltfläche in Pixel.  
  
##  <a name="onglobalfontschanged"></a>CMFCToolBarComboBoxButton::OnGlobalFontsChanged  
 Vom Framework aufgerufen wird das Kombinationsfeld Schaltfläche Schriftart festlegen, wenn die Anwendungsschriftart geändert wird.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
##  <a name="onmove"></a>CMFCToolBarComboBoxButton::OnMove  
 Vom Framework aufgerufen wird, ändern den Speicherort des Kombinationsfelds-Schaltfläche, wenn die übergeordneten Symbolleiste verschoben.  
  
```  
virtual void OnMove();
```  
  
##  <a name="onshow"></a>CMFCToolBarComboBoxButton::OnShow  
 Wird vom Framework aufgerufen, wenn der kombinationsfeldschaltfläche angezeigt oder ausgeblendet wird.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Ob der kombinationsfeldschaltfläche angezeigt oder ausgeblendet.  
  
##  <a name="onsize"></a>CMFCToolBarComboBoxButton::OnSize  
 Vom Framework aufgerufen wird, ändern die Größe des Kombinationsfelds-Schaltfläche, wenn die übergeordneten Symbolleiste Größe geändert wird.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iSize`  
 Die neue Breite des Kombinationsfelds-Schaltfläche.  
  
##  <a name="onupdatetooltip"></a>CMFCToolBarComboBoxButton::OnUpdateToolTip  
 Wird vom Framework aufgerufen, wenn der Benutzer die QuickInfo für die Kombinationsfelds-Schaltfläche ändert.  
  
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
 Die QuickInfo, die kombinationsfeldschaltfläche zugeordnet werden soll.  
  
 [in] `str`  
 Der QuickInfo-Text.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode das Ereignis behandelt. andernfalls `FALSE`.  
  
##  <a name="removeallitems"></a>CMFCToolBarComboBoxButton::RemoveAllItems  
 Löscht alle Elemente aus der Liste, und bearbeiten Sie Felder.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt, die alle Elemente aus der Liste im Feld und edit-Steuerelement eines Kombinationsfelds.  
  
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
 `TRUE`der kombinationsfeldschaltfläche der Auswahl benachrichtigt wird; andernfalls `FALSE`.  
  
 [in] `dwData`  
 Die Daten eines Elements im Listenfeld.  
  
 [in] `lpszText`  
 Der Text eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="selectitemall"></a>CMFCToolBarComboBoxButton::SelectItemAll  
 Wählt ein Element in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine angegebene ID verfügt.  
  
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
 Die Befehls-ID von der kombinationsfeldschaltfläche, die im Listenfeld enthält.  
  
 [in] `iIndex`  
 Der nullbasierte Index des Elements im Listenfeld. Der Wert-1 entfernt aktuelle Auswahl im Listenfeld und löscht das Bearbeitungsfeld.  
  
 [in] `dwData`  
 Die Daten eines Elements im Listenfeld.  
  
 [in] `lpszText`  
 Der Text eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="serialize"></a>CMFCToolBarComboBoxButton::Serialize  
 Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `ar`  
 Die `CArchive` zu serialisierende Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Einstellungen in der `CArchive` Objekt zu bestimmen, ob diese Methode liest oder schreibt in das Archiv.  
  
##  <a name="setaccdata"></a>CMFCToolBarComboBoxButton::SetACCData  
 Füllt das angegebene `CAccessibilityData` Objekt mit Zugriff auf Daten aus der kombinationsfeldschaltfläche.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParent`  
 Das übergeordnete Fenster des Kombinationsfelds-Schaltfläche.  
  
 [out] `data`  
 Ein `CAccessibilityData` -Objekt, das den Zugriff auf Daten aus der kombinationsfeldschaltfläche empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
##  <a name="setcentervert"></a>CMFCToolBarComboBoxButton::SetCenterVert  
 Legt die vertikale Position der Schaltflächen in der Anwendung fest.  
  
```  
static void SetCenterVert(BOOL bCenterVert=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCenterVert`  
 `TRUE`So zentrieren Sie die Kombinationsfelds-Schaltfläche in der Symbolleiste; `FALSE` der Kombinationsfelds-Schaltfläche auf der Symbolleiste oben ausgerichtet.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig werden die Schaltflächen nach oben ausgerichtet.  
  
##  <a name="setcontextmenuid"></a>CMFCToolBarComboBoxButton::SetContextMenuID  
 Legt die Verknüpfung im Menü Ressourcen-ID für das Kombinationsfeld-Schaltfläche fest.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiResID`  
 Die Verknüpfung im Menü Ressourcen-ID.  
  
##  <a name="setdropdownheight"></a>CMFCToolBarComboBoxButton::SetDropDownHeight  
 Legt die Höhe des Listenfelds fest, wenn es sichtbar ist.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHeight`  
 Die Höhe in Pixel, der im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardhöhe ist 150 Pixel.  
  
##  <a name="setflatmode"></a>CMFCToolBarComboBoxButton::SetFlatMode  
 Legt die flache Darstellung von Schaltflächen in der Anwendung fest.  
  
```  
static void SetFlatMode(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bFlat`  
 `TRUE`für eine flache Darstellung; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die flache Standardstil für Schaltflächen ist `FALSE`.  
  
##  <a name="setstyle"></a>CMFCToolBarComboBoxButton::SetStyle  
 Legt das angegebene Format für das Kombinationsfeld-Schaltfläche und zeichnet das Steuerelement neu, wenn er nicht deaktiviert ist.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nStyle`  
 Eine bitweise Kombination (OR) der Toolbar-Stile.  
  
### <a name="remarks"></a>Hinweise  
 Eine Liste der Formatvorlagen für Schaltflächen der Symbolleiste finden Sie unter [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md)  
  
##  <a name="settext"></a>CMFCToolBarComboBoxButton::SetText  
 Legt den Text in das Bearbeitungsfeld des Kombinationsfeld-Schaltfläche fest.  
  
```  
void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
 Ein Zeiger auf eine Zeichenfolge, die den Text für das Bearbeitungsfeld enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Exemplarische Vorgehensweise: Einfügen von Steuerelementen in Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md)




