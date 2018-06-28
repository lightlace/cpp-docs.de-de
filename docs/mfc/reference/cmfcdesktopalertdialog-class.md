---
title: CMFCDesktopAlertDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::CreateFromParams
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::GetDlgSize
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::HasFocus
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::PreTranslateMessage
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertDialog [MFC], CreateFromParams
- CMFCDesktopAlertDialog [MFC], GetDlgSize
- CMFCDesktopAlertDialog [MFC], HasFocus
- CMFCDesktopAlertDialog [MFC], PreTranslateMessage
ms.assetid: a53c60aa-9607-485b-b826-ec64962075f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f162a8da230177509ebe67741580ef224b20ba19
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040794"
---
# <a name="cmfcdesktopalertdialog-class"></a>CMFCDesktopAlertDialog-Klasse
Die `CMFCDesktopAlertDialog` Klasse dient zusammen mit den [CMFCDesktopAlertWnd-Klasse](../../mfc/reference/cmfcdesktopalertwnd-class.md) zum Anzeigen eines benutzerdefinierten Dialogfelds in einem Popupfenster.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDesktopAlertDialog : public CDialogEx  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDesktopAlertDialog::CreateFromParams](#createfromparams)||  
|[CMFCDesktopAlertDialog::GetDlgSize](#getdlgsize)||  
|[CMFCDesktopAlertDialog::HasFocus](#hasfocus)||  
|[CMFCDesktopAlertDialog::PreTranslateMessage](#pretranslatemessage)|(Überschreibt `CDialogEx::PreTranslateMessage`.)|  
  
### <a name="remarks"></a>Hinweise  
 Führen Sie die folgenden Schritte aus, um ein benutzerdefiniertes Dialogfeld in einem Popupfenster anzuzeigen:  
  
1.  Leiten Sie eine Klasse von `CMFCDesktopAlertDialog` ab.  
  
2.  Erstellen Sie eine untergeordnete Dialogfeldvorlage in den Ressourcen des Projekts.  
  
3.  Rufen Sie [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) mit Ressourcen-ID der Dialogfeldvorlage und einem Zeiger auf die laufzeitklasseninformationen der abgeleiteten Klasse als Parameter.  
  
4.  Programmieren Sie das benutzerdefinierte Dialogfeld so, dass es alle Benachrichtigungen von den gehosteten Steuerelementen verarbeitet, oder programmieren Sie die gehosteten Steuerelemente so, dass sie diese Benachrichtigungen direkt verarbeiten.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDesktopAlertDialog.h  
  
##  <a name="createfromparams"></a>  CMFCDesktopAlertDialog::CreateFromParams  

  
```  
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,  
    CMFCDesktopAlertWnd* pParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Params*  
 [in] *pParent*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdlgsize"></a>  CMFCDesktopAlertDialog::GetDlgSize  

  
```  
CSize GetDlgSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasfocus"></a>  CMFCDesktopAlertDialog::HasFocus  

  
```  
BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="pretranslatemessage"></a>  CMFCDesktopAlertDialog::PreTranslateMessage  

  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pMsg*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd-Klasse](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWndInfo-Klasse](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CDialogEx-Klasse](../../mfc/reference/cdialogex-class.md)
