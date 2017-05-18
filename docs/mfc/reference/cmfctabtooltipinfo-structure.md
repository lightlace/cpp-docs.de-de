---
title: CMFCTabToolTipInfo Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
caps.latest.revision: 27
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
ms.openlocfilehash: b9750cd9369313a3ed6ea9474d401cd0068a75fa
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo-Struktur
Diese Struktur enthält Informationen über die MDI-Registerkarte, der der Benutzer über bewegt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|Gibt den Index des Registerkarten-Steuerelements.|  
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|Ein Zeiger auf das Registerkarten-Steuerelement.|  
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|Der QuickInfo-Text.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Zeiger auf eine `CMFCTabToolTipInfo` Struktur als Parameter übergeben wird die `AFX_WM_ON_GET_TAB_TOOLTIP` Nachricht. Diese Meldung wird generiert, wenn MDI-Registerkarten aktiviert sind und der Benutzer über ein Registerkarten-Steuerelement bewegt wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt wie `CMFCTabToolTipInfo` werden in der [MDITabsDemo-Beispiel: MFC-im Registerkartenformat MDI-Anwendung](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxbasetabctrl.h  
  
##  <a name="m_ntabindex"></a>CMFCTabToolTipInfo::m_nTabIndex  
 Gibt den Index des Registerkarten-Steuerelements.  
  
```  
int m_nTabIndex;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Index der Registerkarte für die der Benutzer zeigt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt wie `m_nTabIndex` werden in der [MDITabsDemo-Beispiel: MFC-im Registerkartenformat MDI-Anwendung](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="m_ptabwnd"></a>CMFCTabToolTipInfo::m_pTabWnd  
 Ein Zeiger auf das Registerkarten-Steuerelement.  
  
```  
CMFCBaseTabCtrl* m_pTabWnd;  
```  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt wie `m_pTabWnd` werden in der [MDITabsDemo-Beispiel: MFC-im Registerkartenformat MDI-Anwendung](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="m_strtext"></a>CMFCTabToolTipInfo::m_strText  
 Der QuickInfo-Text.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Zeichenfolge leer ist, wird die QuickInfo nicht angezeigt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt wie `m_strText` werden in der [MDITabsDemo-Beispiel: MFC-im Registerkartenformat MDI-Anwendung](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

