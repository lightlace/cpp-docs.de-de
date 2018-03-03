---
title: COleDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
dev_langs:
- C++
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae60b9e5a0d2e79d2bf6d9cc06eebfa9df0c6e23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="coledialog-class"></a>COleDialog-Klasse
Stellt die Funktionalität allgemeiner Dialogfelder für OLE bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDialog::GetLastError](#getlasterror)|Ruft den vom Dialogfeld zurückgegebenen Fehlercode ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class Library stellt mehrere Klassen abgeleitet `COleDialog`:  
  
- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)  
  
- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)  
  
- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)  
  
- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)  
  
- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)  
  
- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)  
  
- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)  
  
- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `COleDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="getlasterror"></a>COleDialog::GetLastError  
 Rufen Sie die `GetLastError` Memberfunktion zusätzlichen Fehlerinformationen abgerufen beim `DoModal` gibt **IDABORT**.  
  
```  
UINT GetLastError() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zurückgegebene Fehlercodes `GetLastError` richten sich nach den spezifischen Dialogfeld angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter der `DoModal` Memberfunktion in den abgeleiteten Klassen Informationen zu bestimmten Fehlermeldungen.  
  
## <a name="see-also"></a>Siehe auch  
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



