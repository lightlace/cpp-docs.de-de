---
title: CMFCRibbonButtonsGroup-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7a38e9ba4c01e5f3d92640f5ec55c63a45d70fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368858"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup-Klasse
Die `CMFCRibbonButtonsGroup` -Klasse ermöglicht es Ihnen, einen Satz von Menübandschaltflächen in einer Gruppe zu organisieren. Alle Schaltflächen der Gruppe liegen innerhalb eines Rahmens direkt horizontal nebeneinander.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Erstellt ein `CMFCRibbonButtonsGroup`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Fügt eine Schaltfläche zu einer Gruppe hinzu.|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Fügt eine Liste von Schaltflächen zu einer Gruppe hinzu.|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Gibt einen Zeiger auf die Schaltfläche, die auf einem angegebenen Index befindet.|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Gibt die Anzahl von Schaltflächen in der Gruppe zurück.|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Gibt die Bildgröße der normalen Bilder in der Menübandgruppe (Außerkraftsetzungen [cmfcribbonbaseelement:: Getimagesize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Gibt die reguläre Größe des Menübandelements zurück (Außerkraftsetzungen [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Berichte, ob die `CMFCRibbonButtonsGroup` Objekt enthält Symbolleistenbilder.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Zeichnet das entsprechende Image für eine angegebene Schaltfläche, je nachdem, ob die Schaltfläche mit der normalen, hervorgehobene oder deaktiviert.|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Entfernt alle Schaltflächen aus dem `CMFCRibbonButtonsGroup` Objekt.|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Die Gruppe Bilder zugewiesen.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Legt die übergeordnete `CMFCRibbonCategory` von der `CMFCRibbonButtonsGroup` -Objekt und alle Schaltflächen darin (Außerkraftsetzungen [cmfcribbonbaseelement:: Setparentcategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
  
## <a name="remarks"></a>Hinweise  
 Die Gruppe abgeleitet [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) und kann als eine Einheit bearbeitet werden. Sie können die Gruppe in keinem Bereich oder Popup-Menü positionieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCRibbonButtonsGroup` Klasse. Im Beispiel wird gezeigt, wie zum Erstellen einer `CMFCRibbonButtonsGroup` Objekt, weisen Sie der Gruppe der Menübandschaltflächen Bilder und eine Schaltfläche für die Gruppe von Menübandschaltflächen hinzufügen. Dieser Codeausschnitt ist Teil des [Draw Client-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonbuttonsgroup.h  
  
##  <a name="addbutton"></a>  CMFCRibbonButtonsGroup::AddButton  
 Fügt eine Schaltfläche zu einer Gruppe hinzu.  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf eine Schaltfläche hinzufügen.  
  
##  <a name="addbuttons"></a>  CMFCRibbonButtonsGroup::AddButtons  
 Fügt eine Liste von Schaltflächen zu einer Gruppe hinzu.  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lstButtons`  
 Eine Liste von Zeigern auf die Schaltflächen, die Sie hinzufügen möchten.  
  
##  <a name="cmfcribbonbuttonsgroup"></a>  CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 Erstellt ein `CMFCRibbonButtonsGroup`-Objekt.  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Gibt an, eine Schaltfläche hinzufügen auf das neu erstellte `CMFCRibbonButtonsGroup` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getbutton"></a>  CMFCRibbonButtonsGroup::GetButton  
 Gibt einen Zeiger auf die Schaltfläche, die auf einem angegebenen Index befindet.  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `i`  
 Ein nullbasierter Index, der eine Schaltfläche, um zurückzukehren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Schaltfläche ", die sich am angegebenen Index befindet. `NULL` Wenn der angegebene Index außerhalb des gültigen Bereichs liegt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcount"></a>  CMFCRibbonButtonsGroup::GetCount  
 Gibt die Anzahl von Schaltflächen in der Gruppe zurück.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Schaltflächen in der Gruppe.  
  
##  <a name="getimagesize"></a>  CMFCRibbonButtonsGroup::GetImageSize  
 Ruft die Quelle Bildgröße der geschützten `CMFCToolBarImages` Member `m_Images`.  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Quelle Image Größe die Symbolleistenbilder zurück, wenn eine vorhanden ist, bzw. einen `CSize` 0 (null), wenn nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getregularsize"></a>  CMFCRibbonButtonsGroup::GetRegularSize  
 Ruft die maximale Größe des Menübandelements Gruppe ab.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der Gruppe "Menüband".  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasimages"></a>  CMFCRibbonButtonsGroup::HasImages  
 Berichte, ob die `CMFCRibbonButtonsGroup` Objekt enthält Symbolleistenbilder.  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die geschützte `CMFCToolBarImages` Member `m_Images` enthält Bilder oder "false", wenn nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawimage"></a>  CMFCRibbonButtonsGroup::OnDrawImage  
 Zeichnet das entsprechende Image für eine angegebene Schaltfläche, je nachdem, ob die Schaltfläche mit der normalen, hervorgehobene oder deaktiviert.  
  
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
 Die Schaltfläche für die das Bild gezeichnet werden soll.  
  
 [in] `nImageIndex`  
 Der Index des Bilds (in eines der drei Arrays für normale, hervorgehobene oder deaktivierte Schaltflächen) auf die Schaltfläche gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removeall"></a>  CMFCRibbonButtonsGroup::RemoveAll  
 Entfernt alle Schaltflächen aus dem `CMFCRibbonButtonsGroup` Objekt.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setimages"></a>  CMFCRibbonButtonsGroup::SetImages  
 Die Gruppe von Menübandschaltflächen Bilder zugewiesen.  
  
```  
void SetImages(
    CMFCToolBarImages* pImages,  
    CMFCToolBarImages* pHotImages,  
    CMFCToolBarImages* pDisabledImages);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pImages`  
 Reguläre Bilder.  
  
 [in] `pHotImages`  
 Hervorgehobenen Bilder.  
  
 [in] `pDisabledImages`  
 Deaktivierte Bilder.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `SetImages` vor dem Hinzufügen von Schaltflächen zu einer Gruppe. Die Anzahl von Images muss größer oder gleich der Anzahl von Schaltflächen der Gruppe hinzugefügt werden.  
  
> [!NOTE]
>  Hervorgehobenen Bilder sind Bilder, die angezeigt werden, wenn der Benutzer über die Schaltfläche bewegt wird. Deaktivierte Images sind Bilder, die angezeigt werden, wenn die Schaltfläche deaktiviert ist.  
  
##  <a name="setparentcategory"></a>  CMFCRibbonButtonsGroup::SetParentCategory  
 Legt die übergeordnete `CMFCRibbonCategory` von der `CMFCRibbonButtonsGroup` -Objekt und alle Schaltflächen einstuft.  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCategory`  
 Zeiger auf die übergeordnete Kategorie festlegen (der Gruppen im Registerkartenformat im Menübandsteuerelemente sind Kategorien genannt).  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
