---
title: CMFCTasksPaneTaskGroup-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTaskGroup class
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
caps.latest.revision: 33
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 405a69a0c7d8c4179b36e1beec09fdfa7acd2d7b
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup-Klasse
Die `CMFCTasksPaneTaskGroup` Klasse ist eine Hilfsklasse, die von der [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) Steuerelement. Objekte des Typs `CMFCTasksPaneTaskGroup` stellen eine *Aufgabengruppe*dar. Die Aufgabengruppe ist eine Liste von Elementen, die vom Framework in einem separaten Feld angezeigt wird, das eine Schaltfläche zum Reduzieren enthält. Das Feld kann über eine optionale Beschriftung (Gruppennamen) verfügen. Wenn eine Gruppe reduziert ist, ist die Liste der Aufgaben nicht sichtbar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Erstellt ein `CMFCTasksPaneTaskGroup`-Objekt.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Bestimmt die Eingabehilfen-Daten für die aktuelle Aufgabengruppe.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Bestimmt, ob die Aufgabengruppe an das Ende der Aufgabenbereich-Steuerelement ausgerichtet wird.|  
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Bestimmt, ob die Aufgabengruppe reduziert wird.|  
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Bestimmt, ob die Aufgabengruppe ist *besondere.* Das Framework werden spezielle Beschriftungen in einer anderen Farbe angezeigt.|  
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|Enthält die interne Liste der Aufgaben.|  
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Gibt das umschließende Rechteck der gruppenbeschriftung an.|  
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Gibt das umschließende Rechteck der Gruppe an.|  
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Gibt den Namen der Gruppe an.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Abbildung zeigt eine erweiterte Aufgabengruppe:  
  
 ![Aufgabengruppe, erweitert](../../mfc/reference/media/nexttaskgrpexpand.png "Nexttaskgrpexpand")  
  
 Die folgende Abbildung zeigt eine reduzierte Aufgabengruppe:  
  
 ![Reduzierte Aufgabengruppe](../../mfc/reference/media/nexttaskgrpcollapse.png "Nexttaskgrpcollapse")  
  
 Die folgende Abbildung zeigt eine Aufgabengruppe ohne Beschriftung:  
  
 ![Aufgabengruppe ohne Beschriftung](../../mfc/reference/media/nexttaskgrpnocapt.png "Nexttaskgrpnocapt")  
  
 Die folgende Abbildung zeigt zwei Aufgabengruppen. Die erste Aufgabengruppe ist als Sonderzeichen markiert, indem die `m_bIsSpecial` flag auf `TRUE`, während die zweite Aufgabengruppe nicht spezielle ist. Beachten Sie, wie die Beschriftung für die erste Aufgabengruppe dunkler sind als die zweite Aufgabengruppe ist:  
  
 ![Spezielle Aufgabengruppe](../../mfc/reference/media/nexttaskgrpspecial.png "Nexttaskgrpspecial")  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetaskgroup"></a>CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup  
 Erstellt ein `CMFCTasksPaneTaskGroup`-Objekt.  
  
```  
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,  
    BOOL bIsBottom,  
    BOOL bIsSpecial=FALSE,  
    BOOL bIsCollapsed=FALSE,  
    CMFCTasksPanePropertyPage* pPage=NULL,  
    HICON hIcon=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Gibt den Namen der Gruppe in der gruppenbeschriftung an.  
  
 `bIsBottom`  
 Gibt an, ob die Gruppe an das Ende der Aufgabenbereich-Steuerelement ausgerichtet ist.  
  
 `bIsSpecial`  
 Gibt an, ob die Gruppe als vorgesehen ist *besondere* und folglich, ob die gruppenbeschriftung mit einer anderen Farbe ausgefüllt wird.  
  
 `bIsCollapsed`  
 Gibt an, ob die Gruppe reduziert ist.  
  
 `pPage`  
 Gibt die Eigenschaftenseite, der zu dieser Aufgabengruppe gehört.  
  
 `hIcon`  
 Gibt das Symbol an, das in der gruppenbeschriftung anzeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bisbottom"></a>CMFCTasksPaneTaskGroup::m_bIsBottom  
 Bestimmt, ob die Aufgabengruppe an das Ende der Aufgabenbereich-Steuerelement ausgerichtet wird.  
  
```  
BOOL m_bIsBottom;  
```  
  
### <a name="remarks"></a>Hinweise  
 Am Ende der Aufgabenbereich-Steuerelement kann nur eine Gruppe ausgerichtet werden. Diese Aufgabengruppe muss zuletzt hinzugefügt werden. Weitere Informationen finden Sie unter [cmfctaskspane:: addgroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_biscollapsed"></a>CMFCTasksPaneTaskGroup::m_bIsCollapsed  
 Bestimmt, ob die Aufgabengruppe reduziert wird.  
  
```  
BOOL m_bIsCollapsed;  
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können aktivieren oder deaktivieren Sie die Möglichkeit zum Reduzieren von Gruppen im Aufgabenbereich durch Aufrufen von [cmfctaskspane:: Enablegroupcollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).  
  
##  <a name="m_bisspecial"></a>CMFCTasksPaneTaskGroup::m_bIsSpecial  
 Bestimmt, ob die Aufgabengruppe ist *besondere* und gibt an, ob die Beschriftung für eine spezielle Aufgabe mit einer anderen Farbe bestimmt werden soll.  
  
```  
BOOL m_bIsSpecial;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung das visuelle Design von Windows XP und `m_bIsSpecial` ist `FALSE`, das Framework ruft `DrawThemeBackground` mit der `EBP_NORMALGROUPBACKGROUND` Flag. Wenn `m_bIsSpecial` ist `TRUE`, das Framework ruft `DrawThemeBackground` mit der `EBP_SPECIALGROUPBACKGROUND` Flag.  
  
##  <a name="m_lsttasks"></a>CMFCTasksPaneTaskGroup::m_lstTasks  
 Enthält die interne Liste der Aufgaben.  
  
```  
CObList m_lstTasks;  
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen, um diese Liste zu füllen, [cmfctaskspane:: Addtask](../../mfc/reference/cmfctaskspane-class.md#addtask).  
  
##  <a name="m_rect"></a>CMFCTasksPaneTaskGroup::m_rect  
 Gibt das umschließende Rechteck der gruppenbeschriftung an.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird vom Framework automatisch berechnet.  
  
##  <a name="m_rectgroup"></a>CMFCTasksPaneTaskGroup::m_rectGroup  
 Gibt das umschließende Rechteck der Gruppe an.  
  
```  
CRect m_rectGroup;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird vom Framework automatisch berechnet.  
  
##  <a name="m_strname"></a>CMFCTasksPaneTaskGroup::m_strName  
 Gibt den Namen der Gruppe an.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieser Wert leer ist, die gruppenbeschriftung wird nicht angezeigt, und die Gruppe nicht reduziert werden kann.  
  
##  <a name="setaccdata"></a>CMFCTasksPaneTaskGroup::SetACCData  
 Bestimmt die Eingabehilfen-Daten für die aktuelle Aufgabengruppe.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParent`  
 Stellt das übergeordnete Fenster der aktuellen Aufgabe.  
  
 [out] `data`  
 Ein Objekt vom Typ `CAccessibilityData` , die mit den Zugriff auf Daten der aktuellen Aufgabe aufgefüllt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `data` Parameter wurde erfolgreich mit den Zugriff auf Daten der aktuellen Aufgabe ausgefüllt, andernfalls `FALSE`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPane-Klasse](../../mfc/reference/cmfctaskspane-class.md)   
 [Cmfctaskspanetask-Klasse](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)

