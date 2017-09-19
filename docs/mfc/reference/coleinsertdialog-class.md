---
title: Klasse COleInsertDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
dev_langs:
- C++
helpviewer_keywords:
- OLE Insert Object dialog box
- dialog boxes, OLE
- COleInsertDialog class
- Insert Object dialog box
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 078f421dacc79ff929249cd35c520b0c4d4a222e
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="coleinsertdialog-class"></a>COleInsertDialog-Klasse
Wird für das OLE-Dialogfeld "Objekt einfügen" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Erstellt ein `COleInsertDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleInsertDialog::CreateItem](#createitem)|Erstellt im Dialogfeld ausgewählten Elements an.|  
|[COleInsertDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE Objekt einfügen.|  
|[COleInsertDialog::GetClassID](#getclassid)|Ruft die **CLSID** dem ausgewählten Element zugeordnet.|  
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Legt fest, ob zum Zeichnen des Elements als Symbol.|  
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle auf die Metadatei iconic Form dieses Elements zugeordnet.|  
|[COleInsertDialog::GetPathName](#getpathname)|Ruft den vollständigen Pfad zu den im Dialogfeld ausgewählte Datei ab.|  
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Ruft den Typ des ausgewählten Objekts ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleInsertDialog::m_io](#m_io)|Eine Struktur vom Typ **OLEUIINSERTOBJECT** , steuert das Verhalten des Dialogfelds.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleInsertDialog` Wenn Sie dieses Dialogfeld aufrufen möchten. Nach einer `COleInsertDialog` -Objekts, können Sie die [M_io](#m_io) Struktur, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_io` Struktur ist vom Typ **OLEUIINSERTOBJECT**. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Member-Funktion.  
  
> [!NOTE]
>  Diese Klasse wird von Anwendung Container vom Assistenten generierten Code verwendet.  
  
 Weitere Informationen finden Sie unter der [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="coleinsertdialog"></a>COleInsertDialog::COleInsertDialog  
 Diese Funktion erstellt nur eine `COleInsertDialog` Objekt.  
  
```  
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Erstellung-Flag, die eine beliebige Anzahl von mit dem bitweisen OR-Operator kombiniert werden die folgenden Werte enthält:  
  
- **IOF_SHOWHELP** gibt an, dass die Hilfeschaltfläche angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
- **IOF_SELECTCREATENEW** gibt an, dass das Optionsfeld neu erstellen zunächst ausgewählt ist, wenn das Dialogfeld aufgerufen wird. Dies ist die Standardeinstellung und kann nicht verwendet werden, mit **IOF_SELECTCREATEFROMFILE**.  
  
- **IOF_SELECTCREATEFROMFILE** gibt an, dass das Optionsfeld aus Datei erstellen zunächst ausgewählt ist, wenn das Dialogfeld aufgerufen wird. Kann nicht verwendet werden, mit **IOF_SELECTCREATENEW**.  
  
- **IOF_CHECKLINK** gibt an, dass das Kontrollkästchen Verknüpfung zunächst geprüft wird, wenn das Dialogfeld aufgerufen wird.  
  
- **IOF_DISABLELINK** gibt an, dass das Kontrollkästchen Verknüpfung deaktiviert wird, wenn das Dialogfeld aufgerufen wird.  
  
- **IOF_CHECKDISPLAYASICON** gibt, aktivieren Sie das Kontrollkästchen als Symbol wird zunächst überprüft, die das aktuelle Symbol angezeigt und die Schaltfläche "Symbol ändern" wird aktiviert, wenn das Dialogfeld aufgerufen wird.  
  
- **IOF_VERIFYSERVERSEXIST** gibt an, dass im Dialogfeld Klassen überprüft werden sollen, sicherzustellen, dass die in der Registrierungsdatenbank angegebenen Server vorhanden sein, bevor das Dialogfeld angezeigt wird, dem Listenfeld hinzugefügt. Dieses Flag kann die Leistung erheblich beeinträchtigen.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist dies **NULL**, das übergeordnete Fenster des Dialog-Objekts zum Hauptfenster der Anwendung festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen Sie die [DoModal](#domodal) Funktion.  
  
##  <a name="createitem"></a>COleInsertDialog::CreateItem  
 Rufen Sie diese Funktion zum Erstellen eines Objekts vom Typ [COleClientItem](../../mfc/reference/coleclientitem-class.md) nur, wenn [DoModal](#domodal) gibt **IDOK**.  
  
```  
BOOL CreateItem(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Verweist auf das Element erstellt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn er erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Belegen der `COleClientItem` -Objekt, bevor Sie diese Funktion aufrufen können.  
  
##  <a name="domodal"></a>COleInsertDialog::DoModal  
 Rufen Sie diese Funktion, um das Dialogfeld OLE Objekt einfügen anzuzeigen.  
  
```  
virtual INT_PTR   
    DoModal();

 
INT_PTR   
    DoModal(DWORD  dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Einer der folgenden Werte:  
  
 `COleInsertDialog::DocObjectsOnly`Fügt nur DocObjects.  
  
 `COleInsertDialog::ControlsOnly`Fügt nur ActiveX-Steuerelemente.  
  
 0 (null) Fügt DocObject weder ein ActiveX-Steuerelement. Dieser Wert führt dieselbe Implementierung als erste Prototyp oben aufgeführten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
-   IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
-   IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
-   IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) Memberfunktion, um weitere Informationen über die Art des Fehlers zu erhalten, die aufgetreten sind. Eine Liste möglicher Fehler, finden Sie unter der [OleUIInsertObject](http://msdn.microsoft.com/library/windows/desktop/ms694325) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeld-Steuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_io](#m_io) -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt IDOK, Sie können andere Memberfunktionen Aufrufen der Einstellungen oder der Eingabe von Informationen in das Dialogfeld vom Benutzer abgerufen.  
  
##  <a name="getclassid"></a>COleInsertDialog::GetClassID  
 Rufen Sie diese Funktion zum Abrufen der **CLSID** nur, wenn das ausgewählte Element zugeordneten [DoModal](#domodal) gibt **IDOK** und der Auswahltyp **COleInsertDialog::createNewItem**.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die **CLSID** mit dem ausgewählten Element verknüpft sind.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [CLSID-Schlüssel](http://msdn.microsoft.com/library/windows/desktop/ms691424) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdrawaspect"></a>COleInsertDialog::GetDrawAspect  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das ausgewählte Element als Symbol angezeigt hat.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Methode, die zum Rendern des Objekts erforderlich sind.  
  
- `DVASPECT_CONTENT`Zurückgegeben, wenn das Kontrollkästchen als Symbol nicht aktiviert wurde.  
  
- `DVASPECT_ICON`Zurückgegeben, wenn das Kontrollkästchen als Symbol aktiviert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion nur, wenn [DoModal](#domodal) gibt **IDOK**.  
  
 Weitere Informationen zum Zeichnen von Aspekt, finden Sie unter [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Datenstruktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="geticonicmetafile"></a>COleInsertDialog::GetIconicMetafile  
 Rufen Sie diese Funktion, um ein Handle für die Metadatei abzurufen, die den iconic Aspekt des ausgewählten Elements enthält.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei mit den iconic Aspekt des ausgewählten Elements, wenn das Kontrollkästchen als Symbol wurde aktiviert, wenn das Dialogfeld geschlossen wurde, indem Sie auswählen **OK**andernfalls **NULL**.  
  
##  <a name="getpathname"></a>COleInsertDialog::GetPathName  
 Mit dieser Funktion können Sie den vollständigen Pfad des ausgewählten Datei nur, wenn [DoModal](#domodal) gibt **IDOK** und den Typ der Auswahl ist nicht **COleInsertDialog::createNewItem**.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vollständige Pfad der Datei im Dialogfeld ausgewählt. Wenn der Auswahltyp ist `createNewItem`, diese Funktion gibt eine bedeutungslos `CString` im Releasemodus oder verursacht eine Assertion im Debugmodus.  
  
##  <a name="getselectiontype"></a>COleInsertDialog::GetSelectionType  
 Rufen Sie diese Funktion zum Abrufen des Auswahltyps ausgewählt wird, wenn das Dialogfeld "Objekt einfügen" wählen geschlossen wurde **OK**.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Typ der ausgewählten Optionen.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabetyp Werte werden angegeben, indem die **Auswahl** Enumerationstyp deklariert wird, der `COleInsertDialog` Klasse.  
  
```  
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };  
```  
  
 Führen Sie die kurze Beschreibungen der folgenden Werte:  
  
- **COleInsertDialog::createNewItem** der Create New Optionsfeld ausgewählt wurde.  
  
- **COleInsertDialog::insertFromFile** Optionsfeld das Erstellen von Datei ausgewählt wurde, und aktivieren Sie das Kontrollkästchen links nicht aktiviert wurde.  
  
- **COleInsertDialog::linkToFile** der aus Datei erstellen Optionsfeld ausgewählt wurde und das Kontrollkästchen Verknüpfung aktiviert wurde.  
  
##  <a name="m_io"></a>COleInsertDialog::m_io  
 Struktur des Typs **OLEUIINSERTOBJECT** zum Steuern des Verhaltens im Dialogfeld "Objekt einfügen" verwendet.  
  
```  
OLEUIINSERTOBJECT m_io;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können entweder direkt oder über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)

