---
title: COleChangeSourceDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08b4095b535724f7132a2b286ce52cb46286932b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037595"
---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog-Klasse
Wird für das OLE-Dialogfeld "Quelle ändern" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Erstellt ein `COleChangeSourceDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|Zeigt das Dialogfeld für die Quelle für das OLE-ändern.|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Ruft den vollständigen Quellcode-Anzeigenamen ab.|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|Ruft den Dateinamen aus dem Quellnamen ab.|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Ruft das Präfix des vorherigen Quelle ab.|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|Ruft den Namen des Elements nicht mit dem Quellnamen ab.|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Ruft das Präfix der Quelle ab|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Gibt an, ob die Datenquelle gültig ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleChangeSourceDialog` Wenn Sie das Dialogfeld aufgerufen werden soll. Nach einem `COleChangeSourceDialog` -Objekts können Sie mithilfe der [M_cs](#m_cs) Struktur initialisiert werden, die Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_cs` Struktur ist vom Typ [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160). Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Memberfunktion.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur im Windows SDK.  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="colechangesourcedialog"></a>  COleChangeSourceDialog::COleChangeSourceDialog  
 Diese Funktion erstellt eine `COleChangeSourceDialog` Objekt.  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pItem*  
 Zeiger auf die verknüpften [COleClientItem](../../mfc/reference/coleclientitem-class.md) , deren Datenquellen aktualisiert werden wird.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist er **NULL**, das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur und [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) -Funktion in Windows SDK.  
  
##  <a name="domodal"></a>  COleChangeSourceDialog::DoModal  
 Mit dieser Funktion wird zum Anzeigen der Quelle für das OLE-ändern-Dialogfelds.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** wird das Dialogfeld erfolgreich angezeigt.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Auflistung möglicher Fehler finden Sie die [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) -Funktion in Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cs](#m_cs) -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können zum Abrufen von Einstellungen für Benutzer eingegeben oder Informationen über das Dialogfeld Memberfunktionen aufrufen. Die folgende Liste enthält die typische Abfragefunktionen:  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>  COleChangeSourceDialog::GetDisplayName  
 Mit dieser Funktion wird zum Abrufen der vollständige Anzeigename für den verknüpften Client-Element.  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den vollständigen Quellcode-Anzeigenamen (Moniker) für die [COleClientItem](../../mfc/reference/coleclientitem-class.md) im Konstruktor angegeben.  
  
##  <a name="getfilename"></a>  COleChangeSourceDialog::GetFileName  
 Mit dieser Funktion wird zum Abrufen des Datei Moniker Teils des Anzeigenamens für den verknüpften Client-Element.  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Datei Moniker Teil der Anzeigename der Quelle für die [COleClientItem](../../mfc/reference/coleclientitem-class.md) im Konstruktor angegeben.  
  
### <a name="remarks"></a>Hinweise  
 Der Moniker Datei zusammen mit der Element-Moniker bietet der vollständige Anzeigename.  
  
##  <a name="getfromprefix"></a>  COleChangeSourceDialog::GetFromPrefix  
 Rufen Sie diese Funktion, um die vorherigen Präfixzeichenfolge für die Quelle zu erhalten.  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Präfixzeichenfolge der Quelle.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach dem Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Dieser Wert stammt direkt aus der **LpszFrom** Mitglied der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur im Windows SDK.  
  
##  <a name="getitemname"></a>  COleChangeSourceDialog::GetItemName  
 Mit dieser Funktion wird zum Abrufen des Element-Moniker Teils der Anzeigename für den verknüpften Client-Element.  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Element-Moniker Teil der Anzeigename der Quelle für die [COleClientItem](../../mfc/reference/coleclientitem-class.md) im Konstruktor angegeben.  
  
### <a name="remarks"></a>Hinweise  
 Der Moniker Datei zusammen mit der Element-Moniker bietet der vollständige Anzeigename.  
  
##  <a name="gettoprefix"></a>  COleChangeSourceDialog::GetToPrefix  
 Rufen Sie diese Funktion, um die neue Präfixzeichenfolge für die Quelle zu erhalten.  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Präfixzeichenfolge der Quelle.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach dem Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Dieser Wert stammt direkt aus der **LpszTo** Mitglied der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur im Windows SDK.  
  
##  <a name="m_cs"></a>  COleChangeSourceDialog::m_cs  
 Datenmember ist eine Struktur vom Typ [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>Hinweise  
 `OLEUICHANGESOURCE` Dient zum Steuern des Verhaltens des Dialogfelds Quelle für das OLE-ändern. Mitglieder dieser Struktur können direkt geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur im Windows SDK.  
  
##  <a name="isvalidsource"></a>  COleChangeSourceDialog::IsValidSource  
 Rufen Sie diese Funktion, um zu bestimmen, ob die neue Datenquelle gültig ist.  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die neue Datenquelle gültig ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion nur nach dem Aufruf [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Struktur im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
