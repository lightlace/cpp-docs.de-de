---
title: Klasse CMFCPropertyPage | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyPage::PreTranslateMessage method
- CMFCPropertyPage::CreateObject method
- CMFCPropertyPage class
- CMFCPropertyPage::OnSetActive method
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
caps.latest.revision: 30
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
ms.openlocfilehash: 0e9cdfa8a98c034839fac119c828cf1b92a1867a
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage-Klasse
Die `CMFCPropertyPage` Klasse unterstützt die Anzeige von Popupmenüs auf einer Eigenschaftenseite.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Erstellt ein `CMFCPropertyPage`-Objekt.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCPropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCPropertyPage::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|`CMFCPropertyPage::OnSetActive`|Diese Member-Funktion wird vom Framework aufgerufen, wenn die Seite vom Benutzer ausgewählt und wird die aktive Seite. (Überschreibt [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|  
|`CMFCPropertyPage::PreTranslateMessage`|Windows-Nachrichten übersetzt, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. Weitere Informationen und Methodensyntax finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CPropertyPage::PreTranslateMessage`.)|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCPropertyPage` Klasse darstellt, einzelne Seiten eines Eigenschaftenblatts, auch als Dialogfeld im Registerkartenformat bekannt.  
  
 Verwenden der `CMFCPropertyPage` -Klasse zusammen mit der [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) Klasse. Für die Verwendung der Menüs auf einer Eigenschaftenseite ersetzt alle Vorkommen der `CPropertyPage` Klasse, wobei die `CMFCPropertyPage` Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpropertypage.h  
  
##  <a name="a-namecmfcpropertypagea--cmfcpropertypagecmfcpropertypage"></a><a name="cmfcpropertypage"></a>CMFCPropertyPage::CMFCPropertyPage  
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
 Ressourcen-ID der Bezeichnung, die auf der Registerkarte für diese Seite zu platzieren. Bei 0 wird der Name aus der Dialogfeldvorlage für diese Seite abgerufen. Der Standardwert ist 0.  
  
 `lpszTemplateName`  
 Zeigt den Namen der Vorlage für diese Seite. Nicht `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den Konstruktorparametern, finden Sie unter [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertySheet-Klasse](../../mfc/reference/cmfcpropertysheet-class.md)

