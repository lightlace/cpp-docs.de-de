---
title: Klasse CSnapInItemImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9148ee71ba03a1a0492d390378c64f988e6e0f39
ms.lasthandoff: 02/24/2017

---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl-Klasse
Diese Klasse stellt Methoden zum Implementieren einer Snap-in-Node-Objekts.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, BOOL bIsExtension = FALSE>  
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `CSnapInItemImpl`.  
  
 *bIsExtension*  
 **True,** Wenn das Objekt ein Snap-In-Erweiterung; andernfalls **FALSE**.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|Ein Kontextmenü hinzugefügt Menüelemente.|  
|[CSnapInItemImpl::Command](#command)|Wird von der Konsole aufgerufen, wenn ein benutzerdefiniertes Menüelement ausgewählt ist.|  
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Seiten hinzugefügt auf den Eigenschaftenseiten des Snap-Ins.|  
|[CSnapInItemImpl::FillData](#filldata)|Kopiert die Informationen für das Snap-In-Objekt in einen angegebenen Stream.|  
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Ruft die **RESULTDATAITEM** Struktur das Snap-in.|  
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Bestimmt den Typ der Ansicht, die von den Ergebnisbereich verwendet.|  
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Ruft die **SCOPEDATAITEM** Struktur das Snap-in.|  
|[CSnapInItemImpl::Notify](#notify)|Wird von der Konsole, um das Snap-in von Aktionen durch den Benutzer zu benachrichtigen.|  
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Wird aufgerufen, um festzustellen, ob der Snap-In-Knoten Eigenschaftenseiten unterstützt.|  
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Ändert die im Menü Einfügen-Flags für ein Objekt-Snap-in.|  
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Die Informationen der angegebenen Symbolleisten-Schaltfläche fest.|  
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Aktualisiert den Status eines Menüelements Kontext.|  
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Aktualisiert den Zustand der angegebenen Symbolleisten-Schaltfläche.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Der Name des Objekts-Snap-in.|  
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Windows **RESULTDATAITEM** Struktur anhand der `CSnapInItemImpl` Objekt.|  
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Windows **SCOPEDATAITEM** Struktur anhand der `CSnapInItemImpl` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CSnapInItemImpl`Stellt eine grundlegende Implementierung einer Snap-in-Node-Objekts, z. B. Menüelemente und Symbolleisten hinzufügen und das Weiterleiten von Befehlen für den Knoten-Snap-in für die entsprechenden Handler-Funktion. Diese Features werden mit mehrere Schnittstellen implementiert und Zuordnen von Typen. Die standardmäßige Implementierung verarbeitet Benachrichtigungen an den Node-Objekts bestimmen die richtige Instanz der abgeleiteten Klasse, und klicken Sie dann die Nachricht an die richtige Instanz weitergeleitet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsnap.h  
  
##  <a name="addmenuitems"></a>CSnapInItemImpl::AddMenuItems  
 Diese Methode implementiert die Win32-Funktion [IExtendContextMenu::AddMenuItems](http://msdn.microsoft.com/library/aa814841).  
  
```
AddMenuItems(  
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Parameter  
 *piCallback*  
 [in] Zeiger auf die **IContextMenuCallback** können, die Elemente im Kontextmenü hinzufügen.  
  
 `pInsertionAllowed`  
 [in, out] Bezeichnet die Microsoft Management Console MMC benutzerdefinierte Menüelemente Einfügemarken, die verwendet werden können. Dies kann eine Kombination der folgenden Werte sein:  
  
- **CCM_INSERTIONALLOWED_TOP** Elemente am Anfang eines Kontextmenüs eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_NEW** Elemente im Untermenü "neu erstellen" eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_TASK** Elemente im Untermenü "Aufgabe" eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_VIEW** Elemente im Menü Ansicht Symbolleiste oder im Untermenü anzeigen des Kontextmenüs im Bereich Ergebnis eingefügt werden können.  
  
 `type`  
 [in] Gibt den Typ des Objekts. Die folgenden Werte sind möglich:  
  
- **CCT_SCOPE** -Datenobjekt für den Bereich im Bereichskontext.  
  
- **CCT_RESULT** Datenobjekt für Ergebnis Bereich Kontext.  
  
- **CCT_SNAPIN_MANAGER** -Datenobjekt für den Kontext-Manager-Snap-in.  
  
- **CCT_UNINITIALIZED** Datenobjekt hat einen ungültigen Typ.  
  
##  <a name="command"></a>CSnapInItemImpl::Command  
 Diese Methode implementiert die Win32-Funktion [IExtendContextMenu::Command](http://msdn.microsoft.com/library/aa814842).  
  
```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Parameter  
 *lCommandID*  
 [in] Gibt die Befehls-ID des Menüelements.  
  
 `type`  
 [in] Gibt den Typ des Objekts. Die folgenden Werte sind möglich:  
  
- **CCT_SCOPE** -Datenobjekt für den Bereich im Bereichskontext.  
  
- **CCT_RESULT** Datenobjekt für Ergebnis Bereich Kontext.  
  
- **CCT_SNAPIN_MANAGER** -Datenobjekt für den Kontext-Manager-Snap-in.  
  
- **CCT_UNINITIALIZED** Datenobjekt hat einen ungültigen Typ.  
  
##  <a name="createpropertypages"></a>CSnapInItemImpl::CreatePropertyPages  
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
 [in] Gibt das Handle verwendet Route die **MMCN_PROPERTY_CHANGE** Benachrichtigung, um die entsprechenden Daten-Klasse.  
  
 *pUnk*  
 [in] Zeiger auf die **IExtendPropertySheet** Schnittstelle für das Objekt, das Kontextinformationen über den Knoten enthält.  
  
 `type`  
 [in] Gibt den Typ des Objekts. Die folgenden Werte sind möglich:  
  
- **CCT_SCOPE** -Datenobjekt für den Bereich im Bereichskontext.  
  
- **CCT_RESULT** Datenobjekt für Ergebnis Bereich Kontext.  
  
- **CCT_SNAPIN_MANAGER** -Datenobjekt für den Kontext-Manager-Snap-in.  
  
- **CCT_UNINITIALIZED** Datenobjekt hat einen ungültigen Typ.  
  
##  <a name="csnapinitemimpl"></a>CSnapInItemImpl::CSnapInItemImpl  
 Erstellt ein `CSnapInItemImpl`-Objekt.  
  
```
CSnapInItemImpl();
```  
  
##  <a name="filldata"></a>CSnapInItemImpl::FillData  
 Diese Funktion wird aufgerufen, um Informationen über das Element abzurufen.  
  
```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 [in] Das Format (Text, rich-Text oder rich-Text mit OLE-Elementen) aus der Zwischenablage.  
  
 `pStream`  
 [in] Ein Zeiger auf den Stream, der die Daten des Objekts enthält.  
  
### <a name="remarks"></a>Hinweise  
 Um diese Funktion ordnungsgemäß zu implementieren, kopieren Sie die richtige Informationen in den Datenstrom ( `pStream`), abhängig vom Format Zwischenablage `cf`.  
  
##  <a name="getresultviewtype"></a>CSnapInItemImpl::GetResultViewType  
 Rufen Sie diese Funktion, um den Typ der Ansicht für den Ergebnisbereich des Snap-in-Objekts abrufen.  
  
```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```  
  
### <a name="parameters"></a>Parameter  
 *ppViewType*  
 [out] Ein Zeiger auf die Adresse des zurückgegebenen geben.  
  
 *pViewOptions*  
 [out] Zeiger auf die **MMC_VIEW_OPTIONS** -Enumeration, die die Konsole mit der besitzenden-Snap-in angegebenen Optionen bietet. Dieser Wert kann eine der folgenden sein:  
  
- **MMC_VIEW_OPTIONS_NOLISTVIEWS** = 0 x 00000001 weist die Konsole stellen sicher, dass von der Vorlage der Standardliste Ansichtsoptionen in der **Ansicht** Menü. Ermöglicht das Snap-in eine eigene benutzerdefinierten Ansichten nur im Bereich Ansicht Ergebnis angezeigt. Dies ist das einzige Optionsflag zu diesem Zeitpunkt definiert.  
  
- **MMC_VIEW_OPTIONS_NONE** = 0 ermöglicht die Standardoptionen für die Ansicht.  
  
##  <a name="getscopepaneinfo"></a>CSnapInItemImpl::GetScopePaneInfo  
 Rufen Sie diese Funktion zum Abrufen der **SCOPEDATAITEM** Struktur das Snap-in.  
  
```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pScopeDataItem*  
 [out] Ein Zeiger auf die **SCOPEDATAITEM** Struktur der `CSnapInItemImpl` Objekt.  
  
##  <a name="getresultpaneinfo"></a>CSnapInItemImpl::GetResultPaneInfo  
 Rufen Sie diese Funktion zum Abrufen der **RESULTDATAITEM** Struktur das Snap-in.  
  
```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pResultDataItem*  
 [out] Ein Zeiger auf die **RESULTDATAITEM** Struktur der `CSnapInItemImpl` Objekt.  
  
##  <a name="m_bstrdisplayname"></a>CSnapInItemImpl::m_bstrDisplayName  
 Enthält die Zeichenfolge für das Knotenelement angezeigt.  
  
```
CComBSTR m_bstrDisplayName;
```  
  
##  <a name="m_scopedataitem"></a>CSnapInItemImpl::m_scopeDataItem  
 Die `SCOPEDATAITEM` Struktur des-Snap-in-Objekts.  
  
```
SCOPEDATAITEM m_scopeDataItem;
```  
  
##  <a name="m_resultdataitem"></a>CSnapInItemImpl::m_resultDataItem  
 Die [RESULTDATAITEM](http://msdn.microsoft.com/library/aa815165) Struktur des-Snap-in-Objekts.  
  
```
RESULTDATAITEM m_resultDataItem;
```  
  
##  <a name="notify"></a>CSnapInItemImpl::Notify  
 Wird aufgerufen, wenn das Objekt-Snap-in auf der Benutzer ausgeführt wird.  
  
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
 [in] Identifiziert eine Aktion, die von einem Benutzer. Die folgenden Benachrichtigungen sind möglich:  
  
- **MMCN_ACTIVATE** gesendet, wenn ein Fenster aktiviert und deaktiviert wird.  
  
- **MMCN_ADD_IMAGES** gesendet, um den Ergebnisbereich Bilder hinzuzufügen.  
  
- **MMCN_BTN_CLICK** gesendet, wenn der Benutzer eine Symbolleisten-Schaltflächen klickt.  
  
- **MMCN_CLICK** gesendet, wenn ein Benutzer eine Maustaste drückt, die auf ein Element anzeigen.  
  
- **MMCN_DBLCLICK** gesendet, wenn ein Benutzer eine Maustaste auf ein Element der Liste anzeigen doppelklickt.  
  
- **MMCN_DELETE** das Snap-in informiert werden, die das Objekt sollte gelöscht.  
  
- **MMCN_EXPAND** gesendet, wenn Sie ein Ordner erweitert oder verkürzt werden muss.  
  
- **MMCN_MINIMIZED** gesendet, wenn ein Fenster wird minimiert oder maximiert.  
  
- **MMCN_PROPERTY_CHANGE** gesendet, um ein Snap-In-Objekt zu benachrichtigen, dass die Ansicht-Snap-in des Objekts geändert wird.  
  
- **MMCN_REMOVE_CHILDREN** gesendet, wenn das Snap-in die gesamte Unterstruktur löschen müssen sie unter dem angegebenen Knoten hinzugefügt.  
  
- **MMCN_RENAME** gesendet erstmalig zur Abfrage umbenennen und das zweite Mal umbenennen möchten.  
  
- **MMCN_SELECT** gesendet, wenn ein Element im Ansichtsbereich Bereich oder das Ergebniselement ausgewählt ist.  
  
- **MMCN_SHOW** gesendet, wenn ein Objekt ausgewählt oder zum ersten Mal deaktiviert ist.  
  
- **MMCN_VIEW_CHANGE** gesendet, wenn das Snap-in allen Ansichten aktualisieren kann, wenn eine Änderung vorgenommen wird.  
  
 `arg`  
 [in] Hängt von der Benachrichtigungstyp.  
  
 `param`  
 [in] Hängt von der Benachrichtigungstyp.  
  
 *pComponentData*  
 [out] Ein Zeiger auf das Objekt implementiert **IComponentData**. Dieser Parameter ist **NULL** , wenn die Benachrichtigung über nicht weitergeleitet wird **IComponentData::Notify**.  
  
 *pComponent*  
 [out] Ein Zeiger auf das Objekt, das implementiert **IComponent**. Dieser Parameter ist **NULL** , wenn die Benachrichtigung über nicht weitergeleitet wird **IComponent::Notify**.  
  
 `type`  
 [in] Gibt den Typ des Objekts. Die folgenden Werte sind möglich:  
  
- **CCT_SCOPE** -Datenobjekt für den Bereich im Bereichskontext.  
  
- **CCT_RESULT** Datenobjekt für Ergebnis Bereich Kontext.  
  
- **CCT_SNAPIN_MANAGER** -Datenobjekt für den Kontext-Manager-Snap-in.  
  
- **CCT_UNINITIALIZED** Datenobjekt hat einen ungültigen Typ.  
  
##  <a name="querypagesfor"></a>CSnapInItemImpl::QueryPagesFor  
 Wird aufgerufen, um festzustellen, ob der Snap-In-Knoten Eigenschaftenseiten unterstützt.  
  
```
QueryPagesFor(DATA_OBJECT_TYPES type);
```  
  
##  <a name="setmenuinsertionflags"></a>CSnapInItemImpl::SetMenuInsertionFlags  
 Mit dieser Funktion können Sie im Menü Einfügen, angegebenen Flags durch Ändern `pInsertionAllowed`, für das Snap-In-Objekt.  
  
```
void SetMenuInsertionFlags(  
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```  
  
### <a name="parameters"></a>Parameter  
 *bBeforeInsertion*  
 [in] Wert ungleich NULL, wenn die Funktion aufgerufen werden soll, bevor das Kontextmenü Elemente hinzugefügt werden; andernfalls 0.  
  
 `pInsertionAllowed`  
 [in, out] Bezeichnet die Microsoft Management Console MMC benutzerdefinierte Menüelemente Einfügemarken, die verwendet werden können. Dies kann eine Kombination der folgenden Werte sein:  
  
- **CCM_INSERTIONALLOWED_TOP** Elemente am Anfang eines Kontextmenüs eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_NEW** Elemente im Untermenü "neu erstellen" eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_TASK** Elemente im Untermenü "Aufgabe" eingefügt werden können.  
  
- **CCM_INSERTIONALLOWED_VIEW** Elemente im Menü Ansicht Symbolleiste oder im Untermenü anzeigen des Kontextmenüs im Bereich Ergebnis eingefügt werden können.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine primäre Snap-In entwickeln, können Sie eines der einfügen-Flags als die Art der Menüelemente, die eine Erweiterung von Drittanbietern hinzufügen können eingeschränkt zurücksetzen. Z. B. das primäre Snap-In kann Deaktivieren der **CCM_INSERTIONALLOWED_NEW** Flag, um zu verhindern, dass Erweiterungen ihre eigenen erstellen neue Menüelemente hinzufügen.  
  
 Sie sollten nicht versuchen, legen Sie die Bits in `pInsertionAllowed` , wurden ursprünglich gelöscht. Zukünftige Versionen von MMC können Bits, die derzeit nicht definiert werden, sodass Sie Bits nicht ändern müssen, die derzeit nicht definiert sind.  
  
##  <a name="settoolbarbuttoninfo"></a>CSnapInItemImpl::SetToolbarButtonInfo  
 Rufen Sie diese Funktion, um alle Symbolleiste Schaltflächenstile, des Objekts-Snap-in zu ändern, bevor die Symbolleiste erstellt wird.  
  
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
  
- `TBSTATE_CHECKED`Die Schaltfläche der **TBSTYLE_CHECKED** formatieren und gedrückt wird.  
  
- `TBSTATE_ENABLED`Die Schaltfläche akzeptiert Benutzereingaben. Eine Schaltfläche, die diesem Zustand nicht akzeptiert keine Benutzereingaben und ist deaktiviert.  
  
- `TBSTATE_HIDDEN`Die Schaltfläche ist nicht sichtbar und Eingaben.  
  
- `TBSTATE_INDETERMINATE`Die Schaltfläche ist abgeblendet.  
  
- `TBSTATE_PRESSED`Die Schaltfläche wird gedrückt wird.  
  
- `TBSTATE_WRAP`Ein Zeilenumbruch folgt auf die Schaltfläche. Die Schaltfläche müssen auch die `TBSTATE_ENABLED`.  
  
 *fsType*  
 [in] Die Statusflags der Schaltfläche. Hierbei kann es sich um eine oder mehrere der folgenden sein:  
  
- `TBSTYLE_BUTTON`Erstellt eine Standardschaltflächen.  
  
- `TBSTYLE_CHECK`Erstellt eine Schaltfläche, die zwischen dem gedrückt und nicht gedrückten Zustand jedes Mal schaltet der Benutzer darauf klickt. Die Schaltfläche hat eine andere Hintergrundfarbe, wenn es im gedrückten Zustand ist.  
  
- `TBSTYLE_CHECKGROUP`Erstellt eine Kontrollkästchen-Schaltfläche, die gedrückt bleibt, bis eine andere Schaltfläche in der Gruppe gedrückt wird.  
  
- `TBSTYLE_GROUP`Erstellt eine Schaltfläche, die gedrückt bleibt, bis eine andere Schaltfläche in der Gruppe gedrückt wird.  
  
- `TBSTYLE_SEP`Erstellt ein Trennzeichen, eine kleine zeitliche Lücke zwischen Schaltflächengruppen bereitstellen. Eine Schaltfläche mit diesem Format erhält keine Benutzereingaben.  
  
##  <a name="updatemenustate"></a>CSnapInItemImpl::UpdateMenuState  
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
 [in] Gibt den neuen Statusflags. Dies kann eine Kombination der folgenden Werte sein:  
  
- **MF_POPUP** gibt an, dass dies ein Untermenü im Kontextmenü. Menüelemente, Einfügemarken und weitere Untermenüs an dieses Untermenü hinzugefügt werden die **lCommandID** als ihre **IInsertionPointID**.  
  
- **MF_BITMAP** und `MF_OWNERDRAW` diese Flags sind nicht zulässig und führt dazu, dass der Rückgabewert `E_INVALIDARG`.  
  
- **MF_SEPARATOR** zeichnet eine horizontale Trennlinie. Nur **IContextMenuProvider** ist zulässig, Hinzufügen von Menüelementen mit **MF_SEPARATOR** festgelegt.  
  
- **MF_CHECKED** setzt ein Häkchen neben dem Menüelement.  
  
- **MF_DISABLED** das Menüelement deaktiviert, damit nicht ausgewählt werden, aber das Flag wird nicht grau.  
  
- `MF_ENABLED`Können das Menüelement aus, damit es kann vom grau Zustand wiederherstellen ausgewählt werden.  
  
- **MF_GRAYED** deaktiviert das Menüelement, das es abblendet, damit es nicht ausgewählt werden kann.  
  
- **MF_MENUBARBREAK** die gleiche Funktion wie die **MF_MENUBREAK** einer Menüleiste zu kennzeichnen. Für ein Dropdown-Menü, Untermenü oder Kontextmenü wird die neue Spalte durch eine vertikale Linie von der alten Spalte getrennt.  
  
- **MF_MENUBREAK** platziert das Element in einer neuen Zeile (für eine Menüleiste) oder in einer neuen Spalte (für ein Dropdown-Menü, Untermenü oder Kontextmenü) ohne die Trennung von Spalten.  
  
- **MF_UNCHECKED** kein Häkchen neben dem Element (Standard).  
  
 Die folgenden Gruppen von Flags können nicht zusammen verwendet werden:  
  
- **MF_DISABLED**, `MF_ENABLED`, und **MF_GRAYED**.  
  
- **MF_MENUBARBREAK** und **MF_MENUBREAK**.  
  
- **MF_CHECKED** und **MF_UNCHECKED**.  
  
##  <a name="updatetoolbarbutton"></a>CSnapInItemImpl::UpdateToolbarButton  
 Rufen Sie diese Funktion, um eine Symbolleisten-Schaltfläche des Objekts-Snap-in zu ändern, bevor er angezeigt wird.  
  
```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 Gibt die Schaltfläche-ID der Symbolleisten-Schaltfläche aktualisiert werden.  
  
 `fsState`  
 Gibt den Status der Symbolleisten-Schaltfläche. Wenn dieser Status wird festgelegt werden, zurück **TRUE**. Dies kann eine Kombination der folgenden Werte sein:  
  
- **AKTIVIERT** die Schaltfläche Benutzereingaben akzeptiert. Eine Schaltfläche, die diesem Zustand nicht akzeptiert keine Benutzereingaben und ist deaktiviert.  
  
- **ÜBERPRÜFT** verfügt über die Schaltfläche der **überprüft** formatieren und gedrückt wird.  
  
- **Ausgeblendete** die Schaltfläche ist nicht sichtbar und Eingaben.  
  
- **Unbestimmt** die Schaltfläche ist abgeblendet.  
  
- **BUTTONPRESSED** die Schaltfläche gedrückt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

