---
title: Csnapinitemimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::AddMenuItems
- ATLSNAP/ATL::CSnapInItemImpl::Command
- ATLSNAP/ATL::CSnapInItemImpl::CreatePropertyPages
- ATLSNAP/ATL::CSnapInItemImpl::FillData
- ATLSNAP/ATL::CSnapInItemImpl::GetResultPaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::GetResultViewType
- ATLSNAP/ATL::CSnapInItemImpl::GetScopePaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::Notify
- ATLSNAP/ATL::CSnapInItemImpl::QueryPagesFor
- ATLSNAP/ATL::CSnapInItemImpl::SetMenuInsertionFlags
- ATLSNAP/ATL::CSnapInItemImpl::SetToolbarButtonInfo
- ATLSNAP/ATL::CSnapInItemImpl::UpdateMenuState
- ATLSNAP/ATL::CSnapInItemImpl::UpdateToolbarButton
- ATLSNAP/ATL::CSnapInItemImpl::m_bstrDisplayName
- ATLSNAP/ATL::CSnapInItemImpl::m_resultDataItem
- ATLSNAP/ATL::CSnapInItemImpl::m_scopeDataItem
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
ms.openlocfilehash: a9ebcf8827d79a9613ce14251d361dd607aa6af3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496551"
---
# <a name="csnapinitemimpl-class"></a>Csnapinitemimpl-Klasse

Diese Klasse stellt Methoden zum Implementieren eines Snap-in-Knoten Objekts bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `CSnapInItemImpl`abgeleitete Klasse.

*bIsExtension*<br/>
TRUE, wenn das Objekt eine Snap-in-Erweiterung ist. andernfalls false.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|Fügt einem Kontextmenü Menü Elemente hinzu.|
|[Csnapinitemimpl:: Command](#command)|Wird von der-Konsole aufgerufen, wenn ein benutzerdefiniertes Menü Element ausgewählt wird.|
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Fügt dem Eigenschaften Blatt des Snap-Ins Seiten hinzu.|
|[CSnapInItemImpl::FillData](#filldata)|Kopiert Informationen über das Snap-in-Objekt in einen angegebenen Stream.|
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Ruft die `RESULTDATAITEM` Struktur des Snap-Ins ab.|
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Bestimmt den Ansichtstyp, der vom Ergebnisbereich verwendet wird.|
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Ruft die `SCOPEDATAITEM` Struktur des Snap-Ins ab.|
|[CSnapInItemImpl::Notify](#notify)|Wird von der Konsole aufgerufen, um das Snap-in der vom Benutzer ausgeführten Aktionen zu benachrichtigen.|
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Wird aufgerufen, um festzustellen, ob der Snap-in-Knoten Eigenschaften Seiten unterstützt.|
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Ändert die Menü einfügeflags für ein Snap-in-Objekt.|
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Legt die Informationen der angegebenen Symbolleisten Schaltfläche fest.|
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Aktualisiert den Zustand eines Kontextmenü Elements.|
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Aktualisiert den Zustand der angegebenen Symbolleisten Schaltfläche.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Der Name des Snap-in-Objekts.|
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|`RESULTDATAITEM` Die`CSnapInItemImpl` vom-Objekt verwendete Windows-Struktur.|
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|`SCOPEDATAITEM` Die`CSnapInItemImpl` vom-Objekt verwendete Windows-Struktur.|

## <a name="remarks"></a>Hinweise

`CSnapInItemImpl`stellt eine grundlegende Implementierung für ein Snap-in-Knoten Objekt bereit, z. b. das Hinzufügen von Menü Elementen und Symbolleisten und das Weiterleiten von Befehlen für den Snap-in-Knoten zur entsprechenden Handlerfunktion. Diese Features werden mithilfe verschiedener Schnittstellen und Kartentypen implementiert. Die Standard Implementierung verarbeitet Benachrichtigungen, die an das Knoten Objekt gesendet werden, indem die richtige Instanz der abgeleiteten Klasse ermittelt und die Nachricht dann an die richtige Instanz weitergeleitet wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlsnap. h

##  <a name="addmenuitems"></a>Csnapinitemimpl:: AddMenuItems

Diese Methode implementiert die Win32-Funktion [IExtendContextMenu:: AddMenuItems](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems).

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parameter

*piCallback*<br/>
in Ein Zeiger auf `IContextMenuCallback` den, der dem Kontextmenü Elemente hinzufügen kann.

*pinsertionallowed*<br/>
[in, out] Identifiziert von Microsoft Management Console (MMC) definierte Einfügepunkte für Menü Elemente, die verwendet werden können. Dabei kann es sich um eine Kombination der folgenden Flags handeln:

- CCM_INSERTIONALLOWED_TOP Elemente können am oberen Rand eines Kontextmenüs eingefügt werden.

- CCM_INSERTIONALLOWED_NEW Items können im Untermenü neue erstellen eingefügt werden.

- CCM_INSERTIONALLOWED_TASK Items können im Untermenü "Aufgabe" eingefügt werden.

- CCM_INSERTIONALLOWED_VIEW Items können im Menü der Symbolleisten Ansicht oder im Untermenü Ansicht des Kontextmenüs für den Ergebnisbereich eingefügt werden.

*Typ*<br/>
in Gibt den Objekttyp an. Sie kann einen der folgenden Werte aufweisen:

- CCT_SCOPE-Datenobjekt für den Kontext Bereichs Kontext.

- CCT_RESULT-Datenobjekt für den Kontext des Ergebnis Bereichs.

- CCT_SNAPIN_MANAGER-Datenobjekt für den Snap-In-Manager-Kontext.

- Das CCT_UNINITIALIZED-Datenobjekt weist einen ungültigen Typ auf.

##  <a name="command"></a>Csnapinitemimpl:: Command

Diese Methode implementiert die Win32-Funktion [IExtendContextMenu:: Command](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-command).

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parameter

*lCommandID*<br/>
in Gibt den Befehls Bezeichner des Menü Elements an.

*Typ*<br/>
in Gibt den Objekttyp an. Sie kann einen der folgenden Werte aufweisen:

- CCT_SCOPE-Datenobjekt für den Kontext Bereichs Kontext.

- CCT_RESULT-Datenobjekt für den Kontext des Ergebnis Bereichs.

- CCT_SNAPIN_MANAGER-Datenobjekt für den Snap-In-Manager-Kontext.

- Das CCT_UNINITIALIZED-Datenobjekt weist einen ungültigen Typ auf.

##  <a name="createpropertypages"></a>Csnapinitemimpl:: "deatepropertypages"

Diese Methode implementiert die Win32-Funktion [IExtendPropertySheet:: deatepropertypages](/windows/win32/api/mmc/nn-mmc-iextendpropertysheet2).

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parameter

*lpProvider*<br/>
in Ein Zeiger auf `IPropertySheetCallback` die-Schnittstelle.

*bewältigen*<br/>
in Gibt das Handle an, das zum Weiterleiten der MMCN_PROPERTY_CHANGE-Benachrichtigungs Meldung an die entsprechende Datenklasse verwendet wird.

*pUnk*<br/>
in Ein Zeiger auf `IExtendPropertySheet` die-Schnittstelle für das-Objekt, das Kontextinformationen über den Knoten enthält.

*Typ*<br/>
in Gibt den Objekttyp an. Sie kann einen der folgenden Werte aufweisen:

- CCT_SCOPE-Datenobjekt für den Kontext Bereichs Kontext.

- CCT_RESULT-Datenobjekt für den Kontext des Ergebnis Bereichs.

- CCT_SNAPIN_MANAGER-Datenobjekt für den Snap-In-Manager-Kontext.

- Das CCT_UNINITIALIZED-Datenobjekt weist einen ungültigen Typ auf.

##  <a name="csnapinitemimpl"></a>Csnapinitemimpl:: csnapinitemimpl

Erstellt ein `CSnapInItemImpl`-Objekt.

```
CSnapInItemImpl();
```

##  <a name="filldata"></a>Csnapinitemimpl:: filldata

Diese Funktion wird aufgerufen, um Informationen über das Element abzurufen.

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>Parameter

*cf*<br/>
in Das Format (Text, Rich-Text oder Rich Text mit OLE-Elementen) der Zwischenablage.

*pStream*<br/>
in Ein Zeiger auf den Stream, der die Objektdaten enthält.

### <a name="remarks"></a>Hinweise

Um diese Funktion ordnungsgemäß zu implementieren, kopieren Sie die richtigen Informationen in den Stream (*pStream*), abhängig vom Zwischenablage Format, das von *CF*angegeben wird.

##  <a name="getresultviewtype"></a>Csnapinitemimpl:: getresultviewtype

Rufen Sie diese Funktion auf, um den Typ der Ansicht für den Ergebnisbereich des Snap-in-Objekts abzurufen.

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>Parameter

*ppViewType*<br/>
vorgenommen Ein Zeiger auf die Adresse des zurückgegebenen Ansichts Typs.

*pViewOptions*<br/>
vorgenommen Ein Zeiger auf die MMC_VIEW_OPTIONS-Enumeration, die der Konsole die Optionen bereitstellt, die vom besitzenden Snap-in angegeben werden. Folgende Werte sind möglich:

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0x00000001 weist die Konsole an, keine Standardoptionen für die Listenansicht im Menü **Ansicht anzuzeigen** . Ermöglicht dem Snap-in, seine eigenen benutzerdefinierten Ansichten nur im Ergebnis Ansichts Bereich anzuzeigen. Dies ist das einzige zu diesem Zeitpunkt definierte Optionsflag.

- MMC_VIEW_OPTIONS_NONE = 0 ermöglicht die Standard Ansichtsoptionen.

##  <a name="getscopepaneinfo"></a>Csnapinitemimpl:: getscopepaneinfo

Rufen Sie diese Funktion auf, `SCOPEDATAITEM` um die Struktur des Snap-Ins abzurufen.

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>Parameter

*pScopeDataItem*<br/>
vorgenommen Ein Zeiger auf die `SCOPEDATAITEM` Struktur `CSnapInItemImpl` des-Objekts.

##  <a name="getresultpaneinfo"></a>Csnapinitemimpl:: getresultpaneingefo

Rufen Sie diese Funktion auf, `RESULTDATAITEM` um die Struktur des Snap-Ins abzurufen.

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>Parameter

*pResultDataItem*<br/>
vorgenommen Ein Zeiger auf die `RESULTDATAITEM` Struktur `CSnapInItemImpl` des-Objekts.

##  <a name="m_bstrdisplayname"></a>Csnapinitemimpl:: m_bstrDisplayName

Enthält die Zeichenfolge, die für das Knoten Element angezeigt wird.

```
CComBSTR m_bstrDisplayName;
```

##  <a name="m_scopedataitem"></a>Csnapinitemimpl:: m_scopeDataItem

Die `SCOPEDATAITEM` Struktur des Snap-in-Datenobjekts.

```
SCOPEDATAITEM m_scopeDataItem;
```

##  <a name="m_resultdataitem"></a>Csnapinitemimpl:: m_resultDataItem

Die [RESULTDATAITEM](/windows/win32/api/mmc/ns-mmc-resultdataitem) -Struktur des Snap-in-Datenobjekts.

```
RESULTDATAITEM m_resultDataItem;
```

##  <a name="notify"></a>Csnapinitemimpl:: notify

Wird aufgerufen, wenn das Snap-in-Objekt vom Benutzer bearbeitet wird.

```
STDMETHOD(Notify)(
    MMC_NOTIFY_TYPE event,
    long arg,
    long param,
    IComponentData* pComponentData,
    IComponent* pComponent,
    DATA_OBJECT_TYPES type) = 0;
```

### <a name="parameters"></a>Parameter

*event*<br/>
in Identifiziert eine Aktion, die von einem Benutzer ausgeführt wird. Die folgenden Benachrichtigungen sind möglich:

- MMCN_ACTIVATE wird gesendet, wenn ein Fenster aktiviert und deaktiviert wird.

- MMCN_ADD_IMAGES wird gesendet, um dem Ergebnisbereich Bilder hinzuzufügen.

- MMCN_BTN_CLICK wird gesendet, wenn der Benutzer auf eine der Symbolleisten Schaltflächen klickt.

- MMCN_CLICK wird gesendet, wenn ein Benutzer in einem Listen Ansichts Element auf eine Maustaste klickt.

- MMCN_DBLCLICK wird gesendet, wenn ein Benutzer auf eine Maustaste auf ein Listen Ansichts Element doppelklickt.

- MMCN_DELETE gesendet, um das Snap-in zu informieren, dass das Objekt gelöscht werden soll.

- MMCN_EXPAND wird gesendet, wenn ein Ordner erweitert oder verkleinert werden muss.

- MMCN_MINIMIZED wird gesendet, wenn ein Fenster minimiert oder maximiert wird.

- MMCN_PROPERTY_CHANGE wird gesendet, um ein Snap-in-Objekt zu benachrichtigen, dass die Ansicht des Snap-in-Objekts gerade geändert wird.

- MMCN_REMOVE_CHILDREN wird gesendet, wenn das Snap-in die gesamte Unterstruktur löschen muss, die unterhalb des angegebenen Knotens hinzugefügt wurde.

- MMCN_RENAME hat das erste Mal gesendet, um eine Umbenennung abzufragen, und das zweite Mal zum Umbenennen.

- MMCN_SELECT wird gesendet, wenn ein Element im Bereich Bereich oder Ergebnis Ansicht ausgewählt ist.

- MMCN_SHOW wird gesendet, wenn ein Bereichs Element zum ersten Mal ausgewählt oder deaktiviert wird.

- MMCN_VIEW_CHANGE wird gesendet, wenn das Snap-in alle Ansichten aktualisieren kann, wenn eine Änderung auftritt.

*arg*<br/>
in Hängt vom Benachrichtigungstyp ab.

*param*<br/>
in Hängt vom Benachrichtigungstyp ab.

*pComponentData*<br/>
vorgenommen Ein Zeiger auf das Objekt, `IComponentData`das implementiert. Dieser Parameter ist NULL, wenn die Benachrichtigung nicht von `IComponentData::Notify`weitergeleitet wird.

*pComponent*<br/>
vorgenommen Ein Zeiger auf das Objekt, das `IComponent`implementiert. Dieser Parameter ist NULL, wenn die Benachrichtigung nicht von `IComponent::Notify`weitergeleitet wird.

*Typ*<br/>
in Gibt den Objekttyp an. Sie kann einen der folgenden Werte aufweisen:

- CCT_SCOPE-Datenobjekt für den Kontext Bereichs Kontext.

- CCT_RESULT-Datenobjekt für den Kontext des Ergebnis Bereichs.

- CCT_SNAPIN_MANAGER-Datenobjekt für den Snap-In-Manager-Kontext.

- Das CCT_UNINITIALIZED-Datenobjekt weist einen ungültigen Typ auf.

##  <a name="querypagesfor"></a>Csnapinitemimpl:: querypgesfor

Wird aufgerufen, um festzustellen, ob der Snap-in-Knoten Eigenschaften Seiten unterstützt.

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

##  <a name="setmenuinsertionflags"></a>Csnapinitemimpl:: setmenuinsertionflags

Mit dieser Funktion können Sie für das Snap-in-Objekt die durch *pinsertionallowed*angegebenen Menü einfügeflags ändern.

```
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>Parameter

*bBeforeInsertion*<br/>
in Ein Wert ungleich 0 (null), wenn die Funktion aufgerufen werden soll, bevor Elemente zum Kontextmenü hinzugefügt werden. andernfalls 0.

*pinsertionallowed*<br/>
[in, out] Identifiziert von Microsoft Management Console (MMC) definierte Einfügepunkte für Menü Elemente, die verwendet werden können. Dabei kann es sich um eine Kombination der folgenden Flags handeln:

- CCM_INSERTIONALLOWED_TOP Elemente können am oberen Rand eines Kontextmenüs eingefügt werden.

- CCM_INSERTIONALLOWED_NEW Items können im Untermenü neue erstellen eingefügt werden.

- CCM_INSERTIONALLOWED_TASK Items können im Untermenü "Aufgabe" eingefügt werden.

- CCM_INSERTIONALLOWED_VIEW Items können im Menü der Symbolleisten Ansicht oder im Untermenü Ansicht des Kontextmenüs für den Ergebnisbereich eingefügt werden.

### <a name="remarks"></a>Hinweise

Wenn Sie ein primäres Snap-in entwickeln, können Sie alle einfügeflags als Möglichkeit zum Einschränken der Art von Menü Elementen zurücksetzen, die von einer Drittanbieter Erweiterung hinzugefügt werden können. Beispielsweise kann das primäre Snap-in das Flag CCM_INSERTIONALLOWED_NEW löschen, um zu verhindern, dass Erweiterungen eigene Menü Elemente erstellen.

Sie sollten nicht versuchen, Bits in *pinsertionallowed* festzulegen, die ursprünglich gelöscht wurden. In zukünftigen Versionen von MMC werden möglicherweise Bits verwendet, die derzeit nicht definiert sind. Daher sollten Sie keine Bits ändern, die derzeit nicht definiert sind.

##  <a name="settoolbarbuttoninfo"></a>Csnapinitemimpl:: settoolbarbuttoninfo

Mit dieser Funktion können Sie alle Symbolleisten-Schaltflächen Stile des Snap-in-Objekts ändern, bevor die Symbolleiste erstellt wird.

```
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
in Die ID der festzulegenden Symbolleisten-Schaltfläche.

*fsState*<br/>
in Die Statusflags der Schaltfläche. Kann eine oder mehrere der folgenden sein:

- TBSTATE_CHECKED die Schaltfläche hat den TBSTYLE_CHECKED-Stil und wird gedrückt.

- TBSTATE_ENABLED die Schaltfläche akzeptiert Benutzereingaben. Eine Schaltfläche, die nicht über diesen Zustand verfügt, akzeptiert keine Benutzereingaben und ist ausgegraut.

- TBSTATE_HIDDEN die Schaltfläche ist nicht sichtbar und kann keine Benutzereingaben empfangen.

- TBSTATE_INDETERMINATE die Schaltfläche ist abgeblendet.

- TBSTATE_PRESSED die Schaltfläche wird gedrückt.

- TBSTATE_WRAP ein Zeilenumbruch folgt der Schaltfläche. Die Schaltfläche muss auch über das TBSTATE_ENABLED verfügen.

*fsType*<br/>
in Die Statusflags der Schaltfläche. Kann eine oder mehrere der folgenden sein:

- TBSTYLE_BUTTON erstellt eine Standard-pushschaltfläche.

- TBSTYLE_CHECK erstellt eine Schaltfläche, die jedes Mal zwischen den gedrückten und nicht gedrückten Zuständen wechselt, wenn der Benutzer darauf klickt. Die Schaltfläche hat eine andere Hintergrundfarbe, wenn Sie sich im gedrückten Zustand befindet.

- TBSTYLE_CHECKGROUP erstellt eine Check-Taste, die gedrückt bleibt, bis eine andere Schaltfläche in der Gruppe gedrückt wird.

- TBSTYLE_GROUP erstellt eine Schaltfläche, die gedrückt bleibt, bis eine andere Schaltfläche in der Gruppe gedrückt wird.

- TBSTYLE_SEP erstellt ein Trennzeichen, das eine kleine Lücke zwischen Schaltflächen Gruppen bereitstellt. Eine Schaltfläche mit diesem Stil erhält keine Benutzereingaben.

##  <a name="updatemenustate"></a>Csnapinitemimpl:: updatemenustate

Mit dieser Funktion können Sie ein Menü Element ändern, bevor es in das Kontextmenü des Snap-in-Objekts eingefügt wird.

```
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
in Die ID des festzulegenden Menü Elements.

*pBuf*<br/>
in Ein Zeiger auf die Zeichenfolge für das zu Aktualisier Ende Menü Element.

*flags*<br/>
in Gibt die neuen Statusflags an. Dabei kann es sich um eine Kombination der folgenden Flags handeln:

- MF_POPUP gibt an, dass es sich um ein Untermenü im Kontextmenü handelt. Menü Elemente, Einfügepunkte und weitere Untermenüs können zu diesem Untermenü `lCommandID` `IInsertionPointID`hinzugefügt werden.

- MF_BITMAP und MF_OWNERDRAW diese Flags sind nicht zulässig und führen zu einem Rückgabewert von E_INVALIDARG.

- MF_SEPARATOR zeichnet eine horizontale Trennlinie. Nur `IContextMenuProvider` mit MF_SEPARATOR Set können Menü Elemente hinzugefügt werden.

- MF_CHECKED platziert ein Häkchen neben dem Menü Element.

- MF_DISABLED deaktiviert das Menü Element, sodass es nicht ausgewählt werden kann, aber das Flag ist nicht grau.

- MF_ENABLED aktiviert das Menü Element, sodass es ausgewählt werden kann, sodass es aus seinem ausgefallenen Zustand wieder hergestellt werden kann.

- MF_GRAYED deaktiviert das Menü Element, sodass es nicht ausgewählt werden kann.

- MF_MENUBARBREAK funktioniert genauso wie das MF_MENUBREAK-Flag für eine Menüleiste. Für ein Dropdown Menü, ein Untermenü oder ein Kontextmenü wird die neue Spalte durch eine vertikale Linie von der alten Spalte getrennt.

- MF_MENUBREAK platziert das Element in einer neuen Zeile (für eine Menüleiste) oder in einer neuen Spalte (für ein Dropdown Menü, ein Untermenü oder ein Kontextmenü), ohne Spalten zu trennen.

- MF_UNCHECKED platziert kein Häkchen neben dem Element (Standard).

Die folgenden Gruppen von Flags können nicht gleichzeitig verwendet werden:

- MF_DISABLED, MF_ENABLED und MF_GRAYED.

- MF_MENUBARBREAK und MF_MENUBREAK.

- MF_CHECKED und MF_UNCHECKED.

##  <a name="updatetoolbarbutton"></a>Csnapinitemimpl:: updatetoolbarbutton

Mit dieser Funktion können Sie eine Symbolleisten-Schaltfläche des Snap-in-Objekts ändern, bevor Sie angezeigt wird.

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Gibt die Schaltflächen-ID der zu aktualisierenden Symbolleisten-Schaltfläche an

*fsState*<br/>
Gibt einen Symbolleisten-Schaltflächen Zustand an. Wenn dieser Status festgelegt werden soll, geben Sie "true" zurück. Dabei kann es sich um eine Kombination der folgenden Flags handeln:

- Aktiviert die Schaltfläche akzeptiert Benutzereingaben. Eine Schaltfläche, die nicht über diesen Zustand verfügt, akzeptiert keine Benutzereingaben und ist ausgegraut.

- Aktiviert: die Schaltfläche verfügt über den aktivierten Stil und wird gedrückt.

- Ausgeblendet: die Schaltfläche ist nicht sichtbar und kann keine Benutzereingaben empfangen.

- Unbestimmt: die Schaltfläche ist abgeblendet.

- ButtonPressed: die Schaltfläche wird gedrückt.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
