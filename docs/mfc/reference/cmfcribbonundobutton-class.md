---
title: CMFCRibbonUndoButton Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 720a1de11dcf4c37b4b321bb0e014a9ae4e2e459
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton-Klasse
Die `CMFCRibbonUndoButton` Klasse implementiert eine Dropdownliste-Schaltfläche, die letzten Benutzerbefehle enthält. Benutzer können eine oder mehrere der neuesten Befehle auswählen, aus der Dropdown-Liste entweder wiederherstellen oder rückgängig machen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Erstellt ein neues `CMFCRibbonUndoButton` Objekt mithilfe des Befehls-ID, die Sie angeben, Beschriftung und Bilder aus der Bildliste des übergeordneten Objekts.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Die Liste der Aktionen wird eine neue Aktion hinzugefügt.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Löscht die Liste der Aktionen, die in der Dropdown Liste ist.|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Bestimmt die Anzahl der Elemente, die ein Benutzer aus der Dropdown-Liste ausgewählt.|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Gibt an, ob das Objekt ein Menü enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCRibbonUndoButton` Klasse verwendet einen Stapel, um die Dropdownliste darzustellen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCRibbonUndoButton` Klasse, und eine neue Aktion hinzufügen, um die Liste der Aktionen. Dieser Codeausschnitt ist Teil der [Menüband Gadgets Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonundobutton.h  
  
##  <a name="addundoaction"></a>CMFCRibbonUndoButton::AddUndoAction  
 Die Liste der Aktionen wird eine neue Aktion hinzugefügt.  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Die aktionsbezeichnung, die in der Dropdown-Liste angezeigt werden sollen.  
  
##  <a name="cleanupundolist"></a>CMFCRibbonUndoButton::CleanUpUndoList  
 Löscht die Liste der Aktionen, die in der Dropdown Liste ist.  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="cmfcribbonundobutton"></a>CMFCRibbonUndoButton::CMFCRibbonUndoButton  
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
 Nullbasierte Index in der Bildliste des übergeordneten Objekts für die Schaltfläche Miniaturansicht.  
  
 [in] `nLargeImageIndex`  
 Nullbasierten Index in der Bildliste des übergeordneten Objekts für die von großen Schaltflächenbild.  
  
 [in] `hIcon`  
 Ein Handle für ein Symbol, das Sie als eine Schaltfläche verwenden können.  
  
##  <a name="getactionnumber"></a>CMFCRibbonUndoButton::GetActionNumber  
 Bestimmt die Anzahl der Elemente, die ein Benutzer aus der Dropdown-Liste ausgewählt.  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente, die ein Benutzer ausgewählt.  
  
##  <a name="hasmenu"></a>CMFCRibbonUndoButton::HasMenu  
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
