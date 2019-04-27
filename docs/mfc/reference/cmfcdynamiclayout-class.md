---
title: CMFCDynamicLayout-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout::AddItem
- AFXLAYOUT/CMFCDynamicLayout::Adjust
- AFXLAYOUT/CMFCDynamicLayout::Create
- AFXLAYOUT/CMFCDynamicLayout::GetHostWnd
- AFXLAYOUT/CMFCDynamicLayout::GetMinSize
- AFXLAYOUT/CMFCDynamicLayout::GetWindowRect
- AFXLAYOUT/CMFCDynamicLayout::HasItem
- AFXLAYOUT/CMFCDynamicLayout::IsEmpty
- AFXLAYOUT/CMFCDynamicLayout::LoadResource
- AFXLAYOUT/CMFCDynamicLayout::SetMinSize
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
ms.openlocfilehash: 40dedbe2737a79b7531b8acd47870ce7cb788604
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237586"
---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout-Klasse

Gibt an, wie Steuerelemente in einem Fenster verschoben und verkleinert oder vergrößert werden, wenn Benutzer die Größe des Fensters ändern.

## <a name="syntax"></a>Syntax

```
class CMFCDynamicLayout : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCDynamicLayout::CMFCDynamicLayout`|Erstellt ein `CMFCDynamicLayout`-Objekt.|
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCDynamicLayout::AddItem](#additem)|Fügt der Liste von Fenstern, die vom dynamischen Layout-Manager gesteuert werden, ein untergeordnetes Fenster hinzu, in der Regel ein Steuerelement.|
|[CMFCDynamicLayout::Adjust](#adjust)|Fügt der Liste von Fenstern, die vom dynamischen Layout-Manager gesteuert werden, ein untergeordnetes Fenster hinzu, in der Regel ein Steuerelement.|
|[CMFCDynamicLayout::Create](#create)|Speichert und überprüft das Hostfenster.|
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|Gibt einen Zeiger auf ein Hostfenster zurück.|
|[CMFCDynamicLayout::GetMinSize](#getminsize)|Gibt die Größe des Fensters zurück, unterhalb derer das Layout nicht angepasst wird.|
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|Ruft das Rechteck für den aktuellen Client-Bereich des Fensters ab.|
|[CMFCDynamicLayout::HasItem](#hasitem)|Überprüft, ob dem dynamischen Layout ein untergeordnetes Steuerelement hinzugefügt wurde.|
|[CMFCDynamicLayout::IsEmpty](#isempty)|Überprüft, ob einem dynamischen Layout keine untergeordneten Fenster hinzugefügt wurden.|
|[CMFCDynamicLayout::LoadResource](#loadresource)|Liest das dynamische Layout aus der AFX_DIALOG_LAYOUT-Ressource und wendet das Layout dann auf das Hostfenster an.|
|statische [CMFCDynamicLayout::MoveHorizontal](#movehorizontal)|Ruft eine [MoveSettings](#movesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement horizontal verschoben wird, wenn der Benutzer Größe des hostingfensters ändert.|
|static [CMFCDynamicLayout::MoveHorizontalAndVertical](#movehorizontalandvertical)|Ruft eine [MoveSettings](#movesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement horizontal verschoben wird, wenn der Benutzer Größe des hostingfensters ändert.|
|statische [CMFCDynamicLayout::MoveNone](#movenone)|Ruft eine [MoveSettings](#movesettings_structure) Wert, der keine Bewegung, das eine vertikale oder horizontale für ein untergeordnetes Steuerelement darstellt.|
|statische [CMFCDynamicLayout::MoveVertical](#movevertical)|Ruft eine [MoveSettings](#movesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement vertikal verschoben wird, wenn der Benutzer Größe des hostingfensters ändert.|
|[CMFCDynamicLayout::SetMinSize](#setminsize)|Legt die Größe des Fensters fest, unterhalb derer das Layout nicht angepasst wird.|
|static [CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|Ruft eine [SizeSettings](#sizesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement horizontal angepasst wird, wenn der Benutzer Größe des hostingfensters ändert.|
|static [CMFCDynamicLayout::SizeHorizontalAndVertical](#sizehorizontalandvertical)|Ruft eine [SizeSettings](#sizesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement horizontal angepasst wird, wenn der Benutzer Größe des hostingfensters ändert.|
|statische [CMFCDynamicLayout::SizeNone](#sizenone)|Ruft eine [SizeSettings](#sizesettings_structure) -Wert, der keine Änderung der Größe für ein untergeordnetes Steuerelement darstellt.|
|statische [CMFCDynamicLayout::SizeVertical](#sizevertical)|Ruft eine [SizeSettings](#sizesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement vertikal angepasst wird, wenn der Benutzer Größe des hostingfensters ändert.|

## <a name="nested-types"></a>Geschachtelte Typen

|Name|Beschreibung|
|----------|-----------------|
|[CMFCDynamicLayout::MoveSettings Structure](#movesettings_structure)|Kapselt Daten für die Verschiebung für Steuerelemente in einem dynamischen Layout.|
|[CMFCDynamicLayout::SizeSettings Structure](#sizesettings_structure)|Kapselt Daten für die Größenänderung für Steuerelemente in einem dynamischen Layout.|

## <a name="remarks"></a>Hinweise

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxlayout.h

##  <a name="additem"></a>  Cmfcdynamiclayout:: AddItem

Fügt der Liste von Fenstern, die vom dynamischen Layout-Manager gesteuert werden, ein untergeordnetes Fenster hinzu, in der Regel ein Steuerelement.

```
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```

### <a name="parameters"></a>Parameter

*hwnd*<br/>
Das Handle zum hinzuzufügenden Fenster.

*nID*<br/>
Die ID des hinzuzufügenden untergeordneten Steuerelements.

*moveSettings*<br/>
Eine Struktur, die beschreibt, wie das Steuerelement verschoben werden soll, wenn sich die Fenstergröße ändert.

*sizeSettings*<br/>
Eine Struktur, die beschreibt, wie die Größe des Steuerelements geändert werden soll, wenn sich die Fenstergröße ändert.

### <a name="return-value"></a>Rückgabewert

„True“, wenn das Element erfolgreich hinzugefügt wurde, andernfalls „false“.

### <a name="remarks"></a>Hinweise

Die Position und Größe eines untergeordneten Steuerelements werden dynamisch geändert, wenn die Größe eines Hostingfensters geändert wird.

##  <a name="adjust"></a>  Cmfcdynamiclayout:: Adjust

Fügt der Liste von Fenstern, die vom dynamischen Layout-Manager gesteuert werden, ein untergeordnetes Fenster hinzu, in der Regel ein Steuerelement.

```
void Adjust();
```

### <a name="remarks"></a>Hinweise

Die Position und Größe eines untergeordneten Steuerelements werden dynamisch geändert, wenn die Größe eines Hostingfensters geändert wird.

##  <a name="create"></a>  CMFCDynamicLayout::Create

Speichert und überprüft das Hostfenster.

```
BOOL Create(CWnd* pHostWnd);
```

### <a name="parameters"></a>Parameter

*pHostWnd*<br/>
Ein Zeiger zum Hostfenster.

### <a name="return-value"></a>Rückgabewert

„True“, wenn die Erstellung erfolgreich war, andernfalls „false“.

### <a name="remarks"></a>Hinweise

##  <a name="gethostwnd"></a>  CMFCDynamicLayout::GetHostWnd

Gibt einen Zeiger auf ein Hostfenster zurück.

```
CWnd* GetHostWnd();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger zum Hostfenster.

### <a name="remarks"></a>Hinweise

Standardmäßig alle untergeordneten Steuerelementpositionen, die in Bezug auf dieses Fenster neuberechnet wurden.

##  <a name="getminsize"></a>  CMFCDynamicLayout::GetMinSize

Gibt die Größe des Fensters zurück, unterhalb derer das Layout nicht angepasst wird.

```
CSize GetMinSize();
```

### <a name="return-value"></a>Rückgabewert

Legt die Größe des Fensters fest, unterhalb derer das Layout nicht angepasst wird.

### <a name="remarks"></a>Hinweise

Die Position und Größe eines untergeordneten Steuerelements werden dynamisch geändert, wenn die Größe eines Hostingfensters geändert wird. Es gibt jedoch eine Mindestgröße, unterhalb derer das Layout nicht angepasst wird. Der Benutzer kann die Größe des Fensters auf eine kleinere Größe ändern, Teile des Fensters werden jedoch aus der Ansicht ausgeblendet.

##  <a name="getwindowrect"></a>  CMFCDynamicLayout::GetWindowRect

Ruft das Rechteck für den aktuellen Client-Bereich des Fensters ab.

```
void GetHostWndRect(CRect& rect,);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
Nach Rückgabe der Funktion enthält dieser Parameter das umschließende Rechteck für den Layoutbereich. Dies ist ein out-Parameter; der Eingabewert wird überschrieben.

### <a name="remarks"></a>Hinweise

##  <a name="hasitem"></a>  Cmfcdynamiclayout:: Hasitem

Überprüft, ob dem dynamischen Layout ein untergeordnetes Steuerelement hinzugefügt wurde.

```
BOOL HasItem(HWND hwnd);
```

### <a name="parameters"></a>Parameter

*hwnd*<br/>
Erstellt ein Handle für das Steuerelement-Fenster.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Layout bereits dieses Element besitzt; andernfalls FALSE.

### <a name="remarks"></a>Hinweise

##  <a name="isempty"></a>  Cmfcdynamiclayout:: IsEmpty

Überprüft, ob einem dynamischen Layout keine untergeordneten Fenster hinzugefügt wurden.

```
BOOL IsEmpty();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Layout keine Elemente aufweist, ansonsten FALSE.

### <a name="remarks"></a>Hinweise

##  <a name="loadresource"></a>  CMFCDynamicLayout::LoadResource

Liest das dynamische Layout aus der AFX_DIALOG_LAYOUT-Ressource und wendet das Layout dann auf das Hostfenster an.

```
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);
```

### <a name="parameters"></a>Parameter

*pHostWnd*<br/>
Ein Zeiger zum Hostfenster.

*lpResource*<br/>
Ein Zeiger zum Puffer, der die AFX_DIALOG_LAYOUT-Ressource enthält.

*dwSize*<br/>
Die Puffergröße in Byte.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Ressource geladen und auf das Hostfenster angewendet wird; andernfalls FALSE.

### <a name="remarks"></a>Hinweise

##  <a name="movehorizontal"></a>  CMFCDynamicLayout::MoveHorizontal

Ruft eine [MoveSettings](#movesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement horizontal verschoben wird, wenn der Benutzer Größe des hostingfensters ändert.

```
static MoveSettings MoveHorizontal(int nRatio);
```

### <a name="parameters"></a>Parameter

*nRatio*<br/>
Definiert einen Prozentwert, der angibt, wie weit ein untergeordnetes Steuerelement horizontal verschoben wird, wenn der Benutzer die Größe des Hostfensters ändert.

### <a name="return-value"></a>Rückgabewert

Ein [MoveSettings](#movesettings_structure) verschiebungsverhältnis der Wert, der den angeforderten kapselt.

### <a name="remarks"></a>Hinweise

##  <a name="movehorizontalandvertical"></a>  CMFCDynamicLayout::MoveHorizontalAndVertical

Ruft eine [MoveSettings](#movesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement horizontal verschoben wird, wenn der Benutzer Größe des hostingfensters ändert.

```
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Parameter

*nXRatio*<br/>
Definiert einen Prozentwert, der angibt, wie weit ein untergeordnetes Steuerelement horizontal verschoben wird, wenn der Benutzer die Größe des Hostfensters ändert.

*nYRatio*<br/>
Definiert einen Prozentwert, der angibt, wie weit ein untergeordnetes Steuerelement vertikal verschoben wird, wenn der Benutzer die Größe des Hostfensters ändert.

### <a name="return-value"></a>Rückgabewert

Ein [MoveSettings](#movesettings_structure) verschiebungsverhältnis der Wert, der den angeforderten kapselt.

### <a name="remarks"></a>Hinweise

##  <a name="movenone"></a>  CMFCDynamicLayout::MoveNone

Ruft eine [MoveSettings](#movesettings_structure) Wert, der keine Bewegung, das eine vertikale oder horizontale für ein untergeordnetes Steuerelement darstellt.

```
static MoveSettings MoveNone();
```

### <a name="return-value"></a>Rückgabewert

Ein [MoveSettings](#movesettings_structure) -Wert, der das Steuerelement direktes behebt, damit es nicht verschieben lässt, wie der Benutzer das Hostfenster ändert.

### <a name="remarks"></a>Hinweise

##  <a name="movesettings_structure"></a>  Cmfcdynamiclayout:: Movesettings-Struktur

Kapselt Daten für die Verschiebung für Steuerelemente in einem dynamischen Layout.

```
struct CMFCDynamicLayout::MoveSettings;
```

### <a name="remarks"></a>Hinweise

Dies ist eine geschachtelte Klasse innerhalb von `CMFCDynamicLayout`.

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::IsHorizontal

Überprüft, ob die Verschiebungsdaten eine horizontale Verschiebung ungleich null angeben.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Rückgabewert

„True“, wenn das `MoveSettings`-Objekt eine horizontale Verschiebung ungleich null angibt.

## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::IsNone

Überprüft, ob die Verschiebungsdaten keine Verschiebung angeben.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Rückgabewert

TRUE, wenn das `MoveSettings`-Objekt keine Veschiebung angibt.

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::IsVertical

  Überprüft, ob die Verschiebungsdaten eine vertikale Verschiebung ungleich 0 angeben.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Rückgabewert

TRUE, wenn das `MoveSettings`-Objekt eine vertikale Verschiebung ungleich 0 angibt.

##  <a name="movevertical"></a>  CMFCDynamicLayout::MoveVertical

Ruft eine [MoveSettings](#movesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement vertikal verschoben wird, wenn der Benutzer Größe des hostingfensters ändert.

```
static MoveSettings MoveVertical(int nRatio);
```

### <a name="parameters"></a>Parameter

*nRatio*<br/>
Definiert einen Prozentwert, der angibt, wie weit ein untergeordnetes Steuerelement vertikal verschoben wird, wenn der Benutzer die Größe des Hostfensters ändert.

### <a name="return-value"></a>Rückgabewert

Ein [MoveSettings](#movesettings_structure) verschiebungsverhältnis der Wert, der den angeforderten kapselt.

### <a name="remarks"></a>Hinweise

##  <a name="setminsize"></a>  CMFCDynamicLayout::SetMinSize

Legt die Größe des Fensters fest, unterhalb derer das Layout nicht angepasst wird.

```
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Die gewünschte Fenstergröße, unterhalb derer das Layout nicht angepasst wird.

### <a name="remarks"></a>Hinweise

Die Position und Größe eines untergeordneten Steuerelements werden dynamisch geändert, wenn die Größe eines Hostingfensters geändert wird. Es gibt jedoch eine Mindestgröße, unterhalb derer das Layout nicht angepasst wird. Der Benutzer kann die Größe des Fensters auf eine kleinere Größe ändern, Teile des Fensters werden jedoch aus der Ansicht ausgeblendet.

##  <a name="sizehorizontal"></a>  CMFCDynamicLayout::SizeHorizontal

Ruft eine [SizeSettings](#sizesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement horizontal angepasst wird, wenn der Benutzer Größe des hostingfensters ändert.

```
static SizeSettings SizeHorizontal(int nRatio);
```

### <a name="parameters"></a>Parameter

*nRatio*<br/>
Definiert einen Prozentwert, der angibt, inwieweit die Größe eines untergeordneten Steuerelements horizontal angepasst wird, wenn der Benutzer die Größe des Hostfensters ändert.

### <a name="return-value"></a>Rückgabewert

Ein [SizeSettings](#sizesettings_structure) -Wert, der das angeforderte Größenverhältnis kapselt.

### <a name="remarks"></a>Hinweise

##  <a name="sizehorizontalandvertical"></a>  CMFCDynamicLayout::SizeHorizontalAndVertical

Ruft eine [SizeSettings](#sizesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement horizontal angepasst wird, wenn der Benutzer Größe des hostingfensters ändert.

```
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>Parameter

*nXRatio*<br/>
Definiert einen Prozentwert, der angibt, inwieweit die Größe eines untergeordneten Steuerelements horizontal angepasst wird, wenn der Benutzer die Größe des Hostfensters ändert.

*nYRatio*<br/>
Definiert einen Prozentwert, der angibt, inwieweit die Größe eines untergeordneten Steuerelements vertikal angepasst wird, wenn der Benutzer die Größe des Hostfensters ändert.

### <a name="return-value"></a>Rückgabewert

Ein [SizeSettings](#sizesettings_structure) -Wert, der das angeforderte Größenverhältnis kapselt.

### <a name="remarks"></a>Hinweise

##  <a name="sizenone"></a>  CMFCDynamicLayout::SizeNone

Ruft eine [SizeSettings](#sizesettings_structure) -Wert, der keine Änderung der Größe für ein untergeordnetes Steuerelement darstellt.

```
static SizeSettings SizeNone();
```

### <a name="return-value"></a>Rückgabewert

Ein [SizeSettings](#sizesettings_structure) -Wert, der das Steuerelement in einer bestimmten Größe fixiert, damit Größe nicht geändert wird, wie der Benutzer das Hostfenster ändert.

### <a name="remarks"></a>Hinweise

##  <a name="sizesettings_structure"></a>  Cmfcdynamiclayout:: Sizesettings-Struktur

Kapselt Daten für die Größenänderung für Steuerelemente in einem dynamischen Layout.

```
struct CMFCDynamicLayout::SizeSettings;
```

### <a name="remarks"></a>Hinweise

Dies ist eine geschachtelte Klasse innerhalb von `CMFCDynamicLayout`.

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::SizeSettings::IsHorizontal

Überprüft, ob die Größenanpassungsdaten eine horizontale Größenanpassung ungleich null angeben.

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>Rückgabewert

TRUE, wenn das `SizeSettings`-Objekt eine horizontale Größenanpassung ungleich null angibt.

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::SizeSettings::IsNone

Überprüft, ob die Größenanpassungsdaten keine Größenanpassung angeben.

```
BOOL IsNone() const
```

## <a name="return-value"></a>Rückgabewert

TRUE, wenn das `SizeSettings`-Objekt keine Größenanpassung angibt.

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::SizeSettings::IsVertical

Überprüft, ob die Größenanpassungsdaten eine vertikale Größenanpassung ungleich null angeben.

```
BOOL IsVertical() const
```

## <a name="return-value"></a>Rückgabewert

TRUE, wenn das `SizeSettings`-Objekt eine vertikale Größenanpassung ungleich null angibt.

##  <a name="sizevertical"></a>  CMFCDynamicLayout::SizeVertical

Ruft eine [SizeSettings](#sizesettings_structure) Wert, der definiert, wie viel ein untergeordnetes Steuerelement vertikal angepasst wird, wenn der Benutzer Größe des hostingfensters ändert.

```
static SizeSettings SizeVertical(int nRatio);
```

### <a name="parameters"></a>Parameter

*nRatio*<br/>
Definiert einen Prozentwert, der angibt, inwieweit die Größe eines untergeordneten Steuerelements vertikal angepasst wird, wenn der Benutzer die Größe des Hostfensters ändert.

### <a name="return-value"></a>Rückgabewert

Ein [SizeSettings](#sizesettings_structure) -Wert, der das angeforderte Größenverhältnis kapselt.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
