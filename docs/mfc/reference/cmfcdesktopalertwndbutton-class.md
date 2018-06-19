---
title: CMFCDesktopAlertWndButton Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efabaabdcc3f08a58cb7dc0a7845a56e5238548d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370333"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton-Klasse
Ermöglicht die Schaltflächen zum desktop Warndialogfeld hinzugefügt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Standardkonstruktor|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|Bestimmt, ob die Schaltfläche "" das Dialogfeld Warnung im Bereich "Caption" angezeigt wird.|  
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|Bestimmt, ob die Schaltfläche "" das Dialogfeld Warnung geschlossen wird.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|name|Beschreibung|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Ein boolescher Wert, der angibt, ob die Schaltfläche "" das Dialogfeld Warnung im Bereich "Caption" angezeigt wird.|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Ein boolescher Wert, der angibt, ob die Schaltfläche "" das Dialogfeld Warnung geschlossen wird.|  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig legt der Konstruktor der `m_bIsCaptionButton` und `m_bIsCloseButton` Datenmember zu `FALSE`. Das übergeordnete Element `CMFCDesktopAlertDialog` -Objekt legt `m_bIsCaptionButton` zu `TRUE` , wenn die Schaltfläche "" das Dialogfeld Warnung im Bereich "Caption" positioniert ist. Der `CMFCDesktopAlertDialog` -Klasse erstellt eine `CMFCDesktopAlertWndButton` -Objekt, das fungiert als Schaltfläche, die schließt das Dialogfeld "Warnung" ein, und legt `m_bIsCloseButton` zu `TRUE`.  
  
 Hinzufügen `CMFCDesktopAlertWndButton` Datenbankobjekte in einem `CMFCDesktopAlertDialog` Objekt, wie Sie keine der Schaltflächen hinzufügen. Weitere Informationen zu `CMFCDesktopAlertDialog`, finden Sie unter [CMFCDesktopAlertDialog Klasse](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SetImage` Methode in der `CMFCDesktopAlertWndButton` Klasse. Dieser Codeausschnitt ist Teil der [Desktop Warnung Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdesktopalertwnd.h  
  
##  <a name="iscaptionbutton"></a>  CMFCDesktopAlertWndButton::IsCaptionButton  
 Bestimmt, ob die Schaltfläche "" das Dialogfeld Warnung im Bereich "Caption" angezeigt wird.  
  
```  
BOOL IsCaptionButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche "" das Dialogfeld Warnung im Bereich "Caption" angezeigt wird; andernfalls 0.  
  
##  <a name="isclosebutton"></a>  CMFCDesktopAlertWndButton::IsCloseButton  
 Bestimmt, ob die Schaltfläche "" das Dialogfeld Warnung geschlossen wird.  
  
```  
BOOL IsCloseButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche Warndialogfeld schließt; andernfalls 0.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog-Klasse](../../mfc/reference/cmfcdesktopalertdialog-class.md)
