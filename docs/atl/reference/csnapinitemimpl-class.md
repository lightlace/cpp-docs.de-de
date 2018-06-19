---
title: CSnapInItemImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 759917497f06f80cde97f4e1bba9f3711add94a8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366457"
---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl-Klasse
Diese Klasse stellt Methoden zum Implementieren einer Snap-in-Knotenobjekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, BOOL bIsExtension = FALSE>  
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `CSnapInItemImpl`.  
  
 *bIsExtension*  
 **"True"** ist das Objekt ein Snap-In-Erweiterung; andernfalls **"false"**.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|Ein Kontextmenü hinzugefügt Menüelemente.|  
|[CSnapInItemImpl::Command](#command)|Wird von der Konsole aufgerufen, wenn ein benutzerdefiniertes Menüelement ausgewählt ist.|  
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Eigenschaftenblatt der Snap-in-hinzugefügt Seiten.|  
|[CSnapInItemImpl::FillData](#filldata)|Kopiert die Informationen für das Snap-in-Objekt in einen angegebenen Stream.|  
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Ruft die **RESULTDATAITEM** Struktur das Snap-in.|  
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Bestimmt den Typ der Sicht, die vom Ergebnisbereich verwendet.|  
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Ruft die **SCOPEDATAITEM** Struktur das Snap-in.|  
|[CSnapInItemImpl::Notify](#notify)|Wird aufgerufen, von der Konsole, um das Snap-in der Aktionen, die vom Benutzer zu benachrichtigen.|  
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Wird aufgerufen, um festzustellen, ob der Snap-In-Knoten Eigenschaftenseiten unterstützt.|  
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Ändert die Menü Einfügen-Flags für eine Objekt-Snap-in.|  
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Legt die Informationen des angegebenen Symbolleisten-Schaltfläche fest.|  
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Aktualisiert den Zustand eines Menüelements Kontext.|  
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Aktualisiert den Zustand der angegebenen Symbolleisten-Schaltfläche.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Der Name des Objekts-Snap-in.|  
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Die Windows **RESULTDATAITEM** Struktur verwendet werden, indem die `CSnapInItemImpl` Objekt.|  
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Die Windows **SCOPEDATAITEM** Struktur verwendet werden, indem die `CSnapInItemImpl` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CSnapInItemImpl` Stellt eine grundlegende Implementierung einer-Snap-in-Node-Objekts, z. B. Hinzufügen von Menüelementen und Symbolleisten und Befehle für den Knoten-Snap-in an die entsprechenden Handler-Funktion weiterleiten. Diese Features werden mit mehrere Schnittstellen implementiert, und ordnen Sie Typen. Die standardmäßige Implementierung behandelt Benachrichtigungen an das Knotenobjekt durch Ermitteln der richtigen Instanz der abgeleiteten Klasse, und klicken Sie dann die Nachricht an die richtige Instanz weitergeleitet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsnap.h  
  
##  <a name="addmenuitems"></a>  CSnapInItemImpl::AddMenuItems  
 Diese Methode implementiert die Win32-Funktion [IExtendContextMenu::AddMenuItems](http://msdn.microsoft.com/library/aa814841).  
  
```
AddMenuItems(  
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Parameter  
 *piCallback*  
 [in] Zeiger auf die **IContextMenuCallback** können, die Elemente im Kontextmenü den Befehl hinzufügen.  
  
 `pInsertionAllowed`  
 [in, out] Bezeichnet die Microsoft Management Console MMC benutzerdefinierte Menüelement einfügepunkte, die verwendet werden können. Dies kann eine Kombination der folgenden Flags sein:  
  
- **CCM_INSERTIONALLOWED_TOP** Elemente am Anfang eines Kontextmenüs eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_NEW** Elemente im Untermenü "neu erstellen" eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_TASK** Elemente im Untermenü Aufgabe eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_VIEW** Elemente im Menü Ansicht Symbolleiste oder im Untermenü anzeigen des Kontextmenüs Ergebnis Bereich eingefügt werden können.  
  
 `type`  
 [in] Gibt den Typ des Objekts. Es kann einen der folgenden Werte aufweisen:  
  
- **CCT_SCOPE** -Datenobjekt für den Bereich im Bereich-Kontext.  
  
- **CCT_RESULT** -Datenobjekt für den Bereich der Ergebniskontext.  
  
- **CCT_SNAPIN_MANAGER** -Datenobjekt für den Kontext-Manager-Snap-in.  
  
- **CCT_UNINITIALIZED** Datenobjekt hat einen ungültigen Typ.  
  
##  <a name="command"></a>  CSnapInItemImpl::Command  
 Diese Methode implementiert die Win32-Funktion [IExtendContextMenu::Command](http://msdn.microsoft.com/library/aa814842).  
  
```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Parameter  
 *lCommandID*  
 [in] Gibt die Befehls-ID des Menüelements.  
  
 `type`  
 [in] Gibt den Typ des Objekts. Es kann einen der folgenden Werte aufweisen:  
  
- **CCT_SCOPE** -Datenobjekt für den Bereich im Bereich-Kontext.  
  
- **CCT_RESULT** -Datenobjekt für den Bereich der Ergebniskontext.  
  
- **CCT_SNAPIN_MANAGER** -Datenobjekt für den Kontext-Manager-Snap-in.  
  
- **CCT_UNINITIALIZED** Datenobjekt hat einen ungültigen Typ.  
  
##  <a name="createpropertypages"></a>  CSnapInItemImpl::CreatePropertyPages  
 Diese Methode implementiert die Win32-Funktion [IExtendPropertySheet::CreatePropertyPages](http://msdn.microsoft.com/library/aa814846).  
  
```
CreatePropertyPages(  
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Parameter  
 *lpProvider*  
 [in] Zeiger auf die **IPropertySheetCallback** Schnittstelle.  
  
 *Handle*  
 [in] Gibt das Handle verwendet zum Weiterleiten der **MMCN_PROPERTY_CHANGE** Benachrichtigung, um die entsprechenden Daten-Klasse.  
  
 *pUnk*  
 [in] Zeiger auf die **IExtendPropertySheet** Schnittstelle für das Objekt, das Kontextinformationen über den Knoten enthält.  
  
 `type`  
 [in] Gibt den Typ des Objekts. Es kann einen der folgenden Werte aufweisen:  
  
- **CCT_SCOPE** -Datenobjekt für den Bereich im Bereich-Kontext.  
  
- **CCT_RESULT** -Datenobjekt für den Bereich der Ergebniskontext.  
  
- **CCT_SNAPIN_MANAGER** -Datenobjekt für den Kontext-Manager-Snap-in.  
  
- **CCT_UNINITIALIZED** Datenobjekt hat einen ungültigen Typ.  
  
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
 `cf`  
 [in] Das Format (Text, rich-Text oder rich-Text mit OLE-Elemente) aus der Zwischenablage.  
  
 `pStream`  
 [in] Ein Zeiger auf den Stream, der die Daten des Objekts enthält.  
  
### <a name="remarks"></a>Hinweise  
 Um diese Funktion ordnungsgemäß zu implementieren, kopieren Sie die richtige Informationen in den Datenstrom ( `pStream`), je nachdem, auf das Format der Zwischenablage erkennbar `cf`.  
  
##  <a name="getresultviewtype"></a>  CSnapInItemImpl::GetResultViewType  
 Mit dieser Funktion wird zum Abrufen von der Art der Ansicht für den Ergebnisbereich des Objekts-Snap-in.  
  
```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```  
  
### <a name="parameters"></a>Parameter  
 *ppViewType*  
 [out] Zeiger auf die Adresse des sichttyps zurückgegeben.  
  
 *pViewOptions*  
 [out] Zeiger auf die **MMC_VIEW_OPTIONS** -Enumeration, die die Konsole mit den Optionen, die gemäß der besitzenden-Snap-in bietet. Dieser Wert kann eine der folgenden sein:  
  
- **MMC_VIEW_OPTIONS_NOLISTVIEWS** = 0 x 00000001 weist der Verwaltungskonsole können Sie stellen sicher, dass vorlegen standard Ansicht die Optionen in der **Ansicht** Menü. Ermöglicht das Snap-in eine eigene benutzerdefinierten Ansichten nur im Ansichtsbereich mit Ergebnis angezeigt. Dies ist die einzige Optionsflag "zu diesem Zeitpunkt definiert.  
  
- **MMC_VIEW_OPTIONS_NONE** = 0 ermöglicht die Standardoptionen für die Sicht.  
  
##  <a name="getscopepaneinfo"></a>  CSnapInItemImpl::GetScopePaneInfo  
 Mit dieser Funktion wird zum Abrufen der **SCOPEDATAITEM** Struktur das Snap-in.  
  
```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pScopeDataItem*  
 [out] Ein Zeiger auf die **SCOPEDATAITEM** Struktur der `CSnapInItemImpl` Objekt.  
  
##  <a name="getresultpaneinfo"></a>  CSnapInItemImpl::GetResultPaneInfo  
 Mit dieser Funktion wird zum Abrufen der **RESULTDATAITEM** Struktur das Snap-in.  
  
```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pResultDataItem*  
 [out] Ein Zeiger auf die **RESULTDATAITEM** Struktur der `CSnapInItemImpl` Objekt.  
  
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
 Die [RESULTDATAITEM](http://msdn.microsoft.com/library/aa815165) Objektstruktur-Snap-in-Daten.  
  
```
RESULTDATAITEM m_resultDataItem;
```  
  
##  <a name="notify"></a>  CSnapInItemImpl::Notify  
 Wird aufgerufen, wenn das Snap-in-Objekt auf vom Benutzer ausgeführt wird.  
  
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
 `event`  
 [in] Identifiziert eine Aktion ausgeführt wird, die ein Benutzer an. Folgenden Benachrichtigungen sind möglich:  
  
- **MMCN_ACTIVATE** gesendet, wenn ein Fenster ist, aktiviert und deaktiviert wird.  
  
- **MMCN_ADD_IMAGES** gesendet, um den Ergebnisbereich Bilder hinzuzufügen.  
  
- **MMCN_BTN_CLICK** gesendet, wenn der Benutzer auf eine der Schaltflächen der Symbolleiste klickt.  
  
- **MMCN_CLICK** gesendet, wenn ein Benutzer eine Maustaste drückt, die auf eine des Listenansichtselements.  
  
- **MMCN_DBLCLICK** gesendet, wenn ein Benutzer eine Maustaste auf eine des Listenansichtselements doppelklickt.  
  
- **MMCN_DELETE** gesendet, um das Snap-in zu informieren, die das Objekt sollte gelöscht.  
  
- **MMCN_EXPAND** gesendet, wenn Sie ein Ordner erweitert oder verkürzt werden muss.  
  
- **MMCN_MINIMIZED** gesendet, wenn ein Fenster wird minimiert oder maximiert ist.  
  
- **MMCN_PROPERTY_CHANGE** gesendet, um ein Snap-In-Objekt zu benachrichtigen, dass das Snap-in Objekt-Ansicht zu ändern.  
  
- **MMCN_REMOVE_CHILDREN** gesendet, wenn das Snap-in die gesamte Unterstruktur löschen müssen sie die unter dem angegebenen Knoten hinzugefügt wurde.  
  
- **MMCN_RENAME** gesendet erstmalig zum Abfragen von umbenennen und das zweite Mal umbenennen möchten.  
  
- **MMCN_SELECT** gesendet, wenn ein Element im Ansichtsbereich mit Bereich oder das Ergebnis ausgewählt wird.  
  
- **MMCN_SHOW** gesendet, wenn ein Bereichselement ausgewählt oder zum ersten Mal deaktiviert ist.  
  
- **MMCN_VIEW_CHANGE** gesendet, wenn das Snap-in alle Sichten aktualisiert werden kann, wenn eine Änderung auftritt.  
  
 `arg`  
 [in] Hängt von der Benachrichtigungstyp.  
  
 `param`  
 [in] Hängt von der Benachrichtigungstyp.  
  
 *pComponentData*  
 [out] Ein Zeiger auf das Objekt, durch **IComponentData**. Dieser Parameter ist **NULL** , wenn die Benachrichtigung von nicht weitergeleitet wird **IComponentData::Notify**.  
  
 *pComponent*  
 [out] Ein Zeiger auf das Objekt, das implementiert **IComponent**. Dieser Parameter ist **NULL** , wenn die Benachrichtigung von nicht weitergeleitet wird **IComponent::Notify**.  
  
 `type`  
 [in] Gibt den Typ des Objekts. Es kann einen der folgenden Werte aufweisen:  
  
- **CCT_SCOPE** -Datenobjekt für den Bereich im Bereich-Kontext.  
  
- **CCT_RESULT** -Datenobjekt für den Bereich der Ergebniskontext.  
  
- **CCT_SNAPIN_MANAGER** -Datenobjekt für den Kontext-Manager-Snap-in.  
  
- **CCT_UNINITIALIZED** Datenobjekt hat einen ungültigen Typ.  
  
##  <a name="querypagesfor"></a>  CSnapInItemImpl::QueryPagesFor  
 Wird aufgerufen, um festzustellen, ob der Snap-In-Knoten Eigenschaftenseiten unterstützt.  
  
```
QueryPagesFor(DATA_OBJECT_TYPES type);
```  
  
##  <a name="setmenuinsertionflags"></a>  CSnapInItemImpl::SetMenuInsertionFlags  
 Mit dieser Funktion können Sie im Menü Einfügen, angegebenen Flags durch Ändern `pInsertionAllowed`, für das Snap-in-Objekt.  
  
```
void SetMenuInsertionFlags(  
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```  
  
### <a name="parameters"></a>Parameter  
 *bBeforeInsertion*  
 [in] Wert ungleich NULL, wenn die Funktion aufgerufen werden soll, bevor das Kontextmenü Elemente hinzugefügt werden; andernfalls 0.  
  
 `pInsertionAllowed`  
 [in, out] Bezeichnet die Microsoft Management Console MMC benutzerdefinierte Menüelement einfügepunkte, die verwendet werden können. Dies kann eine Kombination der folgenden Flags sein:  
  
- **CCM_INSERTIONALLOWED_TOP** Elemente am Anfang eines Kontextmenüs eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_NEW** Elemente im Untermenü "neu erstellen" eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_TASK** Elemente im Untermenü Aufgabe eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_VIEW** Elemente im Menü Ansicht Symbolleiste oder im Untermenü anzeigen des Kontextmenüs Ergebnis Bereich eingefügt werden können.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen primären-Snap-in entwickeln, können Sie eines der einfügen-Flags als Möglichkeit einschränken, die Art der Menüelemente, die eine Erweiterung von Drittanbietern hinzufügen können zurücksetzen. Z. B. der primäre-Snap-in kann Deaktivieren der **CCM_INSERTIONALLOWED_NEW** Flag, um zu verhindern, dass Erweiterungen ihre eigenen erstellen neue Menüelemente hinzufügen.  
  
 Sie sollten nicht versuchen, legen Sie die Bits in `pInsertionAllowed` , wurden ursprünglich gelöscht. Zukünftige Versionen von MMC können Bits, die derzeit nicht definiert wurden, sodass Sie Bits nicht ändern sollten, die derzeit nicht definiert werden.  
  
##  <a name="settoolbarbuttoninfo"></a>  CSnapInItemImpl::SetToolbarButtonInfo  
 Mit dieser Funktion können Sie alle Formatvorlagen für Symbolleistenschaltflächen, des Objekts-Snap-in ändern, bevor die Symbolleiste erstellt wird.  
  
```
void SetToolbarButtonInfo(  
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Die ID der Symbolleisten-Schaltfläche festgelegt werden.  
  
 `fsState`  
 [in] Die Statusflags der Schaltfläche. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
- `TBSTATE_CHECKED` Die Schaltfläche "" hat die **TBSTYLE_CHECKED** formatieren und gedrückt wird.  
  
- `TBSTATE_ENABLED` Die Schaltfläche mit der akzeptiert Benutzereingaben. Eine Schaltfläche, die diesen Status nicht akzeptiert keine Benutzereingaben und abgeblendet.  
  
- `TBSTATE_HIDDEN` Die Schaltfläche ist nicht sichtbar und kann keine Benutzereingabe empfangen.  
  
- `TBSTATE_INDETERMINATE` Die Schaltfläche ist abgeblendet.  
  
- `TBSTATE_PRESSED` Die Schaltfläche wird gedrückt wird.  
  
- `TBSTATE_WRAP` Ein Zeilenumbruch folgt auf die Schaltfläche "". Die Schaltfläche "" müssen die `TBSTATE_ENABLED`.  
  
 *fsType*  
 [in] Die Statusflags der Schaltfläche. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
- `TBSTYLE_BUTTON` Erstellt eine Standardschaltflächen.  
  
- `TBSTYLE_CHECK` Erstellt eine Schaltfläche, die zwischen der gedrückten und nicht gedrückt Zustand jedes Mal wechselt der Benutzer darauf klickt. Die Schaltfläche "" hat eine andere Hintergrundfarbe, wenn es in den Zustand "gedrückt" ist.  
  
- `TBSTYLE_CHECKGROUP` Erstellt eine Kontrollkästchen-Schaltfläche, die gedrückt bleibt, bis eine andere Schaltfläche in der Gruppe aufgerufen werden.  
  
- `TBSTYLE_GROUP` Erstellt eine Schaltfläche, die gedrückt bleibt, bis eine andere Schaltfläche in der Gruppe aufgerufen werden.  
  
- `TBSTYLE_SEP` Erstellt ein Trennzeichen, die eine kleine zeitliche Lücke zwischen Schaltflächengruppen bereitstellen. Eine Schaltfläche mit diesem Format empfängt keine Benutzereingaben.  
  
##  <a name="updatemenustate"></a>  CSnapInItemImpl::UpdateMenuState  
 Rufen Sie diese Funktion, um ein Menüelement zu ändern, bevor es in das Kontextmenü des Snap-in-Objekts eingefügt wird.  
  
```
void UpdateMenuState(  
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 [in] Die ID des Menüelements festgelegt werden.  
  
 `pBuf`  
 [in] Ein Zeiger auf die Zeichenfolge für das Menüelement aktualisiert werden.  
  
 `flags`  
 [in] Gibt den neuen Statusflags. Dies kann eine Kombination der folgenden Flags sein:  
  
- **MF_POPUP** gibt an, dass dies ein Untermenü innerhalb im Kontextmenü den Befehl. Menüelemente, einfügepunkte und weitere Untermenüs zur hinzugefügt werden, das Untermenü mithilfe seiner **lCommandID** als ihre **IInsertionPointID**.  
  
- **MF_BITMAP** und `MF_OWNERDRAW` diese Flags sind nicht zulässig und führt zu einem Rückgabewert von `E_INVALIDARG`.  
  
- **MF_SEPARATOR** zeichnet eine horizontale Trennlinie. Nur **IContextMenuProvider** ist zulässig, Hinzufügen von Menüelementen mit **MF_SEPARATOR** festgelegt.  
  
- **MF_CHECKED** setzt ein Häkchen neben dem Menüelement.  
  
- **MF_DISABLED** das Menüelement deaktiviert, damit nicht ausgewählt werden, aber das Flag ist nicht grau.  
  
- `MF_ENABLED` Das Menüelement aktiviert, es ausgewählt werden kann vom grau Zustand wiederhergestellt.  
  
- **MF_GRAYED** deaktiviert das Menüelement, das es abblendet, damit es nicht ausgewählt werden kann.  
  
- **MF_MENUBARBREAK** funktioniert genauso wie die **MF_MENUBREAK** Flag einer Menüleiste. Für eine Dropdown-Menü, Untermenü oder im Kontextmenü ist die neue Spalte durch eine vertikale Linie von der alten Spalte getrennt.  
  
- **MF_MENUBREAK** platziert das Element in einer neuen Zeile (für eine Menüleiste) oder in einer neuen Spalte (für eine Dropdown-Menü, Untermenü oder Kontextmenü) ohne Spalten aufteilen.  
  
- **MF_UNCHECKED** kein Häkchen neben dem Element (Standard).  
  
 Die folgenden Gruppen von Flags können nicht zusammen verwendet werden:  
  
- **MF_DISABLED**, `MF_ENABLED`, und **MF_GRAYED**.  
  
- **MF_MENUBARBREAK** und **MF_MENUBREAK**.  
  
- **MF_CHECKED** und **MF_UNCHECKED**.  
  
##  <a name="updatetoolbarbutton"></a>  CSnapInItemImpl::UpdateToolbarButton  
 Mit dieser Funktion können Sie eine Symbolleisten-Schaltfläche des Objekts-Snap-in ändern, bevor er angezeigt wird.  
  
```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 Gibt die Schaltfläche-ID der Symbolleisten-Schaltfläche aktualisiert werden.  
  
 `fsState`  
 Gibt den Status der Symbolleisten-Schaltfläche. Wenn dieser Status ist festgelegt werden, zurück **"true"**. Dies kann eine Kombination der folgenden Flags sein:  
  
- **AKTIVIERT** die Schaltfläche mit der Benutzereingaben akzeptiert. Eine Schaltfläche, die diesen Status nicht akzeptiert keine Benutzereingaben und abgeblendet.  
  
- **ÜBERPRÜFT** die Schaltfläche "" wurde der **überprüft** formatieren und gedrückt wird.  
  
- **HIDDEN** die Schaltfläche ist nicht sichtbar und kann keine Benutzereingabe empfangen.  
  
- **Unbestimmt** die Schaltfläche ist abgeblendet.  
  
- **BUTTONPRESSED** die Schaltfläche geklickt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
