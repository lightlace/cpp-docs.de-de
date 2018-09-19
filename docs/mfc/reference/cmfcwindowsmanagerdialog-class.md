---
title: CMFCWindowsManagerDialog-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71c85d3061da7cf4c87abef9549542900e962f64
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707004"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog-Klasse
Die `CMFCWindowsManagerDialog` Objekt kann ein Benutzer zum Verwalten von untergeordneten MDI-Fenster in einer MDI-Anwendung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Erstellt ein `CMFCWindowsManagerDialog`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCWindowsManagerDialog` enthält eine Liste von untergeordneten MDI-Fenster, die derzeit in der Anwendung geöffnet sind. Der Benutzer kann den Zustand des untergeordneten MDI-Fenster mithilfe dieses Dialogfelds manuell steuern.  
  
 `CMFCWindowsManagerDialog` eingebettet in der [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md). Die `CMFCWindowsManagerDialog` ist keine Klasse, die manuell erstellt werden soll. Rufen Sie stattdessen die Funktion [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog), und er erstellt und zeigt eine `CMFCWindowsManagerDialog` Objekt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCWindowsManagerDialog` Objekt durch Aufrufen von `CMDIFrameWndEx::ShowWindowsDialog`. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxWindowsManagerDialog.h  
  
##  <a name="cmfcwindowsmanagerdialog"></a>  CMFCWindowsManagerDialog::CMFCWindowsManagerDialog  
 Erstellt eine [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) Objekt.  
  
```  
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,  
    BOOL bHelpButton = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
*pMDIFrame*<br/>
[in] Ein Zeiger auf das übergeordnete Element oder Besitzer-Fenster.  
  
*bHelpButton*<br/>
[in] Ein boolescher Parameter, der angibt, ob das Framework zeigt eine **Hilfe** Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu Erscheinungsbild-Manager, finden Sie unter [Visualisierungs-Manager](../../mfc/visualization-manager.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md)
