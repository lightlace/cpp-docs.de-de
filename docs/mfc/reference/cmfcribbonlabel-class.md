---
title: CMFCRibbonLabel Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32732c08542ff766c265fda93b8cf09ad04387ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel-Klasse
Implementiert eine nicht anklickbare Bezeichnung für ein Menüband.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonLabel : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|Erstellt und initialisiert ein `CMFCRibbonLabel` Objekt mit der angegebenen Textzeichenfolge.|  
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCRibbonLabel::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonLabel::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Bestimmt die barrierefreiheitsdaten für das aktuelle Element der Menüband-Bezeichnung. (Überschreibt [cmfcribbonbutton:: Setaccdata](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
### <a name="remarks"></a>Hinweise  
 Nach der Erstellung einer Bezeichnung Menüband hinzufügen, wenn ein Bereich durch Aufrufen von [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
 Eine Menüband-Bezeichnung kann nicht auf der Symbolleiste für den Schnellzugriff hinzufügen werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonLabel.h  
  
##  <a name="cmfcribbonlabel"></a>CMFCRibbonLabel::CMFCRibbonLabel  
 Erstellt und initialisiert ein [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) -Objekt, das die angegebene Textzeichenfolge angezeigt.  
  
```  
CMFCRibbonLabel(
    LPCTSTR lpszText,  
    BOOL bIsMultiLine = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
 Der Text in der Bezeichnung angezeigt werden.  
  
 [in] `bIsMultiLine`  
 `TRUE`um anzugeben, dass die Bezeichnung eine mehrzeilige Bezeichnung; andernfalls `FALSE`.  
  
##  <a name="setaccdata"></a>CMFCRibbonLabel::SetACCData  
 Bestimmt die barrierefreiheitsdaten für das aktuelle Element der Menüband-Bezeichnung.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParent`  
 Stellt das übergeordnete Fenster des die aktuelle Bezeichnung an Menüband dar.  
  
 [out] `data`  
 Ein Objekt des Typs `CAccessibilityData` , die mit den Zugriff auf Daten der aktuellen Menüband Bezeichnung aufgefüllt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `data` Parameter wurde erfolgreich mit der aktuellen Menüband Bezeichnung die barrierefreiheitsdaten gefüllt ist, andernfalls `FALSE`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)
