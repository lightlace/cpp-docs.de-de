---
title: Klasse COleUpdateDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleUpdateDialog
dev_langs:
- C++
helpviewer_keywords:
- Update dialog
- links [C++], updating
- updating OLE links
- OLE dialog boxes, Edit Link
- OLE link updating
- COleUpdateDialog class
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
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
ms.openlocfilehash: 8066a8dc9e572c14e9423af62d340e249351ac11
ms.lasthandoff: 02/24/2017

---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog-Klasse
Wird für einen Sonderfall des OLE-Dialogfelds "Verknüpfungen bearbeiten" verwendet, das eingesetzt werden sollte, wenn in einem Dokument nur vorhandene Links oder eingebettete Objekte aktualisiert werden müssen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
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
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
 `COleUpdateDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="a-namecoleupdatedialoga--coleupdatedialogcoleupdatedialog"></a><a name="coleupdatedialog"></a>COleUpdateDialog::COleUpdateDialog  
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
 Verweist auf das Dokument mit den Links, die möglicherweise aktualisieren.  
  
 *bUpdateLinks*  
 Flag, die bestimmt, ob verknüpfte Objekte aktualisiert werden.  
  
 *bUpdateEmbeddings*  
 Flag, die bestimmt, ob eingebettete Objekte aktualisiert werden.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist dies **NULL**, wird das übergeordnete Fenster des Dialogfelds zum Hauptfenster der Anwendung festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt nur eine `COleUpdateDialog` Objekt. Um das Dialogfeld anzuzeigen, rufen Sie [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Diese Klasse sollte verwendet werden, sondern `COleLinksDialog` verknüpfte oder eingebettete Elemente Wenn Sie nur vorhandene aktualisieren möchten.  
  
##  <a name="a-namedomodala--coleupdatedialogdomodal"></a><a name="domodal"></a>COleUpdateDialog::DoModal  
 Zeigt das Dialogfeld Verknüpfungen bearbeiten im Aktualisierungsmodus.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** Wenn das Dialogfeld erfolgreich zurückgegeben.  
  
- **IDCANCEL** ggf. keine verknüpfte oder eingebettete Objekte im aktuellen Dokument aktualisieren.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen über die Art des Fehlers zu erhalten, die aufgetreten sind. Eine Liste möglicher Fehler, finden Sie unter der [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Alle Links und eingebetteten werden aktualisiert, wenn der Benutzer auf die Schaltfläche "Abbrechen" auswählt.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [COleLinksDialog-Klasse](../../mfc/reference/colelinksdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog-Klasse](../../mfc/reference/colelinksdialog-class.md)

