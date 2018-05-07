---
title: CMFCRibbonComboBox Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ebe013e8ce674efb0782112cc8cbc8b1462ef24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox-Klasse
Die `CMFCRibbonComboBox` Klasse implementiert ein Kombinationsfeld-Steuerelement, das einer menübandleiste, einem Menübandbereich oder einem Menüband-Popupmenü hinzugefügt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## <a name="members"></a>Member  
  
### <a name="constructors"></a>Konstruktoren  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|Erstellt ein CMFCRibbonComboBox-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonComboBox::AddItem](#additem)|Fügt ein eindeutiges Element in das Listenfeld.|  
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Löscht ein angegebenes Element aus dem Listenfeld aus.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Gibt an, ob das Listenfeld Größe ändern kann, wenn sie nach unten fällt.|  
|[CMFCRibbonComboBox::FindItem](#finditem)|Gibt den Index des ersten Elements in der Liste, die einer angegebenen Zeichenfolge übereinstimmt.|  
|[CMFCRibbonComboBox::GetCount](#getcount)|Gibt die Anzahl der Elemente in der Liste zurück.|  
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.|  
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Ruft die Höhe des Listenfelds ab, wenn Sie im Listenfeld nach unten gelöscht wird.|  
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Gibt die Größe des Kombinationsfelds zurück, wie er im Zwischenstatus angezeigt.|  
|[CMFCRibbonComboBox::GetItem](#getitem)|Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld zugeordnet.|  
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Gibt ein Element am angegebenen Index in das Listenfeld zugeordneten Daten zurück.|  
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Gibt an, ob das Steuerelement ein Bearbeitungsfeld enthält.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Gibt an, und zwar unabhängig davon, ob das Listenfeld Größe geändert werden kann.|  
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Wird vom Framework aufgerufen, wenn der Benutzer ein Element im Listenfeld auswählt.|  
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Löscht alle Elemente aus dem Listenfeld aus, und löscht im Bearbeitungsfeld.|  
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Wählt ein Element im Listenfeld aus.|  
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Legt die Höhe des Listenfelds fest, wenn sie nach unten gelöscht wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die Menüband-Kombinationsfeld besteht aus einem Listenfeld, kombiniert mit einem statische Bezeichnung oder Beschriftung, die vom Benutzer bearbeitet werden kann. Sie müssen angeben, welche Art sollen, wenn Sie die Menüband-Kombinationsfeld erstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel veranschaulicht, wie ein Objekt des erstellen die `CMFCRibbonComboBox` Klasse, ein Element im Kombinationsfeld hinzufügen, wählen Sie ein Element im Kombinationsfeld und ein Kombinationsfeld, wenn ein Bereich hinzufügen.  
  
 [!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncombobox.h  
  
##  <a name="additem"></a>  CMFCRibbonComboBox::AddItem  
 Fügt ein eindeutiges Element in das Listenfeld.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszItem`  
 Die Zeichenfolge des hinzuzufügenden Elements.  
  
 [in] `dwData`  
 Die Daten, die das hinzuzufügende Element zugeordnet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des hinzugefügten Elements.  
  
##  <a name="cmfcribboncombobox"></a>  CMFCRibbonComboBox::CMFCRibbonComboBox  
 Erstellt ein `CMFCRibbonComboBox`-Objekt.  
  
```  
public:  
CMFCRibbonComboBox(
    UINT nID,  
    BOOL bHasEditBox=TRUE,  
    Int nWidth=-1,  
    LPCTSTR lpszLabel=NULL,  
    Int nImage=-1);

protected:  
CMFCRibbonComboBox();
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die ID des Kombinationsfelds.  
  
 [in] `bHasEditBox`  
 `TRUE` Wenn Sie ein Eingabefeld innerhalb des Steuerelements möchten; `FALSE` andernfalls.  
  
 [in] `nWidth`  
 Die Breite des Kombinationsfelds in Pixel; oder -1 für die Standardbreite.  
  
 [in] `lpszLabel`  
 Die Bezeichnung der Anzeige des Kombinationsfelds.  
  
 [in] `nImage`  
 Der Index der Miniaturansicht des Kombinationsfelds.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardbreite beträgt 108 Pixel.  
  
##  <a name="deleteitem"></a>  CMFCRibbonComboBox::DeleteItem  
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
 Die Zeichenfolge des Elements gelöscht werden soll. Wenn mehrere Elemente mit derselben Zeichenfolge vorhanden sind, wird das erste Element gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das angegebene Element gelöscht wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabledropdownlistresize"></a>  CMFCRibbonComboBox::EnableDropDownListResize  
 Gibt an, ob das Listenfeld Größe ändern kann, wenn sie nach unten fällt.  
  
```  
void EnableDropDownListResize(BOOL bEnable=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` So aktivieren Sie das Ändern der Größe; `FALSE` Größenänderung deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Beim Ändern der Größe aktiviert ist, ändern Sie im Listenfeld Größe der Elemente, die angezeigt.  
  
##  <a name="finditem"></a>  CMFCRibbonComboBox::FindItem  
 Gibt den Index des ersten Elements in der Liste, die einer angegebenen Zeichenfolge übereinstimmt.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
 Die Zeichenfolge eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Elements; oder -1, wenn das Element nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcount"></a>  CMFCRibbonComboBox::GetCount  
 Gibt die Anzahl der Elemente in der Liste zurück.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in das Listenfeld oder 0, wenn das Listenfeld keine Elemente enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcursel"></a>  CMFCRibbonComboBox::GetCurSel  
 Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des derzeit ausgewählten Elements im Listenfeld; oder -1, wenn kein Element ausgewählt ist.  
  
##  <a name="getdropdownheight"></a>  CMFCRibbonComboBox::GetDropDownHeight  
 Ruft die Höhe des Listenfelds ab, wenn Sie im Listenfeld nach unten gelöscht wird.  
  
```  
int GetDropDownHeight();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel, der im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonComboBox::GetIntermediateSize  
 Gibt die Größe des Kombinationsfelds zurück, wie er im Zwischenstatus angezeigt.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für das Kombinationsfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Kombinationsfelds.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Größe basiert auf der Größe des Kombinationsfelds kleine Bilder erkennbar.  
  
##  <a name="getitem"></a>  CMFCRibbonComboBox::GetItem  
 Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld zugeordnet.  
  
```  
LPCTSTR GetItem(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Zeichenfolge, die dem Element zugeordnet ist; andernfalls `NULL` Wenn Indexparameter ungültig ist oder wenn Indexparameter ist-1, und es ist kein Element im Kombinationsfeld ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getitemdata"></a>  CMFCRibbonComboBox::GetItemData  
 Gibt ein Element am angegebenen Index in das Listenfeld zugeordneten Daten zurück.  
  
```  
DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Daten, die dem Element zugeordnet; oder 0, wenn das Element nicht vorhanden ist oder wenn Indexparameter ist-1, und es in das Listenfeld ist kein Element ausgewählt.  
  
##  <a name="haseditbox"></a>  CMFCRibbonComboBox::HasEditBox  
 Gibt an, ob das Steuerelement ein Bearbeitungsfeld enthält.  
  
```  
BOOL HasEditBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Steuerelement ein Bearbeitungsfeld enthält; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isresizedropdownlist"></a>  CMFCRibbonComboBox::IsResizeDropDownList  
 Gibt an, und zwar unabhängig davon, ob das Listenfeld Größe geändert werden kann.  
  
```  
BOOL IsResizeDropDownList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Sie im Listenfeld angepasst werden kann. andernfalls `FALSE`. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)  
  
### <a name="remarks"></a>Hinweise  
 Aktivieren Sie Liste Feld Größe ändern, indem Sie mit der [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) Methode.  
  
##  <a name="onselectitem"></a>  CMFCRibbonComboBox::OnSelectItem  
 Wird vom Framework aufgerufen, wenn ein Benutzer ein Element im Listenfeld auswählt.  
  
```  
virtual void OnSelectItem(int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nItem`  
 Der Index des ausgewählten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie eine Eingabe Benutzerauswahl verarbeiten möchten.  
  
##  <a name="removeallitems"></a>  CMFCRibbonComboBox::RemoveAllItems  
 Löscht alle Elemente aus dem Listenfeld aus, und löscht im Bearbeitungsfeld.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="selectitem"></a>  CMFCRibbonComboBox::SelectItem  
 Wählt ein Element im Listenfeld aus.  
  
```  
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
 [in] `dwData`  
 Die Daten, die einem Element im Listenfeld zugeordnet.  
  
 [in] `lpszText`  
 Die Zeichenfolge eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Methode erfolgreich ausgeführt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdropdownheight"></a>  CMFCRibbonComboBox::SetDropDownHeight  
 Legt die Höhe des Listenfelds fest, wenn sie nach unten gelöscht wird.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHeight`  
 Die Höhe in Pixel, der im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardhöhe beträgt 150 Pixel.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonEdit-Klasse](../../mfc/reference/cmfcribbonedit-class.md)
