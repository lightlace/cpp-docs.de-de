---
title: Klasse CMFCRibbonComboBox | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonComboBox
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonComboBox class
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
caps.latest.revision: 35
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 747006ee66445eb312c22d658706e5fe81d2a958
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox-Klasse
Die `CMFCRibbonComboBox` -Klasse implementiert ein Kombinationsfeld-Steuerelement, das einer menübandleiste, einem Menübandbereich oder einem Menüband-Popupmenü hinzugefügt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="constructors"></a>Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|Erstellt ein CMFCRibbonComboBox-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonComboBox::AddItem](#additem)|Fügt ein eindeutiges Element in das Listenfeld.|  
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Löscht ein angegebenes Element aus dem Listenfeld aus.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Gibt an, ob im Listenfeld Größe geändert werden kann, wenn sie nach unten fällt.|  
|[CMFCRibbonComboBox::FindItem](#finditem)|Gibt den Index des ersten Elements im Listenfeld, das einer angegebenen Zeichenfolge übereinstimmt.|  
|[CMFCRibbonComboBox::GetCount](#getcount)|Gibt die Anzahl der Elemente im Listenfeld.|  
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.|  
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Ruft die Höhe des Listenfelds ab, wenn im Listenfeld nach unten gelöscht wird.|  
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Gibt die Größe des Kombinationsfelds zurück, wie in den Zwischenstatus angezeigt.|  
|[CMFCRibbonComboBox::GetItem](#getitem)|Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld zugeordnet.|  
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Gibt ein Element am angegebenen Index in das Listenfeld zugeordneten Daten zurück.|  
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Gibt an, ob das Steuerelement ein Bearbeitungsfeld enthält.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Gibt an, ob das Listenfeld angepasst werden kann.|  
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Wird vom Framework aufgerufen, wenn der Benutzer ein Element im Listenfeld auswählt.|  
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Löscht alle Elemente aus dem Listenfeld aus, und löscht das Bearbeitungsfeld.|  
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Wählt ein Element im Listenfeld aus.|  
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Legt die Höhe des Listenfelds fest, wenn es sichtbar ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die Menüband-Kombinationsfeld besteht aus einem Listenfeld kombiniert mit einem statische Bezeichnung oder Beschriftung, die vom Benutzer bearbeitet werden kann. Sie müssen angeben, welcher Typ sollen, wenn die Menüband-Kombinationsfeld zu erstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCRibbonComboBox` -Klasse im Kombinationsfeld ein Element hinzuzufügen, wählen Sie ein Element im Kombinationsfeld und fügen Sie ein Kombinationsfeld in einem Bereich.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#11;](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncombobox.h  
  
##  <a name="a-nameadditema--cmfcribboncomboboxadditem"></a><a name="additem"></a>CMFCRibbonComboBox::AddItem  
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
  
##  <a name="a-namecmfcribboncomboboxa--cmfcribboncomboboxcmfcribboncombobox"></a><a name="cmfcribboncombobox"></a>CMFCRibbonComboBox::CMFCRibbonComboBox  
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
 `TRUE`Wenn Sie ein Eingabefeld innerhalb des Steuerelements möchten; `FALSE` andernfalls.  
  
 [in] `nWidth`  
 Die Breite des Kombinationsfelds in Pixel; oder -1 für die Standardbreite.  
  
 [in] `lpszLabel`  
 Die Bezeichnung der Anzeige des Kombinationsfelds.  
  
 [in] `nImage`  
 Der Index der Miniaturansicht des Kombinationsfelds.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardbreite beträgt 108 Pixel.  
  
##  <a name="a-namedeleteitema--cmfcribboncomboboxdeleteitem"></a><a name="deleteitem"></a>CMFCRibbonComboBox::DeleteItem  
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
 Die Zeichenfolge des Elements, das gelöscht werden. Wenn mehrere Elemente mit derselben Zeichenfolge vorhanden sind, wird das erste Element gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das angegebene Element gelöscht wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameenabledropdownlistresizea--cmfcribboncomboboxenabledropdownlistresize"></a><a name="enabledropdownlistresize"></a>CMFCRibbonComboBox::EnableDropDownListResize  
 Gibt an, ob im Listenfeld Größe geändert werden kann, wenn sie nach unten fällt.  
  
```  
void EnableDropDownListResize(BOOL bEnable=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die Größe ändern; `FALSE` zum Ändern der Größe zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Beim Ändern der Größe aktiviert ist, wird im Listenfeld Größe angepasst angezeigten Elemente ändern.  
  
##  <a name="a-namefinditema--cmfcribboncomboboxfinditem"></a><a name="finditem"></a>CMFCRibbonComboBox::FindItem  
 Gibt den Index des ersten Elements im Listenfeld, das einer angegebenen Zeichenfolge übereinstimmt.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
 Die Zeichenfolge eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Elements; oder -1, wenn das Element nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetcounta--cmfcribboncomboboxgetcount"></a><a name="getcount"></a>CMFCRibbonComboBox::GetCount  
 Gibt die Anzahl der Elemente im Listenfeld.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Listenfeld oder 0, wenn das Listenfeld keine Elemente enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetcursela--cmfcribboncomboboxgetcursel"></a><a name="getcursel"></a>CMFCRibbonComboBox::GetCurSel  
 Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des derzeit ausgewählten Elements im Listenfeld; oder -1, wenn kein Element ausgewählt ist.  
  
##  <a name="a-namegetdropdownheighta--cmfcribboncomboboxgetdropdownheight"></a><a name="getdropdownheight"></a>CMFCRibbonComboBox::GetDropDownHeight  
 Ruft die Höhe des Listenfelds ab, wenn im Listenfeld nach unten gelöscht wird.  
  
```  
int GetDropDownHeight();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel, der im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetintermediatesizea--cmfcribboncomboboxgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonComboBox::GetIntermediateSize  
 Gibt die Größe des Kombinationsfelds zurück, wie in den Zwischenstatus angezeigt.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext für das Kombinationsfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Kombinationsfelds.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Größe basiert auf der Größe des Kombinationsfelds Wenn kleine Bilder angezeigt.  
  
##  <a name="a-namegetitema--cmfcribboncomboboxgetitem"></a><a name="getitem"></a>CMFCRibbonComboBox::GetItem  
 Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld zugeordnet.  
  
```  
LPCTSTR GetItem(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Zeichenfolge, die dem Element zugeordnet ist; andernfalls `NULL` Wenn der Indexparameter ungültig ist oder der Indexparameter ist-1 und kein Element im Kombinationsfeld ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetitemdataa--cmfcribboncomboboxgetitemdata"></a><a name="getitemdata"></a>CMFCRibbonComboBox::GetItemData  
 Gibt ein Element am angegebenen Index in das Listenfeld zugeordneten Daten zurück.  
  
```  
DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Daten, die dem Element zugeordnete; oder 0, wenn das Element nicht vorhanden ist oder wenn der Indexparameter ist-1 und gibt es kein Element ausgewählt ist, im Listenfeld.  
  
##  <a name="a-namehaseditboxa--cmfcribboncomboboxhaseditbox"></a><a name="haseditbox"></a>CMFCRibbonComboBox::HasEditBox  
 Gibt an, ob das Steuerelement ein Bearbeitungsfeld enthält.  
  
```  
BOOL HasEditBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Steuerelement ein Bearbeitungsfeld enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisresizedropdownlista--cmfcribboncomboboxisresizedropdownlist"></a><a name="isresizedropdownlist"></a>CMFCRibbonComboBox::IsResizeDropDownList  
 Gibt an, ob das Listenfeld angepasst werden kann.  
  
```  
BOOL IsResizeDropDownList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Listenfeld angepasst werden kann. andernfalls `FALSE`. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)  
  
### <a name="remarks"></a>Hinweise  
 Können Sie aktivieren, Ändern der Liste im Feld mithilfe der [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) Methode.  
  
##  <a name="a-nameonselectitema--cmfcribboncomboboxonselectitem"></a><a name="onselectitem"></a>CMFCRibbonComboBox::OnSelectItem  
 Wird vom Framework aufgerufen, wenn ein Benutzer ein Element im Listenfeld auswählt.  
  
```  
virtual void OnSelectItem(int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nItem`  
 Der Index des ausgewählten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie eine Eingabe Benutzerauswahl verarbeiten möchten.  
  
##  <a name="a-nameremoveallitemsa--cmfcribboncomboboxremoveallitems"></a><a name="removeallitems"></a>CMFCRibbonComboBox::RemoveAllItems  
 Löscht alle Elemente aus dem Listenfeld aus, und löscht das Bearbeitungsfeld.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameselectitema--cmfcribboncomboboxselectitem"></a><a name="selectitem"></a>CMFCRibbonComboBox::SelectItem  
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
 Die Daten eines Elements im Listenfeld.  
  
 [in] `lpszText`  
 Die Zeichenfolge eines Elements im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetdropdownheighta--cmfcribboncomboboxsetdropdownheight"></a><a name="setdropdownheight"></a>CMFCRibbonComboBox::SetDropDownHeight  
 Legt die Höhe des Listenfelds fest, wenn es sichtbar ist.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHeight`  
 Die Höhe in Pixel, der im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardhöhe ist 150 Pixel.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonEdit-Klasse](../../mfc/reference/cmfcribbonedit-class.md)

