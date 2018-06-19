---
title: CMFCPropertyPage Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3352841b1b495d1718ffa6be034239ecd7e50c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366641"
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage-Klasse
Die `CMFCPropertyPage` Klasse unterstützt die Anzeige von Popupmenüs auf einer Eigenschaftenseite.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Erstellt ein `CMFCPropertyPage`-Objekt.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCPropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCPropertyPage::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|`CMFCPropertyPage::OnSetActive`|Diese Memberfunktion wird vom Framework aufgerufen, wenn die Seite vom Benutzer ausgewählt wird und als aktive Seite. (Überschreibt [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|  
|`CMFCPropertyPage::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie an verteilt wurden die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. Weitere Informationen und Methodensyntax finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CPropertyPage::PreTranslateMessage`.)|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCPropertyPage` Klasse stellt einzelne Seiten eines Eigenschaftenblatts, auch als Dialogfeld im Registerkartenformat bezeichnet.  
  
 Verwenden der `CMFCPropertyPage` -Klasse zusammen mit der [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) Klasse. Um Menüs auf einer Eigenschaftenseite verwenden möchten, ersetzen Sie alle Vorkommen der `CPropertyPage` -Klasse mit der `CMFCPropertyPage` Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpropertypage.h  
  
##  <a name="cmfcpropertypage"></a>  CMFCPropertyPage::CMFCPropertyPage  
 Erstellt ein `CMFCPropertyPage`-Objekt.  
  
```  
CMFCPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption=0);

 
CMFCPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption=0);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDTemplate`  
 Ressourcen-ID der Vorlage für diese Seite.  
  
 `nIDCaption`  
 Ressourcen-ID der Bezeichnung, auf der Registerkarte für diese Seite eingefügt werden soll. Bei 0 wird der Name aus der Dialogfeldvorlage für diese Seite abgerufen. Der Standardwert ist 0.  
  
 `lpszTemplateName`  
 Verweist auf den Namen der Vorlage für diese Seite. Nicht mit `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den Konstruktorparametern, finden Sie unter [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertySheet-Klasse](../../mfc/reference/cmfcpropertysheet-class.md)
