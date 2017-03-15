---
title: Klasse CMFCRibbonCustomizeDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetThisClass
- CMFCRibbonCustomizeDialog
- ~CMFCRibbonCustomizeDialog
- CMFCRibbonCustomizeDialog::GetThisClass
- CMFCRibbonCustomizeDialog.~CMFCRibbonCustomizeDialog
- CMFCRibbonCustomizeDialog.GetThisClass
- CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizeDialog class
- CMFCRibbonCustomizeDialog class, destructor
- ~CMFCRibbonCustomizeDialog destructor
- GetThisClass method
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d27247f89901adad1778313cdde6fe206a569f0d
ms.lasthandoff: 02/24/2017

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
|`CMFCRibbonCustomizeDialog::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
  
## <a name="remarks"></a>Hinweise  
 MFC instanziiert diese Klasse automatisch, wenn Sie keine AFX_WM_ON_RIBBON_CUSTOMIZE Nachricht verarbeiten, oder wenn Sie 0 aus der Message-Handler zurückgegeben.  
  
 Wenn Sie diese Klasse in Ihrer Anwendung zu verwenden, um das Menüband anzeigen möchten **anpassen** Dialogfeld Feld, einfach instanziieren und Aufrufen der `DoModal` Methode.  
  
 Da von dieser Klasse abgeleitet ist [CMFCPropertySheet Klasse](../../mfc/reference/cmfcpropertysheet-class.md), können Sie benutzerdefinierte Seiten hinzufügen, mit der `CMFCPropertySheet` API.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncustomizedialog.h  
  
##  <a name="a-namecmfcribboncustomizedialoga--cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a>CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog  
 Erstellt ein `CMFCRibbonCustomizeDialog`-Objekt.  
  
```  
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,  
    CMFCRibbonBar* pRibbon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster (in der Regel den Hauptframe).  
  
 [in] `pRibbon`  
 Ein Zeiger auf die `CMFCRibbonBar` das angepasst werden soll.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCRibbonCustomizeDialog` Objekt.  
  
 [!code-cpp[NVC_MFC_RibbonApp&18;](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor instanziiert ein [CMFCRibbonCustomizePropertyPage Klasse](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) -Objekt und fügt es zur Auflistung der Eigenschaftenfenster.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

