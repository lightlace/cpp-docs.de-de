---
title: Klasse COleChangeIconDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeIconDialog
dev_langs:
- C++
helpviewer_keywords:
- OLE dialog boxes, Change Icon
- OLE Change Icon dialog box
- dialog boxes, OLE
- COleChangeIconDialog class
- Change Icon dialog box
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 07dfd7995bbbdb0f52f55dceedc318d8d702111b
ms.lasthandoff: 02/24/2017

---
# <a name="colechangeicondialog-class"></a>COleChangeIconDialog-Klasse
Wird für das OLE-Dialogfeld "Symbol ändern" verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Erstellt ein `COleChangeIconDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|Führt die Änderung im Dialogfeld angegeben.|  
|[COleChangeIconDialog::DoModal](#domodal)|Zeigt das Dialogfeld OLE 2 "Symbol ändern".|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle auf die Metadatei iconic Form dieses Elements zugeordnet.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|Eine Struktur, die das Verhalten des Dialogfelds steuert.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen Sie ein Objekt der Klasse `COleChangeIconDialog` Wenn Sie dieses Dialogfeld aufrufen möchten. Nach einer `COleChangeIconDialog` -Objekts, können Sie die [M_ci](#m_ci) Struktur, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_ci` Struktur ist vom Typ **OLEUICHANGEICON**. Weitere Informationen zur Verwendung dieser Dialogfeldklasse finden Sie unter der [DoModal](#domodal) Member-Funktion.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu OLE-spezifische Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="a-namecolechangeicondialoga--colechangeicondialogcolechangeicondialog"></a><a name="colechangeicondialog"></a>COleChangeIconDialog::COleChangeIconDialog  
 Diese Funktion erstellt nur eine `COleChangeIconDialog` Objekt.  
  
```  
explicit COleChangeIconDialog(
    COleClientItem* pItem,  
    DWORD dwFlags = CIF_SELECTCURRENT,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Verweist auf das Element, das konvertiert werden.  
  
 `dwFlags`  
 Erstellung-Flag, das eine beliebige Anzahl von die folgenden Werte enthält kombiniert mit dem bitweisen- or -Operator:  
  
- **CIF_SELECTCURRENT** gibt an, dass das aktuelle Optionsfeld anfänglich ausgewählt wird, wenn das Dialogfeld aufgerufen wird. Dies ist die Standardeinstellung.  
  
- **CIF_SELECTDEFAULT** gibt an, dass das Optionsfeld standardmäßig zunächst ausgewählt ist, wenn das Dialogfeld aufgerufen wird.  
  
- **CIF_SELECTFROMFILE** gibt an, dass das Optionsfeld aus Datei zunächst ausgewählt ist, wenn das Dialogfeld aufgerufen wird.  
  
- **CIF_SHOWHELP** gibt an, dass die Hilfeschaltfläche angezeigt wird, wenn das Dialogfeld aufgerufen wird.  
  
- **CIF_USEICONEXE** gibt an, dass das Symbol aus der ausführbaren Datei im angegebenen extrahiert werden sollen die **SzIconExe** Feld [M_ci](#m_ci) nicht abgerufen werden, vom Typ. Dies ist nützlich zum Einbetten oder Verknüpfen von nicht-OLE-Dateien.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs `CWnd`), der das Dialogfeldobjekt angehört. Ist dies **NULL**, wird das übergeordnete Fenster des Dialogfelds zum Hauptfenster der Anwendung festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Um das Dialogfeld anzuzeigen, rufen Sie die [DoModal](#domodal) Funktion.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedochangeicona--colechangeicondialogdochangeicon"></a><a name="dochangeicon"></a>COleChangeIconDialog::DoChangeIcon  
 Mit dieser Funktion können Sie das Symbol für das Element, nach dem im Dialogfeld ausgewählten ändern [DoModal](#domodal) gibt **IDOK**.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Verweist auf das Element, dessen Symbol geändert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Änderung erfolgreich ist; andernfalls 0.  
  
##  <a name="a-namedomodala--colechangeicondialogdomodal"></a><a name="domodal"></a>COleChangeIconDialog::DoModal  
 Rufen Sie diese Funktion, um das Dialogfeld OLE "Symbol ändern" anzuzeigen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Abschlussstatus für das Dialogfeld. Einer der folgenden Werte:  
  
- **IDOK** , wenn das Dialogfeld erfolgreich angezeigt wurde.  
  
- **IDCANCEL** , wenn der Benutzer das Dialogfeld abgebrochen.  
  
- **IDABORT** Wenn ein Fehler aufgetreten. Wenn **IDABORT** wird zurückgegeben, rufen Sie die `COleDialog::GetLastError` Memberfunktion, um weitere Informationen über die Art des Fehlers zu erhalten, die aufgetreten sind. Eine Liste möglicher Fehler, finden Sie unter der [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Dialogfeld-Steuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_ci](#m_ci) -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen der Einstellungen oder Informationen, die in das Dialogfeld vom Benutzer eingegeben wurde.  
  
##  <a name="a-namegeticonicmetafilea--colechangeicondialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COleChangeIconDialog::GetIconicMetafile  
 Rufen Sie diese Funktion, um ein Handle für die Metadatei abzurufen, die den iconic Aspekt des ausgewählten Elements enthält.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle der Metadatei mit den iconic Aspekt des neuen Symbols, wird das Dialogfeld, durch Auswahl geschlossen wurde **OK**ist, andernfalls das Symbol an, wie sie war, bevor das Dialogfeld angezeigt wurde.  
  
##  <a name="a-namemcia--colechangeicondialogmci"></a><a name="m_ci"></a>COleChangeIconDialog::m_ci  
 Struktur des Typs **OLEUICHANGEICON** zum Steuern des Verhaltens des Dialogfelds "Symbol ändern" verwendet.  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mitglieder dieser Struktur können entweder direkt oder über Memberfunktionen geändert werden.  
  
 Weitere Informationen finden Sie unter der [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)

