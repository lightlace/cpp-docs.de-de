---
title: Klasse CMFCRibbonUndoButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonUndoButton class
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
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
ms.openlocfilehash: d4406e21a7e2a945965020d85a748b93d66b5682
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton-Klasse
Die `CMFCRibbonUndoButton` -Klasse implementiert eine Dropdown-Liste-Schaltfläche, die der aktuelle Benutzerbefehle enthält. Benutzer können eine oder mehrere der neuesten Befehle auswählen, aus der Dropdown-Liste entweder wiederherstellen oder rückgängig machen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Erstellt ein neues `CMFCRibbonUndoButton` Objekt mithilfe des Befehls-ID, die Sie angeben, Beschriftung und Bilder aus der Bildliste des übergeordneten Objekts.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Die Liste der Aktionen wird eine neue Aktion hinzugefügt.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Löscht die Aktionsliste also die Dropdown-Liste.|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Bestimmt die Anzahl der Elemente, die ein Benutzer aus der Dropdown Liste ausgewählt.|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Gibt an, ob das Objekt ein Menü enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCRibbonUndoButton` Klasse, die einen Stapel verwendet, um die Dropdown-Liste darstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCRibbonUndoButton` -Klasse und die Liste der Aktionen eine neue Aktion hinzu. Dieser Codeausschnitt ist Teil der [Menüband Gadgets Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RibbonGadgets&#2;](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonundobutton.h  
  
##  <a name="a-nameaddundoactiona--cmfcribbonundobuttonaddundoaction"></a><a name="addundoaction"></a>CMFCRibbonUndoButton::AddUndoAction  
 Die Liste der Aktionen wird eine neue Aktion hinzugefügt.  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Die Bezeichnung der Aktion, die in der Dropdown-Liste angezeigt werden.  
  
##  <a name="a-namecleanupundolista--cmfcribbonundobuttoncleanupundolist"></a><a name="cleanupundolist"></a>CMFCRibbonUndoButton::CleanUpUndoList  
 Löscht die Aktionsliste also die Dropdown-Liste.  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="a-namecmfcribbonundobuttona--cmfcribbonundobuttoncmfcribbonundobutton"></a><a name="cmfcribbonundobutton"></a>CMFCRibbonUndoButton::CMFCRibbonUndoButton  
 Erstellt ein neues `CMFCRibbonUndoButton` Objekt mithilfe des Befehls-ID, die Sie angeben, Beschriftung und Bilder aus der Bildliste des übergeordneten Objekts.  
  
```  
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1);

 
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Gibt die Befehls-ID an.  
  
 [in] `lpszText`  
 Gibt die Beschriftung der Schaltfläche.  
  
 [in] `nSmallImageIndex`  
 Nullbasierte Index in der Bildliste, der das übergeordnete Objekt für das Bild der Schaltfläche klein.  
  
 [in] `nLargeImageIndex`  
 Nullbasierte Index in der Bildliste, der das übergeordnete Objekt für das große Bild der Schaltfläche.  
  
 [in] `hIcon`  
 Ein Handle für ein Symbol, das Sie als Bild einer Schaltfläche verwenden können.  
  
##  <a name="a-namegetactionnumbera--cmfcribbonundobuttongetactionnumber"></a><a name="getactionnumber"></a>CMFCRibbonUndoButton::GetActionNumber  
 Bestimmt die Anzahl der Elemente, die ein Benutzer aus der Dropdown Liste ausgewählt.  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente, die ein Benutzer ausgewählt.  
  
##  <a name="a-namehasmenua--cmfcribbonundobuttonhasmenu"></a><a name="hasmenu"></a>CMFCRibbonUndoButton::HasMenu  
 Gibt an, ob das Objekt ein Menü enthält.  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery-Klasse](../../mfc/reference/cmfcribbongallery-class.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)

