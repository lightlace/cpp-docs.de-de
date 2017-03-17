---
title: Klasse CMFCDesktopAlertWndInfo | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- CMFCDesktopAlertWndInfo class
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: 26
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
ms.openlocfilehash: 7013a7c9b29c6dc9e6324ca0490a667ed79c88f7
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo-Klasse
Die `CMFCDesktopAlertWndInfo` -Klasse wird zusammen mit der [CMFCDesktopAlertWnd Klasse](../../mfc/reference/cmfcdesktopalertwnd-class.md). Bestimmt die Steuerelemente, die angezeigt werden, wenn das Desktopwarnungsfenster angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Ein Handle für das Symbol, das angezeigt wird.|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Die Befehls-ID, die einen Link auf der desktop-Benachrichtigungsfenster zugeordnet.|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Der Text, der auf dem desktop-Benachrichtigungsfenster angezeigt wird.|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Der Link, der auf dem desktop-Benachrichtigungsfenster angezeigt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCDesktopAlertWndInfo` Klasse übergeben wird, um die [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) Methode, um die Elemente anzugeben, die auf das Standarddialogfeld von desktop-Benachrichtigungsfenster angezeigt werden. Das Standarddialogfeld kann drei Elemente enthalten:  
  
-   Ein Symbol, das durch Aufrufen von festgelegt ist [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon).  
  
-   Eine Bezeichnung oder eine Textnachricht, die durch Aufrufen von festgelegt ist [CMFCDesktopAlertWndInfo::m_strText](#m_strtext).  
  
-   Eine Verknüpfung, die durch Aufrufen von festgelegt ist [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl). Rufen Sie zum Festlegen des Befehls, der ausgeführt wird, wenn auf der Link geklickt wird [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid).  
  
 Wenn das Standarddialogfeld nicht ausreichend ist, können Sie ein benutzerdefiniertes Dialogfeld erstellen und übergeben es an die [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) -Methode anstelle der Verwendung dieser Klasse. Weitere Informationen finden Sie unter [CMFCDesktopAlertDialog Klasse](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Elemente in der `CMFCDesktopAlertWndInfo` Klasse. Im Beispiel wird veranschaulicht, wie das Handle zu dem Symbol, das angezeigt wird, den Text festzulegen, der angezeigt wird, auf den desktop-Benachrichtigungsfenster, den Link, der auf dem desktop-Benachrichtigungsfenster angezeigt wird und die Befehls-ID, die einen Link auf der desktop-Benachrichtigungsfenster zugeordnet ist. Dieses Beispiel ist Teil der [Desktop Warnung Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&3;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
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
 Die Befehls-ID, die einen Link auf der desktop-Benachrichtigungsfenster zugeordnet.  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Befehls-ID wird an den Besitzer der Popup-Fenster gesendet, klickt der Benutzer auf den angegebenen Link [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl).  
  
##  <a name="m_strtext"></a>CMFCDesktopAlertWndInfo::m_strText  
 Der Text, der auf dem desktop-Benachrichtigungsfenster angezeigt wird.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_strurl"></a>CMFCDesktopAlertWndInfo::m_strURL  
 Der Link, der auf dem desktop-Benachrichtigungsfenster angezeigt wird.  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer auf den Link klickt, hat der Befehl, der die [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) Befehls-ID wird an den Besitzer des Popupfensters gesendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd-Klasse](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [CMFCDesktopAlertDialog-Klasse](../../mfc/reference/cmfcdesktopalertdialog-class.md)

