---
title: Klasse CMFCCustomColorsPropertyPage | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCustomColorsPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCCustomColorsPropertyPage class
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
caps.latest.revision: 23
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
ms.openlocfilehash: fa534f22438b7be37e7893e545c3e060df69384f
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage-Klasse
Stellt eine Eigenschaft dar, die benutzerdefinierte Farben im Dialogfeld Farbe auswählen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCCustomColorsPropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCCustomColorsPropertyPage::Setup](#setup)|Legt die Komponenten der Seite fest.|  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCColorDialog` Klasse, die diese Klasse verwendet, um die Eigenschaftenseite für die benutzerdefinierte Farbe anzuzeigen. Weitere Informationen zu `CMFCColorDialog`, finden Sie unter [CMFCColorDialog Klasse](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCCustomColorsPropertyPage` Objekt, und legen Sie die Komponenten der Eigenschaftenseite.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#35;](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcustomcolorspropertypage.h  
  
##  <a name="a-namesetupa--cmfccustomcolorspropertypagesetup"></a><a name="setup"></a>CMFCCustomColorsPropertyPage::Setup  
 Legt die Komponenten der Seite fest.  
  
```  
void Setup(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `R`|Die rote Komponente des RGB-Wertes.|  
|[in] `G`|Die grünen Komponente den RGB-Wert.|  
|[in] `B`|Die blaue Komponente den RGB-Wert.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode aktualisiert die aktuellen RGB- und die zugehörigen HLS (Farbton, Helligkeit und Sättigung) Farbwerte der Eigenschaftenseite. Die [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) -Methode ruft diese Methode auf, wenn das Framework das Dialogfeld Farbe initialisiert oder der Benutzer die linke Maustaste gedrückt. Weitere Informationen zu `CMFCColorDialog`, finden Sie unter [CMFCColorDialog Klasse](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage-Klasse](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

