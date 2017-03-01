---
title: Klasse CMFCRibbonButtonsGroup | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButtonsGroup
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup class
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
caps.latest.revision: 34
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2d8909ca63bd1d9121e1126d46a08312521cc4ac
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup-Klasse
Die `CMFCRibbonButtonsGroup` -Klasse können Sie einen Satz von Multifunktionsleisten-Schaltflächen in einer Gruppe anordnen. Alle Schaltflächen der Gruppe liegen innerhalb eines Rahmens direkt horizontal nebeneinander.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Erstellt ein `CMFCRibbonButtonsGroup`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Fügt eine Schaltfläche zu einer Gruppe.|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Eine Liste von Schaltflächen hinzugefügt zu einer Gruppe.|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Gibt einen Zeiger auf die Schaltfläche, die sich an einem angegebenen Index befindet.|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Gibt die Anzahl der Schaltflächen in der Gruppe zurück.|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Gibt die Bildgröße der normale Bilder in der Menübandgruppe (überschreibt [cmfcribbonbaseelement:: Getimagesize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Gibt die reguläre Größe des Menübandelements zurück (überschreibt [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Berichte, ob die `CMFCRibbonButtonsGroup` Objekt Symbolleistenbilder enthält.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Zeichnet das entsprechende Bild für die angegebene Schaltfläche, je nachdem, ob die Schaltfläche normal, hervorgehobene oder deaktiviert.|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Entfernt alle Schaltflächen aus der `CMFCRibbonButtonsGroup` Objekt.|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Die Gruppe Bilder zugewiesen.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Legt das übergeordnete Element `CMFCRibbonCategory` von der `CMFCRibbonButtonsGroup` -Objekt und alle darin enthaltenen Schaltflächen (überschreibt [cmfcribbonbaseelement:: Setparentcategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
  
## <a name="remarks"></a>Hinweise  
 Die Gruppe wird von abgeleitet [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) und kann als eine Einheit bearbeitet werden. Sie können die Gruppe alle Panel oder Popup-Menü positionieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCRibbonButtonsGroup` Klasse. Das Beispiel zeigt, wie ein `CMFCRibbonButtonsGroup` Objekt, der Gruppe der Multifunktionsleisten-Schaltflächen Bilder zuweisen, und fügen Sie eine Schaltfläche für die Gruppe von Multifunktionsleisten-Schaltflächen. Dieser Codeausschnitt ist Teil der [zeichnen Clientbeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&#2;](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonbuttonsgroup.h  
  
##  <a name="a-nameaddbuttona--cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a>CMFCRibbonButtonsGroup::AddButton  
 Fügt eine Schaltfläche zu einer Gruppe.  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf eine Schaltfläche zum Hinzufügen.  
  
##  <a name="a-nameaddbuttonsa--cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a>CMFCRibbonButtonsGroup::AddButtons  
 Eine Liste von Schaltflächen hinzugefügt zu einer Gruppe.  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lstButtons`  
 Eine Liste von Zeigern auf die Schaltflächen, die Sie hinzufügen möchten.  
  
##  <a name="a-namecmfcribbonbuttonsgroupa--cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a>CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 Erstellt ein `CMFCRibbonButtonsGroup`-Objekt.  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Gibt eine Schaltfläche zum Hinzufügen auf das neu erstellte `CMFCRibbonButtonsGroup` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetbuttona--cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a>CMFCRibbonButtonsGroup::GetButton  
 Gibt einen Zeiger auf die Schaltfläche, die sich an einem angegebenen Index befindet.  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `i`  
 Ein nullbasierter Index, einer Schaltfläche zurückgegeben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Schaltfläche, die sich am angegebenen Index befindet. `NULL`Wenn der angegebene Index außerhalb des gültigen Bereichs befindet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetcounta--cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a>CMFCRibbonButtonsGroup::GetCount  
 Gibt die Anzahl der Schaltflächen in der Gruppe zurück.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Schaltflächen in der Gruppe.  
  
##  <a name="a-namegetimagesizea--cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a>CMFCRibbonButtonsGroup::GetImageSize  
 Ruft die Größe des Abbilds der geschützten `CMFCToolBarImages` Element `m_Images`.  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe der Symbolleistenbilder, Bild vorhanden sind oder ein `CSize` von&0; (null), wenn nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetregularsizea--cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonButtonsGroup::GetRegularSize  
 Ruft die maximale Größe des Menübandelements Gruppe ab.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der Menübandgruppe.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namehasimagesa--cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a>CMFCRibbonButtonsGroup::HasImages  
 Berichte, ob die `CMFCRibbonButtonsGroup` Objekt Symbolleistenbilder enthält.  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn die geschützte `CMFCToolBarImages` Element `m_Images` Bilder, oder FALSE, wenn nicht enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawimagea--cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a>CMFCRibbonButtonsGroup::OnDrawImage  
 Zeichnet das entsprechende Bild für die angegebene Schaltfläche, je nachdem, ob die Schaltfläche normal, hervorgehobene oder deaktiviert.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rectImage,  
    CMFCRibbonBaseElement* pButton,  
    int nImageIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger auf den Gerätekontext, der die `CMFCRibbonButtonsGroup` Objekt.  
  
 [in] `rectImage`  
 Das Rechteck, in dem das Bild gezeichnet werden soll.  
  
 [in] `pButton`  
 Die Schaltfläche für das Bild gezeichnet werden soll.  
  
 [in] `nImageIndex`  
 Der Index des Bilds (klicken Sie auf eines der drei Arrays für normal, hervorgehobene oder deaktivierte Schaltflächen) auf die Schaltfläche gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameremovealla--cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a>CMFCRibbonButtonsGroup::RemoveAll  
 Entfernt alle Schaltflächen aus der `CMFCRibbonButtonsGroup` Objekt.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetimagesa--cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a>CMFCRibbonButtonsGroup::SetImages  
 Die Gruppe der Multifunktionsleisten-Schaltflächen Bilder zugewiesen.  
  
```  
void SetImages(
    CMFCToolBarImages* pImages,  
    CMFCToolBarImages* pHotImages,  
    CMFCToolBarImages* pDisabledImages);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pImages`  
 Regulären Abbildern.  
  
 [in] `pHotImages`  
 Hot-Abbilder.  
  
 [in] `pDisabledImages`  
 Deaktivierte Bilder.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `SetImages` vor dem Hinzufügen von Schaltflächen zu einer Gruppe. Die Anzahl der Abbilder muss größer oder gleich der Anzahl der Schaltflächen der Gruppe hinzugefügt werden.  
  
> [!NOTE]
>  Hot-Images sind Bilder, die angezeigt werden, wenn der Benutzer über die Schaltfläche bewegt wird. Deaktivierte Abbilder sind Abbilder, die angezeigt werden, wenn die Schaltfläche deaktiviert ist.  
  
##  <a name="a-namesetparentcategorya--cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a>CMFCRibbonButtonsGroup::SetParentCategory  
 Legt das übergeordnete Element `CMFCRibbonCategory` von der `CMFCRibbonButtonsGroup` -Objekt und alle darin enthaltenen Schaltflächen.  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCategory`  
 Zeiger auf die übergeordnete Kategorie festlegen (der Gruppen im Registerkartenformat im Menübandsteuerelemente werden Kategorien genannt).  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

