---
title: COleLinksDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
dev_langs:
- C++
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b998cc18ac0c357b57bc841f6db13700b078063
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="colelinksdialog-class"></a>COleLinksDialog-Klasse
Wird für das OLE-Dialogfeld "Verknüpfungen bearbeiten" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Erstellt ein `COleLinksDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Verknüpfungen bearbeiten.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|Eine Struktur des Typs **OLEUIEDITLINKS** , steuert das Verhalten des Dialogfelds.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleLinksDialog` Wenn Sie das Dialogfeld aufgerufen werden soll. Nach einem `COleLinksDialog` -Objekts können Sie mithilfe der [M_el](#m_el) Struktur initialisiert werden, die Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_el` Struktur ist vom Typ **OLEUIEDITLINKS**. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Memberfunktion.  
  
> [!NOTE]
>  Vom Assistenten generierten Container-Anwendungscode verwendet diese Klasse.  
  
 Weitere Informationen finden Sie unter der [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) Struktur im Windows SDK.  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="domodal"></a>COleLinksDialog::DoModal  
 Zeigt das Dialogfeld OLE Verknüpfungen bearbeiten.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** wird das Dialogfeld erfolgreich angezeigt.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Auflistung möglicher Fehler finden Sie die [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) Funktion im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_el](#m_el) -Struktur, ergreifen Sie es vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
##  <a name="colelinksdialog"></a>COleLinksDialog::COleLinksDialog  
 Erstellt ein `COleLinksDialog`-Objekt.  
  
```  
COleLinksDialog (
    COleDocument* pDoc,  
    CView* pView,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDoc`  
 Verweist auf das OLE-Dokument, das den zu bearbeitenden enthält.  
  
 `pView`  
 Verweist auf die aktuelle Ansicht auf `pDoc`.  
  
 `dwFlags`  
 Erstellung-Flag, das entweder 0 enthält oder **ELF_SHOWHELP** angeben, ob die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld angezeigt wird.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist er **NULL**, das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur bildet eine `COleLinksDialog` Objekt. Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.  
  
##  <a name="m_el"></a>COleLinksDialog::m_el  
 Struktur des Typs **OLEUIEDITLINKS** zum Steuern des Verhaltens im Dialogfeld "Verknüpfungen bearbeiten" verwendet.  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können weder direkt noch über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) Struktur im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
