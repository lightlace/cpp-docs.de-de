---
title: CCommonDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
dev_langs: C++
helpviewer_keywords: CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a42acf9c4655868bcc078b3e40d3966587aeaaad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccommondialog-class"></a>CCommonDialog-Klasse
Die Basisklasse für Klassen, die Funktionalität der allgemeinen Windows-Dialogfelder kapseln.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCommonDialog : public CDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCommonDialog::CCommonDialog](#ccommondialog)|Erstellt ein `CCommonDialog`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Klassen kapseln die Funktionalität des allgemeinen Windows-Dialogfelder:  
  
- [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
- [CFontDialog](../../mfc/reference/cfontdialog-class.md)  
  
- [CColorDialog](../../mfc/reference/ccolordialog-class.md)  
  
- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)  
  
- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)  
  
- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)  
  
- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)  
  
- [COleDialog](../../mfc/reference/coledialog-class.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CCommonDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="ccommondialog"></a>CCommonDialog::CCommonDialog  
 Erstellt ein `CCommonDialog`-Objekt.  
  
```  
explicit CCommonDialog(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist er **NULL**, dem Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog) vollständige Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md)   
 [CFontDialog-Klasse](../../mfc/reference/cfontdialog-class.md)   
 [CColorDialog-Klasse](../../mfc/reference/ccolordialog-class.md)   
 [CPageSetupDialog-Klasse](../../mfc/reference/cpagesetupdialog-class.md)   
 [CPrintDialog-Klasse](../../mfc/reference/cprintdialog-class.md)   
 [CFindReplaceDialog-Klasse](../../mfc/reference/cfindreplacedialog-class.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
