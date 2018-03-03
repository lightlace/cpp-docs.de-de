---
title: CMFCDesktopAlertWndInfo-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f257575abbf405177b2524c4c803c0b3d250187
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo-Klasse
Die `CMFCDesktopAlertWndInfo` Klasse wird verwendet, mit der [CMFCDesktopAlertWnd-Klasse](../../mfc/reference/cmfcdesktopalertwnd-class.md). Bestimmt die Steuerelemente, die angezeigt werden, wenn das Desktopwarnungsfenster angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Ein Handle für das Symbol, das angezeigt wird.|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Die Befehls-ID, das einen Link auf die Warnung Desktopfenster zugeordnet ist.|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Der Text, der auf die Warnung Desktopfenster angezeigt wird.|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Der Link, der auf die Warnung Desktopfenster angezeigt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCDesktopAlertWndInfo` Klasse wird zum Übergeben der [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) Methode, um die Elemente anzugeben, die auf das Standarddialogfeld von die Warnung Desktopfenster angezeigt werden. Das Dialogfeld "Standard" kann drei Elemente enthalten:  
  
-   Ein Symbol, das durch den Aufruf festgelegt ist [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon).  
  
-   Eine Bezeichnung oder eine Textnachricht an, der durch den Aufruf festgelegt wird [CMFCDesktopAlertWndInfo::m_strText](#m_strtext).  
  
-   Ein Link, der durch den Aufruf festgelegt wird [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl). Rufen Sie zum Festlegen des Befehls, der ausgeführt wird, wenn auf der Link geklickt wird [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid).  
  
 Wenn das Dialogfeld "Standard" nicht ausreichend ist, können Sie das Erstellen eines benutzerdefinierten Dialogfelds und übergeben sie an der [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) Methode anstelle der Verwendung dieser Klasse. Weitere Informationen finden Sie unter [CMFCDesktopAlertDialog Klasse](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Elemente in der `CMFCDesktopAlertWndInfo` Klasse. Im Beispiel wird veranschaulicht, wie das Handle auf das Symbol, das angezeigt wird, den Text festgelegt, der angezeigt wird, auf die Warnung Desktopfenster, den Link, der auf die Warnung Desktopfenster angezeigt wird und die Befehls-ID, die einen Link auf die Warnung Desktopfenster zugeordnet ist. In diesem Beispiel ist Teil der [Desktop Warnung Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDesktopAlertDialog.h  
  
##  <a name="operator_eq"></a>CMFCDesktopAlertWndInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_hicon"></a>CMFCDesktopAlertWndInfo::m_hIcon  
 Ein Handle für das Symbol, das angezeigt wird.  
  
```  
HICON m_hIcon;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_nurlcmdid"></a>CMFCDesktopAlertWndInfo::m_nURLCmdID  
 Die Befehls-ID, das einen Link auf die Warnung Desktopfenster zugeordnet ist.  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Befehls-ID wird an den Besitzer der Popup-Fenster gesendet, klickt der Benutzer auf den Link, der gemäß [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl).  
  
##  <a name="m_strtext"></a>CMFCDesktopAlertWndInfo::m_strText  
 Der Text, der auf die Warnung Desktopfenster angezeigt wird.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_strurl"></a>CMFCDesktopAlertWndInfo::m_strURL  
 Der Link, der auf die Warnung Desktopfenster angezeigt wird.  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer auf den Link klickt, den Befehl, hat die [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) Befehls-ID wird an den Besitzer des Popupfensters gesendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd-Klasse](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [Cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [CMFCDesktopAlertDialog-Klasse](../../mfc/reference/cmfcdesktopalertdialog-class.md)
