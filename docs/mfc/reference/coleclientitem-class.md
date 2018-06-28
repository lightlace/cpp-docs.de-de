---
title: COleClientItem Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleClientItem
- AFXOLE/COleClientItem
- AFXOLE/COleClientItem::COleClientItem
- AFXOLE/COleClientItem::Activate
- AFXOLE/COleClientItem::ActivateAs
- AFXOLE/COleClientItem::AttachDataObject
- AFXOLE/COleClientItem::CanCreateFromData
- AFXOLE/COleClientItem::CanCreateLinkFromData
- AFXOLE/COleClientItem::CanPaste
- AFXOLE/COleClientItem::CanPasteLink
- AFXOLE/COleClientItem::Close
- AFXOLE/COleClientItem::ConvertTo
- AFXOLE/COleClientItem::CopyToClipboard
- AFXOLE/COleClientItem::CreateCloneFrom
- AFXOLE/COleClientItem::CreateFromClipboard
- AFXOLE/COleClientItem::CreateFromData
- AFXOLE/COleClientItem::CreateFromFile
- AFXOLE/COleClientItem::CreateLinkFromClipboard
- AFXOLE/COleClientItem::CreateLinkFromData
- AFXOLE/COleClientItem::CreateLinkFromFile
- AFXOLE/COleClientItem::CreateNewItem
- AFXOLE/COleClientItem::CreateStaticFromClipboard
- AFXOLE/COleClientItem::CreateStaticFromData
- AFXOLE/COleClientItem::Deactivate
- AFXOLE/COleClientItem::DeactivateUI
- AFXOLE/COleClientItem::Delete
- AFXOLE/COleClientItem::DoDragDrop
- AFXOLE/COleClientItem::DoVerb
- AFXOLE/COleClientItem::Draw
- AFXOLE/COleClientItem::GetActiveView
- AFXOLE/COleClientItem::GetCachedExtent
- AFXOLE/COleClientItem::GetClassID
- AFXOLE/COleClientItem::GetClipboardData
- AFXOLE/COleClientItem::GetDocument
- AFXOLE/COleClientItem::GetDrawAspect
- AFXOLE/COleClientItem::GetExtent
- AFXOLE/COleClientItem::GetIconFromRegistry
- AFXOLE/COleClientItem::GetIconicMetafile
- AFXOLE/COleClientItem::GetInPlaceWindow
- AFXOLE/COleClientItem::GetItemState
- AFXOLE/COleClientItem::GetLastStatus
- AFXOLE/COleClientItem::GetLinkUpdateOptions
- AFXOLE/COleClientItem::GetType
- AFXOLE/COleClientItem::GetUserType
- AFXOLE/COleClientItem::IsInPlaceActive
- AFXOLE/COleClientItem::IsLinkUpToDate
- AFXOLE/COleClientItem::IsModified
- AFXOLE/COleClientItem::IsOpen
- AFXOLE/COleClientItem::IsRunning
- AFXOLE/COleClientItem::OnActivate
- AFXOLE/COleClientItem::OnActivateUI
- AFXOLE/COleClientItem::OnChange
- AFXOLE/COleClientItem::OnDeactivate
- AFXOLE/COleClientItem::OnDeactivateUI
- AFXOLE/COleClientItem::OnGetClipboardData
- AFXOLE/COleClientItem::OnInsertMenus
- AFXOLE/COleClientItem::OnRemoveMenus
- AFXOLE/COleClientItem::OnSetMenu
- AFXOLE/COleClientItem::OnShowControlBars
- AFXOLE/COleClientItem::OnUpdateFrameTitle
- AFXOLE/COleClientItem::ReactivateAndUndo
- AFXOLE/COleClientItem::Release
- AFXOLE/COleClientItem::Reload
- AFXOLE/COleClientItem::Run
- AFXOLE/COleClientItem::SetDrawAspect
- AFXOLE/COleClientItem::SetExtent
- AFXOLE/COleClientItem::SetHostNames
- AFXOLE/COleClientItem::SetIconicMetafile
- AFXOLE/COleClientItem::SetItemRects
- AFXOLE/COleClientItem::SetLinkUpdateOptions
- AFXOLE/COleClientItem::SetPrintDevice
- AFXOLE/COleClientItem::UpdateLink
- AFXOLE/COleClientItem::CanActivate
- AFXOLE/COleClientItem::OnChangeItemPosition
- AFXOLE/COleClientItem::OnDeactivateAndUndo
- AFXOLE/COleClientItem::OnDiscardUndoState
- AFXOLE/COleClientItem::OnGetClipRect
- AFXOLE/COleClientItem::OnGetItemPosition
- AFXOLE/COleClientItem::OnGetWindowContext
- AFXOLE/COleClientItem::OnScrollBy
- AFXOLE/COleClientItem::OnShowItem
dev_langs:
- C++
helpviewer_keywords:
- COleClientItem [MFC], COleClientItem
- COleClientItem [MFC], Activate
- COleClientItem [MFC], ActivateAs
- COleClientItem [MFC], AttachDataObject
- COleClientItem [MFC], CanCreateFromData
- COleClientItem [MFC], CanCreateLinkFromData
- COleClientItem [MFC], CanPaste
- COleClientItem [MFC], CanPasteLink
- COleClientItem [MFC], Close
- COleClientItem [MFC], ConvertTo
- COleClientItem [MFC], CopyToClipboard
- COleClientItem [MFC], CreateCloneFrom
- COleClientItem [MFC], CreateFromClipboard
- COleClientItem [MFC], CreateFromData
- COleClientItem [MFC], CreateFromFile
- COleClientItem [MFC], CreateLinkFromClipboard
- COleClientItem [MFC], CreateLinkFromData
- COleClientItem [MFC], CreateLinkFromFile
- COleClientItem [MFC], CreateNewItem
- COleClientItem [MFC], CreateStaticFromClipboard
- COleClientItem [MFC], CreateStaticFromData
- COleClientItem [MFC], Deactivate
- COleClientItem [MFC], DeactivateUI
- COleClientItem [MFC], Delete
- COleClientItem [MFC], DoDragDrop
- COleClientItem [MFC], DoVerb
- COleClientItem [MFC], Draw
- COleClientItem [MFC], GetActiveView
- COleClientItem [MFC], GetCachedExtent
- COleClientItem [MFC], GetClassID
- COleClientItem [MFC], GetClipboardData
- COleClientItem [MFC], GetDocument
- COleClientItem [MFC], GetDrawAspect
- COleClientItem [MFC], GetExtent
- COleClientItem [MFC], GetIconFromRegistry
- COleClientItem [MFC], GetIconicMetafile
- COleClientItem [MFC], GetInPlaceWindow
- COleClientItem [MFC], GetItemState
- COleClientItem [MFC], GetLastStatus
- COleClientItem [MFC], GetLinkUpdateOptions
- COleClientItem [MFC], GetType
- COleClientItem [MFC], GetUserType
- COleClientItem [MFC], IsInPlaceActive
- COleClientItem [MFC], IsLinkUpToDate
- COleClientItem [MFC], IsModified
- COleClientItem [MFC], IsOpen
- COleClientItem [MFC], IsRunning
- COleClientItem [MFC], OnActivate
- COleClientItem [MFC], OnActivateUI
- COleClientItem [MFC], OnChange
- COleClientItem [MFC], OnDeactivate
- COleClientItem [MFC], OnDeactivateUI
- COleClientItem [MFC], OnGetClipboardData
- COleClientItem [MFC], OnInsertMenus
- COleClientItem [MFC], OnRemoveMenus
- COleClientItem [MFC], OnSetMenu
- COleClientItem [MFC], OnShowControlBars
- COleClientItem [MFC], OnUpdateFrameTitle
- COleClientItem [MFC], ReactivateAndUndo
- COleClientItem [MFC], Release
- COleClientItem [MFC], Reload
- COleClientItem [MFC], Run
- COleClientItem [MFC], SetDrawAspect
- COleClientItem [MFC], SetExtent
- COleClientItem [MFC], SetHostNames
- COleClientItem [MFC], SetIconicMetafile
- COleClientItem [MFC], SetItemRects
- COleClientItem [MFC], SetLinkUpdateOptions
- COleClientItem [MFC], SetPrintDevice
- COleClientItem [MFC], UpdateLink
- COleClientItem [MFC], CanActivate
- COleClientItem [MFC], OnChangeItemPosition
- COleClientItem [MFC], OnDeactivateAndUndo
- COleClientItem [MFC], OnDiscardUndoState
- COleClientItem [MFC], OnGetClipRect
- COleClientItem [MFC], OnGetItemPosition
- COleClientItem [MFC], OnGetWindowContext
- COleClientItem [MFC], OnScrollBy
- COleClientItem [MFC], OnShowItem
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69836eb254b23c05f2405c8f11b55a6d6293a9cb
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039335"
---
# <a name="coleclientitem-class"></a>COleClientItem-Klasse
Definiert die Containerschnittstelle zu OLE-Elementen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleClientItem : public CDocItem  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleClientItem::COleClientItem](#coleclientitem)|Erstellt ein `COleClientItem`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleClientItem::Activate](#activate)|Öffnet das OLE-Element für einen Vorgang, und führt dann das angegebene Verb.|  
|[COleClientItem::ActivateAs](#activateas)|Aktiviert das Element als anderer Typ.|  
|[COleClientItem::AttachDataObject](#attachdataobject)|Greift auf die Daten in der OLE-Objekts.|  
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|Gibt an, ob eine Steuerelementcontainer-Anwendung ein eingebettetes Objekt erstellen kann.|  
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|Gibt an, ob eine Steuerelementcontainer-Anwendung ein verknüpftes Objekt erstellen kann.|  
|[COleClientItem::CanPaste](#canpaste)|Gibt an, ob die Zwischenablage ein OLE-Element eingebettet werden oder statische enthält.|  
|[COleClientItem::CanPasteLink](#canpastelink)|Gibt an, ob die Zwischenablage verknüpfbares OLE-Element enthält.|  
|[COleClientItem::Close](#close)|Schließt einen Link zu einem Server, jedoch nicht die OLE-Element zerstört.|  
|[COleClientItem::ConvertTo](#convertto)|Konvertiert das Element in einen anderen Typ.|  
|[COleClientItem::CopyToClipboard](#copytoclipboard)|OLE-Element kopiert in die Zwischenablage.|  
|[COleClientItem::CreateCloneFrom](#createclonefrom)|Erstellt ein Duplikat eines vorhandenen Elements.|  
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|Erstellt ein eingebettetes Element aus der Zwischenablage an.|  
|[COleClientItem::CreateFromData](#createfromdata)|Erstellt ein eingebettetes Element von einem Datenobjekt.|  
|[CreateFromFile](#createfromfile)|Erstellt ein eingebettetes Element aus einer Datei an.|  
|[COleClientItem::CreateLinkFromClipboard](#createlinkfromclipboard)|Erstellt ein verknüpftes Element aus der Zwischenablage an.|  
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|Erstellt ein verknüpftes Element von einem Datenobjekt.|  
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|Erstellt ein verknüpftes Element aus einer Datei an.|  
|[COleClientItem::CreateNewItem](#createnewitem)|Erstellt ein neues eingebettetes Element durch die Serveranwendung gestartet.|  
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|Erstellt ein statisches Element aus der Zwischenablage an.|  
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|Erstellt ein statisches Element von einem Datenobjekt.|  
|[COleClientItem::Deactivate](#deactivate)|Deaktiviert das Element an.|  
|[COleClientItem::DeactivateUI](#deactivateui)|Benutzeroberfläche der Steuerelementcontainer-Anwendung wiederhergestellt in den ursprünglichen Zustand.|  
|[COleClientItem::Delete](#delete)|Löscht oder schließt das OLE-Element, wenn es sich um ein verknüpftes Element war.|  
|[COleClientItem::DoDragDrop](#dodragdrop)|Führt einen Drag-and-Drop-Vorgang.|  
|[COleClientItem::DoVerb](#doverb)|Führt das angegebene Verb.|  
|[COleClientItem::Draw](#draw)|Zeichnet das OLE-Element.|  
|[COleClientItem::GetActiveView](#getactiveview)|Ruft die Ansicht auf der das Element direkt aktiviert ist.|  
|[COleClientItem::GetCachedExtent](#getcachedextent)|Gibt die Grenzen des Rechtecks OLE-Element zurück.|  
|[COleClientItem::GetClassID](#getclassid)|Ruft das vorhanden Element Klasse-ID ab.|  
|[COleClientItem::GetClipboardData](#getclipboarddata)|Ruft die Daten, die durch den Aufruf in der Zwischenablage befinden würde die `CopyToClipboard` Memberfunktion.|  
|[COleClientItem::GetDocument](#getdocument)|Gibt die `COleDocument` -Objekt, das vorhandene Element enthält.|  
|[COleClientItem::GetDrawAspect](#getdrawaspect)|Ruft die aktuelle Elementansicht für das Rendering.|  
|[COleClientItem::GetExtent](#getextent)|Gibt die Grenzen des Rechtecks OLE-Element zurück.|  
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|Ruft ein Handle für ein Symbol mit dem Server von einem bestimmten CLSID verknüpft sind.|  
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|Ruft die Metadatei, die zum Zeichnen des Symbols ab.|  
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|Gibt einen Zeiger auf das Element Fenster zur direkten Bearbeitung.|  
|[COleClientItem::GetItemState](#getitemstate)|Ruft das Element des aktuellen Status ab.|  
|[COleClientItem::GetLastStatus](#getlaststatus)|Gibt den Status des letzten OLE-Vorgangs zurück.|  
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|Gibt den Updatemodus für ein verknüpftes Element (erweiterte Funktion).|  
|[COleClientItem::GetType](#gettype)|Gibt den Typ (eingebettete, verknüpfte oder statisch) des OLE-Elements zurück.|  
|[COleClientItem::GetUserType](#getusertype)|Ruft eine Zeichenfolge, die den Typ des Elements ab.|  
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|Gibt `TRUE` Wenn das Element in-Place aktiv ist.|  
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|Gibt **"true"** ist ein verknüpftes Element auf dem neuesten Stand mit dem Quelldokument.|  
|[COleClientItem::IsModified](#ismodified)|Gibt `TRUE` , wenn das Element geändert wurde, seit es zuletzt gespeichert wurde.|  
|[COleClientItem::IsOpen](#isopen)|Gibt `TRUE` Wenn das Element in der Serveranwendung derzeit geöffnet ist.|  
|[COleClientItem::IsRunning](#isrunning)|Gibt `TRUE` , wenn das Element-Serveranwendung ausgeführt wird.|  
|[COleClientItem::OnActivate](#onactivate)|Wird aufgerufen, durch das Framework, um dem Element zu benachrichtigen, dass er aktiviert ist.|  
|[COleClientItem::OnActivateUI](#onactivateui)|Wird aufgerufen, durch das Framework, um dem Element zu benachrichtigen, dass er aktiviert ist und seine Benutzeroberfläche anzeigen.|  
|[COleClientItem:: OnChange](#onchange)|Wird aufgerufen, wenn der Server das OLE-Element geändert. Die Implementierung erforderlich sind.|  
|[COleClientItem::OnDeactivate](#ondeactivate)|Wird vom Framework aufgerufen, wenn ein Element deaktiviert wird.|  
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|Vom Framework aufgerufen, wenn der Server die direkte Benutzeroberfläche entfernt wurde.|  
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|Wird aufgerufen, durch das Framework zum Abrufen der Daten in die Zwischenablage kopiert werden soll.|  
|[COleClientItem::OnInsertMenus](#oninsertmenus)|Wird aufgerufen, durch das Framework zum Erstellen eines zusammengesetzten Menüs.|  
|[COleClientItem::OnRemoveMenus](#onremovemenus)|Wird aufgerufen, durch das Framework des Containers Menüs von einem zusammengesetzten Menü zu entfernen.|  
|[COleClientItem::OnSetMenu](#onsetmenu)|Wird durch das Framework beim Installieren und Entfernen von einem zusammengesetzten Menü aufgerufen.|  
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|Vom Framework ein-und Ausblenden von Steuerleisten aufgerufen.|  
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|Wird aufgerufen, durch das Framework das Rahmenfenster Titelleiste zu aktualisieren.|  
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|Reaktiviert das Element, und macht die letzte direkte Bearbeitung rückgängig.|  
|[COleClientItem::Release](#release)|Die Verbindung mit einer OLE-Element verknüpfte frei, und geschlossen wird, falls er geöffnet ist. Die Client-Element wird nicht zerstört werden.|  
|[COleClientItem::Reload](#reload)|Lädt das Element nach einem Aufruf von `ActivateAs`.|  
|[COleClientItem::Run](#run)|Führt die Anwendung, die dem Element zugeordnet.|  
|[COleClientItem::SetDrawAspect](#setdrawaspect)|Legt die aktuelle Elementansicht für das Rendering.|  
|[COleClientItem::SetExtent](#setextent)|Legt das umschließende Rechteck des OLE-Elements.|  
|[COleClientItem::SetHostNames](#sethostnames)|Legt die Namen der Server anzeigt, wenn das OLE-Element zu bearbeiten.|  
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|Speichert die Metadatei, die zum Zeichnen des Symbols an.|  
|[COleClientItem::SetItemRects](#setitemrects)|Legt die umschließenden Rechtecks des Elements fest.|  
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|Legt den Updatemodus für ein verknüpftes Element (erweiterte Funktion).|  
|[COleClientItem::SetPrintDevice](#setprintdevice)|Legt die Print-Zielgerät für dieses Clientelement.|  
|[COleClientItem::UpdateLink](#updatelink)|Aktualisiert den Cache Präsentation eines Elements.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleClientItem:: CanActivate](#canactivate)|Wird aufgerufen, durch das Framework, um festzustellen, ob die direkte Aktivierung zulässig ist.|  
|[COleClientItem:: OnChangeItemPosition auf](#onchangeitemposition)|Vom Framework aufgerufen, wenn sich die Position eines Elements ändert.|  
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|Vom Framework aufgerufen wird, nach der Aktivierung rückgängig zu machen.|  
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|Vom Framework aufgerufen, das Element zum Rückgängigmachen Zustandsinformationen zu verwerfen.|  
|[COleClientItem::OnGetClipRect](#ongetcliprect)|Wird aufgerufen, durch das Framework das Element Clippingrechteck Koordinaten abrufen.|  
|[COleClientItem:: OnGetItemPosition auf](#ongetitemposition)|Wird aufgerufen, durch das Framework der Position des Elements relativ zu der Ansicht abrufen.|  
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|Vom Framework aufgerufen, wenn ein Element direkt aktiviert ist.|  
|[COleClientItem::OnScrollBy](#onscrollby)|Wird aufgerufen, durch das Framework das Element ein Bildlauf.|  
|[COleClientItem::OnShowItem](#onshowitem)|Wird aufgerufen, durch das Framework zum Anzeigen des OLE-Elements.|  
  
## <a name="remarks"></a>Hinweise  
 Ein OLE-Element stellt Daten dar, erstellt und verwaltet, die für eine Server-Anwendung in ein Dokument "nahtlos" eingebunden werden kann, sodass es dem Benutzer um ein einzelnes Dokument angezeigt wird. Das Ergebnis ist ein "Verbunddokument" setzt sich aus der OLE-Element und einem enthaltenden Dokument.  
  
 Ein OLE-Element kann eingebettet oder verknüpft werden. Wenn es eingebettet ist, werden die Daten im Rahmen des Verbunddokuments gespeichert. Wenn es verknüpft ist, ihre Daten als Teil einer separaten Datei erstellt, indem der Serveranwendung gespeichert ist, und nur ein Link zu dieser Datei wird in Verbunddokuments gespeichert. Alle OLE-Elemente enthalten Informationen, die Angabe der Serveranwendung, die aufgerufen werden soll, um sie zu bearbeiten.  
  
 `COleClientItem` definiert mehrere überschreibbare-Funktionen, die aufgerufen werden als Antwort auf Anforderungen von Server-Anwendung. Diese Overridables dienen in der Regel als Benachrichtigungen. Dadurch kann der Serveranwendung auf den Container der Änderungen zu informieren, die der Benutzer durchgeführt werden, wenn das OLE-Element zu bearbeiten oder beim Abrufen von Informationen, die während der Bearbeitung erforderlich.  
  
 `COleClientItem` kann verwendet werden, entweder mit der [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), oder [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) Klasse. Mit `COleClientItem`, eine Klasse ableiten und Implementieren der [OnChange](#onchange) Memberfunktion, die definiert, wie der Container auf Änderungen am Element vorgenommene reagiert. Überschreiben Sie zur Unterstützung der direkten Aktivierung der [OnGetItemPosition](#ongetitemposition) Memberfunktion. Diese Funktion bietet Informationen zur Position des OLE-Elements angezeigt.  
  
 Weitere Informationen über die Containerschnittstelle finden Sie in den Artikeln [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md) und [Aktivierung](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  Das Windows SDK verweist auf eingebettete und verknüpfte Elemente als "Objekte" und bezieht sich auf die Typen von Elementen als "Klassen". Dieser Verweis wird mit dem Begriff "Item" um die OLE-Entität aus der entsprechenden C++-Objekt und der Begriff "Type" der C++-Klasse die Kategorie OLE unterscheiden zu unterscheiden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="activate"></a>  COleClientItem::Activate  
 Mit dieser Funktion wird zum Ausführen des angegebenen Verbs anstelle von [DoVerb](#doverb) , damit Sie tun können eigene Verarbeitung, wenn eine Ausnahme ausgelöst wird.  
  
```  
void Activate(
    LONG nVerb,  
    CView* pView,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nVerb*  
 Gibt das Verb ausgeführt. Es kann einer der folgenden sein:  
  
|Wert|Bedeutung|Symbol|  
|-----------|-------------|------------|  
|- 0|Primäres Verb|`OLEIVERB_PRIMARY`|  
|- 1|Sekundäre verb|(Keine)|  
|- 1|Artikel für die Bearbeitung anzeigen|`OLEIVERB_SHOW`|  
|- 2|Element in separaten Fenster bearbeiten|`OLEIVERB_OPEN`|  
|- 3|Element ausblenden|`OLEIVERB_HIDE`|  
  
 Der Wert-1 ist in der Regel ein Alias für einen anderen Verb. Wenn Bearbeiten öffnen nicht unterstützt wird, hat-2 dieselbe Wirkung wie – 1. Weitere Werte finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) im Windows SDK.  
  
 *pView*  
 Zeiger auf die Container-Ansichtsfenster, das das OLE-Element enthält; Dies ist für die direkte Aktivierung von Server-Anwendung verwendet. Dieser Parameter muss **NULL** Wenn der Container die direkte Aktivierung nicht unterstützt.  
  
 *lpMsg*  
 Ein Zeiger auf die Nachricht, die zu aktivierenden Elements verursacht hat.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Anwendung für die Verwendung der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion führt dazu, dass die [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb) Memberfunktion der entsprechenden `COleServerItem` Objekt, das ausgeführt werden.  
  
 Wenn das primäre Verb bearbeiten und 0 (null), in angegeben wird der *nVerb* Parameter, die Server-Anwendung wird gestartet, damit das OLE-Element, das bearbeitet werden kann. Wenn die containeranwendung direkte Aktivierung unterstützt, kann bearbeiten festliegen erfolgen. Wenn der Container nicht unterstützt wird, direkte Aktivierung (oder wenn das Verb "Open" angegeben ist), wird der Server in einem separaten Fenster gestartet und bearbeiten kann ausgeführt werden vorhanden. In der Regel, wenn der Benutzer der containeranwendung doppelklickt OLE-Element, den Wert für das primäre Verb in der *nVerb* Parameter bestimmt, welche Aktion der Benutzer ausführen kann. Allerdings bei der Server nur eine Aktion unterstützt wird, dauert es diese Aktion aus, unabhängig davon, welche Wert, in angegeben wird der *nVerb* Parameter.  
  
 Weitere Informationen finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) im Windows SDK.  
  
##  <a name="activateas"></a>  COleClientItem::ActivateAs  
 OLE Objekt Konvertierung Einrichtungen verwendet, um das Element zu aktivieren, als wäre es ein Element des Typs gemäß *ClsidNew*.  
  
```  
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,  
    REFCLSID clsidOld,  
    REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszUserType*  
 Zeiger auf eine Zeichenfolge, die den Typ des Ziel-Benutzer, z. B. "Word-Dokument" darstellt.  
  
 *clsidOld*  
 Ein Verweis auf die aktuelle Elementklasse-ID. Die Klassen-ID muss den Typ des eigentlichen Objekts darstellen, wie gespeichert, wenn es sich um einen Link handelt. In diesem Fall sollten sie die CLSID des Elements sein, auf die der Link verweist. Die [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md) stellt automatisch die ordnungsmäßige Klassen-ID für das Element.  
  
 *clsidNew*  
 Ein Verweis auf das Ziel-Klassen-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Hierbei spricht automatisch vom [COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert). Es ist nicht in der Regel direkt aufgerufen.  
  
##  <a name="attachdataobject"></a>  COleClientItem::AttachDataObject  
 Mit dieser Funktion wird zum Initialisieren einer [COleDataObject](../../mfc/reference/coledataobject-class.md) für den Zugriff auf die Daten in der OLE-Element.  
  
```  
void AttachDataObject(COleDataObject& rDataObject) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *rDataObject*  
 Ein Verweis auf eine `COleDataObject` -Objekt, das für den Zugriff auf die Daten in der OLE-Element initialisiert wird.  
  
##  <a name="canactivate"></a>  COleClientItem:: CanActivate  
 Vom Framework aufgerufen, wenn der Benutzer die direkte Aktivierung des OLE-Elements anfordert; Diese Funktion zurückgegebene Wert bestimmt, ob direkte Aktivierung zulässig ist.  
  
```  
virtual BOOL CanActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die direkte Aktivierung ist zulässig sind. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ermöglicht direkte Aktivierung, wenn der Container ein gültiges Fenster ist. Überschreiben Sie diese Funktion, um spezielle Logik zum annehmen oder ablehnen die Aktivierungsanfrage zu implementieren. Beispielsweise kann ein aktivierungsanforderung abgelehnt werden, das OLE-Element ist zu klein oder derzeit nicht sichtbar.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::CanInPlaceActivate](http://msdn.microsoft.com/library/windows/desktop/ms691236) im Windows SDK.  
  
##  <a name="cancreatefromdata"></a>  COleClientItem::CanCreateFromData  
 Überprüft, ob eine Steuerelementcontainer-Anwendung ein eingebettetes Objekt erstellen, kann die angegebenen `COleDataObject` Objekt.  
  
```  
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataObject*  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der OLE-Element erstellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn ein eingebettetes Objekt aus der Container erstellen, kann die `COleDataObject` -Objekt, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleDataObject` Klasse wird in Datenübertragungen zum Abrufen von Daten in unterschiedlichen Formaten aus der Zwischenablage, per Drag & Drop oder von einem eingebetteten OLE-Element.  
  
 Container können diese Funktion aktivieren oder deaktivieren ihre Befehle bearbeiten, einfügen und bearbeiten Inhalte einfügen möchten.  
  
 Weitere Informationen finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="cancreatelinkfromdata"></a>  COleClientItem::CanCreateLinkFromData  
 Überprüft, ob eine Steuerelementcontainer-Anwendung ein verknüpftes Objekt aus erstellen, kann die angegebenen `COleDataObject` Objekt.  
  
```  
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataObject*  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der OLE-Element erstellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn ein verknüpftes Objekt aus der Container erstellen, kann die `COleDataObject` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleDataObject` Klasse wird in Datenübertragungen zum Abrufen von Daten in unterschiedlichen Formaten aus der Zwischenablage, per Drag & Drop oder von einem eingebetteten OLE-Element.  
  
 Container können diese Funktion aktivieren oder deaktivieren die Befehle für die Inhalte bearbeiten und Einfügen-Link bearbeiten möchten.  
  
 Weitere Informationen finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="canpaste"></a>  COleClientItem::CanPaste  
 Rufen Sie diese Funktion, um festzustellen, ob es sich bei ein eingebettetes OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
static BOOL PASCAL CanPaste();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn es sich bei ein eingebettetes OLE-Element aus der Zwischenablage eingefügt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) und [OleQueryCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms683739) im Windows SDK.  
  
##  <a name="canpastelink"></a>  COleClientItem::CanPasteLink  
 Rufen Sie diese Funktion, um festzustellen, ob ein verknüpftes OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
static BOOL PASCAL CanPasteLink();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein verknüpftes OLE-Element aus der Zwischenablage eingefügt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) und [OleQueryLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms690244) im Windows SDK.  
  
##  <a name="close"></a>  COleClientItem::Close  
 Mit dieser Funktion können dem Statuswechsel eines OLE-Elements vom Zustand Ausführung in den geladenen Zustand, d. h. geladen, mit dem entsprechenden Handler im Arbeitsspeicher jedoch mit dem Server nicht ausgeführt.  
  
```  
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```  
  
### <a name="parameters"></a>Parameter  
 *dwCloseOption*  
 Kennzeichen, das angibt, unter welchen Umständen der OLE-Element gespeichert wird, wenn er in den geladenen Zustand zurückversetzt. Es kann einen der folgenden Werte aufweisen:  
  
- `OLECLOSE_SAVEIFDIRTY` Speichern Sie das OLE-Element.  
  
- `OLECLOSE_NOSAVE` OLE-Element nicht gespeichert werden.  
  
- `OLECLOSE_PROMPTSAVE` Die Aufforderung, ob das OLE-Element zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion hat keine Auswirkung, wenn das OLE-Element nicht ausgeführt wird.  
  
 Weitere Informationen finden Sie unter [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) im Windows SDK.  
  
##  <a name="coleclientitem"></a>  COleClientItem::COleClientItem  
 Erstellt ein `COleClientItem` -Objekt und fügt es der Containerdokument Auflistung von Dokumentelemente, die die C++-Objekt erstellt und führt keine OLE-Initialisierung hinzu.  
  
```  
COleClientItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pContainerDoc*  
 Ein Zeiger auf die Containerdokument, das dieses Element enthält. Dies kann eine [COleDocument](../../mfc/reference/coledocument-class.md) Ableitung.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie übergeben ein **NULL** -Zeiger ist, erfolgt keine Addition zum Containerdokument. Sie müssen explizit aufrufen, [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem).  
  
 Sie müssen eine der folgenden Erstellung Memberfunktionen aufrufen, vor der Verwendung von OLE-Element:  
  
- [CreateFromClipboard](#createfromclipboard)  
  
- [CreateFromData](#createfromdata)  
  
- [CreateFromFile](#createfromfile)  
  
- [CreateStaticFromClipboard](#createstaticfromclipboard)  
  
- [CreateStaticFromData](#createstaticfromdata)  
  
- [CreateLinkFromClipboard](#createlinkfromclipboard)  
  
- [CreateLinkFromData](#createlinkfromdata)  
  
- [CreateLinkFromFile](#createlinkfromfile)  
  
- [CreateNewItem](#createnewitem)  
  
- [CreateCloneFrom](#createclonefrom)  
  
##  <a name="convertto"></a>  COleClientItem::ConvertTo  
 Rufen Sie diese Memberfunktion, um das Element in den vom angegebenen Typ konvertieren *ClsidNew*.  
  
```  
virtual BOOL ConvertTo(REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Parameter  
 *clsidNew*  
 Die Klassen-ID des Zieltyps.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Hierbei spricht automatisch vom [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md). Es ist nicht erforderlich, um sie direkt aufrufen.  
  
##  <a name="copytoclipboard"></a>  COleClientItem::CopyToClipboard  
 Mit dieser Funktion können Sie OLE-Element in die Zwischenablage zu kopieren.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *bIncludeLink*  
 **"True"** Wenn Linkinformationen in die Zwischenablage kopiert werden sollen, sodass ein verknüpftes Element eingefügte andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion beim Schreiben von Meldungshandler für das Kopieren oder Ausschneiden Befehle im Menü Bearbeiten. Sie müssen in Ihre containeranwendung Elementauswahl implementieren, wenn Sie die Befehle Kopieren oder Ausschneiden implementieren möchten.  
  
 Weitere Informationen finden Sie unter [von OleSetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms686623) im Windows SDK.  
  
##  <a name="createclonefrom"></a>  COleClientItem::CreateCloneFrom  
 Mit dieser Funktion wird zum Erstellen einer Kopie des angegebenen OLE-Elements.  
  
```  
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pSrcItem*  
 Ein Zeiger auf das OLE-Element, das dupliziert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Kopie ist identisch mit der Source-Element. Sie können diese Funktion verwenden, um Rückgängig-Vorgängen zu unterstützen.  
  
##  <a name="createfromclipboard"></a>  COleClientItem::CreateFromClipboard  
 Rufen Sie diese Funktion, um ein eingebettetes Element aus dem Inhalt der Zwischenablage zu erstellen.  
  
```  
BOOL CreateFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Rendern*  
 Kennzeichen, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Datenformat der Zwischenablage zwischengespeichert werden soll, wenn OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion von der Message-Handler, für den Einfügen-Befehl im Menü Bearbeiten. (Der Paste-Befehl durch das Framework aktiviert ist, wenn die [CanPaste](#canpaste) Memberfunktion gibt ungleich NULL zurück.)  
  
 Weitere Informationen finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="createfromdata"></a>  COleClientItem::CreateFromData  
 Mit dieser Funktion können Sie erstellen ein eingebettetes Element aus einem `COleDataObject` Objekt.  
  
```  
BOOL CreateFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataObject*  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der OLE-Element erstellt werden.  
  
 *Rendern*  
 Kennzeichen, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Datenformat der Zwischenablage zwischengespeichert werden soll, wenn OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie die Vorgänge, z. B. Einfügen von Daten aus der Zwischenablage oder Drag & Drop-Vorgänge `COleDataObject` -Objekten mit Informationen über das von einer Serveranwendung angeboten. Es dient in der Regel in der Überschreibung der [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop).  
  
 Weitere Informationen finden Sie unter [OleCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms691211), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="createfromfile"></a>  CreateFromFile  
 Mit dieser Funktion können Sie ein eingebettetes OLE-Element aus einer Datei zu erstellen.  
  
```  
BOOL CreateFromFile(
    LPCTSTR lpszFileName,  
    REFCLSID clsid = CLSID_NULL,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszFileName*  
 Ein Zeiger auf den Namen der Datei an, von dem der OLE-Element erstellt werden.  
  
 *clsid*  
 Für zukünftige Verwendung reserviert.  
  
 *Rendern*  
 Kennzeichen, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Datenformat der Zwischenablage zwischengespeichert werden soll, wenn OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion von [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem) Wenn wählt der Benutzer OK im Dialogfeld "Objekt einfügen", wenn das Erstellen von Datei-Schaltfläche aktiviert ist.  
  
 Weitere Informationen finden Sie unter [OleCreateFromFile](http://msdn.microsoft.com/library/windows/desktop/ms690116), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="createlinkfromclipboard"></a>  COleClientItem::CreateLinkFromClipboard  
 Mit dieser Funktion wird zum Erstellen eines verknüpften Elements aus dem Inhalt der Zwischenablage.  
  
```  
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Rendern*  
 Kennzeichen, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Datenformat der Zwischenablage zwischengespeichert werden soll, wenn OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion von der Message-Handler, für den einfügen-Link-Befehl im Menü Bearbeiten. (Der einfügen-Link-Befehl ist aktiviert, in die standardmäßige Implementierung des [COleDocument](../../mfc/reference/coledocument-class.md) , wenn der Zwischenablage ein OLE-Element enthält, die mit verknüpft werden können.)  
  
 Weitere Informationen finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="createlinkfromdata"></a>  COleClientItem::CreateLinkFromData  
 Mit dieser Funktion wird zum Erstellen eines verknüpften Elements aus einem `COleDataObject` Objekt.  
  
```  
BOOL CreateLinkFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataObject*  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der OLE-Element erstellt werden.  
  
 *Rendern*  
 Kennzeichen, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Datenformat der Zwischenablage zwischengespeichert werden soll, wenn OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie dies während eines Drop-Vorgangs, wenn der Benutzer gibt an, dass eine Verknüpfung erstellt werden soll. Sie können auch verwendet werden, behandeln Sie den Befehl Paste bearbeiten. Wird aufgerufen, durch das Framework in `COleClientItem::CreateLinkFromClipboard` und [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) Wenn die Link-Option ausgewählt wurde.  
  
 Weitere Informationen finden Sie unter [OleCreateLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms680731), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="createlinkfromfile"></a>  COleClientItem::CreateLinkFromFile  
 Mit dieser Funktion können ein verknüpftes OLE-Element aus einer Datei zu erstellen.  
  
```  
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszFileName*  
 Ein Zeiger auf den Namen der Datei an, von dem der OLE-Element erstellt werden.  
  
 *Rendern*  
 Kennzeichen, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Datenformat der Zwischenablage zwischengespeichert werden soll, wenn OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion auf, wenn wählt der Benutzer OK im Dialogfeld "Objekt einfügen", wenn das Erstellen, Schaltfläche "Datei" ausgewählt ist, und aktivieren Sie das Kontrollkästchen links aktiviert ist. Aufruf in [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem).  
  
 Weitere Informationen finden Sie unter [OleCreateLinkToFile](http://msdn.microsoft.com/library/windows/desktop/ms678434), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="createnewitem"></a>  COleClientItem::CreateNewItem  
 Rufen Sie diese Funktion, um ein eingebettetes Element zu erstellen. Diese Funktion startet die Serveranwendung, die dem Benutzer ermöglicht, die das OLE-Element zu erstellen.  
  
```  
BOOL CreateNewItem(
    REFCLSID clsid,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *clsid*  
 ID, die den Typ des zu erstellenden OLE-Elements eindeutig identifiziert.  
  
 *Rendern*  
 Kennzeichen, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Datenformat der Zwischenablage zwischengespeichert werden soll, wenn OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion auf, wenn der Benutzer wählt OK aus das Dialogfeld "Objekt einfügen", wenn die Schaltfläche "neu erstellen" ausgewählt ist.  
  
 Weitere Informationen finden Sie unter [OleCreate](http://msdn.microsoft.com/library/windows/desktop/ms678409), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="createstaticfromclipboard"></a>  COleClientItem::CreateStaticFromClipboard  
 Mit dieser Funktion wird zum Erstellen eines statischen Elements aus dem Inhalt der Zwischenablage.  
  
```  
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Rendern*  
 Kennzeichen, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Datenformat der Zwischenablage zwischengespeichert werden soll, wenn OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ein statisches Element enthält die Präsentationsdaten, aber nicht systemeigenen; Daher kann er bearbeitet werden. Diese Funktion wird in der Regel aufrufen, wenn die [CreateFromClipboard](#createfromclipboard) Memberfunktion ein Fehler auftritt.  
  
 Weitere Informationen finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="createstaticfromdata"></a>  COleClientItem::CreateStaticFromData  
 Mit dieser Funktion wird zum Erstellen eines statischen Elements aus einer `COleDataObject` Objekt.  
  
```  
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataObject*  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der OLE-Element erstellt werden.  
  
 *Rendern*  
 Kennzeichen, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Datenformat der Zwischenablage zwischengespeichert werden soll, wenn OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegeben angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ein statisches Element enthält die Präsentationsdaten, aber nicht systemeigenen; Daher kann er bearbeitet werden. Dies ist im Wesentlichen identisch mit [CreateStaticFromClipboard](#createstaticfromclipboard) mit dem Unterschied, dass ein statisches Element über einen beliebigen erstellt werden kann `COleDataObject`, nicht nur aus der Zwischenablage.  
  
 Verwendet [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) Wenn statische aktiviert ist.  
  
 Weitere Informationen finden Sie unter [OleCreateStaticFromData](http://msdn.microsoft.com/library/windows/desktop/ms687290), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) im Windows SDK.  
  
##  <a name="deactivate"></a>  COleClientItem::Deactivate  
 Mit dieser Funktion wird zum Deaktivieren der OLE-Element und alle zugeordneten Ressourcen frei.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein direktes active-OLE-Element wird in der Regel deaktivieren, klickt der Benutzer die Maus auf den Clientbereich außerhalb der Grenzen des Elements. Beachten Sie, dass das Deaktivieren von OLE-Element Zustand rückgängig machen es unmöglich, rufen Sie Verwerfen der [ReactivateAndUndo](#reactivateandundo) Memberfunktion.  
  
 Wenn Ihre Anwendung zum Rückgängigmachen unterstützt, rufen Sie nicht `Deactivate`; stattdessen rufen [DeactivateUI](#deactivateui).  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) im Windows SDK.  
  
##  <a name="deactivateui"></a>  COleClientItem::DeactivateUI  
 Rufen Sie diese Funktion, wenn der Benutzer ein Element deaktiviert, die direkt aktiviert wurde.  
  
```  
void DeactivateUI();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion stellt die Benutzeroberfläche der Steuerelementcontainer-Anwendung in den Originalzustand, Ausblenden von alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden wieder her.  
  
 Diese Funktion leert die rückgängig-Statusinformationen für das Element nicht. Dass Informationen beibehalten werden, damit [ReactivateAndUndo](#reactivateandundo) später auszuführende ein Befehl "Rückgängig" in Server-Anwendung verwendet werden, für den Fall, dass der Container-Befehl "Rückgängig" ausgewählt wird, sofort nach dem Deaktivieren des Elements.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) im Windows SDK.  
  
##  <a name="delete"></a>  COleClientItem::Delete  
 Mit dieser Funktion wird zum Löschen von OLE-Element aus dem Containerdokument.  
  
```  
void Delete(BOOL bAutoDelete = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bAutoDelete*  
 Gibt an, ob das Element aus dem Dokument entfernt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft die [Version](#release) Memberfunktion ist, wodurch wiederum die C++-Objekt für das Element, dauerhaft entfernen des OLE-Elements aus dem Dokument gelöscht. Wenn das OLE-Element eingebettet werden, werden die systemeigenen Daten für das Element gelöscht. Es schließt immer einen bereits aktiven Server; aus diesem Grund ist das Element ein Link öffnen, geschlossen, diese Funktion.  
  
##  <a name="dodragdrop"></a>  COleClientItem::DoDragDrop  
 Rufen Sie die `DoDragDrop` Memberfunktion versucht, einen Drag-and-Drop-Vorgang auszuführen.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpItemRect,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpItemRect*  
 Das Element Rechteck auf dem Bildschirm, in Clientkoordinaten (in Pixel).  
  
 *ptOffset*  
 Der Offset vom *LpItemRect* , bei denen die Position des Mauszeigers war zum Zeitpunkt des Ziehvorgangs.  
  
 *bIncludeLink*  
 Legen Sie **"true"** , wenn die Link-Daten in die Zwischenablage kopiert werden sollen. Legen Sie es auf **"false"** Wenn Ihre Serveranwendung Links nicht unterstützt.  
  
 *dwEffects*  
 Bestimmt die Auswirkungen, die die Quelle des Ziehvorgangs in des Ziehvorgangs ermöglichen.  
  
 *lpRectStartDrag*  
 Ein Zeiger auf das Rechteck, das definiert, in dem der Ziehvorgang beginnt. Weitere Informationen finden Sie im folgenden Abschnitt "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DROPEFFECT`-Wert. Ist er `DROPEFFECT_MOVE`, sollte die ursprünglichen Daten entfernt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Drag-and-Drop-Vorgang wird nicht sofort gestartet. Es wartet, bis der Cursor auf das Rechteck, angegeben durch verlässt *LpRectStartDrag* oder bis eine angegebene Anzahl von Millisekunden erfolgreich abgeschlossen wurden. Wenn *LpRectStartDrag* ist **NULL**, die Größe des Rechtecks beträgt ein Pixel.  
  
 Die Verzögerung wird durch eine Einstellung des Registrierungsschlüssels angegeben. Sie können die Verzögerungszeit ändern, durch den Aufruf [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) oder [CWinApp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint). Wenn Sie die Verzögerung nicht angeben, wird ein Standardwert von 200 Millisekunden verwendet. Ziehen Sie Verzögerungszeit werden wie folgt gespeichert:  
  
-   Ziehen Sie die Windows NT-Verzögerungszeit wird in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay gespeichert.  
  
-   Windows 3.x Drag-Verzögerungszeit wird in der WIN gespeichert. INI-Datei im Abschnitt [Windows}.  
  
-   Ziehen Sie die Windows 95-und Windows 98-Verzögerungszeit wird in eine zwischengespeicherte Version der WIN gespeichert. INI.  
  
 Für Weitere Informationen ziehen wird Verzögerung Informationen gespeichert, in der Registrierung oder der. INI-Datei finden Sie unter [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) im Windows SDK.  
  
##  <a name="doverb"></a>  COleClientItem::DoVerb  
 Rufen Sie `DoVerb` das angegebene Verb ausgeführt.  
  
```  
virtual BOOL DoVerb(
    LONG nVerb,  
    CView* pView,
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nVerb*  
 Gibt das Verb ausgeführt. Sie können eine der folgenden enthalten:  
  
|Wert|Bedeutung|Symbol|  
|-----------|-------------|------------|  
|- 0|Primäres Verb|`OLEIVERB_PRIMARY`|  
|- 1|Sekundäre verb|(Keine)|  
|- 1|Artikel für die Bearbeitung anzeigen|`OLEIVERB_SHOW`|  
|- 2|Element in separaten Fenster bearbeiten|`OLEIVERB_OPEN`|  
|- 3|Element ausblenden|`OLEIVERB_HIDE`|  
  
 Der Wert-1 ist in der Regel ein Alias für einen anderen Verb. Wenn Bearbeiten öffnen nicht unterstützt wird, hat-2 dieselbe Wirkung wie – 1. Weitere Werte finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) im Windows SDK.  
  
 *pView*  
 Zeiger auf das Fenster "; Dies wird vom Server für die direkte Aktivierung verwendet werden. Dieser Parameter muss **NULL** Wenn Steuerelementcontainer-Anwendung keine direkte Aktivierung zulässt.  
  
 *lpMsg*  
 Ein Zeiger auf die Nachricht, die zu aktivierenden Elements verursacht hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Verb erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft die [aktivieren](#activate) Memberfunktion, die das Verb ausgeführt. Außerdem Ausnahmen abfängt und zeigt ein Meldungsfeld an den Benutzer, sofern eine ausgelöst wird.  
  
 Wenn das primäre Verb bearbeiten und 0 (null), in angegeben wird der *nVerb* Parameter, die Server-Anwendung wird gestartet, damit das OLE-Element, das bearbeitet werden kann. Wenn die containeranwendung direkte Aktivierung unterstützt, kann bearbeiten festliegen erfolgen. Wenn der Container nicht unterstützt wird, direkte Aktivierung (oder wenn das Verb "Open" angegeben ist), wird der Server in einem separaten Fenster gestartet und bearbeiten kann ausgeführt werden vorhanden. In der Regel, wenn der Benutzer der containeranwendung doppelklickt OLE-Element, den Wert für das primäre Verb in der *nVerb* Parameter bestimmt, welche Aktion der Benutzer ausführen kann. Allerdings bei der Server nur eine Aktion unterstützt wird, dauert es diese Aktion aus, unabhängig davon, welche Wert, in angegeben wird der *nVerb* Parameter.  
  
##  <a name="draw"></a>  COleClientItem::Draw  
 Mit dieser Funktion wird zum Zeichnen des OLE-Elements in der angegebenen umschließende Rechteck mit den angegebenen Gerätekontext.  
  
```  
BOOL Draw(
    CDC* pDC,  
    LPCRECT lpBounds,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Zeiger auf eine [CDC](../../mfc/reference/cdc-class.md) Objekt, das zum Zeichnen der OLE-Element verwendet.  
  
 *lpBounds*  
 Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder `RECT` Struktur, die das umschließende Rechteck in der zum Zeichnen des OLE-Elements (in logischen Einheiten, die durch den Gerätekontext bestimmt) definiert.  
  
 *nDrawAspect*  
 Gibt an, der Aspekt der OLE-Elements, d. h., wie sie angezeigt werden soll. Wenn *nDrawAspect* ist-1 und der letzte Aspekt Festlegung mithilfe von [SetDrawAspect](#setdrawaspect) verwendet wird. Weitere Informationen zu den möglichen Werten für dieses Flag finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion können die Metadateidarstellung des OLE-Elements erstellt, indem die [OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw) Memberfunktion von `COleServerItem`.  
  
 In der Regel **zeichnen** für die Bildschirmanzeige, übergeben Sie den Bildschirm Gerätekontext als *pDC*. In diesem Fall müssen Sie nur die ersten beiden Parameter angeben.  
  
 Die *LpBounds* Parameter identifiziert das Rechteck in der Ziel-Gerätekontext (in Bezug auf seine aktuellen Zuordnungsmodus). Rendering kann zur Folge haben das Bild zu skalieren und kann von containeranwendungen verwendet werden, um eine Ansicht zu erzwingen, die zwischen der Ansicht und das endgültige gedruckten Bild skaliert.  
  
 Weitere Informationen finden Sie unter [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) im Windows SDK.  
  
##  <a name="getactiveview"></a>  COleClientItem::GetActiveView  
 Gibt die Sicht, auf der das Element aktiviert ist.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Sicht; andernfalls **NULL** , wenn das Element kein direktes aktiviert ist.  
  
##  <a name="getcachedextent"></a>  COleClientItem::GetCachedExtent  
 Mit dieser Funktion wird zum Abrufen der Größe der OLE-Element.  
  
```  
BOOL GetCachedExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 *lpSize*  
 Zeiger auf eine **Größe** Struktur oder ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die Informationen zur Datenbankgröße erhält.  
  
 *nDrawAspect*  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen werden abgerufen werden sollen. Mögliche Werte finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn das OLE-Element leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bietet die gleiche Informationen wie [GetExtent](#getextent). Sie können jedoch aufrufen `GetCachedExtent` Umfang Informationen während der Verarbeitung von anderen OLE-Handler, wie z. B. abzurufenden [OnChange](#onchange). Die Dimensionen sind `MM_HIMETRIC` Einheiten.  
  
 Dies ist möglich, da `GetCachedExtent` verwendet die [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) -Schnittstelle anstelle der [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) Schnittstelle, um das Ausmaß der dieses Element abzurufen. Die **IViewObject2** COM-Objekt speichert die Erweiterungsinformationen in den vorhergehenden Aufruf von verwendet [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655).  
  
 Weitere Informationen finden Sie unter [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) im Windows SDK.  
  
##  <a name="getclassid"></a>  COleClientItem::GetClassID  
 Gibt die Klassen-ID des Elements in den Arbeitsspeicher verweist *pClassID*.  
  
```  
void GetClassID(CLSID* pClassID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pClassID*  
 Zeiger auf den Bezeichner eines Typs [CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) zum Abrufen der Klassen-ID. Informationen zu **CLSID**, finden Sie im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Klassen-ID ist eine 128-Bit-Zahl, die eindeutig von der Anwendung, die das Element bearbeitet.  
  
 Weitere Informationen finden Sie unter [IPersist:: GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) im Windows SDK.  
  
##  <a name="getclipboarddata"></a>  COleClientItem::GetClipboardData  
 Mit dieser Funktion wird zum Abrufen einer `COleDataSource` Objekt mit allen Daten, die durch einen Aufruf in der Zwischenablage platziert werden würde die [CopyToClipboard](#copytoclipboard) Memberfunktion.  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataSource*  
 Zeiger auf eine [COleDataSource](../../mfc/reference/coledatasource-class.md) -Objekt, das die enthaltenen Daten in der OLE-Element erhält.  
  
 *bIncludeLink*  
 **"True"** Wenn Verknüpfungsdaten, andernfalls enthalten werden sollen **"false"**.  
  
 *lpOffset*  
 Der Offset des Mauszeigers vom Ursprung des Objekts in Pixel.  
  
 *lpSize*  
 Die Größe des Objekts in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 `GetClipboardData` wird aufgerufen, als die standardmäßige Implementierung des [OnGetClipboardData](#ongetclipboarddata). Überschreiben Sie `OnGetClipboardData` nur, wenn Sie zusätzlich zu den angebotenen Datenformate anbieten möchten `CopyToClipboard`. Platzieren Sie diese Formate in der `COleDataSource` -Objekt vor oder nach dem Aufruf `CopyToClipboard`, und übergeben Sie dann die `COleDataSource` -Objekt an die [COleDataSource](../../mfc/reference/coledatasource-class.md#setclipboard) Funktion. Z. B. wenn OLE-Element Position in dessen Containerdokument, die sie in der Zwischenablage begleitet werden sollen, Sie würden definieren Ihrer eigenen Format für die Weitergabe von Informationen und platzieren Sie es in der `COleDataSource` vor dem Aufruf `CopyToClipboard`.  
  
##  <a name="getdocument"></a>  COleClientItem::GetDocument  
 Rufen Sie diese Funktion, um einen Zeiger auf das Dokument zu erhalten, die das OLE-Element enthält.  
  
```  
COleDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das OLE-Element enthält. **NULL** ist das Element nicht Teil eines Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger ermöglicht den Zugriff auf die `COleDocument` Objekt, das Sie als Argument übergeben der `COleClientItem` Konstruktor.  
  
##  <a name="getdrawaspect"></a>  COleClientItem::GetDrawAspect  
 Rufen Sie die `GetDrawAspect` Memberfunktion der aktuellen "Aspekt" oder die Ansicht des Elements zu bestimmen.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DVASPECT` Enumeration, deren Werte, in der Referenz für aufgeführt sind [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Hinweise  
 Der Aspekt gibt an, wie das Element gerendert werden soll.  
  
##  <a name="getextent"></a>  COleClientItem::GetExtent  
 Mit dieser Funktion wird zum Abrufen der Größe der OLE-Element.  
  
```  
BOOL GetExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```  
  
### <a name="parameters"></a>Parameter  
 *lpSize*  
 Zeiger auf eine **Größe** Struktur oder ein `CSize` -Objekt, das die Informationen zur Datenbankgröße erhält.  
  
 *nDrawAspect*  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen werden abgerufen werden sollen. Mögliche Werte finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn das OLE-Element leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Anwendung für die Verwendung der Microsoft Foundation Class-Bibliothek geschrieben wurde, diese Funktion führt dazu, dass die [OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent) Memberfunktion der entsprechenden `COleServerItem` Objekt aufgerufen werden. Beachten Sie, dass die abgerufenen Größe sich von der Größe, die zuletzt unterscheiden die [SetExtent](#setextent) Memberfunktion; die Größe von angegebenen `SetExtent` so behandelt, als einen Vorschlag. Die Dimensionen sind `MM_HIMETRIC` Einheiten.  
  
> [!NOTE]
>  Rufen Sie nicht `GetExtent` während der Verarbeitung einen OLE-Handler, wie z. B. [OnChange](#onchange). Rufen Sie [GetCachedExtent](#getcachedextent) stattdessen.  
  
 Weitere Informationen finden Sie unter [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) im Windows SDK.  
  
##  <a name="geticonfromregistry"></a>  COleClientItem::GetIconFromRegistry  
 Rufen Sie diese Memberfunktion, um ein Handle für die Symbolressource des Servers von einem bestimmten CLSID abzurufen.  
  
```  
HICON GetIconFromRegistry() const;  
  
static HICON GetIconFromRegistry(CLSID& clsid);
```  
  
### <a name="parameters"></a>Parameter  
 *clsid*  
 Ein Verweis auf die CLSID für den Server, auf das Symbol zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiges Handle zu die Symbolressource oder **NULL** , wenn das Symbol des Servers oder ein Standardsymbol nicht gefunden werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion auf den Server gestartet wird oder ein Symbol dynamisch abzurufen, selbst wenn der Server bereits ausgeführt wird. Stattdessen wird diese Memberfunktion ausführbares Image des Servers öffnet und ruft das Symbol "statische" dem Server zugeordnet ist, wie er registriert wurde.  
  
##  <a name="geticonicmetafile"></a>  COleClientItem::GetIconicMetafile  
 Ruft die Metadatei, die zum Zeichnen des Symbols ab.  
  
```  
HGLOBAL GetIconicMetafile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf die Metadatei im Erfolgsfall; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine aktuelle Symbol vorhanden ist, wird ein Standardsymbol zurückgegeben. Dies wird automatisch aufgerufen, indem Sie die MFC/OLE-Dialogfelder und wird in der Regel nicht direkt aufgerufen.  
  
 Diese Funktion ruft auch [SetIconicMetafile](#seticonicmetafile) die Metadatei zur späteren Verwendung zwischenspeichern.  
  
##  <a name="getinplacewindow"></a>  COleClientItem::GetInPlaceWindow  
 Rufen Sie die `GetInPlaceWindow` Memberfunktion versucht, einen Zeiger auf das Fenster, in dem das Element geöffnet wurde, für die direkte Bearbeitung zu erhalten.  
  
```  
CWnd* GetInPlaceWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Element Fenster zur direkten Bearbeitung; **NULL** , wenn das Element nicht aktiv ist oder wenn der Server nicht verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur für Elemente aufgerufen werden, die in-Place aktiv sind.  
  
##  <a name="getitemstate"></a>  COleClientItem::GetItemState  
 Mit dieser Funktion wird zum aktuellen Status der OLE-Element abzurufen.  
  
```  
UINT GetItemState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COleClientItem:: ItemState** Enumerationswert, der in der folgenden Werte sind möglich: `emptyState`, `loadedState`, `openState`, `activeState`, `activeUIState`. Informationen zu diesen Statuswerten finden Sie im Artikel [Container: Client-Element-Zustände](../../mfc/containers-client-item-states.md).  
  
### <a name="remarks"></a>Hinweise  
 Um benachrichtigt zu werden, wenn das OLE-Element Zustand ändert verwenden die [OnChange](#onchange) Memberfunktion.  
  
 Weitere Informationen finden Sie im Artikel [Container: Client-Element-Zustände](../../mfc/containers-client-item-states.md).  
  
##  <a name="getlaststatus"></a>  COleClientItem::GetLastStatus  
 Gibt den Statuscode des letzten OLE-Vorgangs zurück.  
  
```  
SCODE GetLastStatus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `SCODE`-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Für Member-Funktionen zurückgegebene eine **BOOL** Wert **"false"**, oder andere Memberfunktionen zurückgegebene **NULL**, `GetLastStatus` ausführlichere Fehlerinformationen zurückgegeben. Denken Sie daran, dass die meisten Memberfunktionen der OLE-Ausnahmen für schwerwiegenderen Fehler auslöst. Die spezifischen Informationen zur Interpretation von der `SCODE` hängt von der zugrunde liegenden OLE-Aufruf, der zuletzt zurückgegebene ein `SCODE` Wert.  
  
 Weitere Informationen zu `SCODE`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in das Windows SDK-Dokumentation.  
  
##  <a name="getlinkupdateoptions"></a>  COleClientItem::GetLinkUpdateOptions  
 Mit dieser Funktion wird zum Abrufen des aktuellen Wert der Option zur Link-Update für das OLE-Element.  
  
```  
OLEUPDATE GetLinkUpdateOptions();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- `OLEUPDATE_ALWAYS` Das verknüpfte Element nach Möglichkeit zu aktualisieren. Diese Option unterstützt das Optionsfeld automatische Link-Update im Dialogfeld "Verknüpfungen".  
  
- `OLEUPDATE_ONCALL` Aktualisieren Sie das verknüpfte Element nur auf Anforderung aus dem Steuerelementcontainer-Anwendung (wenn die [UpdateLink](#updatelink) Memberfunktion aufgerufen wird). Diese Option unterstützt das Optionsfeld manuelle Link-Update im Dialogfeld "Verknüpfungen".  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein erweiterter Vorgang.  
  
 Diese Funktion wird automatisch von der [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) Klasse.  
  
 Weitere Informationen finden Sie unter [IOleLink::GetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680100) im Windows SDK.  
  
##  <a name="gettype"></a>  COleClientItem::GetType  
 Mit dieser Funktion wird zum bestimmen, ob der OLE-Element eingebettet oder verknüpft ist oder statische.  
  
```  
OLE_OBJTYPE GetType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Ganzzahl ohne Vorzeichen mit einem der folgenden Werte:  
  
- `OT_LINK` OLE-Element ist ein Link.  
  
- `OT_EMBEDDED` OLE-Element eingebettet ist.  
  
- `OT_STATIC` OLE-Element statisch ist, bedeutet, dass er nur Präsentationsdaten, nicht einheitlichen Daten enthält und daher kann nicht bearbeitet werden kann.  
  
##  <a name="getusertype"></a>  COleClientItem::GetUserType  
 Mit dieser Funktion können die Benutzer sichtbare Zeichenfolge, die das OLE-Element-Typ, z. B. "Word-Dokument" beschreibt abrufen  
  
```  
void GetUserType(
    USERCLASSTYPE nUserClassType,  
    CString& rString);
```  
  
### <a name="parameters"></a>Parameter  
 *nUserClassType*  
 Ein Wert, der angibt, der gewünschte Variante der Zeichenfolge, die OLE-Element-Typ beschreibt. Dies kann einen der folgenden Werte aufweisen:  
  
- `USERCLASSTYPE_FULL` Der vollständige Typname, der dem Benutzer angezeigt.  
  
- `USERCLASSTYPE_SHORT` Ein kurzer Name (maximal 15 Zeichen) für die Verwendung in Popupmenüs und das Dialogfeld "Verknüpfungen bearbeiten".  
  
- `USERCLASSTYPE_APPNAME` Der Name der Anwendung, die Wartung der-Klasse.  
  
 *rString*  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, in dem die Zeichenfolge, die OLE-Element-Typ beschreibt zurückgegeben werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist häufig der Eintrag in der Registrierung-Systemdatenbank.  
  
 Wenn der vollständige Typname angeforderte jedoch nicht verfügbar ist, wird der Kurzname stattdessen verwendet. OLE-Element wird verwendet, wenn kein Eintrag für den Typ des OLE-Element in der Registrierungsdatenbank gefunden wird, oder es sind keine Benutzertypen, die für den Typ des OLE-Element registriert, klicken Sie dann den Benutzertyp derzeit in gespeichert. Wenn dieser Typ Benutzernamen eine leere Zeichenfolge ist, wird "Unbekannte Object" verwendet.  
  
 Weitere Informationen finden Sie unter [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) im Windows SDK.  
  
##  <a name="isinplaceactive"></a>  COleClientItem::IsInPlaceActive  
 Rufen Sie diese Funktion, um festzustellen, ob der OLE-Element in-Place aktiv ist.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das OLE-Element in-Place aktiv ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Es ist üblich, je nachdem, ob das Element direkt bearbeitet wird eine unterschiedliche Logik ausgeführt werden. Die Funktion überprüft, ob der aktuelle Zustand des Elements entweder gleich ist die `activeState` oder `activeUIState`.  
  
##  <a name="islinkuptodate"></a>  COleClientItem::IsLinkUpToDate  
 Rufen Sie diese Funktion, um festzustellen, ob der OLE-Element auf dem neuesten Stand ist.  
  
```  
BOOL IsLinkUpToDate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das OLE-Element auf dem neuesten Stand ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein verknüpftes Element kann veraltet sein, wenn seine Quelldokument aktualisiert wurde. Ein eingebettetes Element, das Links darin enthält kann auf ähnliche Weise veralten. Die Funktion ist eine rekursive Prüfung des OLE-Elements. Beachten Sie, dass so teuer wie tatsächlich ein Update ausgeführt werden kann, bestimmen, ob ein OLE-Element nicht mehr aktuell ist.  
  
 Hierbei spricht automatisch von der [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) Implementierung.  
  
 Weitere Informationen finden Sie unter [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) im Windows SDK.  
  
##  <a name="ismodified"></a>  COleClientItem::IsModified  
 Rufen Sie diese Funktion, um festzustellen, ob der OLE-Element geändert wurde (wird geändert, seit es zuletzt gespeichert wurde).  
  
```  
BOOL IsModified() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das OLE-Element geändert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) im Windows SDK.  
  
##  <a name="isopen"></a>  COleClientItem::IsOpen  
 Rufen Sie diese Funktion, um festzustellen, ob der OLE-Element geöffnet ist. d. h. in einer Instanz von die Serveranwendung ausgeführt wird, in einem separaten Fenster geöffnet.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das OLE-Element geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Es dient zum Ermitteln, wann das Objekt mit einem Schraffurmuster, das gezeichnet werden soll. Ein Objekt öffnen müssen eine Schraffur auf das Objekt gezeichnet. Sie können eine [CRectTracker](../../mfc/reference/crecttracker-class.md) Objekt, um dies zu erreichen.  
  
##  <a name="isrunning"></a>  COleClientItem::IsRunning  
 Rufen Sie diese Funktion, um festzustellen, ob der OLE-Element ausgeführt wird. Gibt an, ob das Element geladen und ausgeführt, in der Serveranwendung ist.  
  
```  
BOOL IsRunning() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das OLE-Element ausgeführt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OleIsRunning](http://msdn.microsoft.com/library/windows/desktop/ms688705) im Windows SDK.  
  
##  <a name="onactivate"></a>  COleClientItem::OnActivate  
 Wird aufgerufen, durch das Framework dem Element benachrichtigt, dass er nur festliegen aktiviert wurde.  
  
```  
virtual void OnActivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass diese Funktion aufgerufen wird, um anzugeben, dass der Server ausgeführt wird, nicht, um anzugeben, dass die Benutzeroberfläche in der Steuerelementcontainer-Anwendung installiert wurde, ein. Das Objekt verfügt an diesem Punkt nicht über eine aktive Benutzeroberfläche (nicht `activeUIState`). Sie hat nicht die Menüs oder Symbolleisten installiert. Die [OnActivateUI](#onactivateui) Member-Funktion wird aufgerufen, wenn dies geschieht.  
  
 Die Standardimplementierung Ruft die [OnChange](#onchange) Memberfunktion mit **OLE_CHANGEDSTATE** als Parameter. Überschreiben Sie diese Funktion zum Ausführen benutzerdefinierter Verarbeitung, wenn ein Element in-Place aktiv wird.  
  
##  <a name="onactivateui"></a>  COleClientItem::OnActivateUI  
 Das Framework ruft `OnActivateUI` Wenn das Objekt der aktiven Benutzeroberflächenzustand gewechselt hat.  
  
```  
virtual void OnActivateUI();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wurde jetzt die Symbolleiste und Menüs installiert.  
  
 Die standardmäßige Implementierung speichert des Servers `HWND` für die spätere **GetServerWindow** aufrufen.  
  
##  <a name="onchange"></a>  COleClientItem:: OnChange  
 Vom Framework aufgerufen, wenn der Benutzer ändert, speichert oder das OLE-Element schließt.  
  
```  
virtual void OnChange(
    OLE_NOTIFICATION nCode,  
    DWORD dwParam);
```  
  
### <a name="parameters"></a>Parameter  
 *nCode*  
 Der Grund der Server geändert, dieses Element aus. Es kann einen der folgenden Werte aufweisen:  
  
- `OLE_CHANGED` Darstellung der OLE-Element wurde geändert.  
  
- `OLE_SAVED` OLE-Element wurde gespeichert.  
  
- `OLE_CLOSED` OLE-Element wurde geschlossen.  
  
- `OLE_CHANGED_STATE` OLE-Element wurde von einem Zustand in einen anderen geändert.  
  
 *dwParam*  
 Wenn *nCode* ist `OLE_SAVED` oder `OLE_CLOSED`, dieser Parameter wird nicht verwendet. Wenn *nCode* ist `OLE_CHANGED`, dieser Parameter gibt den Aspekt des OLE-Elements, das geändert wurde. Mögliche Werte finden Sie unter der *DwParam* Parameter [COleClientItem::Draw](#draw). Wenn *nCode* ist `OLE_CHANGED_STATE`, dieser Parameter ist ein **COleClientItem:: ItemState** Enumerationswert und beschreibt den Status eingegeben werden. Es kann einen der folgenden Werte aufweisen: `emptyState`, `loadedState`, `openState`, `activeState`, oder `activeUIState`.  
  
### <a name="remarks"></a>Hinweise  
 (Wenn die Anwendung für die Verwendung der Microsoft Foundation Class-Bibliothek geschrieben wird, wird diese Funktion aufgerufen, als Antwort auf die `Notify` Memberfunktionen der `COleServerDoc` oder `COleServerItem`.) Die standardmäßige Implementierung Containerdokument markiert, als wenn geändert *nCode* ist `OLE_CHANGED` oder `OLE_SAVED`.  
  
 Für `OLE_CHANGED_STATE`, den aktuellen Status von zurückgegebenen [GetItemState](#getitemstate) werden immer noch der alte Status, d. h. den Zustand, der vor dieser Änderung war.  
  
 Überschreiben Sie diese Funktion zum Reagieren auf statusänderungen finden Sie in der OLE-Element. In der Regel aktualisieren Sie die Darstellung des Elements durch ungültig macht den Bereich, in dem das Element angezeigt wird. Rufen Sie die basisklassenimplementierung am Anfang der Außerkraftsetzung.  
  
##  <a name="onchangeitemposition"></a>  COleClientItem:: OnChangeItemPosition auf  
 Wird aufgerufen, durch das Framework den Container zu benachrichtigen, den dass das OLE-Element-Block während der direkten Aktivierung geändert hat.  
  
```  
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```  
  
### <a name="parameters"></a>Parameter  
 *rectPos*  
 Gibt das Element Position relativ zum Clientbereich der Steuerelementcontainer-Anwendung an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Position des Elements erfolgreich geändert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung bestimmt das neue sichtbar Rechteck des OLE-Element und ruft [SetItemRects](#setitemrects) mit den neuen Werten. Die standardmäßige Implementierung für das Element sichtbar Rechtecks berechnet und übergibt diese Informationen an den Server.  
  
 Überschreiben Sie diese Funktion zum gelten spezielle Regeln für den Vorgang zum Ändern der Größe/verschieben. Wenn die Anwendung in MFC geschrieben ist, wird dieser Aufruf führt, weil der Server bezeichnet [COleServerDoc::RequestPositionChange](../../mfc/reference/coleserverdoc-class.md#requestpositionchange).  
  
##  <a name="ondeactivate"></a>  COleClientItem::OnDeactivate  
 Vom Framework aufgerufen, wenn das OLE-Element von direkten aktiven Zustand übergeht ( `activeState`) in den geladenen Zustand, was bedeutet, dass es nach einer direkten Aktivierung deaktiviert ist.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass diese Funktion aufgerufen wird, um anzugeben, dass das OLE-Element, nicht geschlossen wird, die zugehörige Benutzeroberfläche aus dem Steuerelementcontainer-Anwendung entfernt wurde. In diesem Fall die [OnDeactivateUI](#ondeactivateui) Memberfunktion aufgerufen wird.  
  
 Die Standardimplementierung Ruft die [OnChange](#onchange) Memberfunktion mit **OLE_CHANGEDSTATE** als Parameter. Überschreiben Sie diese Funktion zum Ausführen der benutzerdefinierten Verarbeitung, wenn ein direkte aktive Element deaktiviert wird. Z. B. Wenn Sie den Befehl "Rückgängig" in der containeranwendung unterstützen, können Sie Überschreiben dieser Funktion können Sie den Zustand "Rückgängig" zu verwerfen, der angibt, dass der letzte Vorgang für das OLE-Element ausgeführt kann nicht rückgängig gemacht werden, nachdem das Element deaktiviert wird.  
  
##  <a name="ondeactivateandundo"></a>  COleClientItem::OnDeactivateAndUndo  
 Wird vom Framework aufgerufen, wenn der Benutzer den Befehl "Rückgängig" aufruft, nach der Aktivierung der OLE-Element vorhanden.  
  
```  
virtual void OnDeactivateAndUndo();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft [DeactivateUI](#deactivateui) So deaktivieren Sie den Server-Benutzeroberfläche. Überschreiben Sie diese Funktion, wenn Sie den Befehl "Rückgängig" in der containeranwendung implementieren. In der Überschreibung Aufrufen der Funktion der Basisklassenversion und rückgängig machen Sie dann mit dem letzten Befehl in Ihrer Anwendung ausgeführt.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::DeactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms683743) im Windows SDK.  
  
##  <a name="ondeactivateui"></a>  COleClientItem::OnDeactivateUI  
 Wird aufgerufen, wenn der Benutzer ein Element deaktiviert, die direkt aktiviert wurde.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Parameter  
 *bUndoable*  
 Gibt an, ob die Bearbeitung rückgängig zu machen sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion stellt die Benutzeroberfläche der Steuerelementcontainer-Anwendung in den Originalzustand, Ausblenden von alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden wieder her.  
  
 Wenn *bUndoable* ist **"false"**, der Container sollte der Befehl "Rückgängig" deaktivieren, ist nicht wirksam Verwerfen von Rückgängig-Zustand des Containers, da darauf, dass der letzte Vorgang vom Server ausgeführt rückgängig gemacht werden.  
  
##  <a name="ondiscardundostate"></a>  COleClientItem::OnDiscardUndoState  
 Vom Framework aufgerufen, wenn der Benutzer eine Aktion ausführt, die wieder rückgängig zu machen, die beim Bearbeiten der OLE-Element werden verworfen.  
  
```  
virtual void OnDiscardUndoState();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, wenn Sie den Befehl "Rückgängig" in der containeranwendung implementieren. Verwerfen Sie die containeranwendung rückgängig Zustand, in der Außerkraftsetzung.  
  
 Wenn der Server mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, der Server kann dazu führen, dass diese Funktion, die durch den Aufruf aufgerufen werden [COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate).  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::DiscardUndoState](http://msdn.microsoft.com/library/windows/desktop/ms688642) im Windows SDK.  
  
##  <a name="ongetclipboarddata"></a>  COleClientItem::OnGetClipboardData  
 Vom Framework abzurufenden aufgerufen, eine `COleDataSource` Objekt mit allen Daten, die durch einen Aufruf von entweder in der Zwischenablage platziert werden würde die [CopyToClipboard](#copytoclipboard) oder [DoDragDrop](#dodragdrop) Memberfunktion.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>Parameter  
 *bIncludeLink*  
 Legen Sie **"true"** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. Legen Sie **"false"** Wenn Ihre Serveranwendung Links nicht unterstützt.  
  
 *lpOffset*  
 Zeiger auf den Offset des Mauszeigers vom Ursprung des Objekts in Pixel.  
  
 *lpSize*  
 Zeiger auf die Größe des Objekts in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt, das Daten aus der Zwischenablage enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion [GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetcliprect"></a>  COleClientItem::OnGetClipRect  
 Das Framework Ruft die `OnGetClipRect` Memberfunktion versucht, erhalten das Clippingrechteck Koordinaten des Elements, das gerade bearbeitet wird, vorhanden.  
  
```  
virtual void OnGetClipRect(CRect& rClipRect);
```  
  
### <a name="parameters"></a>Parameter  
 *rClipRect*  
 Zeiger auf ein Objekt der Klasse [CRect](../../atl-mfc-shared/reference/crect-class.md) , wird das Clippingrechteck Koordinaten des Elements aufnehmen.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zum Clientbereich im Container Anwendungsfenster angezeigt.  
  
 Die Standardimplementierung gibt einfach Clientrechteck des der Sicht, auf der das Element in-Place aktiv ist.  
  
##  <a name="ongetitemposition"></a>  COleClientItem:: OnGetItemPosition auf  
 Das Framework Ruft die `OnGetItemPosition` Memberfunktion versucht, erhalten die Koordinaten des Elements, das gerade bearbeitet wird, vorhanden.  
  
```  
virtual void OnGetItemPosition(CRect& rPosition);
```  
  
### <a name="parameters"></a>Parameter  
 *rposition zurück*  
 Ein Verweis auf die [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das das Element Positionskoordinaten enthalten wird.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zum Clientbereich im Container Anwendungsfenster angezeigt.  
  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Anwendungen, die direkte Bearbeitung unterstützen müssen ihre Implementierung.  
  
##  <a name="ongetwindowcontext"></a>  COleClientItem::OnGetWindowContext  
 Vom Framework aufgerufen, wenn ein Element direkt aktiviert ist.  
  
```  
virtual BOOL OnGetWindowContext(
    CFrameWnd** ppMainFrame,  
    CFrameWnd** ppDocFrame,  
    LPOLEINPLACEFRAMEINFO lpFrameInfo);
```  
  
### <a name="parameters"></a>Parameter  
 *ppMainFrame*  
 Ein Zeiger auf einen Zeiger auf das Hauptrahmenfenster.  
  
 *ppDocFrame*  
 Ein Zeiger auf einen Zeiger auf die Dokumentrahmenfenster.  
  
 *lpFrameInfo*  
 Zeiger auf eine [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) -Struktur, die Frame-Fensters-Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion dient zum Abrufen von Informationen über OLE-Element des übergeordneten Fensters.  
  
 Wenn der Container eine MDI-Anwendung ist, wird die standardmäßige Implementierung gibt einen Zeiger auf die [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) -Objekt in *PpMainFrame* und einen Zeiger auf die aktive [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)-Objekt in *PpDocFrame*. Wenn der Container eine SDI-Anwendung ist, wird die standardmäßige Implementierung gibt einen Zeiger auf die [CFrameWnd](../../mfc/reference/cframewnd-class.md) -Objekt in *PpMainFrame* und gibt **NULL** in  *PpDocFrame*. Füllt die standardmäßige Implementierung auch die Mitglieder der *LpFrameInfo*.  
  
 Überschreiben Sie diese Funktion nur, wenn die standardmäßige Implementierung Ihrer Anwendung nicht geeignet ist; beispielsweise, wenn die Anwendung eine Sichtweise der Benutzeroberfläche, die von SDI- oder MDI-abweicht. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms694366) und [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) Struktur im Windows SDK.  
  
##  <a name="oninsertmenus"></a>  COleClientItem::OnInsertMenus  
 Vom Framework aufgerufen, während der direkten Aktivierung die containeranwendung Menüs in ein leeres Menü eingefügt.  
  
```  
virtual void OnInsertMenus(
    CMenu* pMenuShared,  
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```  
  
### <a name="parameters"></a>Parameter  
 *pMenuShared*  
 Verweist auf ein leeres Menü.  
  
 *lpMenuWidths*  
 Zeigt auf ein Array von sechs **lange** Werte, der angibt, wie viele Menüs in jeder der folgenden Menügruppen sind: Datei, bearbeiten, Container, Fenster Objekt-Hilfe. Die Container-Anwendung ist verantwortlich für die Datei, Container und Fenster Menügruppen, Elemente, 0, 2 und 4 dieses Arrays entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Menü wird dann an den Server übergeben, die eigene Menüs, Erstellen eines zusammengesetzten Menüs einfügt. Diese Funktion kann wiederholt aufgerufen werden, um mehrere zusammengesetzte Menüs zu erstellen.  
  
 Fügt die standardmäßige Implementierung *pMenuShared* den direkten Containermenüs, d. h. der Datei, Container und Fenster Menügruppen. [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo) wird verwendet, um diese Menüressource festgelegt. Die standardmäßige Implementierung weist auch die entsprechenden Werte auf die Elemente 0, 2 und 4 im *LpMenuWidths*, je nachdem, auf die Menüressource. Überschreiben Sie diese Funktion, wenn die standardmäßige Implementierung nicht für Ihre Anwendung geeignet ist; beispielsweise, wenn die Anwendung für das Zuordnen von Ressourcen zu Dokumenttypen keine Dokumentvorlagen verwendet. Wenn Sie diese Funktion überschreiben, sollten Sie auch überschreiben [OnSetMenu](#onsetmenu) und [OnRemoveMenus](#onremovemenus). Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceFrame::InsertMenus](http://msdn.microsoft.com/library/windows/desktop/ms683987) im Windows SDK.  
  
##  <a name="onremovemenus"></a>  COleClientItem::OnRemoveMenus  
 Wird aufgerufen, durch das Framework des Containers Menüs angegebene zusammengesetzte Menü entfernen, wenn direkte Aktivierung beendet.  
  
```  
virtual void OnRemoveMenus(CMenu* pMenuShared);
```  
  
### <a name="parameters"></a>Parameter  
 *pMenuShared*  
 Verweist auf das zusammengesetzte Menü erstellt, die durch Aufrufe der [OnInsertMenus](#oninsertmenus) Memberfunktion.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung entfernt aus *pMenuShared* den direkten Containermenüs, die, die Datei, Container und Fenster Menügruppen. Überschreiben Sie diese Funktion, wenn die standardmäßige Implementierung nicht für Ihre Anwendung geeignet ist; beispielsweise, wenn die Anwendung für das Zuordnen von Ressourcen zu Dokumenttypen keine Dokumentvorlagen verwendet. Wenn Sie diese Funktion überschreiben, müssen Sie wahrscheinlich überschreiben [OnInsertMenus](#oninsertmenus) und [OnSetMenu](#onsetmenu) ebenfalls. Dies ist eine erweiterte überschrieben.  
  
 Die Untermenüs auf *pMenuShared* möglicherweise über mehr als eine zusammengesetzte Menü "freigegeben werden, wenn der Server wiederholt aufgerufen hat `OnInsertMenus`. Aus diesem Grund sollten Sie alle Untermenüs nicht löschen, in der Überschreibung der `OnRemoveMenus`; Sie sollten nur trennen.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceFrame::RemoveMenus](http://msdn.microsoft.com/library/windows/desktop/ms688685) im Windows SDK.  
  
##  <a name="onscrollby"></a>  COleClientItem::OnScrollBy  
 Vom Framework aufgerufen, die OLE-Element als Antwort auf Anforderungen vom Server zu scrollen.  
  
```  
virtual BOOL OnScrollBy(CSize sizeExtent);
```  
  
### <a name="parameters"></a>Parameter  
 *sizeExtent*  
 Gibt die Abstände in Pixel, erfahren Sie, wie in der x- und y-Achse zu scrollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element ein Bildlauf ausgeführt wurde; 0, wenn das Element nicht gescrollt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Beispielsweise wird, wenn das OLE-Element teilweise sichtbar ist, und der Benutzer, die außerhalb des sichtbaren Bereichs beim Ausführen der direkte Bearbeitung bewegt, diese Funktion aufgerufen, um den Cursor sichtbar bleiben. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um das Element um den angegebenen Betrag zu scrollen. Beachten Sie, dass als Ergebnis scrollen, der sichtbare Teil der OLE-Element ändern kann. Rufen Sie [SetItemRects](#setitemrects) sichtbar Rechteck für das Element zu aktualisieren.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::Scroll](http://msdn.microsoft.com/library/windows/desktop/ms690291) im Windows SDK.  
  
##  <a name="onsetmenu"></a>  COleClientItem::OnSetMenu  
 Vom Framework aufgerufen, zwei Mal bei der direkten Aktivierung beginnt und endet; So installieren Sie das zusammengesetzte Menü und ein zweites Mal beim ersten (mit *Holemenu* gleich **NULL**) zu entfernen.  
  
```  
virtual void OnSetMenu(
    CMenu* pMenuShared,  
    HOLEMENU holemenu,  
    HWND hwndActiveObject);
```  
  
### <a name="parameters"></a>Parameter  
 *pMenuShared*  
 Zeiger auf das zusammengesetzte Menü erstellt, die durch Aufrufe der [OnInsertMenus](#oninsertmenus) Memberfunktion und die `InsertMenu` Funktion.  
  
 *holemenu*  
 Handle für den Menü-Deskriptor zurückgegebenes der **OleCreateMenuDescriptor** -Funktion oder **NULL** Wenn verteilen Code entfernt werden.  
  
 *hwndActiveObject*  
 Handle für das Fenster für das OLE-Element. Dies ist das Fenster, das die Befehle zum Bearbeiten von OLE empfangen wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung installiert oder entfernt das zusammengesetzte Menü und ruft dann die [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831) Funktion zu installieren oder entfernen Sie den Code verteilen. Überschreiben Sie diese Funktion, wenn die standardmäßige Implementierung nicht für Ihre Anwendung geeignet ist. Wenn Sie diese Funktion überschreiben, müssen Sie wahrscheinlich überschreiben [OnInsertMenus](#oninsertmenus) und [OnRemoveMenus](#onremovemenus) ebenfalls. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [OleCreateMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms691415), [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831), und [SetMenu](http://msdn.microsoft.com/library/windows/desktop/ms693713) im Windows SDK.  
  
##  <a name="onshowcontrolbars"></a>  COleClientItem::OnShowControlBars  
 Wird aufgerufen, durch das Framework ein-und Ausblenden von Steuerleisten Steuerelementcontainer-Anwendung.  
  
```  
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 *pFrameWnd*  
 Ein Zeiger auf die containeranwendung Rahmenfenster. Dies kann entweder einem Hauptrahmenfenster oder ein untergeordnetes MDI-Fenster sein.  
  
 *bShow*  
 Gibt an, ob die Steuerleisten ein-oder ausgeblendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Aufruf der Funktion bewirkt, dass eine Änderung in den Steuerleisten Status; 0, wenn der Aufruf bewirkt, dass keine Änderung oder *pFrameWnd* zeigt nicht auf den Container Rahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt 0 zurück, wenn die Steuerleisten bereits vom angegebenen Zustand werden *bShow.* Dies würde z. B. auftreten, wenn die Steuerleisten ausgeblendet sind und *bShow* ist **"false"**.  
  
 Die standardmäßige Implementierung entfernt die Symbolleiste im Fenster Framefenster auf oberster Ebene an.  
  
##  <a name="onshowitem"></a>  COleClientItem::OnShowItem  
 Wird aufgerufen, durch das Framework zum Anzeigen des OLE-Elements, das während der Bearbeitung vollständig sichtbar gemacht.  
  
```  
virtual void OnShowItem();
```  
  
### <a name="remarks"></a>Hinweise  
 Wird verwendet, wenn Ihre containeranwendung Links zu eingebetteten Elementen unterstützt (d. h., wenn Sie Ihre Dokumentklasse aus abgeleiteten [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)). Diese Funktion wird aufgerufen, während die direkte Aktivierung oder wenn das OLE-Element ein Link-Quelle ist und der Benutzer möchte, um ihn zu bearbeiten. Die standardmäßige Implementierung wird die erste Ansicht, für das Containerdokument aktiviert. Überschreiben Sie diese Funktion, um das Dokument einen Bildlauf durchführen, damit der OLE-Element angezeigt wird.  
  
##  <a name="onupdateframetitle"></a>  COleClientItem::OnUpdateFrameTitle  
 Vom Framework aufgerufen, während der direkten Aktivierung das Rahmenfenster Titelleiste zu aktualisieren.  
  
```  
virtual BOOL OnUpdateFrameTitle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn diese Funktion wurde erfolgreich aktualisiert die Frametitel, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ändert nicht den Frame Window-Titel. Überschreiben Sie diese Funktion, wenn Sie einen anderen Frametitel für Ihre Anwendung b. z. " *Server app* - *Element* in *Docname*" (wie etwa in "Microsoft Excel - Arbeitsblatt im Bericht. DOC"). Dies ist eine erweiterte überschrieben.  
  
##  <a name="reactivateandundo"></a>  COleClientItem::ReactivateAndUndo  
 Mit dieser Funktion wird zum Reaktivieren der OLE-Element und den letzten Vorgang, der vom Benutzer ausgeführt werden, während die direkte Bearbeitung rückgängig zu machen.  
  
```  
BOOL ReactivateAndUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre containeranwendung über den Befehl "Rückgängig" unterstützt, rufen Sie diese Funktion, wenn der Benutzer den Befehl "Rückgängig" entscheidet, sofort nach dem Deaktivieren von OLE-Element.  
  
 Wenn die Server-Anwendung mit der Microsoft Foundation Class Libraries geschrieben wurde, diese Funktion bewirkt, dass der Server Aufrufen [COleServerDoc::OnReactivateAndUndo](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo).  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) im Windows SDK.  
  
##  <a name="release"></a>  COleClientItem::Release  
 Mit dieser Funktion wird zum Bereinigen von Ressourcen, die von der OLE-Element verwendet.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Parameter  
 *dwCloseOption*  
 Kennzeichen, das angibt, unter welchen Umständen der OLE-Element gespeichert wird, wenn er in den geladenen Zustand zurückversetzt. Eine Liste der möglichen Werte finden Sie unter [COleClientItem::Close](#close).  
  
### <a name="remarks"></a>Hinweise  
 `Release` wird aufgerufen, indem die `COleClientItem` Destruktor.  
  
 Weitere Informationen finden Sie unter [IUnknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) im Windows SDK.  
  
##  <a name="reload"></a>  COleClientItem::Reload  
 Wird geschlossen, und lädt das Element.  
  
```  
BOOL Reload();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `Reload` -Funktion nach Aktivierung des Elements als ein Element eines anderen Typs durch einen Aufruf von [ActivateAs](#activateas).  
  
##  <a name="run"></a>  COleClientItem::Run  
 Führt die Anwendung, die diesem Element zugeordnet.  
  
```  
void Run();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `Run` Memberfunktion zum Starten der Serveranwendung vor dem Aktivieren des Elements. Dies erfolgt automatisch vom [aktivieren](#activate) und [DoVerb](#doverb), daher ist es in der Regel nicht notwendig, diese Funktion aufzurufen. Mit dieser Funktion wird bei Bedarf auf dem Server ausgeführt werden, um ein Elementattribut festzulegen, wie z. B. [SetExtent](#setextent), vor der Ausführung [DoVerb](#doverb).  
  
##  <a name="setdrawaspect"></a>  COleClientItem::SetDrawAspect  
 Rufen Sie die `SetDrawAspect` Memberfunktion zum Festlegen von "Aspekt" oder die Ansicht des Elements.  
  
```  
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Parameter  
 *nDrawAspect*  
 Ein Wert aus der `DVASPECT`-Enumeration. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT` Element wird so dargestellt, als eingebettetes Objekt in dessen Container angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL` Damit es in einem Browser angezeigt werden kann, wird in eine Darstellung "Miniaturansicht" Element gerendert.  
  
- `DVASPECT_ICON` Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT` Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Der Aspekt gibt an, wie das Element gerendert werden [zeichnen](#draw) Wenn der Standardwert für diese Funktion `nDrawAspect` Argument verwendet wird.  
  
 Diese Funktion wird automatisch aufgerufen, durch das Symbol "ändern" (und andere Dialogfelder, die im Dialogfeld "Symbol ändern" direkt aufrufen) zum Aktivieren des Aspekts Symbol angezeigt, wenn vom Benutzer angefordert.  
  
##  <a name="setextent"></a>  COleClientItem::SetExtent  
 Mit dieser Funktion wird zum angeben, wie viel Speicherplatz für das OLE-Element verfügbar ist.  
  
```  
void SetExtent(
    const CSize& size,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parameter  
 *size*  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das Informationen zur Datenbankgröße enthält.  
  
 *nDrawAspect*  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen sind festgelegt werden. Mögliche Werte finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Anwendung für die Verwendung der Microsoft Foundation Class-Bibliothek geschrieben wurde, führt dies zu dem [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent) Memberfunktion der entsprechenden `COleServerItem` Objekt aufgerufen werden. OLE-Element kann seine Darstellung dann entsprechend anpassen. Die Dimensionen muss `MM_HIMETRIC` Einheiten. Rufen Sie diese Funktion, wenn der Benutzer die OLE-Element ändert oder wenn Sie eine Form der Layout-Verhandlung unterstützen.  
  
 Weitere Informationen finden Sie unter [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) im Windows SDK.  
  
##  <a name="sethostnames"></a>  COleClientItem::SetHostNames  
 Rufen Sie diese Funktion, um den Namen der containeranwendung, und der Containername für einem eingebetteten OLE-Element angeben.  
  
```  
void SetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszHost*  
 Ein Zeiger auf den Benutzer sichtbare Name des Steuerelementcontainer-Anwendung.  
  
 *lpszHostObj*  
 Ein Zeiger auf eine identifizierende Zeichenfolge des Containers, die das OLE-Element enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Anwendung für die Verwendung der Microsoft Foundation Class-Bibliothek geschrieben wurde, wird diese Funktion ruft die [OnSetHostNames](../../mfc/reference/coleserverdoc-class.md#onsethostnames) Memberfunktion der `COleServerDoc` Dokument, das die OLE-Element enthält. Diese Informationen werden im Fenstertitel verwendet, wenn das OLE-Element bearbeitet wird. Jedes Mal, wenn ein Containerdokument geladen wird, ruft das Framework diese Funktion, für die OLE-Elemente im Dokument. `SetHostNames` gilt nur für eingebettete Elemente. Es ist nicht notwendig, die mit dieser Funktion wird jedes Mal, wenn ein eingebettetes OLE-Element aktiviert, wird für die Bearbeitung.  
  
 Dies wird auch automatisch mit dem Anwendungsnamen und der Name des Dokuments aufgerufen, wenn ein Objekt geladen wird oder wenn eine Datei unter einem anderen Namen gespeichert wird. Entsprechend ist es nicht in der Regel erforderlich, diese Funktion direkt aufzurufen.  
  
 Weitere Informationen finden Sie unter [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) im Windows SDK.  
  
##  <a name="seticonicmetafile"></a>  COleClientItem::SetIconicMetafile  
 Speichert die Metadatei, die zum Zeichnen des Symbols an.  
  
```  
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```  
  
### <a name="parameters"></a>Parameter  
 *hMetaPict*  
 Ein Handle für die Metadatei, die zum Zeichnen des Symbols.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [GetIconicMetafile](#geticonicmetafile) die Metadatei abgerufen.  
  
 Die *hMetaPict* Parameter in das Element kopiert wird deshalb *hMetaPict* muss vom Aufrufer freigegeben werden.  
  
##  <a name="setitemrects"></a>  COleClientItem::SetItemRects  
 Mit dieser Funktion wird zum Festlegen des umschließenden Rechtecks oder die sichtbaren Rechteck des OLE-Elements.  
  
```  
BOOL SetItemRects(
    LPCRECT lpPosRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lprcPosRect*  
 Ein Zeiger auf das Rechteck, das die Grenzen des OLE-Elements relativ zu seinem übergeordneten Fenster in Clientkoordinaten enthält.  
  
 *lprcClipRect*  
 Ein Zeiger auf das Rechteck, das die Grenzen des sichtbaren Teils des OLE-Elements relativ zu seinem übergeordneten Fenster in Clientkoordinaten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, indem Sie die standardmäßige Implementierung des der [OnChangeItemPosition](#onchangeitemposition) Memberfunktion. Sie sollten diese Funktion aufrufen, wenn die Position oder den sichtbaren Teil der OLE-Element geändert wird. In der Regel bedeutet dies, dass Sie sie in Ihrer Ansicht Aufrufen [OnSize](../../mfc/reference/cwnd-class.md#onsize) und [OnScrollBy](../../mfc/reference/cview-class.md#onscrollby) Memberfunktionen.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) im Windows SDK.  
  
##  <a name="setlinkupdateoptions"></a>  COleClientItem::SetLinkUpdateOptions  
 Mit dieser Funktion können die Link-Update-Option für die Darstellung von das angegebene verknüpfte Element festgelegt.  
  
```  
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```  
  
### <a name="parameters"></a>Parameter  
 *dwUpdateOpt*  
 Der Wert der Link / Update-Option für dieses Element. Dieser Wert muss eine der folgenden sein:  
  
- `OLEUPDATE_ALWAYS` Das verknüpfte Element nach Möglichkeit zu aktualisieren. Diese Option unterstützt das Optionsfeld automatische Link-Update im Dialogfeld "Verknüpfungen".  
  
- `OLEUPDATE_ONCALL` Aktualisieren Sie das verknüpfte Element nur auf Anforderung aus dem Steuerelementcontainer-Anwendung (wenn die [UpdateLink](#updatelink) Memberfunktion aufgerufen wird). Diese Option unterstützt das Optionsfeld manuelle Link-Update im Dialogfeld "Verknüpfungen".  
  
### <a name="remarks"></a>Hinweise  
 In der Regel sollten Sie die Updateoptionen, die vom Benutzer im Dialogfeld Links ausgewählten nicht ändern.  
  
 Weitere Informationen finden Sie unter [IOleLink::SetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680120) im Windows SDK.  
  
##  <a name="setprintdevice"></a>  COleClientItem::SetPrintDevice  
 Mit dieser Funktion wird zum Drucken-Zielgerät für dieses Element zu ändern.  
  
```  
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL SetPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Parameter  
 *ptd*  
 Zeiger auf eine [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Datenstruktur, die Informationen zu dem neuen Druckserver Zielgerät enthält. Kann **NULL**.  
  
 *PPD*  
 Zeiger auf eine [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646940) Datenstruktur, die Informationen zu dem neuen Druckserver Zielgerät enthält. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aktualisiert die Print-Zielgerät für das Element jedoch Präsentation Cache wird nicht aktualisiert. Um die Präsentation Cache nach einem Element zu aktualisieren, rufen [UpdateLink](#updatelink).  
  
 Die Argumente für diese Funktion enthalten Informationen, die das OLE-System verwendet wird, um das Zielgerät zu identifizieren. Die **PRINTDLG** Struktur enthält Informationen, die von Windows verwendet, um das allgemeine Drucken-Dialogfeld zu initialisieren. Nachdem der Benutzer das Dialogfeld geschlossen wurde, gibt Windows Informationen zur Auswahl des Benutzers in dieser Struktur zurück. Die `m_pd` Mitglied einer [CPrintDialog](../../mfc/reference/cprintdialog-class.md) Objekt ist ein **PRINTDLG** Struktur.  
  
 Weitere Informationen zu dieser Struktur finden Sie unter [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) im Windows SDK.  
  
##  <a name="updatelink"></a>  COleClientItem::UpdateLink  
 Rufen Sie diese Funktion, um die OLE-Element-Präsentationsdaten sofort zu aktualisieren.  
  
```  
BOOL UpdateLink();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Für verknüpfte Elemente findet die Funktion die Linkquelle zum Abrufen einer neuen Präsentation für das OLE-Element. Dieser Prozess kann zur Folge haben, mit ein oder mehrere serveranwendungen, die zeitaufwändig sein könnte. Bei eingebetteten Elemente arbeitet die Funktion rekursiv, überprüfen, ob das eingebettete Element Links enthält, die möglicherweise nicht mehr aktuell, und diese zu aktualisieren. Der Benutzer kann einzelne Links, die mithilfe des Dialogfelds Links auch manuell aktualisieren.  
  
 Weitere Informationen finden Sie unter [IOleLink::Update](http://msdn.microsoft.com/library/windows/desktop/ms692660) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MFCBIND](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [CDocItem-Klasse](../../mfc/reference/cdocitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)
