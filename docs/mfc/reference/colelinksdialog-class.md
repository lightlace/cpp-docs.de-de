---
title: Klasse COleLinksDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- Edit Links dialog box
- COleLinksDialog class
- dialog boxes, OLE
- OLE Edit Links dialog box
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
caps.latest.revision: 22
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
ms.openlocfilehash: ed256b3a4d3236863e3dcccb7614949f650f058b
ms.lasthandoff: 02/24/2017

---
# <a name="colelinksdialog-class"></a>COleLinksDialog-Klasse
Wird für das OLE-Dialogfeld "Verknüpfungen bearbeiten" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[COleLinksDialog::m_el](#m_el)|Eine Struktur vom Typ **OLEUIEDITLINKS** , steuert das Verhalten des Dialogfelds.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleLinksDialog` Wenn Sie dieses Dialogfeld aufrufen möchten. Nach einer `COleLinksDialog` -Objekts, können Sie die [M_el](#m_el) Struktur, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_el` Struktur ist vom Typ **OLEUIEDITLINKS**. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Member-Funktion.  
  
> [!NOTE]
>  Diese Klasse wird von Anwendung Container vom Assistenten generierten Code verwendet.  
  
 Weitere Informationen finden Sie unter der [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
  
- **IDOK** , wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen über die Art des Fehlers zu erhalten, die aufgetreten sind. Eine Liste möglicher Fehler, finden Sie unter der [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeld-Steuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_el](#m_el) -Struktur, sollten Sie dies tun sie vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
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
 Erstellung-Flag, das entweder 0 enthält oder **ELF_SHOWHELP** an, ob die Hilfeschaltfläche angezeigt wird, wenn das Dialogfeld angezeigt wird.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist dies **NULL**, das übergeordnete Fenster des Dialogfelds zum Hauptfenster der Anwendung festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt nur eine `COleLinksDialog` Objekt. Um das Dialogfeld anzuzeigen, rufen Sie die [DoModal](#domodal) Funktion.  
  
##  <a name="m_el"></a>COleLinksDialog::m_el  
 Struktur des Typs **OLEUIEDITLINKS** zum Steuern des Verhaltens im Dialogfeld "Verknüpfungen bearbeiten" verwendet.  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können entweder direkt oder über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)

