---
title: CMFCRibbonLabel-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac06722b675af5e8ac8d4136cc2938ac772befc9
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848582"
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
|`CMFCRibbonLabel::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Bestimmt die barrierefreiheitsdaten für das aktuelle Element der Menüband-Bezeichnung an. (Überschreibt [cmfcribbonbutton:: Setaccdata](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
### <a name="remarks"></a>Hinweise  
 Nachdem Sie eine Menüband-Bezeichnung erstellt haben, hinzufügen, einen Bereich durch den Aufruf [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
 Sie können keine Menüband-Bezeichnung Symbolleiste für den Schnellzugriff hinzugefügt werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonLabel.h  
  
##  <a name="cmfcribbonlabel"></a>  CMFCRibbonLabel::CMFCRibbonLabel  
 Erstellt und initialisiert ein [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) -Objekt, das zeigt, an der angegebenen Textzeichenfolge.  
  
```  
CMFCRibbonLabel(
    LPCTSTR lpszText,  
    BOOL bIsMultiLine = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszText*  
 Der Text in der Bezeichnung angezeigt werden.  
  
 [in] *bIsMultiLine*  
 True, um anzugeben, dass die Bezeichnung eine mehrzeilige Bezeichnung ist. andernfalls "false".  
  
##  <a name="setaccdata"></a>  CMFCRibbonLabel::SetACCData  
 Bestimmt die barrierefreiheitsdaten für das aktuelle Element der Menüband-Bezeichnung an.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pParent*  
 Stellt das übergeordnete Fenster des die aktuelle Menüband-Bezeichnung an.  
  
 [out] *Daten*  
 Ein Objekt des Typs `CAccessibilityData` , die mit den Zugriff auf Daten des die aktuelle Menüband-Bezeichnung aufgefüllt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die *Daten* Parameter wurde erfolgreich mit den Zugriff auf Daten des die aktuelle Menüband-Bezeichnung aufgefüllt ist, andernfalls "false".  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)
