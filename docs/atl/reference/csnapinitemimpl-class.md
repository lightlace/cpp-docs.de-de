---
title: CSnapInItemImpl-Klasse
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
ms.openlocfilehash: 27f3e8a17a9538a72a6592177a88a9b415b1a27c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277707"
---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl-Klasse

Diese Klasse stellt Methoden zum Implementieren eines-Snap-in-Node-Objekts.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `CSnapInItemImpl`.

*bIsExtension*<br/>
True, wenn das Objekt eine-Snap-in-Erweiterung. andernfalls "false".

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|Eine Kontextmenü hinzugefügt Menüelemente.|
|[CSnapInItemImpl::Command](#command)|Wird von der Konsole aufgerufen, wenn ein benutzerdefiniertes Menüelement ausgewählt ist.|
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Das Eigenschaftenblatt des Snap-Ins werden Seiten hinzugefügt.|
|[CSnapInItemImpl::FillData](#filldata)|Kopiert die Informationen für das Snap-In-Objekt in einen angegebenen Stream.|
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Ruft die `RESULTDATAITEM` Struktur das Snap-in.|
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Bestimmt den Typ der Ansicht, die von den Ergebnisbereich verwendet.|
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Ruft die `SCOPEDATAITEM` Struktur das Snap-in.|
|[CSnapInItemImpl::Notify](#notify)|Wird aufgerufen, von der Konsole, um das Snap-in von Aktionen, die vom Benutzer zu benachrichtigen.|
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Wird aufgerufen, um festzustellen, ob der Knoten-Snap-in-Eigenschaftenseiten unterstützt.|
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Ändert die Menü-Einfügen-Flags für ein Objekt-Snap-in.|
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Legt fest, die Informationen der angegebenen Symbolleisten-Schaltfläche.|
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Aktualisiert den Zustand eines Menüelements Kontext.|
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Aktualisiert den Zustand der angegebenen Symbolleisten-Schaltfläche.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Der Name des Objekts-Snap-in.|
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Die Windows `RESULTDATAITEM` Struktur, die verwendet werden, indem die `CSnapInItemImpl` Objekt.|
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Die Windows `SCOPEDATAITEM` Struktur, die verwendet werden, indem die `CSnapInItemImpl` Objekt.|

## <a name="remarks"></a>Hinweise

`CSnapInItemImpl` Stellt eine grundlegende Implementierung für ein Snap-in-Knotenobjekt, z. B. hinzugefügt werden, Menüelemente und Symbolleisten und Befehle für den Knoten-Snap-in für die entsprechenden Handler-Funktion weiterleiten. Diese Funktionen werden mithilfe von mehrere Schnittstellen implementiert und Zuordnungstypen. Die Standardimplementierung verarbeitet Benachrichtigungen, die von der richtigen Instanz der abgeleiteten Klasse bestimmen und das anschließende Weiterleiten der Nachricht an die richtige Instanz an das Node-Objekt gesendet werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlsnap.h

##  <a name="addmenuitems"></a>  CSnapInItemImpl::AddMenuItems

Diese Methode implementiert die Win32-Funktion [IExtendContextMenu::AddMenuItems](/windows/desktop/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems).

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parameter

*piCallback*<br/>
[in] Zeiger auf die `IContextMenuCallback` können, die im Kontextmenü Elemente hinzufügen.

*pInsertionAllowed*<br/>
[in, out] Bezeichnet die Microsoft Management Console MMC benutzerdefinierte Menüelemente Einfügemarken, die verwendet werden können. Dies kann eine Kombination der folgenden Flags sein:

- CCM_INSERTIONALLOWED_TOP Elemente können am oberen Rand eines Kontextmenüs eingefügt werden.

- CCM_INSERTIONALLOWED_NEW Elemente können im Untermenü "neu erstellen" eingefügt werden.

- CCM_INSERTIONALLOWED_TASK Elemente können im Untermenü Aufgabe eingefügt werden.

- CCM_INSERTIONALLOWED_VIEW Elemente können im Menü Ansicht Symbolleiste oder im Untermenü anzeigen des Kontextmenüs Ergebnis Bereich eingefügt werden.

*Typ*<br/>
[in] Gibt den Typ des Objekts. Es kann einen der folgenden Werte aufweisen:

- CCT_SCOPE Datenobjekt, das für den Bereich im Bereich-Kontext.

- CCT_RESULT Datenobjekt, das für den Bereich der Ergebniskontext.

- CCT_SNAPIN_MANAGER Datenobjekt, das für den Kontext-Snap-in-Managers.

- CCT_UNINITIALIZED Datenobjekt weist einen ungültigen Typ.

##  <a name="command"></a>  CSnapInItemImpl::Command

Diese Methode implementiert die Win32-Funktion [IExtendContextMenu::Command](/windows/desktop/api/mmc/nf-mmc-iextendcontextmenu-command).

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parameter

*lCommandID*<br/>
[in] Gibt den Befehlsbezeichner des Menüelements.

*Typ*<br/>
[in] Gibt den Typ des Objekts. Es kann einen der folgenden Werte aufweisen:

- CCT_SCOPE Datenobjekt, das für den Bereich im Bereich-Kontext.

- CCT_RESULT Datenobjekt, das für den Bereich der Ergebniskontext.

- CCT_SNAPIN_MANAGER Datenobjekt, das für den Kontext-Snap-in-Managers.

- CCT_UNINITIALIZED Datenobjekt weist einen ungültigen Typ.

##  <a name="createpropertypages"></a>  CSnapInItemImpl::CreatePropertyPages

Diese Methode implementiert die Win32-Funktion [IExtendPropertySheet::CreatePropertyPages](/windows/desktop/api/mmc/nn-mmc-iextendpropertysheet2).

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parameter

*lpProvider*<br/>
[in] Zeiger auf die `IPropertySheetCallback` Schnittstelle.

*handle*<br/>
[in] Gibt das Handle, das die benachrichtigungsmeldung MMCN_PROPERTY_CHANGE an die entsprechenden Datenklasse weitergeleitet.

*pUnk*<br/>
[in] Zeiger auf die `IExtendPropertySheet` Schnittstelle für das Objekt, das Kontextinformationen über den Knoten enthält.

*Typ*<br/>
[in] Gibt den Typ des Objekts. Es kann einen der folgenden Werte aufweisen:

- CCT_SCOPE Datenobjekt, das für den Bereich im Bereich-Kontext.

- CCT_RESULT Datenobjekt, das für den Bereich der Ergebniskontext.

- CCT_SNAPIN_MANAGER Datenobjekt, das für den Kontext-Snap-in-Managers.

- CCT_UNINITIALIZED Datenobjekt weist einen ungültigen Typ.

##  <a name="csnapinitemimpl"></a>  CSnapInItemImpl::CSnapInItemImpl

Erstellt ein `CSnapInItemImpl`-Objekt.

```
CSnapInItemImpl();
```

##  <a name="filldata"></a>  CSnapInItemImpl::FillData

Diese Funktion wird aufgerufen, um Informationen über das Element abzurufen.

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>Parameter

*cf*<br/>
[in] Das Format (Text, rich-Text oder rich-Text mit OLE-Elemente) aus der Zwischenablage.

*pStream*<br/>
[in] Ein Zeiger auf den Stream, der die Daten des Objekts enthält.

### <a name="remarks"></a>Hinweise

Um diese Funktion ordnungsgemäß zu implementieren, kopieren Sie die richtige Informationen in den Datenstrom (*pStream*), je nachdem, auf das Format der Zwischenablage erkennbar *Cf*.

##  <a name="getresultviewtype"></a>  CSnapInItemImpl::GetResultViewType

Rufen Sie diese Funktion, um den Typ der Ansicht für den Ergebnisbereich des Objekts-Snap-in abzurufen.

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>Parameter

*ppViewType*<br/>
[out] Zeiger auf die Adresse des sichttyps zurückgegeben.

*pViewOptions*<br/>
[out] Zeiger auf die MMC_VIEW_OPTIONS-Enumeration, die Konsole mit den Optionen, die gemäß der besitzenden-Snap-in bietet. Dieser Wert kann eine der folgenden sein:

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0 x 00000001 weisen Sie die Konsole, davon absehen, von der Vorlage der Standardliste Ansicht Auswahl in der **Ansicht** Menü. Das Snap-in zum Anzeigen von eigenen benutzerdefinierten Ansichten nur im Ergebnisbereich anzeigen können. Dies ist das einzige Optionsflag zu diesem Zeitpunkt definiert.

- MMC_VIEW_OPTIONS_NONE = 0 ermöglicht die Standardoptionen für die Ansicht.

##  <a name="getscopepaneinfo"></a>  CSnapInItemImpl::GetScopePaneInfo

Mit dieser Funktion wird zum Abrufen der `SCOPEDATAITEM` Struktur das Snap-in.

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>Parameter

*pScopeDataItem*<br/>
[out] Ein Zeiger auf die `SCOPEDATAITEM` Struktur der `CSnapInItemImpl` Objekt.

##  <a name="getresultpaneinfo"></a>  CSnapInItemImpl::GetResultPaneInfo

Mit dieser Funktion wird zum Abrufen der `RESULTDATAITEM` Struktur das Snap-in.

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>Parameter

*pResultDataItem*<br/>
[out] Ein Zeiger auf die `RESULTDATAITEM` Struktur der `CSnapInItemImpl` Objekt.

##  <a name="m_bstrdisplayname"></a>  CSnapInItemImpl::m_bstrDisplayName

Enthält die Zeichenfolge, die für das Knotenelement angezeigt.

```
CComBSTR m_bstrDisplayName;
```

##  <a name="m_scopedataitem"></a>  CSnapInItemImpl::m_scopeDataItem

Die `SCOPEDATAITEM` Objektstruktur-Snap-in-Daten.

```
SCOPEDATAITEM m_scopeDataItem;
```

##  <a name="m_resultdataitem"></a>  CSnapInItemImpl::m_resultDataItem

Die [RESULTDATAITEM](/windows/desktop/api/mmc/ns-mmc-resultdataitem) Objektstruktur-Snap-in-Daten.

```
RESULTDATAITEM m_resultDataItem;
```

##  <a name="notify"></a>  CSnapInItemImpl::Notify

Aufgerufen, wenn das Snap-In-Objekt auf der Benutzer ausgeführt wird.

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
[in] Gibt eine Aktion, die von einem Benutzer an. Die folgenden Benachrichtigungen sind möglich:

- MMCN_ACTIVATE gesendet, wenn ein Fenster wird aktiviert und deaktiviert.

- MMCN_ADD_IMAGES gesendet, um den Ergebnisbereich Bilder hinzuzufügen.

- MMCN_BTN_CLICK gesendet, wenn der Benutzer eine Symbolleisten-Schaltflächen klickt.

- MMCN_CLICK wird gesendet, wenn ein Benutzer eine Maustaste drückt, die auf ein Listenansichtselement.

- MMCN_DBLCLICK gesendet, wenn ein Benutzer auf eine Maustaste auf ein Listenansichtselement doppelklickt.

- MMCN_DELETE gesendet wird, um das Snap-in zu informieren, die das Objekt sollte gelöscht.

- MMCN_EXPAND wird gesendet, wenn Sie ein Ordner erweitert oder verkürzt werden muss.

- MMCN_MINIMIZED gesendet, wenn ein Fenster wird minimiert oder maximiert.

- MMCN_PROPERTY_CHANGE gesendet, um eine Objekt-Snap-in zu benachrichtigen die Ansicht für das Snap-In-Objekt zu ändern.

- MMCN_REMOVE_CHILDREN gesendet, wenn das Snap-in die gesamte Teilstruktur löschen muss, ist es unter dem angegebenen Knoten hinzugefügt.

- MMCN_RENAME werden zum ersten Mal zur Umbenennung einer Abfrage und beim zweiten Mal gesendet, um die Umbenennung ist.

- MMCN_SELECT wird gesendet, wenn ein Element im Ansichtsbereich Bereich oder das Ergebnis ausgewählt ist.

- MMCN_SHOW wird gesendet, wenn ein Bereich ausgewählt oder zum ersten Mal abgewählt.

- MMCN_VIEW_CHANGE wird gesendet, wenn das Snap-in allen Ansichten aktualisieren, wenn eine Änderung vorgenommen wird.

*arg*<br/>
[in] Hängt von der Benachrichtigungstyp.

*param*<br/>
[in] Hängt von der Benachrichtigungstyp.

*pComponentData*<br/>
[out] Ein Zeiger auf die objektimplementierung `IComponentData`. Dieser Parameter ist NULL, wenn die Benachrichtigung nicht über weitergeleitet wird `IComponentData::Notify`.

*pComponent*<br/>
[out] Ein Zeiger auf das Objekt, das implementiert `IComponent`. Dieser Parameter ist NULL, wenn die Benachrichtigung nicht über weitergeleitet wird `IComponent::Notify`.

*Typ*<br/>
[in] Gibt den Typ des Objekts. Es kann einen der folgenden Werte aufweisen:

- CCT_SCOPE Datenobjekt, das für den Bereich im Bereich-Kontext.

- CCT_RESULT Datenobjekt, das für den Bereich der Ergebniskontext.

- CCT_SNAPIN_MANAGER Datenobjekt, das für den Kontext-Snap-in-Managers.

- CCT_UNINITIALIZED Datenobjekt weist einen ungültigen Typ.

##  <a name="querypagesfor"></a>  CSnapInItemImpl::QueryPagesFor

Wird aufgerufen, um festzustellen, ob der Knoten-Snap-in-Eigenschaftenseiten unterstützt.

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

##  <a name="setmenuinsertionflags"></a>  CSnapInItemImpl::SetMenuInsertionFlags

Mit dieser Funktion können Sie ändern, die im Menü Einfügen Flags, die gemäß *pInsertionAllowed*, für das Snap-In-Objekt.

```
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>Parameter

*bBeforeInsertion*<br/>
[in] Ungleich NULL ist, wenn die Funktion aufgerufen werden soll, bevor Sie das Kontextmenü Elemente hinzugefügt werden; andernfalls 0.

*pInsertionAllowed*<br/>
[in, out] Bezeichnet die Microsoft Management Console MMC benutzerdefinierte Menüelemente Einfügemarken, die verwendet werden können. Dies kann eine Kombination der folgenden Flags sein:

- CCM_INSERTIONALLOWED_TOP Elemente können am oberen Rand eines Kontextmenüs eingefügt werden.

- CCM_INSERTIONALLOWED_NEW Elemente können im Untermenü "neu erstellen" eingefügt werden.

- CCM_INSERTIONALLOWED_TASK Elemente können im Untermenü Aufgabe eingefügt werden.

- CCM_INSERTIONALLOWED_VIEW Elemente können im Menü Ansicht Symbolleiste oder im Untermenü anzeigen des Kontextmenüs Ergebnis Bereich eingefügt werden.

### <a name="remarks"></a>Hinweise

Wenn Sie einen primären-Snap-in entwickeln, können Sie diese Zurücksetzen eines der einfügen-Flags als eine Möglichkeit zum Einschränken der Art der Menüelemente, die eine Erweiterung von Drittanbietern hinzufügen können. Die primäre-Snap-in kann z. B. das CCM_INSERTIONALLOWED_NEW-Flag, um zu verhindern, dass Erweiterungen ihre eigenen erstellen neue Menüelemente hinzufügen löschen.

Sie sollten nicht versuchen, zum Festlegen von Bits im *pInsertionAllowed* , wurden ursprünglich deaktiviert. Zukünftige Versionen von MMC können Bits, die derzeit nicht definiert wurden, sodass Sie Bits, die derzeit nicht definiert sind, nicht ändern sollten.

##  <a name="settoolbarbuttoninfo"></a>  CSnapInItemImpl::SetToolbarButtonInfo

Rufen Sie diese Funktion, um alle Formatvorlagen für Symbolleistenschaltflächen, der das Snap-in-Objekt, vor der Erstellung der Symbolleiste zu ändern.

```
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Die ID des der Symbolleisten-Schaltfläche festgelegt werden.

*fsState*<br/>
[in] Die Zustandsflags der Schaltfläche. Hierbei kann es sich um eine oder mehrere der folgenden sein:

- TBSTATE_CHECKED die Schaltfläche mit den hat des Format TBSTYLE_CHECKED und ist gedrückt wird.

- TBSTATE_ENABLED die Schaltfläche mit den akzeptiert Benutzereingaben. Eine Schaltfläche, die keine von diesem Status akzeptiert keine Benutzereingaben und abgeblendet.

- TBSTATE_HIDDEN die Schaltfläche nicht sichtbar ist, und es keine Benutzereingaben empfangen.

- TBSTATE_INDETERMINATE die Schaltfläche ist abgeblendet.

- TBSTATE_PRESSED die Schaltfläche wird gedrückt wird.

- TBSTATE_WRAP ein Zeilenumbruch folgt auf die Schaltfläche. Die Schaltfläche muss auch die TBSTATE_ENABLED verfügen.

*fsType*<br/>
[in] Die Zustandsflags der Schaltfläche. Hierbei kann es sich um eine oder mehrere der folgenden sein:

- TBSTYLE_BUTTON erstellt eine Standardschaltflächen.

- TBSTYLE_CHECK erstellt eine Schaltfläche, die zwischen den gedrückt- oder nicht gedrückt-Zuständen jedes Mal den Benutzer schaltet darauf klickt. Die Schaltfläche "hat eine andere Hintergrundfarbe aus, wenn es im gedrückten Zustand ist.

- TBSTYLE_CHECKGROUP erstellt, für das eine Kontrollkästchen-Schaltfläche, die bleibt gedrückt, bis in der Gruppe eine andere Schaltfläche gedrückt wird.

- TBSTYLE_GROUP erstellt, für das eine Schaltfläche, die bleibt gedrückt, bis in der Gruppe eine andere Schaltfläche gedrückt wird.

- TBSTYLE_SEP erstellt ein Trennzeichen, die eine kleine zeitliche Lücke zwischen Schaltflächengruppen bereitstellen. Eine Schaltfläche mit diesem Format erhält keine Benutzereingaben.

##  <a name="updatemenustate"></a>  CSnapInItemImpl::UpdateMenuState

Rufen Sie diese Funktion, um ein Menüelement zu ändern, bevor es in das Kontextmenü der Snap-In-Objekt eingefügt wird.

```
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
[in] Die ID des Menüelements festgelegt werden.

*pBuf*<br/>
[in] Ein Zeiger auf die Zeichenfolge für das Menüelement aktualisiert werden.

*flags*<br/>
[in] Gibt die neue Statusflags. Dies kann eine Kombination der folgenden Flags sein:

- MF_POPUP gibt an, dass dies ein Untermenü innerhalb des Kontextmenüs. Menüelemente, Einfügemarken und weiteren Untermenüs können hinzugefügt werden diese Untermenü mithilfe der `lCommandID` als ihre `IInsertionPointID`.

- MF_BITMAP und MF_OWNERDRAW, die diese Flags sind nicht zulässig und führt dazu, dass ein Wert, der E_INVALIDARG zurückgegeben.

- MF_SEPARATOR zeichnet eine horizontale Trennlinie. Nur `IContextMenuProvider` Menüelemente mit MF_SEPARATOR hinzufügen können.

- MF_CHECKED wird ein Häkchen neben dem Menüelement platziert.

- MF_DISABLED deaktiviert das Menüelement, damit es nicht ausgewählt werden kann, aber das Flag wird nicht grau, es.

- MF_ENABLED ermöglicht dem Menüelement, das sie ausgewählt werden kann es vom grau Zustand wiederherstellen, mit.

- MF_GRAYED deaktiviert das Menüelement, das es abblendet, damit es nicht ausgewählt werden kann.

- Identisch mit der MF_MENUBREAK für eine Menüleiste flag MF_MENUBARBREAK-Funktionen. Für eine Dropdown-Menü, Untermenüs oder im Kontextmenü ist die neue Spalte durch eine vertikale Linie von der alten Spalte getrennt.

- MF_MENUBREAK platziert das Element in einer neuen Zeile (für eine Menüleiste) oder in einer neuen Spalte (für eine Dropdown-Menü, Untermenüs oder Kontextmenü), ohne die Trennung von Spalten.

- MF_UNCHECKED ist platzieren kein Häkchen neben dem Element (Standard).

Die folgenden Gruppen von Flags können nicht zusammen verwendet werden:

- MF_DISABLED MF_ENABLED und MF_GRAYED.

- MF_MENUBARBREAK und MF_MENUBREAK.

- MF_CHECKED und MF_UNCHECKED.

##  <a name="updatetoolbarbutton"></a>  CSnapInItemImpl::UpdateToolbarButton

Rufen Sie diese Funktion aus, um eine Symbolleisten-Schaltfläche des-Snap-in-Objekts, zu ändern, bevor er angezeigt wird.

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Gibt an, der Schaltflächen-ID der Symbolleisten-Schaltfläche aktualisiert werden.

*fsState*<br/>
Gibt den Symbolleisten-Schaltfläche-Status an. Wenn dieser Status ist festgelegt werden, TRUE zurück. Dies kann eine Kombination der folgenden Flags sein:

- AKTIVIERT die Schaltfläche mit der Benutzereingaben akzeptiert. Eine Schaltfläche, die keine von diesem Status akzeptiert keine Benutzereingaben und abgeblendet.

- ÜBERPRÜFT die Formatierung aktiviert wurde und gedrückt wird.

- HIDDEN die Schaltfläche nicht sichtbar ist, und es keine Benutzereingaben empfangen.

- UNBESTIMMT ist die Schaltfläche abgeblendet.

- BUTTONPRESSED die Schaltfläche wird gedrückt wird.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
