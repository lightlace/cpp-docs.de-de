---
title: COleChangeIconDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
ms.openlocfilehash: 4cbf1137a15a9f86a6377980526e6d188f4d0a69
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504783"
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
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|Führt die im Dialogfeld angegebene Änderung aus.|
|[COleChangeIconDialog::DoModal](#domodal)|Zeigt das Dialogfeld Symbol für OLE 2-Änderung an.|
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Ruft ein Handle für die Metadatei ab, die der ikonischen Form dieses Elements zugeordnet ist.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleChangeIconDialog::m_ci](#m_ci)|Eine-Struktur, die das Verhalten des Dialog Felds steuert.|

## <a name="remarks"></a>Hinweise

Erstellen Sie ein Objekt der `COleChangeIconDialog` -Klasse, wenn Sie dieses Dialogfeld aufzurufen. Nachdem ein `COleChangeIconDialog` -Objekt erstellt wurde, können Sie die [m_ci](#m_ci) -Struktur verwenden, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die `m_ci` Struktur ist vom Typ "oleuichangeicon". Weitere Informationen zum Verwenden dieser Dialogfeld Klasse finden Sie unter der [DoModal](#domodal) -Member-Funktion.

Weitere Informationen finden Sie in der [oleuichangeicon](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) -Struktur in der Windows SDK.

Weitere Informationen zu OLE-spezifischen Dialogfeldern finden Sie in den Artikel [Dialogfeldern in OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeIconDialog`

## <a name="requirements"></a>Anforderungen

**Header:** afxodlgs. h

##  <a name="colechangeicondialog"></a>COleChangeIconDialog:: COleChangeIconDialog

Diese Funktion erstellt nur ein `COleChangeIconDialog` -Objekt.

```
explicit COleChangeIconDialog(
    COleClientItem* pItem,
    DWORD dwFlags = CIF_SELECTCURRENT,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Verweist auf das Element, das konvertiert werden soll.

*dwFlags*<br/>
Erstellungs Kennzeichen, das eine beliebige Anzahl der folgenden Werte enthält, kombiniert mit dem bitweisen OR-Operator:

- CIF_SELECTCURRENT gibt an, dass das aktuelle Optionsfeld anfänglich ausgewählt wird, wenn das Dialogfeld aufgerufen wird. Dies ist die Standardeinstellung.

- CIF_SELECTDEFAULT gibt an, dass das Optionsfeld Standard zuerst ausgewählt wird, wenn das Dialogfeld aufgerufen wird.

- CIF_SELECTFROMFILE gibt an, dass das Optionsfeld aus Datei anfänglich ausgewählt wird, wenn das Dialogfeld aufgerufen wird.

- CIF_SHOWHELP gibt an, dass die Schaltfläche Hilfe angezeigt wird, wenn das Dialogfeld aufgerufen wird.

- CIF_USEICONEXE gibt an, dass das Symbol aus der ausführbaren Datei extrahiert werden `szIconExe` soll, die im Feld von [m_ci](#m_ci) angegeben ist, anstatt aus dem Typ abgerufen zu werden. Dies ist hilfreich beim Einbetten oder Verknüpfen mit nicht-OLE-Dateien.

*pParentWnd*<br/>
Zeigt auf das übergeordnete oder Besitzer Fenster Objekt (vom `CWnd`Typ), zu dem das Dialog Objekt gehört. Wenn er NULL ist, wird das übergeordnete Fenster des Dialog Felds auf das Hauptanwendungsfenster festgelegt.

### <a name="remarks"></a>Hinweise

Um das Dialogfeld anzuzeigen, müssen Sie die Funktion [DoModal](#domodal) aufrufen.

Weitere Informationen finden Sie in der [oleuichangeicon](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) -Struktur in der Windows SDK.

##  <a name="dochangeicon"></a>COleChangeIconDialog::D ochangeicon

Mit dieser Funktion können Sie das Symbol, das das Element darstellt, in das Symbol ändern, das im Dialogfeld ausgewählt ist, nachdem die [Domäne](#domodal) IDOK zurückgegeben hat.

```
BOOL DoChangeIcon(COleClientItem* pItem);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Verweist auf das Element, dessen Symbol geändert wird.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Änderung erfolgreich ist. andernfalls 0.

##  <a name="domodal"></a>COleChangeIconDialog::D omodal

Mit dieser Funktion wird das OLE-Dialogfeld "Symbol ändern" angezeigt.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Rückgabewert

Abschluss Status für das Dialogfeld. Einer der folgenden Werte:

- IDOK, wenn das Dialogfeld erfolgreich angezeigt wurde.

- IDCANCEL, wenn der Benutzer das Dialogfeld abgebrochen hat.

- Idabort, wenn ein Fehler aufgetreten ist. Wenn idabort zurückgegeben wird, können `COleDialog::GetLastError` Sie die Member-Funktion abrufen, um weitere Informationen zum aufgetretenen Fehlertyp abzurufen. Eine Auflistung möglicher Fehler finden Sie unter der [oleuichangeicon](/windows/win32/api/oledlg/nf-oledlg-oleuichangeiconw) -Funktion in der Windows SDK.

### <a name="remarks"></a>Hinweise

Wenn Sie die verschiedenen Dialogfeld-Steuerelemente durch Festlegen der Member der [m_ci](#m_ci) -Struktur initialisieren möchten, sollten Sie dies vor `DoModal`dem Aufrufen von tun, nachdem das Dialogfeld Objekt erstellt wurde.

Wenn `DoModal` IDOK zurückgibt, können Sie andere Element Funktionen aufrufen, um die Einstellungen oder Informationen abzurufen, die vom Benutzer in das Dialogfeld eingegeben wurden.

##  <a name="geticonicmetafile"></a>COleChangeIconDialog:: getikonicmetafile

Mit dieser Funktion können Sie ein Handle für die Metadatei abrufen, die den ikonischen Aspekt des ausgewählten Elements enthält.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Rückgabewert

Das Handle für die Metadatei, das den ikonischen Aspekt des neuen Symbols enthält, wenn das Dialogfeld durch Auswählen von " **OK**" verworfen wurde. andernfalls das Symbol, wie es vor dem Anzeigen des Dialog Felds war.

##  <a name="m_ci"></a>COleChangeIconDialog:: m_ci

Struktur vom Typ "oleuichangeicon", die zum Steuern des Verhaltens des Dialog Felds "Symbol ändern" verwendet wird.

```
OLEUICHANGEICON m_ci;
```

### <a name="remarks"></a>Hinweise

Member dieser Struktur können entweder direkt oder über Element Funktionen geändert werden.

Weitere Informationen finden Sie in der [oleuichangeicon](/windows/win32/api/oledlg/ns-oledlg-oleuichangeiconw) -Struktur in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleDialog-Klasse](../../mfc/reference/coledialog-class.md)
