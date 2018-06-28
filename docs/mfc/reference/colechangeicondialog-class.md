---
title: COleChangeIconDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
dev_langs:
- C++
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a67b1e405f1e3be472f9b9b3b5ebe00be3fb8a5d
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041044"
---
# <a name="colechangeicondialog-class"></a>COleChangeIconDialog-Klasse
Wird für das OLE-Dialogfeld "Symbol ändern" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Erstellt ein `COleChangeIconDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|Führt die Änderung, die Sie im Dialogfeld angegeben.|  
|[COleChangeIconDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE 2 "Symbol ändern".|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle für die Metadatei Elementsymbol Form dieses Elements zugeordnet.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleChangeIconDialog` Wenn Sie das Dialogfeld aufgerufen werden soll. Nach einem `COleChangeIconDialog` -Objekts können Sie mithilfe der [M_ci](#m_ci) Struktur initialisiert werden, die Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_ci` Struktur ist vom Typ **OLEUICHANGEICON**. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Memberfunktion.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Struktur im Windows SDK.  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="colechangeicondialog"></a>  COleChangeIconDialog::COleChangeIconDialog  
 Diese Funktion nur bildet eine `COleChangeIconDialog` Objekt.  
  
```  
explicit COleChangeIconDialog(
    COleClientItem* pItem,  
    DWORD dwFlags = CIF_SELECTCURRENT,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pItem*  
 Verweist auf das Element, das konvertiert werden.  
  
 *dwFlags*  
 Erstellung-Flag, das eine beliebige Anzahl von die folgenden Werte enthält kombiniert mit dem bitweisen- or -Operator:  
  
- **CIF_SELECTCURRENT** gibt an, dass das aktuelle Optionsfeld anfänglich ausgewählt wird, wenn das Dialogfeld aufgerufen wird. Dies ist die Standardeinstellung.  
  
- **CIF_SELECTDEFAULT** gibt an, dass das Standard-Optionsfeld anfänglich ausgewählt wird, wenn das Dialogfeld aufgerufen wird.  
  
- **CIF_SELECTFROMFILE** gibt an, dass das Optionsfeld aus Datei zunächst ausgewählt wird, wenn das Dialogfeld aufgerufen wird.  
  
- **CIF_SHOWHELP** gibt an, dass die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
- **CIF_USEICONEXE** gibt an, dass das Symbol aus der ausführbaren Datei im angegebenen extrahiert werden sollen die **SzIconExe** Feld [M_ci](#m_ci) anstelle von abgerufen, von dem Typ. Dies ist hilfreich beim Einbetten von und Verknüpfen von nicht-OLE-Dateien.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist er **NULL**, das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Struktur im Windows SDK.  
  
##  <a name="dochangeicon"></a>  COleChangeIconDialog::DoChangeIcon  
 Mit dieser Funktion können Sie das Symbol für das Element, nach dem im Dialogfeld ausgewählte ändern [DoModal](#domodal) gibt **IDOK**.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pItem*  
 Verweist auf das Element, dessen Symbol geändert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Änderung erfolgreich ist; andernfalls 0.  
  
##  <a name="domodal"></a>  COleChangeIconDialog::DoModal  
 Rufen Sie diese Funktion, um das Dialogfeld OLE "Symbol ändern" anzuzeigen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** wird das Dialogfeld erfolgreich angezeigt.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Auflistung möglicher Fehler finden Sie die [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307) Funktion im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_ci](#m_ci) -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder der Informationen, die in das Dialogfeld vom Benutzer eingegeben wurde.  
  
##  <a name="geticonicmetafile"></a>  COleChangeIconDialog::GetIconicMetafile  
 Mit dieser Funktion können Sie ein Handle für die Metadatei abzurufen, die das Elementsymbol Aspekt des ausgewählten Elements enthält.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei, enthält das Elementsymbol Aspekt, der das Symbol "Neu", wenn das Dialogfeld, durch Auswahl geschlossen wurde **OK**ist, andernfalls das Symbol ", wie sie war, bevor das Dialogfeld angezeigt wurde.  
  
##  <a name="m_ci"></a>  COleChangeIconDialog::m_ci  
 Struktur des Typs **OLEUICHANGEICON** zum Steuern des Verhaltens im Dialogfeld "Symbol ändern" verwendet.  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können weder direkt noch über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Struktur im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
