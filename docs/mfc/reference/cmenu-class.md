---
title: CMenu-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
dev_langs:
- C++
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c13b4d5c3779d6c4b57ff53a1016b344ed097099
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083359"
---
# <a name="cmenu-class"></a>CMenu-Klasse

Eine Kapselung von Windows- `HMENU`.

## <a name="syntax"></a>Syntax

```
class CMenu : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMenu::CMenu](#cmenu)|Erstellt ein `CMenu`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|Fügt ein neues Element am Ende dieses Menüs an.|
|[CMenu::Attach](#attach)|Fügt ein Windows-Menü-Handle für ein `CMenu` Objekt.|
|[CMenu::CheckMenuItem](#checkmenuitem)|Setzt ein Häkchen neben oder entfernt aus der ein Menüelement im Popupmenü mit einem Häkchen versehen.|
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Ein Optionsfeld neben einem Menüelement platziert, und das Optionsfeld aus allen anderen Menüelemente in der Gruppe entfernt.|
|[CMenu::CreateMenu](#createmenu)|Erstellt ein leeres Menü und fügt sie an einer `CMenu` Objekt.|
|[CMenu::CreatePopupMenu](#createpopupmenu)|Erstellt ein leeres Popup-Menü und fügt sie an einer `CMenu` Objekt.|
|[:: DeleteMenu auf](#deletemenu)|Löscht ein angegebenes Element aus dem Menü an. Weist das Menüelement über ein Popup-Menü verknüpft, das Handle für das Popupmenü zerstört, und gibt die von diesem verwendeten Arbeitsspeicher frei.|
|[CMenu::DeleteTempMap](#deletetempmap)|Löscht temporäre `CMenu` Objekten von erstellt die `FromHandle` Member-Funktion.|
|[CMenu::DestroyMenu](#destroymenu)|Zerstört das Menü angefügt eine `CMenu` Objekt aus, und Speicher, der belegt Sie im Menü frei.|
|[CMenu::Detach](#detach)|Trennt ein Windows-Menü-Handle von einem `CMenu` Objekt und gibt das Handle zurück.|
|[CMenu::DrawItem](#drawitem)|Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Menü ändert.|
|[CMenu:: EnableMenuItem](#enablemenuitem)|Aktiviert, deaktiviert oder abgeblendet (grau) eines Menüelements.|
|[CMenu::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CMenu` Objekts, dem ein Windows-Menü-Handle.|
|[CMenu::GetDefaultItem](#getdefaultitem)|Bestimmt das Standardmenüelement auf das angegebene Menü an.|
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Ruft die Hilfekontext-ID verknüpft ist, mit dem Menü ab.|
|[CMenu::GetMenuInfo](#getmenuinfo)|Ruft die Informationen in einem bestimmten Menü ab.|
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Bestimmt die Anzahl der Elemente in einem Menü Popup- oder der obersten Ebene an.|
|[CMenu::GetMenuItemID](#getmenuitemid)|Ruft die Menü-Element-ID für ein Menüelement, an der angegebenen Position befindet.|
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Ruft Informationen über ein Menüelement ab.|
|[CMenu::GetMenuState](#getmenustate)|Gibt den Status des angegebenen Menüelements oder die Anzahl der Elemente in einem Popupmenü zurück.|
|[CMenu::GetMenuString](#getmenustring)|Ruft die Bezeichnung des angegebenen Menüelements ab.|
|[CMenu::GetSafeHmenu](#getsafehmenu)|Gibt die `m_hMenu` umschlossen, die von diesem `CMenu` Objekt.|
|[CMenu::GetSubMenu](#getsubmenu)|Ruft einen Zeiger auf ein Popup-Menü ab.|
|[CMenu::InsertMenu](#insertmenu)|Fügt ein neues Menüelement an der angegebenen Position, die andere Elemente aus der verschieben.|
|[CMenu::InsertMenuItem](#insertmenuitem)|Fügt ein neues Menüelement an der angegebenen Position in einem Menü an.|
|[CMenu::LoadMenu](#loadmenu)|Lädt eine Menüressource aus der ausführbaren Datei und fügt sie an einer `CMenu` Objekt.|
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Lädt ein Menü, aus einer Menüvorlage im im Arbeitsspeicher und fügt sie an einer `CMenu` Objekt.|
|[CMenu::MeasureItem](#measureitem)|Wird aufgerufen, durch das Framework um Menü Dimensionen zu bestimmen, wenn ein vom Besitzer gezeichnetes Menü erstellt wird.|
|[CMenu::ModifyMenu](#modifymenu)|Ändert eine vorhandene Menüelement, an der angegebenen Position.|
|[CMenu::RemoveMenu](#removemenu)|Löscht ein Menüelement mit einem zugeordneten Popupmenü aus dem angegebenen Menü an.|
|[CMenu::SetDefaultItem](#setdefaultitem)|Legt das Standardmenüelement für das angegebene Menü fest.|
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Legt fest, die Hilfekontext-ID, klicken Sie im Menü zugeordnet werden soll.|
|[CMenu::SetMenuInfo](#setmenuinfo)|Legt die Informationen in einem bestimmten Menü fest.|
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|Ordnet die angegebene Häkchen Bitmaps mit einem Menüelement.|
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|Ändert die Informationen zu einem Menüelement.|
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Zeigt ein Gleitkomma-Popup-Menü an der angegebenen Position und verfolgt die Auswahl der Elemente im Popupmenü.|
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Zeigt ein Gleitkomma-Popup-Menü an der angegebenen Position und verfolgt die Auswahl der Elemente im Popupmenü.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CMenu::operator HMENU](#operator_hmenu)|Ruft das Handle des Menüobjekts im ab.|
|[CMenu::operator! =](#operator_neq)|Bestimmt, ob zwei im Menüobjekte nicht gleich sind.|
|[CMenu::operator ==](#operator_eq_eq)|Bestimmt, ob zwei im Menüobjekte gleich sind.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMenu::m_hMenu](#m_hmenu)|Gibt das Handle für das Windows-Menü hinzugefügt der `CMenu` Objekt.|

## <a name="remarks"></a>Hinweise

Es bietet Memberfunktionen zum Erstellen, nachverfolgen, aktualisieren und löschen ein Menü an.

Erstellen Sie eine `CMenu` Objekt auf dem Stapelrahmen als lokales, rufen Sie dann `CMenu`Member-Funktionen, um das neue Menü zu bearbeiten, je nach Bedarf. Rufen Sie als Nächstes [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) , legen Sie im Menü für ein Fenster, unmittelbar gefolgt von einem Aufruf der `CMenu` des Objekts [trennen](#detach) Member-Funktion. Die `CWnd::SetMenu` Memberfunktion legt das Menü des Fensters für das neue Menü, bewirkt, dass das Fenster neu gezeichnet wird, um die Menü-Änderung zu übernehmen und übergibt außerdem den Besitz des Menüs für das Fenster. Der Aufruf von `Detach` trennt das HMENU aus der `CMenu` Objekt, also bei der lokalen `CMenu` -Variable, die außerhalb des gültigen Bereichs, übergibt die `CMenu` Objektdestruktor wird nicht versucht, um ein Menü zu zerstören, es nicht mehr besitzt. Das Menü selbst automatisch zerstört, wenn das Fenster zerstört wird.

Können Sie die [LoadMenuIndirect](#loadmenuindirect) Memberfunktion versucht, ein Menü, aus einer Vorlage speicherresident, aber ein Menü erstellt aus einer Ressource durch einen Aufruf von erstellen [LoadMenu](#loadmenu) wird einfacher verwaltet werden, und die Menüressource selbst erstellt und im Menü-Editor geändert werden können.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="appendmenu"></a>  CMenu::AppendMenu

Fügt ein neues Element am Ende eines Menüs.

```
BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Parameter

*nFlags*<br/>
Gibt Informationen über den Zustand des neuen Menüelements an, wenn sie zum Menü hinzugefügt wird. Es besteht aus mindestens einer der Werte im Abschnitt "Hinweise" aufgeführt sind.

*nIDNewItem*<br/>
Gibt an, entweder die Befehls-ID des neuen Menüelements oder, wenn Sie *nFlags* nastaven NA hodnotu MF_POPUP, das Menühandle ( `HMENU`) von einem Popup-Menü. Die *nIDNewItem* Parameter wird ignoriert (nicht erforderlich), wenn *nFlags* auf MF_SEPARATOR festgelegt ist.

*lpszNewItem*<br/>
Gibt den Inhalt des neuen Menüelements. Die *nFlags* Parameter wird verwendet, um interpretieren *LpszNewItem* auf folgende Weise:

|nFlags|Interpretation von lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Enthält einen von der Anwendung bereitgestellten 32-Bit-Wert, den die Anwendung verwenden können, um dem Menüelement, das zusätzliche Daten zu verwalten. Dieser 32-Bit-Wert ist für die Anwendung verfügbar, bei der Verarbeitung WM_MEASUREITEM und WM_DRAWITEM Nachrichten. Der Wert befindet sich in der `itemData` Member der Struktur, die mit diesen Nachrichten bereitgestellt.|
|MF_STRING|Enthält einen Zeiger auf eine Null-terminierte Zeichenfolge. Dies ist die Standardinterpretation.|
|MF_SEPARATOR|Die *LpszNewItem* Parameter wird ignoriert (nicht erforderlich).|

*pBmp*<br/>
Verweist auf eine `CBitmap` -Objekt, das als dem Menüelement, das verwendet wird.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Die Anwendung kann den Status des Menüelements angeben, durch Festlegen von Werten in *nFlags*. Wenn *nIDNewItem* gibt an, ein Popup-Menü, Teil des Menüs an das sie angefügt ist. Wenn diesem Menü zerstört wird, wird auch das angefügte Menü zerstört werden. Eine angefügte Menü getrennt werden soll, aus einem `CMenu` Objekt, um Konflikte zu vermeiden. Beachten Sie, dass MF_STRING und MF_OWNERDRAW nicht für die Bitmap-Version des gültig sind `AppendMenu`.

Die folgende Liste beschreibt die Flags, die festgelegt werden können, im *nFlags*:

- MF_CHECKED fungiert als eine Umschaltfläche mit MF_UNCHECKED, platzieren die Standardeinstellung überprüfen Sie die Markierung neben dem Element. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter den [SetMenuItemBitmaps](#setmenuitembitmaps) Member-Funktion), die Bitmap "Häkchen für" angezeigt.

- MF_UNCHECKED fungiert als eine Umschaltfläche mit MF_CHECKED ein Häkchen neben dem Element zu entfernen. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter den `SetMenuItemBitmaps` Member-Funktion), die Bitmap "Häkchen deaktiviert" angezeigt.

- MF_DISABLED deaktiviert das Menüelement, damit es kann nicht ausgewählt werden, aber es ist nicht abgeblendet.

- MF_ENABLED ermöglicht das Menüelement aus, sodass es ausgewählt werden kann und vom abgeblendet Zustand wiederhergestellt werden kann.

- MF_GRAYED deaktiviert das Menüelement, damit sie abgeblendet und kann nicht ausgewählt werden.

- MF_MENUBARBREAK platziert das Element in einer neuen Zeile in statischen Menüs bewirkt oder in einer neuen Spalte in der Popup-Menüs an. Die neue Spalte für die Popup-Menü wird durch eine Division vertikale Linie von der alten Spalte getrennt werden.

- MF_MENUBREAK platziert das Element in einer neuen Zeile in statischen Menüs bewirkt oder in einer neuen Spalte in der Popup-Menüs an. Es wird keine Trennlinie zwischen den Spalten platziert.

- MF_OWNERDRAW gibt an, dass das Element ein Ownerdrawn-Element. Wenn zum ersten Mal im Menü angezeigt wird, das Fenster, das Klicken Sie im Menü besitzt, eine WM_MEASUREITEM Nachricht empfängt, die die Höhe und Breite des Menüelements abruft. Die WM_DRAWITEM-Nachricht wird gesendet, wenn der Besitzer die visuelle Darstellung des Menüelements aktualisieren muss. Diese Option gilt nicht für ein Menüelement der obersten Ebene.

- MF_POPUP gibt an, die dem Menüelement, das ein Popup-Menü verknüpft ist. Die ID-Parameter gibt ein Handle für ein Popup-Menü, das mit dem Element zugeordnet werden soll. Hiermit wird ein Popup-Menü-Element entweder ein Popup-Menü der obersten Ebene oder eine hierarchische Popup-Menü hinzugefügt.

- MF_SEPARATOR zeichnet eine horizontale Trennlinie. Kann nur in einem Popupmenü verwendet werden. Diese Zeile kann nicht abgeblendet, deaktiviert oder hervorgehoben werden. Andere Parameter werden ignoriert.

- MF_STRING gibt an, dass es sich bei dem Menüelement, das eine Zeichenfolge ist.

Jede der folgenden Gruppen enthält Flags, die sich gegenseitig und können nicht zusammen verwendet werden:

- MF_DISABLED MF_ENABLED und MF_GRAYED

- MF_STRING, MF_OWNERDRAW, MF_SEPARATOR und die Bitmap-version

- MF_MENUBARBREAK und MF_MENUBREAK

- MF_CHECKED und MF_UNCHECKED

Wenn ein Menü befindet, die in (ob das Fenster angezeigt wird) ein Fensters geändert wird, sollte die Anwendung aufrufen [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).

##  <a name="attach"></a>  CMenu::Attach

Fügt ein vorhandenes Windows-Menü, um eine `CMenu` Objekt.

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>Parameter

*hMenu*<br/>
Gibt ein Handle zu einem Windows-Menü.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nicht aufgerufen werden, wenn ein Menü bereits, um angefügt ist die `CMenu` Objekt. Das Menühandle im befindet sich in der `m_hMenu` -Datenmember.

Wenn Sie im Menü, das Sie bearbeiten möchten bereits ein Fenster zugeordnet ist, können Sie die [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) Funktion, um ein Handle für das Menü abzurufen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="checkmenuitem"></a>  CMenu::CheckMenuItem

Fügt Häkchen oder Häkchen von Menüelementen im Popup-Menü entfernt.

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>Parameter

*nIDCheckItem*<br/>
Das Menüelement aktiviert werden, gibt an, gemäß *nPrüfen*.

*nPrüfen*<br/>
Gibt an, wie Sie das Menüelement zu überprüfen und Bestimmen der Position des Elements im Menü. Die *nPrüfen* Parameter kann eine Kombination von MF_CHECKED oder MF_UNCHECKED mit Flags MF_BYPOSITION oder MF_BYCOMMAND sein. Diese Flags können mit dem bitweisen OR-Operator kombiniert werden. Sie haben folgende Bedeutung:

- MF_BYCOMMAND gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung.

- MF_BYPOSITION gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0.

- MF_CHECKED fungiert als eine Umschaltfläche mit MF_UNCHECKED, platzieren die Standardeinstellung überprüfen Sie die Markierung neben dem Element.

- MF_UNCHECKED fungiert als eine Umschaltfläche mit MF_CHECKED ein Häkchen neben dem Element zu entfernen.

### <a name="return-value"></a>Rückgabewert

Der vorherige Status des Elements: MF_CHECKED oder MF_UNCHECKED, oder 0xFFFFFFFF, wenn das Menüelement nicht vorhanden war.

### <a name="remarks"></a>Hinweise

Die *nIDCheckItem* Parameter gibt an, das Element, das geändert werden.

Die *nIDCheckItem* Parameter identifizieren kann, ein Popupmenü-Elements als auch für ein Menüelement. Keine speziellen Schritte sind erforderlich, um ein Popupmenü-Elements zu überprüfen. Menüelemente der obersten Ebene können nicht überprüft werden. Ein Popup-Menüelement muss anhand der Position eingecheckt werden, da sie nicht über einem Menüelement Bezeichner zugeordnet verfügt.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::GetMenuState](#getmenustate).

##  <a name="checkmenuradioitem"></a>  CMenu::CheckMenuRadioItem

Sucht in einer angegebenen Menüelements, und definiert es ein Optionsfeld-Element.

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>Parameter

*nIDFirst*<br/>
Gibt an (als ID oder Offset, abhängig vom Wert *nFlags*) das erste Menüelement in der Optionsfeldgruppe.

*nIDLast*<br/>
Gibt an (als ID oder Offset, abhängig vom Wert *nFlags*) das letzte Menüelement in der Optionsfeldgruppe.

*nIDItem*<br/>
Gibt an (als ID oder Offset, abhängig vom Wert *nFlags*) das Element in die Gruppe, die mit einem Optionsfeld überprüft werden.

*nFlags*<br/>
Gibt die Interpretation der *nIDFirst*, *nIDLast*, und *nIDItem* auf folgende Weise:

|nFlags|Interpretation|
|------------|--------------------|
|MF_BYCOMMAND|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder MF_BYCOMMAND noch MF_BYPOSITION festgelegt ist.|
|MF_BYPOSITION|Gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0.|

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; Andernfalls wird 0

### <a name="remarks"></a>Hinweise

Zur gleichen Zeit die Funktion deaktiviert alle anderen Menüelemente in der zugehörigen Gruppe und löscht das Radio-Item-Typ-Flag für diese Elemente. Aktivierten Elements wird anstelle von Bitmap Radio Schaltfläche (oder Aufzählungszeichen) eine Bitmap Häkchen angezeigt.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range).

##  <a name="cmenu"></a>  CMenu::CMenu

Erstellt ein leeres Menü und fügt sie an einer `CMenu` Objekt.

```
CMenu();
```

### <a name="remarks"></a>Hinweise

Klicken Sie im Menü wird nicht erstellt werden, bis Sie rufen Sie eine erstellen, oder laden die Memberfunktionen der `CMenu:`

- [CreateMenu](#createmenu)

- [CreatePopupMenu](#createpopupmenu)

- [LoadMenu](#loadmenu)

- [LoadMenuIndirect](#loadmenuindirect)

- [Anfügen](#attach)

##  <a name="createmenu"></a>  CMenu::CreateMenu

Erstellt ein Menü, und fügt es der `CMenu` Objekt.

```
BOOL CreateMenu();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Menü "wurde erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Klicken Sie im Menü ist anfangs leer. Menüelemente können hinzugefügt werden, mithilfe der `AppendMenu` oder `InsertMenu` Member-Funktion.

Wenn Sie im Menü für ein Fenster zugewiesen ist, wird es automatisch zerstört, wenn das Fenster zerstört wird.

Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei, die mit einem Menü verknüpft ist, wenn das Menü nicht in einem Fenster zugewiesen ist. Eine Anwendung freigegeben ein Menüs durch Aufrufen der [DestroyMenu](#destroymenu) Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

##  <a name="createpopupmenu"></a>  CMenu::CreatePopupMenu

Erstellt ein Popup-Menü und fügt es der `CMenu` Objekt.

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn Sie im Popupmenü erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Klicken Sie im Menü ist anfangs leer. Menüelemente können hinzugefügt werden, mithilfe der `AppendMenu` oder `InsertMenu` Member-Funktion. Die Anwendung können Sie im Popupmenü zu einem vorhandenen Menü oder einer Popup-Menü hinzufügen. Die `TrackPopupMenu` Member-Funktion kann verwendet werden, um dieses Menü als unverankerte Popupmenü anzuzeigen und Auswahl den Popup-Menü nachverfolgen.

Wenn Sie im Menü für ein Fenster zugewiesen ist, wird es automatisch zerstört, wenn das Fenster zerstört wird. Wenn das Menü zu einem vorhandenen Menü hinzugefügt wird, wird es automatisch zerstört, wenn diesem Menü zerstört wird.

Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei, die ein Popupmenü zugeordnet, wenn das Menü nicht in einem Fenster zugewiesen ist. Eine Anwendung freigegeben ein Menüs durch Aufrufen der [DestroyMenu](#destroymenu) Member-Funktion.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).

##  <a name="deletemenu"></a>  :: DeleteMenu auf

Löscht ein Element aus dem Menü an.

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parameter

*nPosition*<br/>
Gibt an, das Menüelement, das gelöscht werden, gemäß *nFlags*.

*nFlags*<br/>
Wird verwendet, um interpretieren *nPosition* auf folgende Weise:

|nFlags|Interpretation der nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder MF_BYCOMMAND noch MF_BYPOSITION festgelegt ist.|
|MF_BYPOSITION|Gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0.|

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Das Menüelement besitzt eine zugeordnete Popup-Menü `DeleteMenu` zerstört das Handle zu dem Popup-Menü, und gibt den Arbeitsspeicher frei, die von dem Popup-Menü verwendet.

Wenn ein Menü befindet, die in (ob das Fenster angezeigt wird) ein Fensters geändert wird, muss die Anwendung aufrufen [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

##  <a name="deletetempmap"></a>  CMenu::DeleteTempMap

Wird automatisch aufgerufen, die `CWinApp` -leerlaufzeithandler, löscht temporäre `CMenu` Objekten von erstellt die [FromHandle](#fromhandle) Member-Funktion.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Hinweise

`DeleteTempMap` trennt das Windows-Menü-Objekt angefügt, die an einen temporären `CMenu` Objekt vor dem Löschen der `CMenu` Objekt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

##  <a name="destroymenu"></a>  CMenu::DestroyMenu

Zerstört das Menü und keine Windows-Ressourcen, die verwendet wurden.

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn Sie im Menü zerstört wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Klicken Sie im Menü getrennt von den `CMenu` -Objekt, bevor es zerstört wird. Die Windows `DestroyMenu` Funktion wird automatisch aufgerufen, der `CMenu` Destruktor.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).

##  <a name="detach"></a>  CMenu::Detach

Trennt ein Windows-Menü aus einem `CMenu` Objekt und gibt das Handle zurück.

```
HMENU Detach();
```

### <a name="return-value"></a>Rückgabewert

Das Handle des Typs HMENU, zu einem Windows-Menü, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Die `m_hMenu` -Datenmember auf NULL festgelegt ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="drawitem"></a>  CMenu::DrawItem

Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Menü ändert.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, Informationen über den Typ der Zeichnung, die erforderlich sind enthält.

### <a name="remarks"></a>Hinweise

Die `itemAction` Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CMenu` Objekt. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext in angegeben wiederherstellen *LpDrawItemStruct* vor der Beendigung von dieser Memberfunktion.

Finden Sie unter [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) eine Beschreibung der `DRAWITEMSTRUCT` Struktur.

### <a name="example"></a>Beispiel

Der folgende Code stammt aus der MFC [CTRLTEST](../../visual-cpp-samples.md) Beispiel:

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

##  <a name="enablemenuitem"></a>  CMenu:: EnableMenuItem

Aktiviert, deaktiviert oder abgeblendet ein Menüelements.

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>Parameter

*nIDEnableItem*<br/>
Das Menüelement aktiviert werden, gibt an, gemäß *nEnable*. Dieser Parameter kann im Popupmenü-Elemente sowie Standardmenüelementen angeben.

*nEnable*<br/>
Gibt die auszuführende Aktion an. Sie können eine Kombination von MF_DISABLED MF_ENABLED oder MF_GRAYED, MF_BYCOMMAND oder MF_BYPOSITION sein. Diese Werte können mit dem bitweisen OR-Operator kombiniert werden. Diese Werte haben folgende Bedeutung:

- MF_BYCOMMAND gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung.

- MF_BYPOSITION gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0.

- MF_DISABLED deaktiviert das Menüelement, damit es kann nicht ausgewählt werden, aber es ist nicht abgeblendet.

- MF_ENABLED ermöglicht das Menüelement aus, sodass es ausgewählt werden kann und vom abgeblendet Zustand wiederhergestellt werden kann.

- MF_GRAYED deaktiviert das Menüelement, damit sie abgeblendet und kann nicht ausgewählt werden.

### <a name="return-value"></a>Rückgabewert

Vorherigen Status (MF_DISABLED, MF_ENABLED oder MF_GRAYED) oder 1, wenn nicht gültig.

### <a name="remarks"></a>Hinweise

Die [CreateMenu](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu), und [LoadMenuIndirect](#loadmenuindirect) Member-Funktionen können auch festlegen, den Status (aktiviert, deaktiviert oder abgeblendet) eines Menüelements.

Mit dem MF_BYPOSITION-Wert muss eine Anwendung für den richtigen `CMenu`. Wenn die `CMenu` des Menüs Leiste verwendet wird, wird ein Menüelement der obersten Ebene (ein Element in der Menüleiste) beeinflusst. Den Status eines Elements in einem Popupfenster oder geschachtelte Popupmenü anhand der Position eine Anwendung muss Geben Sie zum Festlegen der `CMenu` des Popupmenüs.

Wenn eine Anwendung das MF_BYCOMMAND-Flag angegeben ist, überprüft Windows alle Popup-Menü-Elemente, die untergeordnet sind die `CMenu`daher es sei denn, Sie doppelte Menüeinträge vorhanden sind, mithilfe der `CMenu` Balken im Menü ist ausreichend.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

##  <a name="fromhandle"></a>  CMenu::FromHandle

Gibt einen Zeiger auf eine `CMenu` Objekts, dem ein Windows-Handle zu einem Menü.

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>Parameter

*hMenu*<br/>
Ein Windows-Handle zu einem Menü.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CMenu` temporär oder permanent sein können.

### <a name="remarks"></a>Hinweise

Wenn eine `CMenu` Objekt ist noch nicht angefügt, das Windows-Menu-Objekt, ein temporäres `CMenu` Objekt erstellt und angefügt.

Diese temporären `CMenu` Objekt ist nur gültig, bis das nächste Mal die Anwendung hat die Zeit im Leerlauf in seiner Event-Schleife, die zu diesem Zeitpunkt werden alle temporären Objekte gelöscht.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).

##  <a name="getdefaultitem"></a>  CMenu::GetDefaultItem

Bestimmt das Standardmenüelement auf das angegebene Menü an.

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parameter

*gmdiFlags*<br/>
Wert, der angibt, wie die Funktion für Menüelemente durchsucht. Dieser Parameter kann keine, eine oder eine Kombination der folgenden Werte sein:

|Wert|Bedeutung|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|Gibt an, dass, sofern das Standardelement, das ein Untermenü geöffnet wird, die Funktion in die entsprechende Untermenü rekursiv gesucht werden soll. Wenn das Untermenü kein Standardelement hat, gibt der Rückgabewert das Element, das das Untermenü wird geöffnet.<br /><br /> Standardmäßig gibt die Funktion das erste Element der Standardwert für das angegebene Menü, unabhängig davon, ob es ein Element, das ein Untermenü geöffnet wird.|
|GMDI_USEDISABLED|Gibt an, dass die Funktion eine Standardelement zurückgeben, selbst wenn er deaktiviert ist.<br /><br /> Standardmäßig überspringt die Funktion deaktiviert oder abgeblendet.|

*fByPos*<br/>
Wert, der angibt, ob das Menüelement-ID oder seine Position abzurufen. Wenn dieser Parameter auf "false" ist, wird die ID zurückgegeben. Andernfalls wird die Position zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert die Bezeichner oder die Position des Menüelements. Wenn die Funktion fehlschlägt, ist der zurückgegebene Wert - 1.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion auf, die das Verhalten der Win32-Funktion [GetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-getmenudefaultitem), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).

##  <a name="getmenucontexthelpid"></a>  CMenu::GetMenuContextHelpId

Ruft die Kontexthilfe-ID zugeordnet `CMenu`.

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>Rückgabewert

Die ID derzeit zugeordnete Kontexthilfe `CMenu` , wenn vorhanden; andernfalls NULL.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).

##  <a name="getmenuinfo"></a>  CMenu::GetMenuInfo

Ruft Informationen für ein Menü ab.

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>Parameter

*lpcmi*<br/>
Ein Zeiger auf eine [MENUINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo) Struktur, die Informationen für das Menü enthält.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ungleich null; Andernfalls ist der Rückgabewert 0 (null).

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Abrufen von Informationen über das Menü an.

##  <a name="getmenuitemcount"></a>  CMenu::GetMenuItemCount

Bestimmt die Anzahl der Elemente in einem Menü Popup- oder der obersten Ebene an.

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in das Menü, wenn die Funktion erfolgreich ist; andernfalls -1.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

##  <a name="getmenuitemid"></a>  CMenu::GetMenuItemID

Der Menüelemente Bezeichner für ein Menüelement befindet sich an der Position von definierten *nPos*.

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Gibt die Position (nullbasiert) des Menüelements, dessen ID abgerufen wird.

### <a name="return-value"></a>Rückgabewert

Die Element-ID für das angegebene Element in einem Popup-Menü, wenn die Funktion erfolgreich ist. Wenn das angegebene Element um ein Popupmenü (im Gegensatz zu einem Element im Popup-Menü) ist, wird der Wert-1 zurückgegeben. Wenn *nPos* entspricht einem TRENNZEICHEN-Menüelement, ist der Rückgabewert 0.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).

##  <a name="getmenuiteminfo"></a>  CMenu::GetMenuItemInfo

Ruft Informationen über ein Menüelement ab.

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parameter

*uItem*<br/>
Bezeichner oder die Position des Menüelements zu dem Informationen abgerufen. Die Bedeutung dieses Parameters hängt vom Wert der `ByPos`.

*lpMenuItemInfo*<br/>
Ein Zeiger auf eine [MENUITEMINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuiteminfoa), wie im Windows SDK ist beschrieben, die Informationen über das Menü enthält.

*fByPos*<br/>
Wert, der die Bedeutung des angibt `nIDItem`. In der Standardeinstellung `ByPos` ist "false", der angibt, uItem ist eine Element-ID im Menü. Wenn `ByPos` ist nicht festgelegt auf "false", es gibt eine Position eines Elements im Menü an.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ungleich NULL. Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null. Um erweiterte Fehlerinformationen abzurufen, verwenden Sie die Win32-Funktion [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360), wie im Windows SDK beschrieben.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion auf, die das Verhalten der von der Win32-Funktion [GetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-getmenuiteminfoa)gemäß der Beschreibung in das Windows SDK. Beachten Sie, dass in der MFC-Implementierung von `GetMenuItemInfo`, verwenden Sie kein Handle für ein Menü.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

##  <a name="getmenustate"></a>  CMenu::GetMenuState

Gibt den Status des angegebenen Menüelements oder die Anzahl der Elemente in einem Popupmenü zurück.

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Gibt die Menü-Element-ID an, gemäß *nFlags*.

*nFlags*<br/>
Gibt die Art der *nID*. Es kann eine der folgenden Werte sein:

- MF_BYCOMMAND gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung.

- MF_BYPOSITION gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0.

### <a name="return-value"></a>Rückgabewert

Der Wert "0xFFFFFFFF", wenn das angegebene Element nicht vorhanden ist. Wenn *nId* identifiziert ein Popup-Menü, das höherwertige Byte enthält die Anzahl der Elemente im Popup-Menü und die niederwertigen Bytes die Menü-Flags, die mit dem Popup-Menü verknüpft ist. Andernfalls ist der Rückgabewert eine Maske (boolescher oder) der Werte in der folgenden Liste (dieser Maske beschreibt den Status des Menüs Element *nId* bezeichnet):

- MF_CHECKED fungiert als eine Umschaltfläche mit MF_UNCHECKED, platzieren die Standardeinstellung überprüfen Sie die Markierung neben dem Element. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter den `SetMenuItemBitmaps` Member-Funktion), die Bitmap "Häkchen für" angezeigt.

- MF_DISABLED deaktiviert das Menüelement, damit es kann nicht ausgewählt werden, aber es ist nicht abgeblendet.

- MF_ENABLED ermöglicht das Menüelement aus, sodass es ausgewählt werden kann und vom abgeblendet Zustand wiederhergestellt werden kann. Beachten Sie, dass der Wert dieser Konstanten 0 ist. eine Anwendung sollte nicht für 0 für Fehler testen, wenn dieser Wert verwendet.

- MF_GRAYED deaktiviert das Menüelement, damit sie abgeblendet und kann nicht ausgewählt werden.

- MF_MENUBARBREAK platziert das Element in einer neuen Zeile in statischen Menüs bewirkt oder in einer neuen Spalte in der Popup-Menüs an. Die neue Spalte für die Popup-Menü wird durch eine Division vertikale Linie von der alten Spalte getrennt werden.

- MF_MENUBREAK platziert das Element in einer neuen Zeile in statischen Menüs bewirkt oder in einer neuen Spalte in der Popup-Menüs an. Es wird keine Trennlinie zwischen den Spalten platziert.

- MF_SEPARATOR zeichnet eine horizontale Trennlinie. Kann nur in einem Popupmenü verwendet werden. Diese Zeile kann nicht abgeblendet, deaktiviert oder hervorgehoben werden. Andere Parameter werden ignoriert.

- MF_UNCHECKED fungiert als eine Umschaltfläche mit MF_CHECKED ein Häkchen neben dem Element zu entfernen. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter den `SetMenuItemBitmaps` Member-Funktion), die Bitmap "Häkchen deaktiviert" angezeigt. Beachten Sie, dass der Wert dieser Konstanten 0 ist. eine Anwendung sollte nicht für 0 für Fehler testen, wenn dieser Wert verwendet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

##  <a name="getmenustring"></a>  CMenu::GetMenuString

Kopiert die Bezeichnung des angegebenen Menüelements in den angegebenen Puffer.

```
int GetMenuString(
    UINT nIDItem,
    LPTSTR lpString,
    int nMaxCount,
    UINT nFlags) const;

int GetMenuString(
    UINT nIDItem,
    CString& rString,
    UINT nFlags) const;
```

### <a name="parameters"></a>Parameter

*nIDItem*<br/>
Gibt den Offset des Menüelements oder der ganzzahlige Bezeichner der dem Menüelement, das im Menü, abhängig vom Wert *nFlags*.

*lpString*<br/>
Verweist auf den Puffer, der die Bezeichnung erhalten.

*rString*<br/>
Ein Verweis auf eine `CString` -Objekt, das die kopierte Menüzeichenfolge empfangen.

*nMaxCount*<br/>
Gibt die maximale Länge (in Zeichen) der Bezeichnung kopiert werden soll. Wenn sich die Bezeichnung überschreitet die maximal zulässigen Wert im angegebenen *nMaxCount*, die zusätzlichen Zeichen werden abgeschnitten.

*nFlags*<br/>
Gibt an, die Interpretation der *nIDItem* Parameter. Es kann eine der folgenden Werte sein:

|nFlags|Interpretation von nIDItem|
|------------|-------------------------------|
|MF_BYCOMMAND|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder MF_BYCOMMAND noch MF_BYPOSITION festgelegt ist.|
|MF_BYPOSITION|Gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0.|

### <a name="return-value"></a>Rückgabewert

Gibt die tatsächliche Anzahl von Zeichen in den Puffer, einschließlich nicht auf null-Terminator kopiert.

### <a name="remarks"></a>Hinweise

Die *nMaxCount* Parameter sollte einer größer als die Anzahl der Zeichen in der Bezeichnung für das Null-Zeichen sein, die eine Zeichenfolge beendet werden.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).

##  <a name="getsafehmenu"></a>  CMenu::GetSafeHmenu

Gibt zurück, das von diesem umschlossenen HMENU `CMenu` Objekt oder ein NULL-Wert`CMenu` Zeiger.

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::LoadMenu](#loadmenu).

##  <a name="getsubmenu"></a>  CMenu::GetSubMenu

Ruft die `CMenu` Objekt ein Popup-Menü.

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Gibt die Position des Popupmenüs enthalten sind, klicken Sie im Menü. Positionswerte beginnen bei 0 für das erste Menüelement. Das Popup-Menü-ID kann nicht in dieser Funktion verwendet werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CMenu` Objekt, dessen `m_hMenu` Element enthält ein Handle für das Popup-Menü aus, wenn ein Popupmenü an der angegebenen Position vorhanden ist, andernfalls NULL. Wenn eine `CMenu` Objekt ist nicht vorhanden ist, wird eine temporäre erstellt. Die `CMenu` zurückgegebenen Zeiger sollten nicht gespeichert werden.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::TrackPopupMenu](#trackpopupmenu).

##  <a name="insertmenu"></a>  CMenu::InsertMenu

Fügt ein neues Menüelement, an der Position gemäß *nPosition* und andere Elemente nach unten klicken Sie im Menü.

```
BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Parameter

*nPosition*<br/>
Gibt an, dem Menüelement, das vor dem ist das neue Menüelement eingefügt werden soll. Die *nFlags* Parameter kann verwendet werden, um interpretieren *nPosition* auf folgende Weise:

|nFlags|Interpretation der nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder MF_BYCOMMAND noch MF_BYPOSITION festgelegt ist.|
|MF_BYPOSITION|Gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0. Wenn *nPosition* ist-1. das neue Menüelement wird am Ende des Menüs angefügt.|

*nFlags*<br/>
Gibt an, wie *nPosition* interpretiert, und gibt Informationen über den Zustand des neuen Menüelements an, wenn sie zum Menü hinzugefügt wird. Eine Liste der Flags, die festgelegt werden können, finden Sie unter den [AppendMenu](#appendmenu) Member-Funktion. Um mehr als einen Wert anzugeben, verwenden Sie die bitweisen OR-Operator, um sie mit dem Flag MF_BYCOMMAND oder MF_BYPOSITION zu kombinieren.

*nIDNewItem*<br/>
Gibt an, entweder die Befehls-ID des neuen Menüelements oder, wenn Sie *nFlags* auf MF_POPUP, das Menühandle (HMENU) des Popupmenüs festgelegt ist. Die *nIDNewItem* Parameter wird ignoriert (nicht erforderlich), wenn *nFlags* auf MF_SEPARATOR festgelegt ist.

*lpszNewItem*<br/>
Gibt den Inhalt des neuen Menüelements. *nFlags* können verwendet werden, um interpretieren *LpszNewItem* auf folgende Weise:

|nFlags|Interpretation von lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Enthält einen von der Anwendung bereitgestellten 32-Bit-Wert, den die Anwendung verwenden können, um dem Menüelement, das zusätzliche Daten zu verwalten. Dieser 32-Bit-Wert steht für die Anwendung in der `itemData` Member der Struktur, die vom der [WM_MEASUREITEM](/windows/desktop/Controls/wm-measureitem) und [WM_DRAWITEM](/windows/desktop/Controls/wm-drawitem) Nachrichten. Diese Nachrichten werden gesendet, wenn das Menüelement zunächst angezeigt wird oder geändert wird.|
|MF_STRING|Enthält einen long-Zeiger auf eine Null-terminierte Zeichenfolge an. Dies ist die Standardinterpretation.|
|MF_SEPARATOR|Die *LpszNewItem* Parameter wird ignoriert (nicht erforderlich).|

*pBmp*<br/>
Verweist auf eine `CBitmap` -Objekt, das als dem Menüelement, das verwendet wird.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Die Anwendung kann den Status des Menüelements angeben, durch Festlegen von Werten in *nFlags*.

Wenn ein Menü befindet, die in (ob das Fenster angezeigt wird) ein Fensters geändert wird, sollte die Anwendung aufrufen `CWnd::DrawMenuBar`.

Wenn *nIDNewItem* gibt an, ein Popup-Menü, Teil des Menüs in der er eingefügt wird. Wenn diesem Menü zerstört wird, wird auch das Menü "inserted" zerstört werden. Ein eingefügter Menü sollte getrennt werden, von einem `CMenu` Objekt, um Konflikte zu vermeiden.

Wenn die aktive, die untergeordneten Fenster der multiple Document Interface (MDI) maximiert wird und eine Anwendung fügt ein Popup-Menü im der MDI-Anwendung durch Aufrufen, diese Funktion und angeben, die die MF_BYPOSITION-, das Menü Flag eine Position weiter nach links als eingefügt erwartet wird. Dies geschieht, weil das Systemmenü der aktiven untergeordneten MDI-Fensters in der ersten Position der Menüleiste des MDI-Rahmenfensters eingefügt wird. Um das Menü ordnungsgemäß zu positionieren, muss die Anwendung 1 den-Positionswerts hinzufügen, die andernfalls verwendet werden. Eine Anwendung kann die WM_MDIGETACTIVE-Nachricht verwenden, um zu bestimmen, ob das derzeit aktiven untergeordneten Fenster maximiert ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

##  <a name="insertmenuitem"></a>  CMenu::InsertMenuItem

Fügt ein neues Menüelement an der angegebenen Position in einem Menü an.

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parameter

*uItem*<br/>
Finden Sie in der Beschreibung der *uItem* in [InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema) im Windows SDK.

*lpMenuItemInfo*<br/>
Finden Sie in der Beschreibung der *Lpmii* in `InsertMenuItem` im Windows SDK.

*fByPos*<br/>
Finden Sie in der Beschreibung der *fByPosition* in `InsertMenuItem` im Windows SDK.

### <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für [InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema), die im Windows SDK beschrieben.

##  <a name="loadmenu"></a>  CMenu::LoadMenu

Lädt eine Menüressource aus ausführbaren Datei der Anwendung und fügt es der `CMenu` Objekt.

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge mit dem Namen der Menüressource laden.

*nIDResource*<br/>
Gibt an, die Menü-ID der Menüressource laden.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Menüressource erfolgreich geladen wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei, die mit einem Menü verknüpft ist, wenn das Menü nicht in einem Fenster zugewiesen ist. Eine Anwendung freigegeben ein Menüs durch Aufrufen der [DestroyMenu](#destroymenu) Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

##  <a name="loadmenuindirect"></a>  CMenu::LoadMenuIndirect

Lädt eine Ressource aus einer Menüvorlage im im Arbeitsspeicher und fügt es der `CMenu` Objekt.

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>Parameter

*lpMenuTemplate*<br/>
Verweist auf eine Menüvorlage (Dies ist eine einzelne [MENUITEMTEMPLATEHEADER](/windows/desktop/api/winuser/ns-winuser-menuitemtemplateheader) Struktur und eine Auflistung von einem oder mehreren [MENUITEMTEMPLATE](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate) Strukturen). Weitere Informationen zu diesen zwei Strukturen finden Sie im Windows-SDK.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Menüressource erfolgreich geladen wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Eine Menüvorlage ist eine Kopfzeile gefolgt von einer Auflistung von einem oder mehreren [MENUITEMTEMPLATE](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate) Strukturen, von denen jedes einen oder mehrere Menüelemente und einen Popupmenüs enthalten kann.

Die Versionsnummer sollte 0 sein.

Die `mtOption` Flags sollte für das letzte Element in einer Popup-Liste und die für das letzte Element in der Hauptliste MF_END umfassen. Finden Sie unter den `AppendMenu` Member-Funktion für andere Flags. Die `mtId` Member muss aus der Struktur MENUITEMTEMPLATE weggelassen werden, wenn MF_POPUP, in angegeben wird `mtOption`.

Der Speicherplatz für die Struktur MENUITEMTEMPLATE muss groß genug sein `mtString` den Namen des Menüelements als Null-terminierte Zeichenfolge enthält.

Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei, die mit einem Menü verknüpft ist, wenn das Menü nicht in einem Fenster zugewiesen ist. Eine Anwendung freigegeben ein Menüs durch Aufrufen der [DestroyMenu](#destroymenu) Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

##  <a name="m_hmenu"></a>  CMenu::m_hMenu

Gibt an, das HMENU-Handle für das Windows-Menü hinzugefügt der `CMenu` Objekt.

```
HMENU m_hMenu;
```

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::LoadMenu](#loadmenu).

##  <a name="measureitem"></a>  CMenu::MeasureItem

Vom Framework aufgerufen, wenn ein Menü mit den Ownerdrawn-Stil erstellt wird.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parameter

*lpMeasureItemStruct*<br/>
Ein Zeiger auf eine `MEASUREITEMSTRUCT` Struktur.

### <a name="remarks"></a>Hinweise

Standardmäßig ist diese Member-Funktion mit "nothing". Überschreiben Sie diese Memberfunktion auf, und geben Sie die `MEASUREITEMSTRUCT` Struktur, um Windows die Menüs Dimensionen zu informieren.

Finden Sie unter [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) eine Beschreibung der `MEASUREITEMSTRUCT` Struktur.

### <a name="example"></a>Beispiel

Der folgende Code stammt aus der MFC [CTRLTEST](../../visual-cpp-samples.md) Beispiel:

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

##  <a name="modifymenu"></a>  CMenu::ModifyMenu

Ändert ein vorhandenes Menüelement an der Position gemäß *nPosition*.

```
BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Parameter

*nPosition*<br/>
Gibt an, dem Menüelement, das geändert werden. Die *nFlags* Parameter kann verwendet werden, um interpretieren *nPosition* auf folgende Weise:

|nFlags|Interpretation der nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder MF_BYCOMMAND noch MF_BYPOSITION festgelegt ist.|
|MF_BYPOSITION|Gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0.|

*nFlags*<br/>
Gibt an, wie *nPosition* interpretiert, und erhalten Sie Informationen zu den Änderungen, die an das Menüelement vorgenommen werden. Eine Liste von Flags, die festgelegt werden können, finden Sie unter den [AppendMenu](#appendmenu) Member-Funktion.

*nIDNewItem*<br/>
Gibt an, entweder die Befehls-ID des geänderten Menüelements oder, wenn Sie *nFlags* nastaven NA hodnotu MF_POPUP, das Menühandle (HMENU), der ein Popup-Menü. Die *nIDNewItem* Parameter wird ignoriert (nicht erforderlich), wenn *nFlags* auf MF_SEPARATOR festgelegt ist.

*lpszNewItem*<br/>
Gibt den Inhalt des neuen Menüelements. Die *nFlags* Parameter kann verwendet werden, um interpretieren *LpszNewItem* auf folgende Weise:

|nFlags|Interpretation von lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Enthält einen von der Anwendung bereitgestellten 32-Bit-Wert, den die Anwendung verwenden können, um dem Menüelement, das zusätzliche Daten zu verwalten. Dieser 32-Bit-Wert ist für die Anwendung verfügbar, bei der Verarbeitung MF_MEASUREITEM und MF_DRAWITEM.|
|MF_STRING|Einen long-Zeiger auf eine Null-terminierte Zeichenfolge oder enthält ein `CString`.|
|MF_SEPARATOR|Die *LpszNewItem* Parameter wird ignoriert (nicht erforderlich).|

*pBmp*<br/>
Verweist auf eine `CBitmap` -Objekt, das als dem Menüelement, das verwendet wird.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Die Anwendung den neuen Zustand des Menüelements angibt, durch Festlegen von Werten in *nFlags*. Wenn diese Funktion über ein Popup-Menü verknüpft ist, mit dem Menüelement ersetzt, die alte Popupmenü zerstört und gibt den Arbeitsspeicher frei, die von dem Popup-Menü verwendet.

Wenn *nIDNewItem* gibt an, ein Popup-Menü, Teil des Menüs in der er eingefügt wird. Wenn diesem Menü zerstört wird, wird auch das Menü "inserted" zerstört werden. Ein eingefügter Menü sollte getrennt werden, von einem `CMenu` Objekt, um Konflikte zu vermeiden.

Wenn ein Menü befindet, die in (ob das Fenster angezeigt wird) ein Fensters geändert wird, sollte die Anwendung aufrufen `CWnd::DrawMenuBar`. Um die Attribute eines vorhandenen Menüelementen zu ändern, es ist viel schneller, verwenden Sie die `CheckMenuItem` und `EnableMenuItem` Memberfunktionen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).

##  <a name="operator_hmenu"></a>  CMenu::operator HMENU

Verwenden Sie diesen Operator das Handle des abzurufenden der `CMenu` Objekt.

```
operator HMENU() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, das Handle des dem `CMenu` Objekt; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Sie können das Handle verwenden, um Windows-APIs direkt aufrufen.

##  <a name="operator_neq"></a>  CMenu::operator! =

Bestimmt, ob zwei Menüs logisch nicht gleich sind.

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>Parameter

*Menü "*<br/>
Ein `CMenu` Objekt für den Vergleich.

### <a name="remarks"></a>Hinweise

Testet, ob ein Menüobjekt im auf der linken Seite nicht gleich einem Menüobjekt im auf der rechten Seite ist.

##  <a name="operator_eq_eq"></a>  CMenu::operator ==

Bestimmt, ob zwei Menüs logisch gleich sind.

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>Parameter

*Menü "*<br/>
Ein `CMenu` Objekt für den Vergleich.

### <a name="remarks"></a>Hinweise

Testet, ob ein Menüobjekt im auf der linken Seite ist gleich (hinsichtlich der HMENU-Wert) ein Menüobjekt im auf der rechten Seite.

##  <a name="removemenu"></a>  CMenu::RemoveMenu

Löscht aus dem Menü ein Menüelement mit einem Popup-Menü verknüpft.

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Parameter

*nPosition*<br/>
Gibt an, dem Menüelement, das entfernt werden soll. Die *nFlags* Parameter kann verwendet werden, um interpretieren *nPosition* auf folgende Weise:

|nFlags|Interpretation der nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder MF_BYCOMMAND noch MF_BYPOSITION festgelegt ist.|
|MF_BYPOSITION|Gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0.|

*nFlags*<br/>
Gibt an, wie *nPosition* interpretiert wird.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Zerstört es nicht das Handle für ein Popup-Menü, sodass Sie im Menü wiederverwendet werden kann. Vor dem Aufrufen dieser Funktion, die Anwendung aufrufen, kann die `GetSubMenu` Member-Funktion zum Abrufen der Popupliste `CMenu` Objekt für die Wiederverwendung.

Wenn ein Menü befindet, die in (ob das Fenster angezeigt wird) ein Fensters geändert wird, muss die Anwendung aufrufen `CWnd::DrawMenuBar`.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).

##  <a name="setdefaultitem"></a>  CMenu::SetDefaultItem

Legt das Standardmenüelement für das angegebene Menü fest.

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parameter

*uItem*<br/>
Bezeichner oder die Position des neuen Standardmenüelement oder -1 für kein Standardelement. Die Bedeutung dieses Parameters hängt vom Wert der *fByPos*.

*fByPos*<br/>
Wert, der die Bedeutung des angibt *uItem*. Wenn dieser Parameter auf "FALSE" ist *uItem* eine Menü-Element-ID ist. Andernfalls ist es eine Position eines Elements im Menü.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ungleich NULL. Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null. Um erweiterte Fehlerinformationen abzurufen, verwenden Sie die Win32-Funktion [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360), wie im Windows SDK beschrieben.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion auf, die das Verhalten der Win32-Funktion [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).

##  <a name="setmenucontexthelpid"></a>  CMenu::SetMenuContextHelpId

Ordnet eine Kontext-Hilfe-ID mit `CMenu`.

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>Parameter

*dwContextHelpId*<br/>
Kontexthilfe-ID zugeordnet werden soll `CMenu`.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; Andernfalls wird 0

### <a name="remarks"></a>Hinweise

Alle Elemente im Menü Freigeben dieser Bezeichner – es ist nicht möglich, eine Hilfekontextbezeichner an einzelne Menüelemente anzufügen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).

##  <a name="setmenuinfo"></a>  CMenu::SetMenuInfo

Legt fest, für ein Menü.

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>Parameter

*lpcmi*<br/>
Ein Zeiger auf eine [MENUINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo) Struktur, die Informationen für das Menü enthält.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ungleich null; Andernfalls ist der Rückgabewert 0 (null).

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um spezifische Informationen über das Menü "festgelegt.

##  <a name="setmenuitembitmaps"></a>  CMenu::SetMenuItemBitmaps

Ordnet die angegebene Bitmaps mit einem Menüelement.

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>Parameter

*nPosition*<br/>
Gibt an, dem Menüelement, das geändert werden. Die *nFlags* Parameter kann verwendet werden, um interpretieren *nPosition* auf folgende Weise:

|nFlags|Interpretation der nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder MF_BYCOMMAND noch MF_BYPOSITION festgelegt ist.|
|MF_BYPOSITION|Gibt an, dass der Parameter die Position des vorhandenen Menüelements enthält. Das erste Element ist an Position 0.|

*nFlags*<br/>
Gibt an, wie *nPosition* interpretiert wird.

*pBmpUnchecked*<br/>
Gibt an, die Bitmap, die für Menüelemente verwendet wird, die nicht überprüft werden.

*pBmpChecked*<br/>
Gibt an, die Bitmap, die für Menüelemente verwendet wird, die überprüft werden.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Ob das Menüelement aktiviert oder deaktiviert ist, zeigt Windows die entsprechende Bitmap neben dem Menüelement.

Wenn entweder *pBmpUnchecked* oder *pBmpChecked* NULL ist, und klicken Sie dann Windows nichts neben dem Menüelement, das für das entsprechende Attribut angezeigt wird. Wenn beide Parameter NULL sind, verwendet Windows das Standard-Kontrollkästchen, wenn das Element aktiviert wird, und das Häkchen, entfernt Wenn das Element nicht aktiviert ist.

Wenn Sie im Menü zerstört wird, werden diese Bitmaps nicht gelöscht werden; die Anwendung muss diese zerstört werden.

Die Windows `GetMenuCheckMarkDimensions` Funktion ruft die Abmessungen des Häkchens Standard für Menüelemente verwendet. Die Anwendung verwendet diese Werte, um zu bestimmen, die geeignete Größe für die Bitmaps, die mit dieser Funktion bereitgestellt. Rufen Sie die Größe, erstellen Sie die Bitmaps, und legen Sie sie.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

##  <a name="setmenuiteminfo"></a>  CMenu::SetMenuItemInfo

Ändert die Informationen zu einem Menüelement.

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Parameter

*uItem*<br/>
Finden Sie in der Beschreibung der *uItem* in [SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa) im Windows SDK.

*lpMenuItemInfo*<br/>
Finden Sie in der Beschreibung der *Lpmii* in `SetMenuItemInfo` im Windows SDK.

*fByPos*<br/>
Finden Sie in der Beschreibung der *fByPosition* in `SetMenuItemInfo` im Windows SDK.

### <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für [SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa), die im Windows SDK beschrieben.

##  <a name="trackpopupmenu"></a>  CMenu::TrackPopupMenu

Zeigt ein Gleitkomma-Popup-Menü an der angegebenen Position und verfolgt die Auswahl der Elemente im Popupmenü.

```
BOOL TrackPopupMenu(
    UINT nFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPCRECT lpRect = 0);
```

### <a name="parameters"></a>Parameter

*nFlags*<br/>
Gibt Flags an Bildschirmposition und Position des Mauszeigers. Finden Sie unter [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) eine Liste der verfügbaren Flags.

*w*<br/>
Gibt die horizontale Position in Bildschirmkoordinaten, der dem Popup-Menü an. Abhängig vom Wert der *nFlags* Parameter, klicken Sie im Menü kann sein, linksbündig, rechtsbündig oder zentriert relativ zu dieser Position.

*y*<br/>
Gibt die vertikale Position in Bildschirmkoordinaten des oberen Rands klicken Sie im Menü auf dem Bildschirm an.

*Aufnehmen*<br/>
Gibt das Fenster, das Sie im Popupmenü besitzt. Dieser Parameter darf nicht NULL sein, auch wenn das TPM_NONOTIFY-Flag angegeben wird. In diesem Fenster empfängt alle WM_COMMAND-Meldungen aus dem Menü. In Windows-Versionen 3.1 und höher, das Fenster erhält keine WM_COMMAND-Meldungen bis `TrackPopupMenu` zurückgibt. Windows 3.0 wird das Fenster empfängt WM_COMMAND-Meldungen vor dem `TrackPopupMenu` zurückgibt.

*lpRect*<br/>
Ignoriert.

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt das Ergebnis des Aufrufs [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) im Windows SDK.

### <a name="remarks"></a>Hinweise

Ein Gleitkomma-Popup-Menü kann überall auf dem Bildschirm angezeigt werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

##  <a name="trackpopupmenuex"></a>  CMenu::TrackPopupMenuEx

Zeigt ein Gleitkomma-Popup-Menü an der angegebenen Position und verfolgt die Auswahl der Elemente im Popupmenü.

```
BOOL TrackPopupMenuEx(
    UINT fuFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPTPMPARAMS lptpm);
```

### <a name="parameters"></a>Parameter

*fuFlags*<br/>
Gibt verschiedene Funktionen für das erweiterte Menü an. Eine Liste aller Werte und deren Bedeutung finden Sie [TrackPopupMenuEx](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex).

*w*<br/>
Gibt die horizontale Position in Bildschirmkoordinaten, der dem Popup-Menü an.

*y*<br/>
Gibt die vertikale Position in Bildschirmkoordinaten des oberen Rands klicken Sie im Menü auf dem Bildschirm an.

*Aufnehmen*<br/>
Ein Zeiger auf das Fenster besitzt die Popup-Menü und Empfang der Nachrichten aus dem Menü erstellt werden soll. Dieses Fenster kann einem beliebigen Fenster aus der aktuellen Anwendung jedoch darf nicht NULL sein. Bei Angabe von TPM_NONOTIFY in die *FuFlags* -Parameter die Funktion sendet alle Nachrichten, die keine *aufnehmen*. Die Funktion zurück, für das Fenster zeigt *aufnehmen* zum Empfangen der WM_COMMAND-Meldung.

*lptpm*<br/>
Zeiger auf eine [TPMPARAMS](/windows/desktop/api/winuser/ns-winuser-tagtpmparams) Struktur, die einen Bereich des Bildschirms im Menü angibt sollten sich nicht überschneiden. Dieser Parameter kann NULL sein.

### <a name="return-value"></a>Rückgabewert

Bei Angabe von TPM_RETURNCMD in die *FuFlags* Parameter, der Rückgabewert ist der Menü-Elementbezeichner des Elements, das der Benutzer ausgewählt. Wenn der Benutzer das Menü abbricht, ohne eine Auswahl zu treffen, oder wenn ein Fehler auftritt, ist der Rückgabewert 0.

Wenn Sie keine TPM_RETURNCMD im Angeben der *FuFlags* Parameter, die der Rückgabewert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wird und 0 ist, wenn ein Fehler auftritt. Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="remarks"></a>Hinweise

Ein Gleitkomma-Popup-Menü kann überall auf dem Bildschirm angezeigt werden. Weitere Informationen zum Behandeln von Fehlern, wenn das Popup-Menü zu erstellen, finden Sie unter [TrackPopupMenuEx](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CTRLTEST](../../visual-cpp-samples.md)<br/>
[MFC-Beispiel DYNAMENU](../../visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)
