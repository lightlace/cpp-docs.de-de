---
title: COleUpdateDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
dev_langs: C++
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32a7d41c507c2b7b932ba33df911151bfc417091
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog-Klasse
Wird für einen Sonderfall des OLE-Dialogfelds "Verknüpfungen bearbeiten" verwendet, das eingesetzt werden sollte, wenn in einem Dokument nur vorhandene Links oder eingebettete Objekte aktualisiert werden müssen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|Erstellt ein `COleUpdateDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleUpdateDialog::DoModal](#domodal)|Zeigt die **Verknüpfungen bearbeiten** Dialogfeld in einem Updatemodus.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
 `COleUpdateDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="coleupdatedialog"></a>COleUpdateDialog::COleUpdateDialog  
 Erstellt ein `COleUpdateDialog`-Objekt.  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Verweist auf das Dokument mit den Links, die ggf. aktualisieren.  
  
 *bUpdateLinks*  
 Flag, die bestimmt, ob verknüpfte Objekte aktualisiert werden.  
  
 *bUpdateEmbeddings*  
 Flag, die bestimmt, ob eingebettete Objekte aktualisiert werden.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist er **NULL**, das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur bildet eine `COleUpdateDialog` Objekt. Um das Dialogfeld anzuzeigen, rufen [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Diese Klasse sollte verwendet werden, anstelle von `COleLinksDialog` verknüpfte oder eingebettete Elemente Wenn Sie nur vorhandene aktualisieren möchten.  
  
##  <a name="domodal"></a>COleUpdateDialog::DoModal  
 Zeigt das Dialogfeld "Verknüpfungen bearbeiten" im Feld Updatemodus.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** des Dialogfelds "" wurde erfolgreich zurückgegeben.  
  
- **IDCANCEL** ggf. keine verknüpfte oder eingebettete Objekte im aktuellen Dokument aktualisieren.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Auflistung möglicher Fehler finden Sie die [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) Funktion im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer die Schaltfläche "Abbrechen" auswählt, werden alle Verknüpfungen und/oder einbettungen aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [COleLinksDialog-Klasse](../../mfc/reference/colelinksdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog-Klasse](../../mfc/reference/colelinksdialog-class.md)
