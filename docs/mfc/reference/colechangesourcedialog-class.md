---
title: Klasse COleChangeSourceDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
dev_langs:
- C++
helpviewer_keywords:
- OLE Change Source dialog box
- COleChangeSourceDialog class
- dialog boxes, OLE
- OLE dialog boxes, Change Source
- OleUIChangeSource structure
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
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
ms.openlocfilehash: 4a1af032b9a10a0262f0267056b675eed7da509c
ms.lasthandoff: 02/24/2017

---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog-Klasse
Wird für das OLE-Dialogfeld "Quelle ändern" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Erstellt ein `COleChangeSourceDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Ändern der Quelle an.|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Ruft den Anzeigenamen für die vollständige Quelle ab.|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|Ruft den Dateinamen aus dem Quellnamen ab.|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Ruft das Präfix der vorherigen Quelle ab.|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|Ruft den Elementnamen aus dem Quellnamen ab.|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Ruft das Präfix des neuen Quelle|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Gibt an, ob die Datenquelle gültig ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleChangeSourceDialog` Wenn Sie dieses Dialogfeld aufrufen möchten. Nach einer `COleChangeSourceDialog` -Objekts, können Sie die [M_cs](#m_cs) Struktur, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_cs` Struktur ist vom Typ [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160). Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Member-Funktion.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) -Struktur im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="colechangesourcedialog"></a>COleChangeSourceDialog::COleChangeSourceDialog  
 Diese Funktion erstellt ein `COleChangeSourceDialog` Objekt.  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Zeiger auf das verknüpfte [COleClientItem](../../mfc/reference/coleclientitem-class.md) , dessen Datenquelle ist, aktualisiert werden.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist dies **NULL**, wird das übergeordnete Fenster des Dialogfelds zum Hauptfenster der Anwendung festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen Sie die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur und [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) -Funktion im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="domodal"></a>COleChangeSourceDialog::DoModal  
 Rufen Sie diese Funktion, um das Dialogfeld OLE Ändern der Quelle anzuzeigen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** , wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen über die Art des Fehlers zu erhalten, die aufgetreten sind. Eine Liste möglicher Fehler, finden Sie unter der [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) -Funktion im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeld-Steuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cs](#m_cs) -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können zum Abrufen von eingegebenen Einstellungen oder Informationen aus dem Dialogfeld Memberfunktionen aufrufen. Der folgenden Liste werden die normalen Abfragefunktionen:  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>COleChangeSourceDialog::GetDisplayName  
 Rufen Sie diese Funktion zum Abrufen der vollständige Anzeigename für den verknüpften Client-Element.  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die vollständige Quelle Anzeigenamen (Moniker) für die [COleClientItem](../../mfc/reference/coleclientitem-class.md) im Konstruktor angegeben.  
  
##  <a name="getfilename"></a>COleChangeSourceDialog::GetFileName  
 Rufen Sie diese Funktion zum Abrufen des Datei-Moniker Teils der Anzeigename für den verknüpften Client-Element.  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Datei-Moniker Teil der Anzeigename der Quelle für die [COleClientItem](../../mfc/reference/coleclientitem-class.md) im Konstruktor angegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Datei-Moniker zusammen mit der Element-Moniker bietet der vollständige Anzeigename.  
  
##  <a name="getfromprefix"></a>COleChangeSourceDialog::GetFromPrefix  
 Rufen Sie diese Funktion, um die vorherigen Präfixzeichenfolge für die Quelle zu erhalten.  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Präfixzeichenfolge der Quelle.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Dieser Wert stammt direkt aus der **LpszFrom** Mitglied der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) -Struktur im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getitemname"></a>COleChangeSourceDialog::GetItemName  
 Rufen Sie diese Funktion zum Abrufen des Element-Moniker Teils der Anzeigename für den verknüpften Client-Element.  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Element-Moniker Teil der Anzeigename der Quelle für die [COleClientItem](../../mfc/reference/coleclientitem-class.md) im Konstruktor angegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Datei-Moniker zusammen mit der Element-Moniker bietet der vollständige Anzeigename.  
  
##  <a name="gettoprefix"></a>COleChangeSourceDialog::GetToPrefix  
 Rufen Sie diese Funktion, um die neue Präfixzeichenfolge für die Quelle zu erhalten.  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Präfixzeichenfolge der Quelle.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Dieser Wert stammt direkt aus der **LpszTo** Mitglied der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) -Struktur im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_cs"></a>COleChangeSourceDialog::m_cs  
 Datenmember ist eine Struktur vom Typ [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>Hinweise  
 `OLEUICHANGESOURCE`Dient zum Steuern des Verhaltens des Dialogfelds OLE Ändern der Quelle. Mitglieder dieser Struktur können direkt geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) -Struktur im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isvalidsource"></a>COleChangeSourceDialog::IsValidSource  
 Rufen Sie diese Funktion, um zu bestimmen, ob die neue Datenquelle gültig ist.  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die neue Datenquelle gültig ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) -Struktur im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)

