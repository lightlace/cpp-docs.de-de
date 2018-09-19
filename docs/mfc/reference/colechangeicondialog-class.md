---
title: COleChangeIconDialog-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 089fe435c86b524acc41ba528452d93032d1b1a4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214492"
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
|[COleChangeIconDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE 2 Symbol ändern.|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle der Metadatei zugeordnete Symbol Form dieses Elements ab.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleChangeIconDialog` Wenn das Dialogfeld aufgerufen werden soll. Nach einer `COleChangeIconDialog` -Objekts wird, können Sie mit der [M_ci](#m_ci) Struktur zum Initialisieren der Werte oder Zustände von Steuerelementen im Dialogfeld. Die `m_ci` Struktur des Typs OLEUICHANGEICON ist. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter den [DoModal](#domodal) Member-Funktion.  
  
 Weitere Informationen finden Sie unter den [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) Struktur im Windows SDK.  
  
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
 Diese Funktion erstellt nur eine `COleChangeIconDialog` Objekt.  
  
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
 Flag der Erstellung, die eine beliebige Anzahl von die folgenden Werte enthält, kombiniert mit dem bitweisen- or -Operator:  
  
- CIF_SELECTCURRENT gibt an, die das aktuelle Optionsfeld ausgewählt anfänglich Wenn das Dialogfeld aufgerufen wird. Dies ist die Standardeinstellung.  
  
- CIF_SELECTDEFAULT gibt an, die die Standardschaltfläche für das Optionsfeld ausgewählt anfänglich Wenn das Dialogfeld aufgerufen wird.  
  
- CIF_SELECTFROMFILE angibt, das Optionsfeld aus der Datei ist ausgewählt, anfänglich Wenn das Dialogfeld aufgerufen wird.  
  
- CIF_SHOWHELP gibt an, dass die Schaltfläche "Hilfe" angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
- CIF_USEICONEXE gibt an, dass das Symbol aus der ausführbaren Datei im angegebenen extrahiert werden sollen die `szIconExe` Feld [M_ci](#m_ci) nicht abgerufen werden soll, aus dem Typ. Dies ist nützlich zum Einbetten oder Verknüpfen von nicht-OLE-Dateien.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs `CWnd`) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das übergeordnete Fenster des Dialogfelds auf das Hauptanwendungsfenster festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter den [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) Struktur im Windows SDK.  
  
##  <a name="dochangeicon"></a>  COleChangeIconDialog::DoChangeIcon  
 Mit dieser Funktion können Sie das Symbol für das Element, nachdem Sie im Dialogfeld ausgewählte ändern [DoModal](#domodal) IDOK zurückgibt.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pItem*  
 Verweist auf das Element, dessen Symbol geändert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn die Änderung erfolgreich ist; andernfalls 0.  
  
##  <a name="domodal"></a>  COleChangeIconDialog::DoModal  
 Rufen Sie diese Funktion, um das Dialogfeld "Symbol für das OLE-ändern" anzuzeigen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.  
  
- IDABORT, wenn ein Fehler aufgetreten. Wenn IDABORT zurückgegeben wird, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen zu den Typ des Fehlers zu erhalten, die aufgetreten sind. Eine Liste der möglichen Fehler, finden Sie unter den [OleUIChangeIcon](/windows/desktop/api/oledlg/nf-oledlg-oleuichangeicona) -Funktion in das Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeldsteuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_ci](#m_ci) Struktur, sollten Sie dies tun, vor dem Aufruf `DoModal`, allerdings nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt IDOK, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder die Informationen, die in das Dialogfeld vom Benutzer eingegeben wurde.  
  
##  <a name="geticonicmetafile"></a>  COleChangeIconDialog::GetIconicMetafile  
 Rufen Sie diese Funktion, um ein Handle der Metadatei zu erhalten, den Symbol Aspekt des ausgewählten Elements enthält.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei, die den iconic Aspekt, der das Symbol "Neu" enthält, wenn das Dialogfeld, dazu geschlossen wurde **OK**ist, andernfalls das Symbol an, wie sie war, bevor das Dialogfeld angezeigt wurde.  
  
##  <a name="m_ci"></a>  COleChangeIconDialog::m_ci  
 Struktur des Typs OLEUICHANGEICON verwendet zur Steuerung des Verhaltens im Dialogfeld "Symbol ändern".  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können entweder direkt oder über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter den [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) Struktur im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
