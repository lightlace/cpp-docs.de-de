---
title: CContextMenuManager-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
dev_langs:
- C++
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0890b18316a9b61c3e86858e76176a8d68501852
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082129"
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager-Klasse

Die `CContextMenuManager` Objekt verwaltet Kontextmenüs, die auch als Verknüpfungsmenüs bezeichnet.

## <a name="syntax"></a>Syntax

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Erstellt ein `CContextMenuManager`-Objekt.|
|`CContextMenuManager::~CContextMenuManager`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CContextMenuManager::AddMenu](#addmenu)|Fügt ein neues Kontextmenü an.|
|[CContextMenuManager::GetMenuById](#getmenubyid)|Gibt ein Handle für das Menü mit der angegebenen Ressource-ID verknüpft ist|
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Gibt ein Handle auf das Menü, das der angegebene Name entspricht.|
|[CContextMenuManager::GetMenuNames](#getmenunames)|Gibt eine Liste der Menünamen zurück.|
|[CContextMenuManager::LoadState](#loadstate)|Lädt die Kontextmenüs, die in der Windows-Registrierung gespeichert.|
|[CContextMenuManager::ResetState](#resetstate)|Löscht die Kontextmenüs, über den Kontext-Menü-Manager.|
|[CContextMenuManager::SaveState](#savestate)|Kontextmenüs in der Windows-Registrierung gespeichert.|
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Steuerelemente, ob die `CContextMenuManager` im aktiven Kontextmenü geschlossen wird, wenn er ein neues Kontextmenü angezeigt.|
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Zeigt das angegebene Kontextmenü an.|
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Zeigt das angegebene Kontextmenü an. Gibt den Index des ausgewählten Menübefehls.|

## <a name="remarks"></a>Hinweise

`CContextMenuManager` verwaltet Kontextmenüs und stellt sicher, dass sie ein einheitliches Erscheinungsbild aufweisen.

Erstellen Sie keine `CContextMenuManager` Objekt manuell. Das Framework der Anwendung erstellt die `CContextMenuManager` Objekt. Sie sollten jedoch aufrufen [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) Wenn Ihre Anwendung initialisiert wird. Nach der Initialisierung des Kontext-Managers, verwenden Sie die Methode [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) um einen Zeiger auf die Kontext-Manager für Ihre Anwendung zu erhalten.

Sie können zur Laufzeit Kontextmenüs erstellen, durch den Aufruf `AddMenu`. Wenn Sie das Menü, ohne zuerst empfängt Benutzereingaben anzeigen möchten, rufen Sie `ShowPopupMenu`. `TrackPopupMenu` wird verwendet, wenn Sie verwenden möchten, erstellen Sie ein Menüelement, und Benutzereingaben. `TrackPopupMenu` Gibt den Index des ausgewählten Befehls oder 0 zurück, wenn der Benutzer beendet, ohne etwas auszuwählen.

Die `CContextMenuManager` können auch speichern und Laden von Zuständen in die Windows-Registrierung.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Menü Hinzufügen einer `CContextMenuManager` Objekt und das nicht dem aktiven Popup-Menü zu schließen bei der `CContextMenuManager` Objekt wird ein neues Popupmenü angezeigt. Dieser Codeausschnitt ist Teil der [Beispiel für benutzerdefinierte Seiten](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>Anforderungen

**Header:** afxcontextmenumanager.h

##  <a name="addmenu"></a>  CContextMenuManager::AddMenu

Fügt eine neue im Kontextmenü der [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
BOOL AddMenu(
    UINT uiMenuNameResId,
    UINT uiMenuResId);

BOOL AddMenu(
    LPCTSTR lpszName,
    UINT uiMenuResId);
```

### <a name="parameters"></a>Parameter

*uiMenuNameResId*<br/>
[in] Ein Ressourcen-ID für eine Zeichenfolge, die den Namen für das neue Menü enthält.

*uiMenuResId*<br/>
[in] Die Menü-Ressourcen-ID.

*Wert*<br/>
[in] Eine Zeichenfolge, die den Namen für das neue Menü enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode erfolgreich war; 0, wenn die Methode fehlschlägt.

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn *UiMenuResId* ist ungültig, oder wenn bereits ein weiteres Menü mit dem gleichen Namen wird die `CContextMenuManager`.

##  <a name="ccontextmenumanager"></a>  CContextMenuManager::CContextMenuManager

Erstellt eine [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) Objekt.

```
CContextMenuManager();
```

### <a name="remarks"></a>Hinweise

In den meisten Fällen sollten Sie keine erstellen eine `CContextMenuManager` manuell. Das Framework der Anwendung erstellt die `CContextMenuManager` Objekt. Rufen Sie [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) während der Initialisierung der Anwendung. Um einen Zeiger an dem Kontextmanager zu erhalten, rufen [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).

##  <a name="getmenubyid"></a>  CContextMenuManager::GetMenuById

Gibt ein Handle für das Menü, das eine bestimmte Ressource-ID zugeordnet ist

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>Parameter

*nMenuResId*<br/>
[in] Die Ressourcen-ID für das Menü.

### <a name="return-value"></a>Rückgabewert

Ein Handle für das zugeordnete Menü oder `NULL` Wenn das Menü "nicht gefunden wird.

##  <a name="getmenubyname"></a>  CContextMenuManager::GetMenuByName

Gibt ein Handle zu einem bestimmten Menü an.

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
[in] Eine Zeichenfolge, die den Namen des abzurufenden Menüs enthält.

*puiOrigResID*<br/>
[out] Ein Zeiger auf eine "uint". Dieser Parameter enthält die Ressourcen-ID des angegebenen Menüs auf, wenn gefunden.

### <a name="return-value"></a>Rückgabewert

Ein Handle für das Menü, das mit dem Namen übereinstimmt, die von angegeben wurde *Wert*. NULL, wenn es kein Menü ist *Wert*.

### <a name="remarks"></a>Hinweise

Wenn diese Methode ein Menü findet, die entspricht *Wert*, `GetMenuByName` speichert die Menü-Ressourcen-ID im Parameter *PuiOrigResID*.

##  <a name="getmenunames"></a>  CContextMenuManager::GetMenuNames

Gibt die Liste der Menünamen hinzugefügt, die [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Parameter

*listOfNames*<br/>
[out] Ein Verweis auf eine [CStringList](../../mfc/reference/cstringlist-class.md) Parameter. Diese Methode schreibt die Liste der Menünamen für diesen Parameter an.

##  <a name="loadstate"></a>  CContextMenuManager::LoadState

Lädt die Informationen im Zusammenhang mit der [CContextMenuManager-Klasse](../../mfc/reference/ccontextmenumanager-class.md) aus der Windows-Registrierung.

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die *LpszProfileName* Parameter ist nicht der absolute Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standardschlüssel für die Registrierung für Ihre Anwendung hinzugefügt wird. Verwenden Sie zum Abrufen oder Festlegen des Standard-Registrierungsschlüssels, die Methoden [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) und [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) bzw.

Verwenden Sie die Methode [CContextMenuManager::SaveState](#savestate) auf die Kontextmenüs in der Registrierung speichern.

##  <a name="resetstate"></a>  CContextMenuManager::ResetState

Löscht alle Elemente aus der zugeordneten Kontextmenüs der [CContextMenuManager-Klasse](../../mfc/reference/ccontextmenumanager-class.md).

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich ist. "False", wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Diese Methode löscht das Popup-Menüs und entfernt sie aus der `CContextMenuManager`.

##  <a name="savestate"></a>  CContextMenuManager::SaveState

Speichert Informationen im Zusammenhang mit der [CContextMenuManager-Klasse](../../mfc/reference/ccontextmenumanager-class.md) an der Windows-Registrierung.

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die *LpszProfileName* Parameter ist nicht der absolute Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standardschlüssel für die Registrierung für Ihre Anwendung hinzugefügt wird. Verwenden Sie zum Abrufen oder Festlegen des Standard-Registrierungsschlüssels, die Methoden [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) und [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) bzw.

Verwenden Sie die Methode [CContextMenuManager::LoadState](#loadstate) die Kontextmenüs aus der Registrierung geladen.

##  <a name="setdontcloseactivemenu"></a>  CContextMenuManager::SetDontCloseActiveMenu

Steuerelemente, ob die [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) im Popupmenü aktiv wird geschlossen, wenn es ein neues Popup-Menü angezeigt wird.

```
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parameter

*bSet*<br/>
[in] Ein boolescher Parameter, der steuert, ob die aktive Popupmenü geschlossen. Der Wert "true" gibt an, dass die aktive Popupmenü nicht geschlossen ist. FALSE gibt an, dass die aktive Popupmenü geschlossen wird.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung die `CContextMenuManager` schließt die aktive Popupmenü.

##  <a name="showpopupmenu"></a>  CContextMenuManager::ShowPopupMenu

Zeigt das angegebene Kontextmenü an.

```
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bRightAlign = FALSE);

virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bAutoDestroy = TRUE,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>Parameter

*uiMenuResId*<br/>
[in] Die Ressourcen-ID des Menüs, das diese Methode angezeigt wird.

*w*<br/>
[in] Der horizontale offset für das Kontextmenü in Clientkoordinaten.

*y*<br/>
[in] Der vertikale Offset für das Kontextmenü in Clientkoordinaten

*pWndOwner*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster des Kontextmenüs.

*bOwnMessage*<br/>
[in] Ein boolescher Parameter, der angibt, wie Nachrichten weitergeleitet werden. Wenn *bOwnMessage* ist "false" "," standard-MFC routing verwendet wird. Andernfalls *pWndOwner* empfängt die Nachrichten.

*hmenuPopup*<br/>
[in] Das Handle des Menüs, das diese Methode angezeigt wird.

*bAutoDestroy*<br/>
[in] Ein boolescher Parameter, der angibt, ob das Menü automatisch zerstört wird.

*bRightAlign*<br/>
[in] Ein boolescher Parameter, der angibt, wie die Menüelemente ausgerichtet werden. Wenn *bRightAlign* ist "true", klicken Sie im Menü ist für rechts-nach-Links-Lesefolge rechtsbündig ausgerichtet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode klicken Sie im Menü zeigt, die erfolgreich, gibt die erste methodenüberladung zurück. andernfalls 0. Die zweite methodenüberladung gibt einen Zeiger auf [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) , wenn die Verknüpfung wird ordnungsgemäß; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Diese Methode ähnelt die Methode [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) , beide Methoden ein Kontextmenü anzuzeigen. Allerdings `TrackPopupMenu` gibt den Index des ausgewählten Menübefehls zurück.

Wenn der Parameter *bAutoDestroy* ist "false", Sie müssen manuell aufrufen, die geerbte `DestroyMenu` Methode, um Speicherressourcen freizugeben. Die standardmäßige Implementierung des `ShowPopupMenu` verwendet nicht den Parameter *bAutoDestroy*. Er wird bereitgestellt, für die zukünftige Verwendung oder für benutzerdefinierte Klassen, die von der `CContextMenuManager` Klasse.

##  <a name="trackpopupmenu"></a>  CContextMenuManager::TrackPopupMenu

Zeigt das angegebene Kontextmenü, und gibt den Index des ausgewählten Verknüpfung Menübefehls zurück.

```
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>Parameter

*hmenuPopup*<br/>
[in] Das Handle des Kontextmenüs, die diese Methode zeigt.

*w*<br/>
[in] Der horizontale offset für das Kontextmenü in Clientkoordinaten.

*y*<br/>
[in] Der vertikale offset für das Kontextmenü in Clientkoordinaten.

*pWndOwner*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster des Kontextmenüs.

*bRightAlign*<br/>
[in] Ein boolescher Parameter, der angibt, wie Menüelemente ausgerichtet werden. Wenn *bRightAlign* ist "true", klicken Sie im Menü ist für rechts-nach-Links-Lesefolge rechtsbündig ausgerichtet. Wenn *bRightAlign* ist "false", klicken Sie im Menü wird für Links-nach-rechts-Lesefolge linksbündig ausgerichtet.

### <a name="return-value"></a>Rückgabewert

Die Menübefehl-ID des Befehls, der der Benutzer auswählt; 0, wenn der Benutzer im Kontextmenü den Befehl schließt, ohne einen Menübefehl auszuwählen.

### <a name="remarks"></a>Hinweise

Diese Methode funktioniert als modales Aufruf an ein Kontextmenü anzuzeigen. Die Anwendung wird nicht auf die folgende Zeile im Code fortgesetzt, bis der Benutzer im Kontextmenü geschlossen oder einen Befehl auswählt. Eine alternative Methode, die Sie verwenden können, um ein Kontextmenü anzuzeigen ist [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Diese Methode handelt es sich nicht um einen Aufruf der modale und nicht die ID des ausgewählten Befehls zurück.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)
