---
title: Cshellmanager-Klasse
ms.date: 11/04/2016
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
ms.openlocfilehash: 8151550dafdd1bdf8593d555008af387cf548bc8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502618"
---
# <a name="cshellmanager-class"></a>Cshellmanager-Klasse

Implementiert mehrere Möglichkeiten für die Verwendung von Zeigern auf Bezeichnerlisten (PIDLs).

## <a name="syntax"></a>Syntax

```
class CShellManager : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CShellManager::CShellManager](#cshellmanager)|Erstellt ein `CShellManager`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CShellManager::BrowseForFolder](#browseforfolder)|Zeigt ein Dialogfeld an, in dem der Benutzer einen Shellordner auswählen kann.|
|[CShellManager::ConcatenateItem](#concatenateitem)|Verkettet zwei pidls.|
|[CShellManager::CopyItem](#copyitem)|Erstellt eine neue PIDL und kopiert die angegebene PIDL in diese.|
|[CShellManager::CreateItem](#createitem)|Erstellt eine neue PIDL der angegebenen Größe.|
|[CShellManager::FreeItem](#freeitem)|Löscht die angegebene PIDL.|
|[CShellManager::GetItemCount](#getitemcount)|Gibt die Anzahl der Elemente in der angegebenen PIDL zurück.|
|[CShellManager::GetItemSize](#getitemsize)|Gibt die Größe der bereitgestellten PIDL zurück.|
|[CShellManager::GetNextItem](#getnextitem)|Gibt das nächste Element aus der PIDL zurück.|
|[CShellManager::GetParentItem](#getparentitem)|Ruft das übergeordnete Element des angegebenen Elements ab.|
|[CShellManager::ItemFromPath](#itemfrompath)|Ruft die PIDL für das durch den angegebenen Pfad identifizierte Element ab.|

## <a name="remarks"></a>Hinweise

Die Methoden der `CShellManager` -Klasse behandeln alle pidls. Eine PIDL ist ein eindeutiger Bezeichner für ein Shellobjekt.

Ein `CShellManager` -Objekt sollte nicht manuell erstellt werden. Sie wird automatisch vom Framework der Anwendung erstellt. Sie sollten jedoch beim Initialisierungs Prozess der Anwendung [CWinAppEx:: initshellmanager](../../mfc/reference/cwinappex-class.md#initshellmanager) aufrufen. Rufen Sie [CWinAppEx:: getshellmanager](../../mfc/reference/cwinappex-class.md#getshellmanager)auf, um einen Zeiger auf den Shellmanager für Ihre Anwendung zu erhalten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[Cshellmanager](../../mfc/reference/cshellmanager-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxshellmanager. h

##  <a name="browseforfolder"></a>Cshellmanager:: browsegforfolder

Zeigt ein Dialogfeld an, in dem der Benutzer einen Shellordner auswählen kann.

```
BOOL BrowseForFolder(
    CString& strOutFolder,
    CWnd* pWndParent = NULL,
    LPCTSTR lplszInitialFolder = NULL,
    LPCTSTR lpszTitle = NULL,
    UINT ulFlags = BIF_RETURNONLYFSDIRS,
    LPINT piFolderImage = NULL);
```

### <a name="parameters"></a>Parameter

*strOutFolder*<br/>
vorgenommen Die Zeichenfolge, die von der-Methode verwendet wird, um den Pfad des ausgewählten Ordners zu speichern.

*pWndParent*<br/>
in Ein Zeiger auf das übergeordnete Fenster.

*lplszInitialFolder*<br/>
in Eine Zeichenfolge, die den Ordner enthält, der standardmäßig ausgewählt wird, wenn das Dialogfeld angezeigt wird.

*lpszTitle*<br/>
in Der Titel für das Dialogfeld.

*ulFlags*<br/>
in Flags, die Optionen für das Dialogfeld angeben. Die ausführliche Beschreibung finden Sie unter [Browseinfo](/windows/win32/api/shlobj_core/ns-shlobj_core-browseinfow) .

*piFolderImage*<br/>
vorgenommen Ein Zeiger auf den ganzzahligen Wert, in dem die-Methode den Image Index des ausgewählten Ordners schreibt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Benutzer einen Ordner aus dem Dialogfeld auswählt. andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn Sie diese Methode aufgerufen haben, erstellt die Anwendung ein Dialogfeld und zeigt ein Dialogfeld an, in dem der Benutzer einen Ordner auswählen kann. Mit der-Methode wird der Pfad des Ordners in den *stroutfolder* -Parameter geschrieben.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Verweis auf ein `CShellManager` -Objekt mithilfe der `CWinAppEx::GetShellManager` -Methode abgerufen wird und wie `BrowseForFolder` die-Methode verwendet wird. Dieser Code Ausschnitt ist Teil des [Explorer](../../overview/visual-cpp-samples.md)-Beispiels.

[!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]

##  <a name="concatenateitem"></a>Cshellmanager:: concatenateitem

Erstellt eine neue Liste, die zwei pidls enthält.

```
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,
    LPCITEMIDLIST pidl2);
```

### <a name="parameters"></a>Parameter

*pidl1*<br/>
in Das erste Element.

*pidl2*<br/>
in Das zweite Element.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die neue Elementliste, wenn die Funktion erfolgreich ausgeführt wird, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Diese Methode erstellt eine neue [itemittel List](/windows/win32/api/shtypes/ns-shtypes-itemidlist) , die groß genug ist, um sowohl *pidl1* als auch *pidl2*zu enthalten. Anschließend werden *pidl1* und *pidl2* in die neue Liste kopiert.

##  <a name="copyitem"></a>Cshellmanager:: CopyItem

Kopiert eine Elementliste.

```
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```

### <a name="parameters"></a>Parameter

*pidlSource*<br/>
in Die ursprüngliche Elementliste.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die neu erstellte Elementliste, wenn erfolgreich. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Die neu erstellte Elementliste hat dieselbe Größe wie die Quell Elementliste.

##  <a name="createitem"></a>Cshellmanager:: kreateitem

Erstellt eine neue PIDL.

```
LPITEMIDLIST CreateItem(UINT cbSize);
```

### <a name="parameters"></a>Parameter

*cbSize*<br/>
in Die Größe der Elementliste.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die erstellte Elementliste, wenn erfolgreich. andernfalls NULL.

##  <a name="cshellmanager"></a>Cshellmanager:: cshellmanager

Erstellt ein `CShellManager`-Objekt.

```
CShellManager();
```

### <a name="remarks"></a>Hinweise

In den meisten Fällen ist es nicht erforderlich, einen `CShellManager` direkt zu erstellen. Standardmäßig erstellt das Framework eines. Rufen Sie `CShellManager` [CWinAppEx:: getshellmanager](../../mfc/reference/cwinappex-class.md#getshellmanager)auf, um einen Zeiger auf den zu erhalten. Wenn Sie einen `CShellManager` manuell erstellen, müssen Sie ihn mit der-Methode [CWinAppEx:: initshellmanager](../../mfc/reference/cwinappex-class.md#initshellmanager)initialisieren.

##  <a name="freeitem"></a>Cshellmanager:: freeitem

Löscht eine Elementliste.

```
void FreeItem(LPITEMIDLIST pidl);
```

### <a name="parameters"></a>Parameter

*PIDL*<br/>
in Eine Elementliste, die gelöscht werden soll.

##  <a name="getitemcount"></a>Cshellmanager:: GetItemCount

Gibt die Anzahl der Elemente in einer Elementliste zurück.

```
UINT GetItemCount(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parameter

*PIDL*<br/>
in Ein Zeiger auf eine Elementliste.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in der Elementliste.

##  <a name="getitemsize"></a>Cshellmanager:: getitemsize

Gibt die Größe einer Elementliste zurück.

```
UINT GetItemSize(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parameter

*PIDL*<br/>
in Ein Zeiger auf eine Elementliste.

### <a name="return-value"></a>Rückgabewert

Die Größe der Elementliste.

##  <a name="getnextitem"></a>Cshellmanager:: GetNextItem

Ruft das nächste Element von einem Zeiger auf eine Element Bezeichner Liste (PIDL) ab.

```
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parameter

*PIDL*<br/>
in Die Liste der Elemente, die durchlaufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das nächste Element in der Liste.

### <a name="remarks"></a>Hinweise

Wenn in der Liste keine weiteren Elemente vorhanden sind, gibt diese Methode NULL zurück.

##  <a name="getparentitem"></a>Cshellmanager:: getparameentitem

Ruft das übergeordnete Element eines Zeigers auf eine elementbezeichnerliste (PIDL) ab.

```
int GetParentItem(
    LPCITEMIDLIST lpidl,
    LPITEMIDLIST& lpidlParent);
```

### <a name="parameters"></a>Parameter

*lpidl*<br/>
in Eine PIDL, deren übergeordnetes Element abgerufen wird.

*lpidlParent*<br/>
vorgenommen Ein Verweis auf eine PIDL, in der die-Methode das Ergebnis speichert.

### <a name="return-value"></a>Rückgabewert

Die Ebene der übergeordneten PIDL.

### <a name="remarks"></a>Hinweise

Die Ebene einer PIDL ist relativ zum Desktop. Die Desktop-PIDL wird als 0 (null) eingestuft.

##  <a name="itemfrompath"></a>Cshellmanager:: itemfrompath

Ruft den Zeiger auf eine Element Bezeichner Liste (PIDL) aus dem durch einen Zeichen folgen Pfad identifizierten Element ab.

```
HRESULT ItemFromPath(
    LPCTSTR lpszPath,
    LPITEMIDLIST& pidl);
```

### <a name="parameters"></a>Parameter

*lpszPath*<br/>
in Eine Zeichenfolge, die den Pfad für das Element angibt.

*PIDL*<br/>
vorgenommen Ein Verweis auf eine PIDL. Die-Methode verwendet diese PIDL, um den Zeiger auf seinen Rückgabewert zu speichern.

### <a name="return-value"></a>Rückgabewert

Gibt noError zurück, wenn erfolgreich; ein OLE-definierter Fehlerwert.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
