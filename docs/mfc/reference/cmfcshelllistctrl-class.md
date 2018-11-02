---
title: CMFCShellListCtrl-Klasse
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
ms.openlocfilehash: bd978bfa65cc003bcb69a309b44254a6d36a2ebd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588630"
---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl-Klasse

Die `CMFCShellListCtrl` -Klasse bietet Windows eine Liste und erweitert diese durch die Möglichkeit, eine Liste von shellelementen anzuzeigen.

## <a name="syntax"></a>Syntax

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Zeigt eine Liste von Elementen, die in einem angegebenen Ordner enthalten sind.|
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Zeigt eine Liste von Elementen, die im Ordner enthalten sind, die das übergeordnete Element des aktuell angezeigten Ordners ist.|
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Aktiviert oder deaktiviert das Kontextmenü.|
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Ruft den Pfad des aktuellen Ordners.|
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Ruft den Namen des aktuellen Ordners.|
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Gibt die PIDL, der dem aktuellen Listenelement-Steuerelement zurück.|
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Gibt einen Zeiger auf den aktuellen Shell-Ordner zurück.|
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Gibt den Text Pfad eines Elements.|
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Gibt zurück, Shell-Elementtypen, die durch das Strukturelement-Steuerelement angezeigt werden.|
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Überprüft, ob die aktuell ausgewählte Ordner den Ordner "desktop" ist.|
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|Das Framework ruft diese Methode auf, wenn es sich um zwei Elemente vergleicht. (Überschreibt [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Aufgerufen, wenn das Framework Ruft ab, das Datum der Datei durch das Listensteuerelement angezeigt.|
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Wird aufgerufen, wenn das Framework die Dateigröße eines Listensteuerelements konvertiert.|
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Wird aufgerufen, wenn das Framework das Symbol von einem Steuerelement ein Element abruft.|
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Wird aufgerufen, wenn das Framework den Text von einem Steuerelement ein Element konvertiert.|
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Vom Framework aufgerufen, wenn sie den Namen der Spalten festlegt.|
|[CMFCShellListCtrl::Refresh](#refresh)|Wird aktualisiert und neu aufgebaut, das Strukturelement-Steuerelement.|
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Legt fest, den Typ der Elemente, die das Strukturelement-Steuerelement angezeigt.|

## <a name="remarks"></a>Hinweise

Die `CMFCShellListCtrl` -Klasse erweitert die Funktionalität der [CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md) aktivieren Sie das Programm Windows-Shell-Elemente auflisten. Das Anzeigeformat, das verwendet wird, ist wie eine Ansicht für ein Explorer-Fenster.

Ein [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt zugeordnet sein kann eine `CMFCShellListCtrl` Objekt, das eine vollständige Explorerfenster zu erstellen. Klicken Sie dann, Auswählen eines Elements in der `CMFCShellTreeCtrl` führt dazu, dass die `CMFCShellListCtrl` Objekt zum Auflisten des Inhalts des ausgewählten Elements.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCShellListCtrl` -Klasse und wie den übergeordnete Ordner des derzeit angezeigten Ordners angezeigt. Dieser Codeausschnitt ist Teil der [Explorer-Beispiel](../../visual-cpp-samples.md).

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

**Header:** afxshelllistCtrl.h

##  <a name="displayfolder"></a>  CMFCShellListCtrl::DisplayFolder

Zeigt eine Liste von Elementen, die im angegebenen Ordner enthalten sind.

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>Parameter

*lpszPath*<br/>
[in] Eine Zeichenfolge, die den Pfad eines Ordners enthält.

*lpItemInfo*<br/>
[in] Ein Zeiger auf eine `LPAFX_SHELLITEMINFO` -Struktur, die beschreibt, einen Ordner angezeigt.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; E_FAIL andernfalls.

##  <a name="displayparentfolder"></a>  CMFCShellListCtrl::DisplayParentFolder

Updates der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt, um den übergeordneten Ordner des derzeit angezeigten Ordners anzuzeigen.

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; E_FAIL andernfalls.

##  <a name="enableshellcontextmenu"></a>  CMFCShellListCtrl::EnableShellContextMenu

Können das Kontextmenü an.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
[in] Ein boolescher Wert, der angibt, ob das Framework das Kontextmenü ermöglicht.

##  <a name="getcurrentfolder"></a>  CMFCShellListCtrl::GetCurrentFolder

Ruft den Pfad des ausgewählten Ordners, in der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>Parameter

*strPath*<br/>
[out] Ein Verweis auf einen Zeichenfolgenparameter, an die Methode für den Pfad schreibt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn es keine Ordner im ausgewählten der `CMFCShellListCtrl`.

##  <a name="getcurrentfoldername"></a>  CMFCShellListCtrl::GetCurrentFolderName

Ruft den Namen des aktuell ausgewählten Ordners, in der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>Parameter

*strName*<br/>
[out] Ein Verweis auf einen Zeichenfolgenparameter, der die Methode den Namen schreibt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn es keine Ordner im ausgewählten der `CMFCShellListCtrl`.

##  <a name="getcurrentitemidlist"></a>  CMFCShellListCtrl::GetCurrentItemIdList

Gibt die PIDL des derzeit ausgewählten Elements zurück.

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>Rückgabewert

Die PIDL des aktuellen Elements.

##  <a name="getcurrentshellfolder"></a>  CMFCShellListCtrl::GetCurrentShellFolder

Ruft einen Zeiger auf das aktuell ausgewählte Element in der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [IShellFolder Schnittstelle](https://msdn.microsoft.com/library/windows/desktop/bb775075) für das ausgewählte Objekt.

### <a name="remarks"></a>Hinweise

Diese Methode gibt NULL zurück, wenn derzeit kein Objekt ausgewählt ist.

##  <a name="getitempath"></a>  CMFCShellListCtrl::GetItemPath

Ruft den Pfad für ein Element.

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>Parameter

*strPath*<br/>
[out] Ein Verweis auf eine Zeichenfolge, die den Pfad zu empfangen.

*iItem*<br/>
[in] Der Index des Listenelements.

### <a name="return-value"></a>Rückgabewert

True, wenn erfolgreich; "False" andernfalls.

### <a name="remarks"></a>Hinweise

Der Index, der vom *iItem* basiert auf die vom aktuell angezeigten Elemente der [CMFCShellListCtrl-Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.

##  <a name="getitemtypes"></a>  CMFCShellListCtrl::GetItemTypes

Gibt den Typ der Elemente, die angezeigt werden, indem die [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf) -Wert, den Typ der Elemente in aufgeführten enthält, die `CMFCShellListCtrl`.

### <a name="remarks"></a>Hinweise

Beim Festlegen des Typs der Elemente aufgeführt, die einem `CMFCShellListCtrl`, rufen Sie [CMFCShellListCtrl::SetItemTypes](#setitemtypes).

##  <a name="isdesktop"></a>  CMFCShellListCtrl::IsDesktop

Bestimmt, ob der Ordner, der angezeigt wird, der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt ist der desktop-Ordner.

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn es sich bei der angezeigte Ordner den Ordner "desktop" ist. "False" andernfalls.

##  <a name="oncompareitems"></a>  CMFCShellListCtrl::OnCompareItems

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Parameter

[in] *lParam1*<br/>
[in] *lParam2*<br/>
[in] *der iColumn*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onformatfiledate"></a>  CMFCShellListCtrl::OnFormatFileDate

Das Framework ruft diese Methode auf, wenn sie das Datum, die einem Objekt zugeordnet sind, in eine Zeichenfolge konvertieren muss.

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>Parameter

*tmFile*<br/>
[in] Das Datum, an einer Datei zugeordnet.

*str*<br/>
[out] Eine Zeichenfolge, die die formatierte Datum enthält.

### <a name="remarks"></a>Hinweise

Wenn eine [CMFCShellListCtrl-Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt zeigt das Datum, die einer Datei zugeordnet, es muss dieses Datum in ein Zeichenfolgenformat zu konvertieren. Die `CMFCShellListCtrl` verwendet diese Methode, um sicherzustellen, dass die Konvertierung. Standardmäßig verwendet diese Methode des aktuellen Gebietsschemas zum Formatieren des Datums in eine Zeichenfolge.

##  <a name="onformatfilesize"></a>  CMFCShellListCtrl::OnFormatFileSize

Das Framework ruft diese Methode auf, wenn die Größe eines Objekts in eine Zeichenfolge konvertiert.

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>Parameter

*lFileSize*<br/>
[in] Die Größe der Datei, die das Framework angezeigt wird.

*str*<br/>
[out] Eine Zeichenfolge, die die Größe der Datei enthält.

### <a name="remarks"></a>Hinweise

Wenn eine [CMFCShellListCtrl-Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt benötigt, um die Größe einer Datei anzuzeigen, muss Sie die Dateigröße in ein Zeichenfolgenformat zu konvertieren. Die `CMFCShellListCtrl` verwendet diese Methode, um sicherzustellen, dass die Konvertierung. Standardmäßig wird diese Methode konvertiert die Dateigröße in Bytes und KB, und klicken Sie dann das aktuelle Gebietsschema verwendet, um die Größe in Zeichenfolge formatieren.

##  <a name="ongetitemicon"></a>  CMFCShellListCtrl::OnGetItemIcon

Das Framework ruft diese Methode, um das Symbol für den ein Listenelement Shell abrufen.

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parameter

*iItem*<br/>
[in] Der Index des Elements.

*pItem*<br/>
[in] Ein LPAFX_SHELLITEMINFO-Parameter, der das Element beschreibt.

### <a name="return-value"></a>Rückgabewert

Der Index des Symbolbilds im Erfolgsfall, andernfalls -1, wenn die Funktion fehlschlägt.

### <a name="remarks"></a>Hinweise

Der Bildindex des Symbols basiert auf der System-Bildliste.

Standardmäßig diese Methode beruht auf der *pItem* Parameter. Der Wert des *iItem* wird nicht in der Standardimplementierung verwendet. Sie können *iItem* um benutzerdefiniertes Verhalten zu implementieren.

##  <a name="ongetitemtext"></a>  CMFCShellListCtrl::OnGetItemText

Das Framework ruft diese Methode auf, wenn er nicht den Text eines Elements Shell abrufen muss.

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parameter

*iItem*<br/>
[in] Der Index des Elements.

*der iColumn*<br/>
[in] Die Spalte von Interesse sind.

*pItem*<br/>
[in] Ein LPAFX_SHELLITEMINFO-Parameter, der das Element beschreibt.

### <a name="return-value"></a>Rückgabewert

Ein `CString` , die dem Element zugeordneten Text enthält.

### <a name="remarks"></a>Hinweise

Jedes Element in der `CMFCShellListCtrl` Objekt kann Text in eine oder mehrere Spalten enthalten. Wenn das Framework diese Methode aufruft, gibt es die Spalte, der von Interesse sind. Wenn Sie diese Funktion manuell aufrufen, müssen Sie auch die Spalte angeben, der Sie interessiert sind.

Standardmäßig diese Methode beruht auf der *pItem* Parameter zu bestimmen, die den Prozess Element. Der Wert des *iItem* wird nicht in der Standardimplementierung verwendet.

##  <a name="onsetcolumns"></a>  CMFCShellListCtrl::OnSetColumns

Das Framework ruft diese Methode auf, wenn sie den Namen der Spalten festlegt.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Hinweise

Standardmäßig erstellt das Framework die vier Spalten in einer `CMFCShellListCtrl` Objekt. Die Namen dieser Spalten sind **Namen**, **Größe**, **Typ**, und **"geändert"**. Sie können diese Methode, um die Anzahl der Spalten und deren Namen anpassen überschreiben.

##  <a name="refresh"></a>  CMFCShellListCtrl::Refresh

Aktualisiert und neu aufgebaut, die [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>Rückgabewert

`S_OK` Wenn erfolgreich; andernfalls einen Fehlerwert.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Aktualisieren der Liste der Elemente angezeigt, indem die `CMFCShellListCtrl` Objekt.

##  <a name="setitemtypes"></a>  CMFCShellListCtrl::SetItemTypes

Bestimmt den Typ der Elemente, die in aufgeführt sind die [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.

```
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>Parameter

*nTypes*<br/>
[in] Eine Liste der Elemente Typen, die `CMFCShellListCtrl` -Objekt unterstützt.

### <a name="remarks"></a>Hinweise

Weitere Informationen zur Liste der work Item Types, finden Sie unter [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md)<br/>
[CMFCShellTreeCtrl-Klasse](../../mfc/reference/cmfcshelltreectrl-class.md)
