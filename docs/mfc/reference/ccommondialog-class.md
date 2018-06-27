---
title: CCommonDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
dev_langs:
- C++
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53f53bdb19c6f40d73179b600051ecfaf6b69c94
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950634"
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
  
##  <a name="ccommondialog"></a>  CCommonDialog::CCommonDialog  
 Erstellt ein `CCommonDialog`-Objekt.  
  
```  
explicit CCommonDialog(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
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
