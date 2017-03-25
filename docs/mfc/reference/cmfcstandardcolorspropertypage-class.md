---
title: Klasse CMFCStandardColorsPropertyPage | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CMFCStandardColorsPropertyPage class
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: fade2cc91d9681604fbd664419c693dde1527b84
ms.lasthandoff: 03/17/2017

---
# <a name="cmfcstandardcolorspropertypage-class"></a>CMFCStandardColorsPropertyPage-Klasse
Stellt eine Eigenschaft dar, die Benutzer mit Standardfarben im Dialogfeld Farbe auswählen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCStandardColorsPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCStandardColorsPropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCStandardColorsPropertyPage::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCColorDialog` Klasse, die diese Klasse verwendet, um die Standardfarbe Eigenschaftenseite anzuzeigen. Weitere Informationen zu `CMFCColorDialog`, finden Sie unter [CMFCColorDialog Klasse](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxstandardcolorspropertypage.h  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCCustomColorsPropertyPage-Klasse](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

