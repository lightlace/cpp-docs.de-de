---
title: CMFCRibbonCustomizeDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
dev_langs: C++
helpviewer_keywords: CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0681e993695dadfbbfe4ef369fda44b2b9eddc2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog-Klasse
Zeigt das Menüband **anpassen** Seite.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|Erstellt ein `CMFCRibbonCustomizeDialog`-Objekt.|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
  
## <a name="remarks"></a>Hinweise  
 MFC instanziiert diese Klasse automatisch, wenn Sie keine die AFX_WM_ON_RIBBON_CUSTOMIZE Nachricht verarbeiten oder wenn Sie 0 aus der Message-Handler zurückgegeben.  
  
 Wenn Sie diese Klasse in der Anwendung zu verwenden, um das Menüband anzeigen möchten **anpassen** Dialogfeld Feld, einfach zu instanziieren und Aufrufen der `DoModal` Methode.  
  
 Da von dieser Klasse abgeleitetes [CMFCPropertySheet Klasse](../../mfc/reference/cmfcpropertysheet-class.md), können Sie benutzerdefinierte Seiten hinzufügen, mit der `CMFCPropertySheet` API.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncustomizedialog.h  
  
##  <a name="cmfcribboncustomizedialog"></a>CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog  
 Erstellt ein `CMFCRibbonCustomizeDialog`-Objekt.  
  
```  
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,  
    CMFCRibbonBar* pRibbon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster (normalerweise der Hauptframe).  
  
 [in] `pRibbon`  
 Ein Zeiger auf die `CMFCRibbonBar` also angepasst werden.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCRibbonCustomizeDialog` Objekt.  
  
 [!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor instanziiert eine [CMFCRibbonCustomizePropertyPage Klasse](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) -Objekt und fügt es der Auflistung der Sheet-Eigenschaftenseiten hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)