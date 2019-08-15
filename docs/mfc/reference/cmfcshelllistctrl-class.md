---
title: Cmfcshelllistctrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayParentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::EnableShellContextMenu
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolderName
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentItemIdList
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentShellFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemPath
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemTypes
- AFXSHELLLISTCTRL/CMFCShellListCtrl::IsDesktop
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnCompareItems
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileDate
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileSize
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemIcon
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemText
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnSetColumns
- AFXSHELLLISTCTRL/CMFCShellListCtrl::Refresh
- AFXSHELLLISTCTRL/CMFCShellListCtrl::SetItemTypes
helpviewer_keywords:
- CMFCShellListCtrl [MFC], DisplayFolder
- CMFCShellListCtrl [MFC], DisplayParentFolder
- CMFCShellListCtrl [MFC], EnableShellContextMenu
- CMFCShellListCtrl [MFC], GetCurrentFolder
- CMFCShellListCtrl [MFC], GetCurrentFolderName
- CMFCShellListCtrl [MFC], GetCurrentItemIdList
- CMFCShellListCtrl [MFC], GetCurrentShellFolder
- CMFCShellListCtrl [MFC], GetItemPath
- CMFCShellListCtrl [MFC], GetItemTypes
- CMFCShellListCtrl [MFC], IsDesktop
- CMFCShellListCtrl [MFC], OnCompareItems
- CMFCShellListCtrl [MFC], OnFormatFileDate
- CMFCShellListCtrl [MFC], OnFormatFileSize
- CMFCShellListCtrl [MFC], OnGetItemIcon
- CMFCShellListCtrl [MFC], OnGetItemText
- CMFCShellListCtrl [MFC], OnSetColumns
- CMFCShellListCtrl [MFC], Refresh
- CMFCShellListCtrl [MFC], SetItemTypes
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
ms.openlocfilehash: 02d4883c6b5445515d891c5e76ccf10b6bb35bba
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504923"
---
# <a name="cmfcshelllistctrl-class"></a>Cmfcshelllistctrl-Klasse

Die `CMFCShellListCtrl` -Klasse stellt die Funktionalität des Windows-Listen Steuer Elements bereit und erweitert Sie durch Einbeziehen der Möglichkeit, eine Liste von shellelementen anzuzeigen.

## <a name="syntax"></a>Syntax

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Zeigt eine Liste von Elementen an, die in einem bereitgestellten Ordner enthalten sind.|
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Zeigt eine Liste von Elementen an, die im Ordner enthalten sind, der das übergeordnete Element des aktuell angezeigten Ordners ist.|
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Aktiviert oder deaktiviert das Kontextmenü.|
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Ruft den Pfad des aktuellen Ordners ab.|
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Ruft den Namen des aktuellen Ordners ab.|
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Gibt die PIDL des aktuellen Listen Steuerelement Elements zurück.|
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Gibt einen Zeiger auf den aktuellen Shellordner zurück.|
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Gibt den Textpfad eines Elements zurück.|
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Gibt shellelementtypen zurück, die vom Listen Steuerelement angezeigt werden.|
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Überprüft, ob der aktuell ausgewählte Ordner der Desktop Ordner ist.|
|[Cmfcshelllistctrl:: oncompareitems](#oncompareitems)|Das Framework ruft diese Methode auf, wenn zwei Elemente verglichen werden. (Überschreibt [CMF CListCtrl:: oncompareitems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Wird aufgerufen, wenn das Framework das vom Listen Steuerelement angezeigte Datei Datum abruft.|
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Wird aufgerufen, wenn das Framework die Dateigröße eines Listen Steuer Elements konvertiert.|
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Wird aufgerufen, wenn das Framework das Symbol eines Listen Steuerelement-Elements abruft.|
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Wird aufgerufen, wenn das Framework den Text eines Listen Steuerelement Elements konvertiert.|
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Wird vom Framework aufgerufen, wenn die Namen der Spalten festgelegt werden.|
|[CMFCShellListCtrl::Refresh](#refresh)|Aktualisiert das Listen Steuerelement und zeichnet es neu.|
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Legt den Typ der Elemente fest, die vom Listen Steuerelement angezeigt werden.|

## <a name="remarks"></a>Hinweise

Die `CMFCShellListCtrl` -Klasse erweitert die Funktionalität der [cmfclistctrl-Klasse](../../mfc/reference/cmfclistctrl-class.md) , indem das Programm das Auflisten von Windows-shellelementen ermöglicht. Das Anzeige Format, das verwendet wird, ähnelt dem einer Listenansicht für ein Explorer-Fenster.

Ein [cmfcshelltreectrl](../../mfc/reference/cmfcshelltreectrl-class.md) -Objekt kann einem `CMFCShellListCtrl` -Objekt zugeordnet werden, um ein umfassendes Explorer-Fenster zu erstellen. Wenn Sie ein Element in der `CMFCShellTreeCtrl` auswählen, wird der Inhalt des ausgewählten Elements durch das `CMFCShellListCtrl` -Objekt aufgelistet.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Objekt der `CMFCShellListCtrl` -Klasse erstellt wird und wie der übergeordnete Ordner des aktuell angezeigten Ordners angezeigt wird. Dieser Code Ausschnitt ist Teil des [Explorer](../../overview/visual-cpp-samples.md)-Beispiels.

[!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

`CMFCShellListCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxshelllistctrl. h

##  <a name="displayfolder"></a>Cmfcshelllistctrl::D isplayfolder

Zeigt eine Liste von Elementen an, die im angegebenen Ordner enthalten sind.

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>Parameter

*lpszPath*<br/>
in Eine Zeichenfolge, die den Pfad eines Ordners enthält.

*lpItemInfo*<br/>
in Ein Zeiger auf eine `LPAFX_SHELLITEMINFO` -Struktur, die einen Ordner beschreibt, der angezeigt werden soll.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; E_FAIL andernfalls.

##  <a name="displayparentfolder"></a>Cmfcshelllistctrl::D isplaypartfolder

Aktualisiert das [cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt, um den übergeordneten Ordner des aktuell angezeigten Ordners anzuzeigen.

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; E_FAIL andernfalls.

##  <a name="enableshellcontextmenu"></a>Cmfcshelllistctrl:: enableshellcontextmenu

Aktiviert das Kontextmenü.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
in Ein boolescher Wert, der angibt, ob das Framework das Kontextmenü aktiviert.

##  <a name="getcurrentfolder"></a>Cmfcshelllistctrl:: getcurrentfolder

Ruft den Pfad des aktuell ausgewählten Ordners im [cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt ab.

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>Parameter

*strPath*<br/>
vorgenommen Ein Verweis auf einen Zeichen folgen Parameter, bei dem die Methode den Pfad schreibt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn kein Ordner in der `CMFCShellListCtrl`ausgewählt ist.

##  <a name="getcurrentfoldername"></a>Cmfcshelllistctrl:: getcurrentfoldername

Ruft den Namen des aktuell ausgewählten Ordners im [cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt ab.

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>Parameter

*strName*<br/>
vorgenommen Ein Verweis auf einen Zeichen folgen Parameter, bei dem die-Methode den Namen schreibt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn kein Ordner in der `CMFCShellListCtrl`ausgewählt ist.

##  <a name="getcurrentitemidlist"></a>Cmfcshelllistctrl:: GetEvents Items

Gibt die PIDL des aktuell ausgewählten Elements zurück.

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>Rückgabewert

Die PIDL des aktuellen Elements.

##  <a name="getcurrentshellfolder"></a>Cmfcshelllistctrl:: getcurrentshellfolder

Ruft einen Zeiger auf das aktuell ausgewählte Element im [cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt ab.

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [IShellFolder-Schnittstelle](/windows/win32/api/shobjidl_core/nn-shobjidl_core-ishellfolder) für das ausgewählte Objekt.

### <a name="remarks"></a>Hinweise

Diese Methode gibt NULL zurück, wenn derzeit kein Objekt ausgewählt ist.

##  <a name="getitempath"></a>Cmfcshelllistctrl:: getitempath

Ruft den Pfad für ein Element ab.

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>Parameter

*strPath*<br/>
vorgenommen Ein Verweis auf eine Zeichenfolge, die den Pfad empfängt.

*iItem*<br/>
in Der Index des Listen Elements.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich; Andernfalls false.

### <a name="remarks"></a>Hinweise

Der von *iItem* angegebene Index basiert auf den Elementen, die zurzeit vom [cmfcshelllistctrl-Klassen](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt angezeigt werden.

##  <a name="getitemtypes"></a>Cmfcshelllistctrl:: getitemtypes

Gibt den Typ der Elemente zurück, die vom [cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt angezeigt werden.

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [shcontf](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf) -Wert, der den Typ der Elemente enthält, `CMFCShellListCtrl`die in der aufgeführt sind.

### <a name="remarks"></a>Hinweise

Um den Typ der in einer `CMFCShellListCtrl`aufgelisteten Elemente festzulegen, müssen Sie [cmfcshelllistctrl:: setitemtypes](#setitemtypes)aufrufen.

##  <a name="isdesktop"></a>Cmfcshelllistctrl:: isdesktop

Bestimmt, ob der Ordner, der im [cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt angezeigt wird, der Desktop Ordner ist.

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der angezeigte Ordner der Desktop Ordner ist. Andernfalls false.

##  <a name="oncompareitems"></a>Cmfcshelllistctrl:: oncompareitems

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Parameter

[in] *lParam1*<br/>
[in] *lParam2*<br/>
in *icolumn*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onformatfiledate"></a>Cmfcshelllistctrl:: onformatfiledate

Das Framework ruft diese Methode auf, wenn das mit einem Objekt verknüpfte Datum in eine Zeichenfolge konvertiert werden muss.

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>Parameter

*tmFile*<br/>
in Das Datum, das einer Datei zugeordnet ist.

*str*<br/>
vorgenommen Eine Zeichenfolge, die das formatierte Dateidatum enthält.

### <a name="remarks"></a>Hinweise

Wenn ein [cmfcshelllistctrl-Klassen](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt das Datum anzeigt, das einer Datei zugeordnet ist, muss dieses Datum in ein Zeichen folgen Format konvertiert werden. `CMFCShellListCtrl` Verwendet diese Methode, um diese Konvertierung durchführen. Standardmäßig verwendet diese Methode das aktuelle Gebiets Schema, um das Datum in eine Zeichenfolge zu formatieren.

##  <a name="onformatfilesize"></a>Cmfcshelllistctrl:: onformatfilesize

Das Framework ruft diese Methode auf, wenn die Größe eines Objekts in eine Zeichenfolge konvertiert wird.

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>Parameter

*lFileSize*<br/>
in Die Größe der Datei, die vom Framework angezeigt wird.

*str*<br/>
vorgenommen Eine Zeichenfolge, die die formatierte Dateigröße enthält.

### <a name="remarks"></a>Hinweise

Wenn ein [cmfcshelllistctrl-Klassen](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt die Größe einer Datei anzeigen muss, muss die Dateigröße in ein Zeichen folgen Format konvertiert werden. `CMFCShellListCtrl` Verwendet diese Methode, um diese Konvertierung durchführen. Standardmäßig konvertiert diese Methode die Dateigröße von Bytes in Kilobyte und verwendet dann das aktuelle Gebiets Schema, um die Größe in eine Zeichenfolge zu formatieren.

##  <a name="ongetitemicon"></a>Cmfcshelllistctrl:: ongetitemicon

Das Framework ruft diese Methode auf, um das Symbol abzurufen, das einem shelllistenelement zugeordnet ist.

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parameter

*iItem*<br/>
in Der Element Index.

*pItem*<br/>
in Ein LPAFX_SHELLITEMINFO-Parameter, der das Element beschreibt.

### <a name="return-value"></a>Rückgabewert

Der Index des Symbol Bilds, wenn der Vorgang erfolgreich war. -1, wenn die Funktion fehlschlägt.

### <a name="remarks"></a>Hinweise

Der Symbolbild Index basiert auf der Liste System Abbild.

Diese Methode basiert standardmäßig auf dem *pitem* -Parameter. Der Wert von *iItem* wird in der Standard Implementierung nicht verwendet. Sie können *iItem* verwenden, um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="ongetitemtext"></a>Cmfcshelllistctrl:: ongetitemtext

Das Framework ruft diese Methode auf, wenn der Text eines shellelements abgerufen werden muss.

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parameter

*iItem*<br/>
in Der Element Index.

*icolumn*<br/>
in Die betreffende Spalte.

*pItem*<br/>
in Ein LPAFX_SHELLITEMINFO-Parameter, der das Element beschreibt.

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Wert, der den dem Element zugeordneten Text enthält.

### <a name="remarks"></a>Hinweise

Jedes Element im `CMFCShellListCtrl` -Objekt kann Text in einer oder mehreren Spalten enthalten. Wenn das Framework diese Methode aufruft, gibt es die Spalte an, an der es interessiert ist. Wenn Sie diese Funktion manuell aufzurufen, müssen Sie auch die Spalte angeben, an der Sie interessiert sind.

Standardmäßig hängt diese Methode vom *pitem* -Parameter ab, um zu bestimmen, welches Element verarbeitet werden soll. Der Wert von *iItem* wird in der Standard Implementierung nicht verwendet.

##  <a name="onsetcolumns"></a>Cmfcshelllistctrl:: onsetcolumns

Das Framework ruft diese Methode auf, wenn die Namen der Spalten festgelegt werden.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Hinweise

Standardmäßig erstellt das Framework vier Spalten in einem `CMFCShellListCtrl` -Objekt. Die Namen dieser Spalten lauten **Name**, **Größe**, **Typ**und **geändert**. Sie können diese Methode außer Kraft setzen, um die Anzahl von Spalten und deren Namen anzupassen.

##  <a name="refresh"></a>Cmfcshelllistctrl:: Refresh

Aktualisiert das [cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt und zeichnet es neu.

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>Rückgabewert

`S_OK`, wenn erfolgreich; andernfalls ein Fehlerwert.

### <a name="remarks"></a>Hinweise

Ruft diese Methode auf, um die Liste der Elemente zu aktualisieren `CMFCShellListCtrl` , die vom-Objekt angezeigt werden.

##  <a name="setitemtypes"></a>Cmfcshelllistctrl::-Enumerationstypen

Legt den Typ der Elemente fest, die im [cmfcshelllistctrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt aufgelistet sind.

```
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>Parameter

*nTypes*<br/>
in Eine Liste von Elementtypen, die `CMFCShellListCtrl` vom-Objekt unterstützt werden.

### <a name="remarks"></a>Hinweise

Weitere Informationen zur Liste der Elementtypen finden Sie unter [shcontf](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md)<br/>
[CMFCShellTreeCtrl-Klasse](../../mfc/reference/cmfcshelltreectrl-class.md)
