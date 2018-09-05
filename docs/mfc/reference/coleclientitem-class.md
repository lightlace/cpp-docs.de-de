---
title: COleClientItem-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 43f9e1b342d6de1a93906d2469d0fd1eb211e886
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765004"
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
|[COleClientItem::Activate](#activate)|Öffnet das OLE-Element für einen Vorgang aus, und klicken Sie dann führt das angegebene Verb.|  
|[COleClientItem::ActivateAs](#activateas)|Aktiviert das Element als einen anderen Typ.|  
|[COleClientItem::AttachDataObject](#attachdataobject)|Greift auf die Daten in das OLE-Objekt.|  
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|Gibt an, ob eine containeranwendung ein eingebettetes Objekt erstellen können.|  
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|Gibt an, ob eine containeranwendung ein verknüpftes Objekt erstellen können.|  
|[COleClientItem::CanPaste](#canpaste)|Gibt an, ob die Zwischenablage ein OLE-Element eingebettet werden oder eine statische enthält.|  
|[COleClientItem::CanPasteLink](#canpastelink)|Gibt an, ob die Zwischenablage ein verknüpfbares OLE-Element enthält.|  
|[COleClientItem::Close](#close)|Schließt einen Link zu einem Server, jedoch nicht zerstört das OLE-Element.|  
|[COleClientItem::ConvertTo](#convertto)|Das Element konvertiert in einen anderen Typ.|  
|[COleClientItem::CopyToClipboard](#copytoclipboard)|Das OLE-Element kopiert in die Zwischenablage.|  
|[COleClientItem::CreateCloneFrom](#createclonefrom)|Erstellt ein Duplikat eines vorhandenen Elements.|  
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|Erstellt ein eingebettetes Element aus der Zwischenablage an.|  
|[COleClientItem::CreateFromData](#createfromdata)|Erstellt ein eingebettetes Element von einem Datenobjekt.|  
|[CreateFromFile](#createfromfile)|Erstellt ein eingebettetes Element aus einer Datei an.|  
|[COleClientItem::CreateLinkFromClipboard](#createlinkfromclipboard)|Erstellt ein verknüpftes Element aus der Zwischenablage an.|  
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|Erstellt ein verknüpftes Element von einem Datenobjekt.|  
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|Erstellt ein verknüpftes Element aus einer Datei an.|  
|[COleClientItem::CreateNewItem](#createnewitem)|Erstellt ein neues eingebettetes Element durch die Server-Anwendung zu starten.|  
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|Erstellt ein statisches Element aus der Zwischenablage an.|  
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|Erstellt ein statisches Element von einem Datenobjekt.|  
|[COleClientItem::Deactivate](#deactivate)|Deaktiviert das Element an.|  
|[COleClientItem::DeactivateUI](#deactivateui)|Wird die Benutzeroberfläche für die Container-Anwendung in seinen ursprünglichen Zustand wiederhergestellt.|  
|[COleClientItem::Delete](#delete)|Löscht oder schließt das OLE-Element, wenn es sich um ein verknüpftes Element war.|  
|[COleClientItem::DoDragDrop](#dodragdrop)|Führt einen Drag & Drop-Vorgang.|  
|[COleClientItem::DoVerb](#doverb)|Führt das angegebene Verb aus.|  
|[COleClientItem::Draw](#draw)|Zeichnet das OLE-Element.|  
|[COleClientItem::GetActiveView](#getactiveview)|Ruft die Ansicht, die auf der das Element direkt aktiviert ist.|  
|[COleClientItem::GetCachedExtent](#getcachedextent)|Gibt die Grenzen des Rechtecks für das OLE-Element zurück.|  
|[COleClientItem::GetClassID](#getclassid)|Ruft das Element vorhanden Klasse-ID ab.|  
|[COleClientItem::GetClipboardData](#getclipboarddata)|Ruft ab, die Daten, die durch den Aufruf in der Zwischenablage abgelegt werden die `CopyToClipboard` Member-Funktion.|  
|[COleClientItem::GetDocument](#getdocument)|Gibt die `COleDocument` -Objekt, das vorhandene-Element enthält.|  
|[COleClientItem::GetDrawAspect](#getdrawaspect)|Ruft die aktuelle Ansicht des Elements für das Rendering ab.|  
|[COleClientItem::GetExtent](#getextent)|Gibt die Grenzen des Rechtecks für das OLE-Element zurück.|  
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|Ruft ein Handle für ein Symbol fest, die der Server von einer bestimmten CLSID zugeordnet ist.|  
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|Ruft die Metadatei, die zum Zeichnen des Symbols ab.|  
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|Gibt einen Zeiger auf das Element des direktes-Bearbeitungsfenster.|  
|[COleClientItem::GetItemState](#getitemstate)|Ruft die aktuellen Zustand des Elements ab.|  
|[COleClientItem::GetLastStatus](#getlaststatus)|Der Status des letzten Vorgangs OLE zurückgegeben.|  
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|Gibt den Updatemodus für ein verknüpftes Element (erweiterte Funktion) zurück.|  
|[COleClientItem::GetType](#gettype)|Gibt den Typ (embedded, Verbindungs- oder statisch) des OLE-Elements zurück.|  
|[COleClientItem::GetUserType](#getusertype)|Ruft eine Zeichenfolge, die den Typ des Elements beschreibt.|  
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|Gibt TRUE zurück, wenn das Element direkt aktiv ist.|  
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|Gibt "true", wenn ein verknüpftes Element ist auf dem neuesten Stand mit dem Quelldokument.|  
|[COleClientItem::IsModified](#ismodified)|Gibt TRUE zurück, wenn das Element geändert wurde, seit dem letzten gespeichert.|  
|[COleClientItem::IsOpen](#isopen)|Gibt "true" Öffnen Wenn das Element derzeit in der Serveranwendung.|  
|[COleClientItem::IsRunning](#isrunning)|Gibt TRUE zurück, wenn das Element die Serveranwendung ausgeführt wird.|  
|[COleClientItem::OnActivate](#onactivate)|Wird aufgerufen, durch das Framework, um dem Element zu benachrichtigen, dass es aktiviert ist.|  
|[COleClientItem::OnActivateUI](#onactivateui)|Wird aufgerufen, durch das Framework dem Element benachrichtigt, dass es aktiviert wird und die Benutzeroberfläche angezeigt werden sollte.|  
|[COleClientItem:: OnChange](#onchange)|Wird aufgerufen, wenn der Server das OLE-Element geändert wird. Die Implementierung erforderlich sind.|  
|[COleClientItem::OnDeactivate](#ondeactivate)|Wird vom Framework aufgerufen, wenn ein Element deaktiviert ist.|  
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|Vom Framework aufgerufen, wenn der Server die direkte Benutzeroberfläche entfernt wurde.|  
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|Wird aufgerufen, durch das Framework zum Abrufen der Daten in die Zwischenablage kopiert werden sollen.|  
|[COleClientItem::OnInsertMenus](#oninsertmenus)|Wird aufgerufen, durch das Framework zum Erstellen eines zusammengesetzten Menüs.|  
|[COleClientItem::OnRemoveMenus](#onremovemenus)|Wird aufgerufen, durch das Framework die Menüs des Containers von einem zusammengesetzten Menü zu entfernen.|  
|[COleClientItem::OnSetMenu](#onsetmenu)|Wird aufgerufen, durch das Framework zum Installieren und entfernen ein zusammengesetztes Menü.|  
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|Wird aufgerufen, durch das Framework zum ein- und Ausblenden des Schiebeleisten-Steuerelemente.|  
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|Wird aufgerufen, durch das Framework das Rahmenfenster Titelleiste zu aktualisieren.|  
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|Reaktiviert das Element, und macht die letzte direkte Bearbeitung des.|  
|[COleClientItem::Release](#release)|Die Verbindung mit einer OLE-Element verknüpfte frei, und geschlossen wird, wenn es geöffnet war. Die Client-Element wird nicht zerstört werden.|  
|[COleClientItem::Reload](#reload)|Lädt das Element nach einem Aufruf von `ActivateAs`.|  
|[COleClientItem::Run](#run)|Führt die Anwendung, die dem Element zugeordnet.|  
|[COleClientItem::SetDrawAspect](#setdrawaspect)|Aktuelle Ansicht des Elements, für das Rendering festgelegt.|  
|[COleClientItem::SetExtent](#setextent)|Legt das umschließende Rechteck des OLE-Elements fest.|  
|[COleClientItem::SetHostNames](#sethostnames)|Legt die Namen des Servers angezeigt werden soll, wenn das OLE-Element zu bearbeiten.|  
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|Speichert die Metadatei, die zum Zeichnen des Symbols.|  
|[COleClientItem::SetItemRects](#setitemrects)|Legt die umschließende Rechteck des Elements fest.|  
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|Legt fest, den Updatemodus für ein verknüpftes Element (erweiterte Funktion).|  
|[COleClientItem::SetPrintDevice](#setprintdevice)|Legt fest, das Drucken-Zielgerät für diese Client-Element.|  
|[COleClientItem::UpdateLink](#updatelink)|Aktualisiert den Cache Darstellung eines Elements.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleClientItem:: CanActivate](#canactivate)|Wird aufgerufen, durch das Framework, um zu bestimmen, ob die direkte Aktivierung zulässig ist.|  
|[COleClientItem:: OnChangeItemPosition auf](#onchangeitemposition)|Vom Framework aufgerufen, wenn sich die Position eines Elements ändert.|  
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|Vom Framework aufgerufen, nach der Aktivierung rückgängig zu machen.|  
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|Wird aufgerufen, durch das Framework zum Verwerfen von Rückgängig-Statusinformationen des Elements.|  
|[COleClientItem::OnGetClipRect](#ongetcliprect)|Wird aufgerufen, durch das Framework die Auswahlrechteck Koordinaten des Elements zu erhalten.|  
|[COleClientItem:: OnGetItemPosition auf](#ongetitemposition)|Wird aufgerufen, durch das Framework zum Abrufen der Position des Elements relativ zu der Ansicht.|  
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|Vom Framework aufgerufen, wenn ein Element direkt aktiviert ist.|  
|[COleClientItem::OnScrollBy](#onscrollby)|Wird aufgerufen, durch das Framework das Element in der Ansicht einen Bildlauf durchführen.|  
|[COleClientItem::OnShowItem](#onshowitem)|Wird aufgerufen, durch das Framework zum Anzeigen des OLE-Elements.|  
  
## <a name="remarks"></a>Hinweise  
 Ein OLE-Element stellt Daten dar, von einer Serveranwendung, die in ein Dokument "nahtlos" integriert werden kann, sodass es dem Benutzer werden von einem einzelnen Dokument angezeigt wird erstellt und verwaltet. Das Ergebnis ist ein "Verbunddokument" setzt sich aus der OLE-Element und ein Dokument enthält.  
  
 Ein OLE-Element kann eingebettet oder verknüpft werden. Wenn es eingebettet ist, werden die Daten im Rahmen des Verbunddokuments gespeichert. Wenn sie verknüpft ist, befindet sich die Daten im Rahmen einer separaten Datei, die von der Serveranwendung erstellt und nur ein Link zu dieser Datei werden im Verbunddokument gespeichert. Alle OLE-Elemente enthalten Informationen, die Angabe der Serveranwendung, die aufgerufen werden soll, um sie zu bearbeiten.  
  
 `COleClientItem` definiert mehrere überschreibbare-Funktionen, die aufgerufen werden als Antwort auf Anforderungen von der Serveranwendung an. Diese / / Overridables fungieren in der Regel als Benachrichtigungen. Dadurch kann es sich um die Serveranwendung, um den Container der Änderungen zu informieren, die der Benutzer vornimmt, wenn das OLE-Element zu bearbeiten oder zum Abrufen von Informationen, die während der Bearbeitung erforderlich.  
  
 `COleClientItem` kann verwendet werden, entweder mit der [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), oder [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) Klasse. Verwendung von `COleClientItem`, eine Klasse ableiten und Implementieren der [OnChange](#onchange) Member-Funktion, die definiert, wie der Container an einem Element vorgenommenen Änderungen reagiert. Zur Unterstützung der Aktivierung des direktes überschreiben die [OnGetItemPosition](#ongetitemposition) Member-Funktion. Diese Funktion bietet Informationen zur Position des OLE-Elements angezeigt.  
  
 Weitere Informationen über die Containerschnittstelle, finden Sie in den Artikeln [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md) und [Aktivierung](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  Das Windows SDK verweist auf eingebettete und verknüpfte Elemente als "Objekt", und bezieht sich auf die Typen von Elementen als "Classes". Dieser Verweis wird der Begriff "Item" verwendet, zur Unterscheidung von der OLE-Entität über die entsprechende C++-Objekt und der Begriff "Type", um die OLE-Kategorie von C++-Klasse zu unterscheiden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="activate"></a>  COleClientItem::Activate  
 Mit dieser Funktion können Sie nicht das angegebene Verb aufzurufen [DoVerb](#doverb) , damit Sie durchführen können, Ihre eigenen Verarbeitung verwendet werden, wenn eine Ausnahme ausgelöst wird.  
  
```  
void Activate(
    LONG nVerb,  
    CView* pView,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nVerb*  
 Gibt das Verb ausgeführt. Sie können eine der folgenden sein:  
  
|Wert|Bedeutung|Symbol|  
|-----------|-------------|------------|  
|- 0|Primäres Verb|OLEIVERB_PRIMARY|  
|- 1|Sekundäre verb|(Keine)|  
|- 1|Display-Element für die Bearbeitung|OLEIVERB_SHOW|  
|- 2|Element in separaten Fenster bearbeiten|OLEIVERB_OPEN|  
|- 3|Element ausblenden|OLEIVERB_HIDE|  
  
 Der Wert-1 wird in der Regel einen Alias für ein anderes Verb. Wenn Bearbeiten öffnen nicht unterstützt wird, hat-2 dieselbe Wirkung wie das-1 auf. Weitere Werte finden Sie unter [IOleObject](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) im Windows SDK.  
  
 *pView*  
 Zeiger auf das Fenster "Container anzeigen", das das OLE-Element enthält; Dies wird durch die Server-Anwendung für die direkte Aktivierung verwendet werden. Dieser Parameter sollte NULL sein, wenn der Container die direkte Aktivierung nicht unterstützt.  
  
 *lpMsg*  
 Zeiger auf die Meldung, die das Element, das aktiviert werden, verursacht hat.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Serveranwendung über die Microsoft Foundation Class-Library geschrieben wurde, diese Funktion führt dazu, dass die [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb) -Memberfunktion des entsprechenden `COleServerItem` Objekt, das ausgeführt werden.  
  
 Wenn das primäre Verb, bearbeiten ist und 0 (null), in angegeben wird der *nVerb* Parameter, die Server-Anwendung wird gestartet, um das OLE-Element bearbeitet werden können. Wenn die Container-Anwendung direkten Aktivierung unterstützt, kann bearbeiten an Stelle erfolgen. Wenn der Container nicht unterstützt wird, direkte Aktivierung (oder wenn das Verb öffnen angegeben ist), der Server in einem separaten Fenster gestartet und bearbeiten kann erfolgen vorhanden. In der Regel, wenn der Container-Anwendung doppelgeklickt das OLE-Element, den Wert für das primäre Verb in der *nVerb* Parameter bestimmt, welche Aktion, die der Benutzer durchführen kann. Allerdings, wenn der Server nur eine Aktion unterstützt werden, dauert es diese Aktion aus, unabhängig davon, welche-Wert, in angegeben wird der *nVerb* Parameter.  
  
 Weitere Informationen finden Sie unter [IOleObject](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) im Windows SDK.  
  
##  <a name="activateas"></a>  COleClientItem::ActivateAs  
 OLE Objekt Konvertierung Funktionen verwendet, um das Element zu aktivieren, als wäre es ein Element vom angegebenen Typ *ClsidNew*.  
  
```  
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,  
    REFCLSID clsidOld,  
    REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszUserType*  
 Zeiger auf eine Zeichenfolge mit den Benutzer-Zieltyp, z. B. "Word-Dokument."  
  
 *clsidOld*  
 Ein Verweis auf das Element der aktuellen Klasse-ID Die Klassen-ID sollte den Typ, der das eigentliche Objekt darstellen, da gespeichert, wenn es sich um einen Link handelt. In diesem Fall sollten sie die CLSID des Elements sein, auf die der Link verweist. Die [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md) stellt automatisch die richtige Klasse-ID für das Element.  
  
 *clsidNew*  
 Ein Verweis auf die Ziel-Klasse-ID  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Dies wird automatisch vom bezeichnet [COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert). Es ist nicht in der Regel direkt aufgerufen.  
  
##  <a name="attachdataobject"></a>  COleClientItem::AttachDataObject  
 Mit dieser Funktion wird zum Initialisieren einer [COleDataObject](../../mfc/reference/coledataobject-class.md) für den Zugriff auf die Daten in das OLE-Element.  
  
```  
void AttachDataObject(COleDataObject& rDataObject) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *rDataObject*  
 Ein Verweis auf eine `COleDataObject` -Objekt, das für den Zugriff auf die Daten in das OLE-Element initialisiert werden.  
  
##  <a name="canactivate"></a>  COleClientItem:: CanActivate  
 Vom Framework aufgerufen, wenn der Benutzer die direkte Aktivierung des OLE-Elements anfordert; Rückgabewert dieser Funktion bestimmt, ob die direkte Aktivierung zulässig ist.  
  
```  
virtual BOOL CanActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die direkte Aktivierung ist zulässig. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ermöglicht direkte Aktivierung, wenn der Container über ein gültiges Fenster verfügt. Überschreiben Sie diese Funktion, um spezielle Logik für das annehmen oder Ablehnen der Anforderung zur Aktivierung implementieren. Beispielsweise kann eine aktivierungsanforderung abgelehnt werden, wenn das OLE-Element zu klein ist oder nicht aktuell sichtbar ist.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::CanInPlaceActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-caninplaceactivate) im Windows SDK.  
  
##  <a name="cancreatefromdata"></a>  COleClientItem::CanCreateFromData  
 Überprüft, ob eine Container-Anwendung ein eingebettetes Objekt erstellen kann der angegebenen `COleDataObject` Objekt.  
  
```  
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataObject*  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der das OLE-Element erstellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn ein eingebettetes Objekt aus der Container erstellen, kann die `COleDataObject` -Objekt, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleDataObject` -Klasse wird in Datenübertragungen zum Abrufen von Daten in verschiedenen Formaten, aus der Zwischenablage, per Drag & Drop, oder aus einer eingebetteten OLE-Element verwendet.  
  
 Container können diese Funktion aktivieren oder deaktivieren die Befehle für die bearbeiten, einfügen und bearbeiten Sie Inhalte einfügen möchten.  
  
 Weitere Informationen finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="cancreatelinkfromdata"></a>  COleClientItem::CanCreateLinkFromData  
 Überprüft, ob eine Container-Anwendung über ein verknüpftes Objekt erstellen, kann die angegebenen `COleDataObject` Objekt.  
  
```  
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataObject*  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der das OLE-Element erstellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn ein verknüpftes Objekt aus der Container erstellen, kann die `COleDataObject` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleDataObject` -Klasse wird in Datenübertragungen zum Abrufen von Daten in verschiedenen Formaten, aus der Zwischenablage, per Drag & Drop, oder aus einer eingebetteten OLE-Element verwendet.  
  
 Container können diese Funktion aktivieren oder deaktivieren die Befehle für die Inhalte einfügen bearbeiten und Einfügen-Link bearbeiten möchten.  
  
 Weitere Informationen finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="canpaste"></a>  COleClientItem::CanPaste  
 Rufen Sie diese Funktion, um festzustellen, ob es sich bei ein eingebetteten OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
static BOOL PASCAL CanPaste();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Legen Sie ungleich NULL, wenn es sich bei ein eingebetteten OLE-Element aus der Zwischenablage eingefügt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OleGetClipboard](/windows/desktop/api/ole2/nf-ole2-olegetclipboard) und [OleQueryCreateFromData](/windows/desktop/api/ole2/nf-ole2-olequerycreatefromdata) im Windows SDK.  
  
##  <a name="canpastelink"></a>  COleClientItem::CanPasteLink  
 Rufen Sie diese Funktion, um festzustellen, ob ein verknüpftes OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
static BOOL PASCAL CanPasteLink();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn ein verknüpftes OLE-Element aus der Zwischenablage eingefügt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OleGetClipboard](/windows/desktop/api/ole2/nf-ole2-olegetclipboard) und [OleQueryLinkFromData](/windows/desktop/api/ole2/nf-ole2-olequerylinkfromdata) im Windows SDK.  
  
##  <a name="close"></a>  COleClientItem::Close  
 Mit dieser Funktion können Sie ändern Sie den Zustand eines OLE-Elements aus dem laufenden Zustand in den geladenen Zustand, d. h. geladen, mit dem Handler im Arbeitsspeicher, aber mit dem Server nicht ausgeführt.  
  
```  
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```  
  
### <a name="parameters"></a>Parameter  
 *dwCloseOption*  
 Flag, das angibt, unter welchen Umständen das OLE-Element gespeichert wird, wenn in den geladenen Zustand zurückgegeben. Es kann einen der folgenden Werte aufweisen:  
  
- OLECLOSE_SAVEIFDIRTY speichern Sie das OLE-Element.  
  
- Das OLE-Element OLECLOSE_NOSAVE werden nicht gespeichert werden.  
  
- OLECLOSE_PROMPTSAVE fordert den Benutzer auf, ob das OLE-Element gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion hat keine Auswirkungen, wenn das OLE-Element nicht ausgeführt wird.  
  
 Weitere Informationen finden Sie unter [IOleObject::Close](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-close) im Windows SDK.  
  
##  <a name="coleclientitem"></a>  COleClientItem::COleClientItem  
 Erstellt eine `COleClientItem` -Objekt und fügt sie Auflistung des Containerdokuments der Dokumentelemente, die nur das C++-Objekt erstellt und führt keine OLE-Initialisierung hinzu.  
  
```  
COleClientItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pContainerDoc*  
 Zeiger auf das Containerdokument, das dieses Element enthält. Mögliche [COleDocument](../../mfc/reference/coledocument-class.md) Ableitung.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen NULL-Zeiger übergeben, wird keine Addition mit Containerdokument hergestellt. Sie müssen explizit aufrufen [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem).  
  
 Sie müssen eine der folgenden Erstellung Memberfunktionen aufrufen, vor der Verwendung von OLE-Elements:  
  
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
 Dies wird automatisch vom bezeichnet [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md). Es ist nicht notwendig, direkt aufgerufen.  
  
##  <a name="copytoclipboard"></a>  COleClientItem::CopyToClipboard  
 Rufen Sie diese Funktion, um das OLE-Element in die Zwischenablage zu kopieren.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *bIncludeLink*  
 True, wenn die Informationen zu mehrfachverbindungen kopiert werden sollen, in die Zwischenablage, sodass ein verknüpftes Element eingefügt werden. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion beim Schreiben der Message-Handler für den Kopier- oder Ausschneidevorgang-Befehlen im Menü Bearbeiten. Sie müssen die Elementauswahl in Ihrem Container-Anwendung implementieren, sollten Sie die Befehle Kopieren oder Ausschneiden zu implementieren.  
  
 Weitere Informationen finden Sie unter [von OleSetClipboard](/windows/desktop/api/ole2/nf-ole2-olesetclipboard) im Windows SDK.  
  
##  <a name="createclonefrom"></a>  COleClientItem::CreateCloneFrom  
 Rufen Sie diese Funktion zum Erstellen einer Kopie des angegebenen OLE-Elements.  
  
```  
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pSrcItem*  
 Zeiger auf das OLE-Element, das dupliziert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Kopie ist identisch mit dem Quellelement. Sie können diese Funktion verwenden, um Rückgängig-Vorgänge zu unterstützen.  
  
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
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn Sie das OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur verwendet, wenn *Rendern* OLERENDER_FORMAT oder OLERENDER_DRAW ist. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion von der Message-Handler, für den Befehl "Einfügen" auf das Menü "Bearbeiten". (Der Befehl "Einfügen" wird vom Framework aktiviert, wenn die [CanPaste](#canpaste) Memberfunktion gibt ungleich NULL zurück.)  
  
 Weitere Informationen finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
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
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der das OLE-Element erstellt werden.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn Sie das OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur verwendet, wenn *Rendern* OLERENDER_FORMAT oder OLERENDER_DRAW ist. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie die Vorgänge, z. B. Einfügen von Daten aus der Zwischenablage oder Drag & Drop-Vorgänge, `COleDataObject` Objekte, die durch eine Serveranwendung angeboten, das Informationen enthält. Es wird normalerweise verwendet, in der Überschreibung der [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop).  
  
 Weitere Informationen finden Sie unter [OleCreateFromData](/windows/desktop/api/ole2/nf-ole2-olecreatefromdata), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
##  <a name="createfromfile"></a>  CreateFromFile  
 Mit dieser Funktion können Sie ein eingebetteten OLE-Element aus einer Datei zu erstellen.  
  
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
 Zeiger auf den Namen der Datei, aus der das OLE-Element erstellt werden.  
  
 *clsid*  
 Für zukünftige Verwendung reserviert.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn Sie das OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur verwendet, wenn *Rendern* OLERENDER_FORMAT oder OLERENDER_DRAW ist. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion aus [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem) , wenn der Benutzer wählt OK im Dialogfeld "Objekt einfügen", wenn das Erstellen von Datei-Schaltfläche aktiviert ist.  
  
 Weitere Informationen finden Sie unter [OleCreateFromFile](/windows/desktop/api/ole/nf-ole-olecreatefromfile), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
##  <a name="createlinkfromclipboard"></a>  COleClientItem::CreateLinkFromClipboard  
 Rufen Sie diese Funktion zum Erstellen eines verknüpften Elements aus dem Inhalt der Zwischenablage ein.  
  
```  
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn Sie das OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur verwendet, wenn *Rendern* OLERENDER_FORMAT oder OLERENDER_DRAW ist. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion von der Message-Handler, für den Befehl "Link einfügen" auf das Menü "Bearbeiten". (Der Link einfügen-Befehl ist aktiviert, in der Standardimplementierung des [COleDocument](../../mfc/reference/coledocument-class.md) , wenn die Zwischenablage ein OLE-Element enthält, die mit verknüpft werden können.)  
  
 Weitere Informationen finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
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
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der das OLE-Element erstellt werden.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn Sie das OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur verwendet, wenn *Rendern* OLERENDER_FORMAT oder OLERENDER_DRAW ist. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese während eines Drop-Vorgangs, wenn der Benutzer gibt an, dass eine Verknüpfung erstellt werden soll. Sie können auch verwendet werden, behandeln den Befehl Paste bearbeiten. Sie wird aufgerufen, durch das Framework in `COleClientItem::CreateLinkFromClipboard` und [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) Wenn die Link-Option ausgewählt wurde.  
  
 Weitere Informationen finden Sie unter [OleCreateLinkFromData](/windows/desktop/api/ole2/nf-ole2-olecreatelinkfromdata), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
##  <a name="createlinkfromfile"></a>  COleClientItem::CreateLinkFromFile  
 Rufen Sie diese Funktion zum Erstellen eines verknüpften OLE-Elements aus einer Datei.  
  
```  
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszFileName*  
 Zeiger auf den Namen der Datei, aus der das OLE-Element erstellt werden.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn Sie das OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur verwendet, wenn *Rendern* OLERENDER_FORMAT oder OLERENDER_DRAW ist. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion auf, wenn der Benutzer wählt im Dialogfeld "Objekt einfügen" OK, beim Erstellen von Datei-Schaltfläche aktiviert ist, und das Kontrollkästchen "Link" aktiviert ist. Aufruf in [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem).  
  
 Weitere Informationen finden Sie unter [OleCreateLinkToFile](/windows/desktop/api/ole2/nf-ole2-olecreatelinktofile), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
##  <a name="createnewitem"></a>  COleClientItem::CreateNewItem  
 Aufrufen dieser Funktion können Sie ein eingebettetes Element zu erstellen. Diese Funktion wird gestartet, die Serveranwendung, die dem Benutzer ermöglicht, die das OLE-Element zu erstellen.  
  
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
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn Sie das OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur verwendet, wenn *Rendern* OLERENDER_FORMAT oder OLERENDER_DRAW ist. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion auf, wenn der Benutzer wählt im Dialogfeld "Objekt einfügen" OK, wenn die Schaltfläche "neu erstellen" ausgewählt ist.  
  
 Weitere Informationen finden Sie unter [OleCreate](/windows/desktop/api/ole/nf-ole-olecreate), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
##  <a name="createstaticfromclipboard"></a>  COleClientItem::CreateStaticFromClipboard  
 Rufen Sie diese Funktion zum Erstellen eines statischen Elements aus dem Inhalt der Zwischenablage ein.  
  
```  
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn Sie das OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur verwendet, wenn *Rendern* OLERENDER_FORMAT oder OLERENDER_DRAW ist. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ein statisches Element enthält die Präsentationsdaten jedoch nicht die systemeigenen Daten; Daher kann er bearbeitet werden. Diese Funktion wird in der Regel aufzurufen, wenn die [CreateFromClipboard](#createfromclipboard) Member-Funktion ein Fehler auftritt.  
  
 Weitere Informationen finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
##  <a name="createstaticfromdata"></a>  COleClientItem::CreateStaticFromData  
 Mit dieser Funktion wird zum Erstellen eines statischen Elements aus einem `COleDataObject` Objekt.  
  
```  
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataObject*  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt aus der das OLE-Element erstellt werden.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) im Windows SDK.  
  
 *cfFormat*  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn Sie das OLE-Element zu erstellen.  
  
 *lpFormatEtc*  
 Zeiger auf eine [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Struktur verwendet, wenn *Rendern* OLERENDER_FORMAT oder OLERENDER_DRAW ist. Geben Sie einen Wert für diesen Parameter nur, wenn Sie zusätzliche Informationen über das Format der Zwischenablage durch angegebene angeben möchten *CfFormat*. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der `FORMATETC` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ein statisches Element enthält die Präsentationsdaten jedoch nicht die systemeigenen Daten; Daher kann er bearbeitet werden. Dies ist im Wesentlichen identisch mit [CreateStaticFromClipboard](#createstaticfromclipboard) mit dem Unterschied, dass ein statisches Element aus einer beliebigen erstellt werden kann `COleDataObject`, nicht nur aus der Zwischenablage.  
  
 Verwendet [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) Wenn statische ausgewählt ist.  
  
 Weitere Informationen finden Sie unter [OleCreateStaticFromData](/windows/desktop/api/ole2/nf-ole2-olecreatestaticfromdata), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), und [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) im Windows SDK.  
  
##  <a name="deactivate"></a>  COleClientItem::Deactivate  
 Mit dieser Funktion können deaktivieren das OLE-Element, und geben Sie alle zugeordneten Ressourcen frei.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein direktes active OLE-Element in der Regel deaktivieren, klickt der Benutzer die Maus auf den Clientbereich außerhalb der Grenzen des Elements. Beachten Sie, dass deaktivieren das OLE-Element die wieder rückgängig zu machen, kann aufrufen, verwirft der [ReactivateAndUndo](#reactivateandundo) Member-Funktion.  
  
 Wenn Ihre Anwendung zum Rückgängigmachen unterstützt, rufen Sie nicht `Deactivate`; stattdessen Aufrufen [DeactivateUI](#deactivateui).  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::InPlaceDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) im Windows SDK.  
  
##  <a name="deactivateui"></a>  COleClientItem::DeactivateUI  
 Rufen Sie diese Funktion, wenn der Benutzer ein Element deaktiviert, das direkt aktiviert wurde.  
  
```  
void DeactivateUI();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion stellt die Benutzeroberfläche für die Container-Anwendung auf den ursprünglichen Zustand, Ausblenden von alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden, wieder her.  
  
 Diese Funktion wird die rückgängig-Statusinformationen für das Element nicht entleert. Dass Informationen aufbewahrt werden, damit [ReactivateAndUndo](#reactivateandundo) kann später verwendet werden, um einen Befehl "Rückgängig" in die Serveranwendung ausgeführt für den Fall, dass der Container den Befehl "Rückgängig" ausgewählt ist, sofort nach dem Deaktivieren des Elements.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::InPlaceDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) im Windows SDK.  
  
##  <a name="delete"></a>  COleClientItem::Delete  
 Rufen Sie diese Funktion, um das OLE-Element aus dem Containerdokument zu löschen.  
  
```  
void Delete(BOOL bAutoDelete = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bAutoDelete*  
 Gibt an, ob das Element aus dem Dokument entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft die [Version](#release) Memberfunktion, wodurch wiederum die C++-Objekt, für das Element, der dauerhaft entfernen des OLE-Elements aus dem Dokument gelöscht. Wenn das OLE-Element eingebettet ist, werden die systemeigenen Daten für das Element gelöscht. Es schließt immer einen laufenden Server; aus diesem Grund ist das Element über einen Link öffnen, wird geschlossen dieser Funktion.  
  
##  <a name="dodragdrop"></a>  COleClientItem::DoDragDrop  
 Rufen Sie die `DoDragDrop` Memberfunktion versucht, einen Drag & Drop-Vorgang auszuführen.  
  
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
 Das Element Rechteck auf dem Bildschirm in Clientkoordinaten (in Pixel).  
  
 *ptOffset*  
 Der Offset vom *LpItemRect* , bei denen die Position des Mauszeigers war zum Zeitpunkt des Ziehvorgangs.  
  
 *bIncludeLink*  
 Legen Sie diese auf "true" den Link, auf die Daten in die Zwischenablage kopiert werden sollen. Legen Sie sie auf "false", wenn die Serveranwendung Links nicht unterstützt.  
  
 *dwEffects*  
 Bestimmt, die Auswirkungen, die die Quelle des Ziehvorgangs in des Ziehvorgangs ermöglichen.  
  
 *lpRectStartDrag*  
 Zeiger auf das Rechteck, das definiert, in dem der Ziehvorgang tatsächlich gestartet. Weitere Informationen finden Sie im folgenden Abschnitt "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Ein-DropEffect-Wert. Wenn es sich um DROPEFFECT_MOVE handelt, sollte die ursprünglichen Daten entfernt werden.  
  
### <a name="remarks"></a>Hinweise  
 Der Drag & Drop-Vorgang wird nicht sofort gestartet. Er wartet, bis der Mauszeiger das durch angegebene Rechteck verlässt *LpRectStartDrag* oder eine angegebene Anzahl von Millisekunden verstrichen sind. Wenn *LpRectStartDrag* NULL ist, die Größe des Rechtecks ist 1 Pixel.  
  
 Die Verzögerungszeit wird durch eine registrierungsschlüsseleinstellung angegeben. Sie können die Verzögerungszeit ändern, durch den Aufruf [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) oder [CWinApp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint). Wenn Sie die Verzögerung nicht angeben, wird ein Standardwert 200 Millisekunden verwendet. Ziehen Sie Verzögerungszeit wird wie folgt gespeichert:  
  
-   Ziehen Sie die Windows NT-Verzögerungszeit wird in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay gespeichert.  
  
-   Windows 3.x Drag-Verzögerungszeit wird in der Windows-Taste gespeichert. INI-Datei unter dem [Windows}-Abschnitt.  
  
-   Ziehen Sie die Windows 95-und Windows 98-Verzögerungszeit wird in eine zwischengespeicherte Version des Windows-Taste gespeichert. INI.  
  
 Für Weitere Informationen ziehen wird der Informationen in der Registrierung gespeichert oder. INI-Datei finden Sie unter [WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) im Windows SDK.  
  
##  <a name="doverb"></a>  COleClientItem::DoVerb  
 Rufen Sie `DoVerb` auf das angegebene Verb aufzurufen.  
  
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
|- 0|Primäres Verb|OLEIVERB_PRIMARY|  
|- 1|Sekundäre verb|(Keine)|  
|- 1|Display-Element für die Bearbeitung|OLEIVERB_SHOW|  
|- 2|Element in separaten Fenster bearbeiten|OLEIVERB_OPEN|  
|- 3|Element ausblenden|OLEIVERB_HIDE|  
  
 Der Wert-1 wird in der Regel einen Alias für ein anderes Verb. Wenn Bearbeiten öffnen nicht unterstützt wird, hat-2 dieselbe Wirkung wie das-1 auf. Weitere Werte finden Sie unter [IOleObject](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) im Windows SDK.  
  
 *pView*  
 Zeiger auf das Fenster anzuzeigen; Dies wird durch den Server für die direkte Aktivierung verwendet werden. Dieser Parameter sollte NULL sein, wenn die Container-Anwendung keine direkte Aktivierung zulässt.  
  
 *lpMsg*  
 Zeiger auf die Meldung, die das Element, das aktiviert werden, verursacht hat.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Verb erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft die [aktivieren](#activate) Memberfunktion, die das Verb ausgeführt. Außerdem fängt Ausnahmen ab, und zeigt ein Meldungsfeld für den Benutzer, sofern eine ausgelöst wird.  
  
 Wenn das primäre Verb, bearbeiten ist und 0 (null), in angegeben wird der *nVerb* Parameter, die Server-Anwendung wird gestartet, um das OLE-Element bearbeitet werden können. Wenn die Container-Anwendung direkten Aktivierung unterstützt, kann bearbeiten an Stelle erfolgen. Wenn der Container nicht unterstützt wird, direkte Aktivierung (oder wenn das Verb öffnen angegeben ist), der Server in einem separaten Fenster gestartet und bearbeiten kann erfolgen vorhanden. In der Regel, wenn der Container-Anwendung doppelgeklickt das OLE-Element, den Wert für das primäre Verb in der *nVerb* Parameter bestimmt, welche Aktion, die der Benutzer durchführen kann. Allerdings, wenn der Server nur eine Aktion unterstützt werden, dauert es diese Aktion aus, unabhängig davon, welche-Wert, in angegeben wird der *nVerb* Parameter.  
  
##  <a name="draw"></a>  COleClientItem::Draw  
 Rufen Sie diese Funktion, um das OLE-Element in das angegebene umschließende Rechteck mit den angegebenen Gerätekontext gezeichnet werden soll.  
  
```  
BOOL Draw(
    CDC* pDC,  
    LPCRECT lpBounds,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Zeiger auf eine [CDC](../../mfc/reference/cdc-class.md) Objekt, das zum Zeichnen von OLE-Elements verwendet.  
  
 *lpBounds*  
 Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder `RECT` Struktur, die das umschließende Rechteck in der zum Zeichnen des OLE-Elements (in logischen Einheiten, die durch den Gerätekontext bestimmt) definiert.  
  
 *nDrawAspect*  
 Gibt an, der Aspekt von der OLE-Elements, d. h. wie es angezeigt werden soll. Wenn *nDrawAspect* ist-1, der letzte Aspekt, legen Sie mithilfe von [SetDrawAspect](#setdrawaspect) verwendet wird. Weitere Informationen zu den möglichen Werten für dieses Flag finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion können Sie die Metadateidarstellung des OLE-Elements erstellt, indem die [OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw) Memberfunktion `COleServerItem`.  
  
 In der Regel `Draw` für die Bildschirmanzeige, übergeben Sie den Bildschirm Gerätekontext als *pDC*. In diesem Fall müssen Sie nur die ersten beiden Parameter angeben.  
  
 Die *LpBounds* Parameter identifiziert das Rechteck in die Ziel-Gerätekontext (in Bezug auf die aktuelle Zuordnungsmodus). Rendering kann zur Folge haben das Bild skalieren und kann von containeranwendungen verwendet werden, um eine Ansicht zu erzwingen, die zwischen der angezeigten Ansicht und das letzte gedruckte Bild skaliert werden kann.  
  
 Weitere Informationen finden Sie unter [IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw) im Windows SDK.  
  
##  <a name="getactiveview"></a>  COleClientItem::GetActiveView  
 Gibt zurück, die Ansicht, die auf der das Element direkt aktiviert ist.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Sicht; Wenn das Element nicht direkt aktiviert ist, sonst NULL.  
  
##  <a name="getcachedextent"></a>  COleClientItem::GetCachedExtent  
 Rufen Sie diese Funktion das OLE-Element abzurufen.  
  
```  
BOOL GetCachedExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 *lpSize*  
 Zeiger auf eine `SIZE` Struktur oder ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die Größeninformationen erhält.  
  
 *nDrawAspect*  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen sind, abgerufen werden sollen. Mögliche Werte finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL Wenn erfolgreich; 0, wenn das OLE-Element leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bietet die gleiche Informationen wie [GetExtent](#getextent). Sie können jedoch aufrufen `GetCachedExtent` Umfang Informationen während der Verarbeitung andere OLE-Handler, wie z. B. abzurufenden [OnChange](#onchange). Die Dimensionen sind in MM_HIMETRIC Einheiten.  
  
 Dies ist möglich, da `GetCachedExtent` verwendet die [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2) Schnittstelle anstatt verwenden die [IOleObject](/windows/desktop/api/oleidl/nn-oleidl-ioleobject) Schnittstelle, um das Extent dieses Elements. Die `IViewObject2` COM-Objekt speichert die Block-Informationen verwendet, in dem vorherigen Aufruf von [IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw).  
  
 Weitere Informationen finden Sie unter [IViewObject2::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-iviewobject2-getextent) im Windows SDK.  
  
##  <a name="getclassid"></a>  COleClientItem::GetClassID  
 Gibt die Klassen-ID des Elements in den Arbeitsspeicher verweist *pClassID*.  
  
```  
void GetClassID(CLSID* pClassID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pClassID*  
 Zeiger auf einen Bezeichner des Typs [CLSID](/windows/desktop/com/clsid-key-hklm) die Klasse-ID abrufen Informationen dazu, CLSID finden Sie im Windows-SDK.  
  
### <a name="remarks"></a>Hinweise  
 Die Klassen-ID ist eine 128-Bit-Zahl, die eindeutig von der Anwendung, die das Element bearbeitet.  
  
 Weitere Informationen finden Sie unter [IPersist:: GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) im Windows SDK.  
  
##  <a name="getclipboarddata"></a>  COleClientItem::GetClipboardData  
 Mit dieser Funktion wird zum Abrufen einer `COleDataSource` -Objekt, das alle Daten, die durch einen Aufruf in der Zwischenablage abgelegt werden enthält die [CopyToClipboard](#copytoclipboard) Member-Funktion.  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pDataSource*  
 Zeiger auf eine [COleDataSource](../../mfc/reference/coledatasource-class.md) -Objekt, das die Daten in das OLE-Element erhält.  
  
 *bIncludeLink*  
 True, wenn die Daten des Quelllinks einbezogen werden sollen. andernfalls "false".  
  
 *lpOffset*  
 Der Offset des Mauszeigers über den Ursprung des Objekts in Pixel.  
  
 *lpSize*  
 Die Größe des Objekts in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 `GetClipboardData` wird aufgerufen, als die standardmäßige Implementierung des [OnGetClipboardData](#ongetclipboarddata). Außer Kraft setzen `OnGetClipboardData` nur, wenn Sie die Datenformate zusätzlich zu den Angeboten von Angeboten `CopyToClipboard`. Platzieren Sie diese Formate in der `COleDataSource` Objekt vor oder nach dem Aufruf `CopyToClipboard`, und übergeben Sie dann die `COleDataSource` -Objekt an die [COleDataSource](../../mfc/reference/coledatasource-class.md#setclipboard) Funktion. Z. B. Wenn Sie möchten, dass das OLE-Element-Position in die Containerdokument, die sie in der Zwischenablage begleitet, Sie definieren ein eigenes Format für die Übergabe dieser Informationen und versetzen Sie ihn in das `COleDataSource` vor dem Aufruf `CopyToClipboard`.  
  
##  <a name="getdocument"></a>  COleClientItem::GetDocument  
 Rufen Sie diese Funktion, um einen Zeiger auf das Dokument zu erhalten, die das OLE-Element enthält.  
  
```  
COleDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das OLE-Element enthält. NULL, wenn das Element nicht Teil eines Dokuments ist.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger ermöglicht den Zugriff auf die `COleDocument` Objekt, das Sie als Argument für das Übergeben der `COleClientItem` Konstruktor.  
  
##  <a name="getdrawaspect"></a>  COleClientItem::GetDrawAspect  
 Rufen Sie die `GetDrawAspect` Memberfunktion der aktuellen "Aspekt", oder die Ansicht des Elements zu bestimmen.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der DVASPECT-Enumeration, deren Werte Sie in der Referenz für finden [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaft gibt an, wie das Element gerendert werden soll.  
  
##  <a name="getextent"></a>  COleClientItem::GetExtent  
 Rufen Sie diese Funktion das OLE-Element abzurufen.  
  
```  
BOOL GetExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```  
  
### <a name="parameters"></a>Parameter  
 *lpSize*  
 Zeiger auf eine `SIZE` Struktur oder ein `CSize` -Objekt, das die Größeninformationen erhält.  
  
 *nDrawAspect*  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen sind, abgerufen werden sollen. Mögliche Werte finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL Wenn erfolgreich; 0, wenn das OLE-Element leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Serveranwendung über die Microsoft Foundation Class-Library geschrieben wurde, diese Funktion führt dazu, dass die [OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent) -Memberfunktion des entsprechenden `COleServerItem` Objekt aufgerufen werden. Beachten Sie, dass die abgerufene Größe der zuletzt festgelegten Größe unterscheidet sich möglicherweise die [SetExtent](#setextent) Member-Funktion, durch die angegebene Größe `SetExtent` behandelt, als einen Vorschlag. Die Dimensionen sind in MM_HIMETRIC Einheiten.  
  
> [!NOTE]
>  Rufen Sie keine `GetExtent` während der Verarbeitung eines OLE-Handlers, wie z. B. [OnChange](#onchange). Rufen Sie [GetCachedExtent](#getcachedextent) stattdessen.  
  
 Weitere Informationen finden Sie unter [IOleObject::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getextent) im Windows SDK.  
  
##  <a name="geticonfromregistry"></a>  COleClientItem::GetIconFromRegistry  
 Rufen Sie diese Memberfunktion, um ein Handle für eine Symbolressource mit dem Server von einer bestimmten CLSID verknüpft abzurufen.  
  
```  
HICON GetIconFromRegistry() const;  
  
static HICON GetIconFromRegistry(CLSID& clsid);
```  
  
### <a name="parameters"></a>Parameter  
 *clsid*  
 Ein Verweis auf die CLSID für den Server, auf dem Symbol zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiges handle für die Symbolressource oder NULL, wenn das Symbol des Servers oder ein Standardsymbol, nicht gefunden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird nicht starten Sie den Server oder ein Symbol dynamisch abrufen, selbst wenn der Server bereits ausgeführt wird. Diese Memberfunktion wird stattdessen ausführbares Image des Servers öffnet und ruft das Symbol "statische" mit dem Server verknüpft werden, da er registriert wurde.  
  
##  <a name="geticonicmetafile"></a>  COleClientItem::GetIconicMetafile  
 Ruft die Metadatei, die zum Zeichnen des Symbols ab.  
  
```  
HGLOBAL GetIconicMetafile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle der Metadatei im Erfolgsfall; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine aktuelle Symbol vorhanden ist, wird ein Standardsymbol zurückgegeben. Dies wird automatisch aufgerufen, indem Sie die MFC/OLE-Dialogfelder und wird in der Regel nicht direkt aufgerufen.  
  
 Diese Funktion ruft auch [SetIconicMetafile](#seticonicmetafile) die Metadatei für die spätere Verwendung zwischengespeichert.  
  
##  <a name="getinplacewindow"></a>  COleClientItem::GetInPlaceWindow  
 Rufen Sie die `GetInPlaceWindow` Memberfunktion versucht, einen Zeiger auf das Fenster, in dem das Element geöffnet wurde, für direktes Editieren zu erhalten.  
  
```  
CWnd* GetInPlaceWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Element des direktes-Bearbeitungsfenster; NULL, wenn das Element nicht aktiv ist oder wenn der Server nicht verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur für Elemente aufgerufen werden, die direkt aktiv sind.  
  
##  <a name="getitemstate"></a>  COleClientItem::GetItemState  
 Rufen Sie diese Funktion, um das OLE-Element des aktuellen Status abzurufen.  
  
```  
UINT GetItemState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `COleClientItem::ItemState` -Enumerationswert ab, die in der folgenden Werte sind möglich: `emptyState`, `loadedState`, `openState`, `activeState`, `activeUIState`. Informationen zu diesen Statuswerten finden Sie im Artikel [Container: Client-Element-Zustände](../../mfc/containers-client-item-states.md).  
  
### <a name="remarks"></a>Hinweise  
 Verwenden, um benachrichtigt zu werden, wenn das OLE-Element-Zustand ändert die [OnChange](#onchange) Member-Funktion.  
  
 Weitere Informationen finden Sie im Artikel [Container: Client-Element-Zustände](../../mfc/containers-client-item-states.md).  
  
##  <a name="getlaststatus"></a>  COleClientItem::GetLastStatus  
 Gibt den Statuscode der der letzte OLE-Vorgang zurück.  
  
```  
SCODE GetLastStatus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein SCODE-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Für Memberfunktionen, die einen Booleschen Wert "false" oder andere Member Funktionen zurückgeben, die NULL zurückgeben, `GetLastStatus` gibt detailliertere Fehlerinformationen. Denken Sie daran, dass die meisten OLE-Memberfunktionen für schwerwiegenderen Fehlern Ausnahmen ausgelöst. Die spezifische Informationen zur Interpretation von der SCODE hängt von der zugrunde liegenden OLE-Aufruf, der zuletzt ein SCODE Wert zurückgegeben.  
  
 Weitere Informationen zu SCODE, finden Sie unter [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes) in der Windows SDK-Dokumentation.  
  
##  <a name="getlinkupdateoptions"></a>  COleClientItem::GetLinkUpdateOptions  
 Rufen Sie diese Funktion, um den aktuellen Wert der Option zur Link-Update für das OLE-Element abzurufen.  
  
```  
OLEUPDATE GetLinkUpdateOptions();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- OLEUPDATE_ALWAYS aktualisieren Sie das verknüpfte Element nach Möglichkeit. Diese Option unterstützt das Optionsfeld für die automatische Link-Update im Dialogfeld "Links".  
  
- OLEUPDATE_ONCALL aktualisieren Sie das verknüpfte Element nur auf Anforderung die Container-Anwendung (wenn die [UpdateLink](#updatelink) Memberfunktion aufgerufen wird). Diese Option unterstützt das Optionsfeld für die manuelle Link-Update im Dialogfeld "Links".  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein erweiterter Vorgang.  
  
 Diese Funktion aufgerufen wird, automatisch von der [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) Klasse.  
  
 Weitere Informationen finden Sie unter [IOleLink::GetUpdateOptions](/windows/desktop/api/oleidl/nf-oleidl-iolelink-getupdateoptions) im Windows SDK.  
  
##  <a name="gettype"></a>  COleClientItem::GetType  
 Rufen Sie diese Funktion, um zu bestimmen, ob das OLE-Element eingebettet oder verknüpft ist, oder statisch.  
  
```  
OLE_OBJTYPE GetType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ganze Zahl ohne Vorzeichen mit einem der folgenden Werte:  
  
- OT_LINK das OLE-Element ist ein Link.  
  
- OT_EMBEDDED das OLE-Element eingebettet ist.  
  
- OT_STATIC das OLE-Element ist statisch, das heißt, er enthält nur Präsentationsdaten nicht systemeigen und kann daher nicht bearbeitet werden.  
  
##  <a name="getusertype"></a>  COleClientItem::GetUserType  
 Mit dieser Funktion können Sie die Benutzer sichtbare Zeichenfolge, die das OLE-Element-Typ, z. B. "Word-Dokument" beschreibt abzurufen  
  
```  
void GetUserType(
    USERCLASSTYPE nUserClassType,  
    CString& rString);
```  
  
### <a name="parameters"></a>Parameter  
 *nUserClassType*  
 Ein Wert, der angibt, der gewünschte Variante der Zeichenfolge, die das OLE-Element-Typ beschreibt. Dies kann einen der folgenden Werte aufweisen:  
  
- USERCLASSTYPE_FULL der vollständige Typname für den Benutzer angezeigt.  
  
- USERCLASSTYPE_SHORT ein kurzer Name (maximal 15 Zeichen) für die Verwendung in der Popup-Menüs und im Dialogfeld "Verknüpfungen bearbeiten".  
  
- USERCLASSTYPE_APPNAME-Name, der die Anwendung, die Wartung der-Klasse.  
  
 *rString*  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt aus, die die Zeichenfolge, die das OLE-Element-Typ beschreibt, die zurückgegeben werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist häufig der Eintrag in der Registrierung-Systemdatenbank.  
  
 Wenn der vollständige Typname angeforderte, aber nicht verfügbar ist, wird der Kurzname wird stattdessen verwendet. Das OLE-Element wird verwendet, wenn kein Eintrag für den Typ des OLE-Element in der Registrierungsdatenbank gefunden wird, oder es sind keine Typen für den Typ des OLE-Element registriert, klicken Sie dann der Benutzertyp derzeit in gespeichert. Wenn es sich bei diesen Benutzernamen für den Typ auf eine leere Zeichenfolge ist, wird "Unbekannte Objekt" verwendet.  
  
 Weitere Informationen finden Sie unter [IOleObject::GetUserType](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getusertype) im Windows SDK.  
  
##  <a name="isinplaceactive"></a>  COleClientItem::IsInPlaceActive  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element direkt aktiv ist.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das OLE-Element direkt aktiv ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Es ist üblich, führen Sie eine unterschiedliche Logik abhängig davon, ob das Element direkt bearbeitet wird. Die Funktion überprüft, ob der aktuelle Zustand des Elements entweder gleich der `activeState` oder `activeUIState`.  
  
##  <a name="islinkuptodate"></a>  COleClientItem::IsLinkUpToDate  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element auf dem neuesten Stand ist.  
  
```  
BOOL IsLinkUpToDate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das OLE-Element auf dem neuesten Stand ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein verknüpftes Element kann veraltet sein, wenn die Quell-Dokuments aktualisiert wurde. Ein eingebettetes Element, das Links in diesem enthält kann auf ähnliche Weise veralten. Die Funktion ist eine rekursive Überprüfung des OLE-Elements. Beachten Sie, dass so teuer wie die tatsächlich ein Update ausgeführt werden kann, bestimmen, ob ein OLE-Element nicht mehr aktuell ist.  
  
 Dies wird automatisch vom bezeichnet die [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) Implementierung.  
  
 Weitere Informationen finden Sie unter [IOleObject::IsUpToDate](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-isuptodate) im Windows SDK.  
  
##  <a name="ismodified"></a>  COleClientItem::IsModified  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element geändert wurde (wird geändert, seit es zuletzt gespeichert wurde).  
  
```  
BOOL IsModified() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn das OLE-Element geändert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IPersistStorage::IsDirty](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-isdirty) im Windows SDK.  
  
##  <a name="isopen"></a>  COleClientItem::IsOpen  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element geöffnet ist. d. h. in einer Instanz von die Serveranwendung ausgeführt wird, in einem separaten Fenster geöffnet.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das OLE-Element geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Es wird verwendet, um zu bestimmen, wann das Objekt mit dem ein Schraffurmuster, das gezeichnet werden soll. Ein geöffnetes Objekt sollte eine Schraffur auf das Objekt gezeichnet haben. Sie können eine [CRectTracker](../../mfc/reference/crecttracker-class.md) Objekt, um dies zu erreichen.  
  
##  <a name="isrunning"></a>  COleClientItem::IsRunning  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element ausgeführt wird. Gibt an, ob das Element geladen ist und in die Serveranwendung ausgeführt wird.  
  
```  
BOOL IsRunning() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das OLE-Element ausgeführt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OleIsRunning](/windows/desktop/api/ole2/nf-ole2-oleisrunning) im Windows SDK.  
  
##  <a name="onactivate"></a>  COleClientItem::OnActivate  
 Wird aufgerufen, durch das Framework, um dem Element zu benachrichtigen, dass es nur in direkten aktiviert wurde.  
  
```  
virtual void OnActivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass diese Funktion aufgerufen wird, um anzugeben, dass der Server läuft nicht, um anzugeben, dass die Benutzeroberfläche in die Container-Anwendung installiert wurde. Das Objekt verfügt an diesem Punkt nicht über eine Benutzeroberfläche für die aktive (nicht `activeUIState`). Sie hat nicht die Menüs oder Symbolleisten installiert. Die [OnActivateUI](#onactivateui) Memberfunktion aufgerufen wird, wenn dies der Fall ist.  
  
 Die Standardimplementierung Ruft die [OnChange](#onchange) Member-Funktion mit OLE_CHANGEDSTATE als Parameter. Überschreiben Sie diese Funktion zum Ausführen der benutzerdefinierten Verarbeitung, wenn ein Element direkt aktiv ist.  
  
##  <a name="onactivateui"></a>  COleClientItem::OnActivateUI  
 Das Framework ruft `OnActivateUI` Wenn das Objekt den aktiven Benutzeroberflächenzustand gewechselt hat.  
  
```  
virtual void OnActivateUI();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt hat jetzt die Symbolleiste und Menüs installiert.  
  
 Die standardmäßige Implementierung des Servers HWND speichert, für die spätere Verwendung `GetServerWindow` aufrufen.  
  
##  <a name="onchange"></a>  COleClientItem:: OnChange  
 Vom Framework aufgerufen, wenn der Benutzer ändert, speichert oder das OLE-Element schließt.  
  
```  
virtual void OnChange(
    OLE_NOTIFICATION nCode,  
    DWORD dwParam);
```  
  
### <a name="parameters"></a>Parameter  
 *nCode*  
 Der Grund der Server geändert, dieses Element. Es kann einen der folgenden Werte aufweisen:  
  
- OLE_CHANGED das OLE Element Darstellung wurde geändert.  
  
- OLE_SAVED das OLE-Element wurde gespeichert.  
  
- OLE_CLOSED das OLE-Element wurde geschlossen.  
  
- OLE_CHANGED_STATE das OLE-Element wurde von einem Zustand in einen anderen geändert.  
  
 *dwParam*  
 Wenn *nCode* OLE_SAVED oder OLE_CLOSED, ist dieser Parameter wird nicht verwendet. Wenn *nCode* OLE_CHANGED, ist dieser Parameter gibt an, den Aspekt des OLE-Elements, die geändert wurde. Mögliche Werte finden Sie unter den *DwParam* Parameter [COleClientItem::Draw](#draw). Wenn *nCode* OLE_CHANGED_STATE, ist dieser Parameter ist ein `COleClientItem::ItemState` -Enumerationswert ab, und beschreibt den Status, die eingegeben wird. Es kann einen der folgenden Werte aufweisen: `emptyState`, `loadedState`, `openState`, `activeState`, oder `activeUIState`.  
  
### <a name="remarks"></a>Hinweise  
 (Wenn die Serveranwendung über die Microsoft Foundation Class-Library geschrieben ist, diese Funktion wird aufgerufen als Reaktion auf die `Notify` Memberfunktionen der `COleServerDoc` oder `COleServerItem`.) Die Standardimplementierung Containerdokument markiert, als wenn geändert *nCode* OLE_CHANGED oder OLE_SAVED ist.  
  
 Für OLE_CHANGED_STATE, der aktuelle Status von zurückgegeben [GetItemState](#getitemstate) werden weiterhin der alte Status, d. h. den Zustand, der vor dieser statusänderung aktuell war.  
  
 Überschreiben Sie diese Funktion, um die Reaktion auf Änderungen in den Zustand des OLE-Elements. In der Regel aktualisieren Sie das Element in der Darstellung durch das Ungültigmachen des Bereichs, in dem das Element angezeigt wird. Rufen Sie die basisklassenimplementierung am Anfang der Außerkraftsetzung.  
  
##  <a name="onchangeitemposition"></a>  COleClientItem:: OnChangeItemPosition auf  
 Wird aufgerufen, durch das Framework den Container zu benachrichtigen, den dass das OLE-Element-Block während der Aktivierung des direktes geändert hat.  
  
```  
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```  
  
### <a name="parameters"></a>Parameter  
 *rectPos*  
 Gibt an der Position des Elements relativ zum Clientbereich der containeranwendung.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Position des Elements erfolgreich geändert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bestimmt, die standardmäßige Implementierung der neue sichtbare Rechteck des OLE-Element und ruft [SetItemRects](#setitemrects) mit den neuen Werten. Die Standardimplementierung berechnet das Rechteck für das Element sichtbar und übergibt diese Informationen an den Server.  
  
 Überschreiben Sie diese Funktion zum gelten spezielle Regeln an die Größenänderung/Move-Vorgangs. Wenn die Anwendung in MFC geschrieben ist, wird dieser Aufruf führt, da der Server aufgerufen [COleServerDoc::RequestPositionChange](../../mfc/reference/coleserverdoc-class.md#requestpositionchange).  
  
##  <a name="ondeactivate"></a>  COleClientItem::OnDeactivate  
 Vom Framework aufgerufen, wenn das OLE-Element aus den aktiven Status des direktes wechselt ( `activeState`) in den geladenen Zustand, was bedeutet, dass es nach einer Aktivierung des direktes deaktiviert wird.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass diese Funktion aufgerufen wird, um anzugeben, dass das OLE-Element, nicht geschlossen ist, die die Benutzeroberfläche aus der containeranwendung entfernt wurde. In diesem Fall die [OnDeactivateUI](#ondeactivateui) Memberfunktion aufgerufen wird.  
  
 Die Standardimplementierung Ruft die [OnChange](#onchange) Member-Funktion mit OLE_CHANGEDSTATE als Parameter. Überschreiben Sie diese Funktion zum Ausführen der benutzerdefinierten Verarbeitung, wenn ein direktes aktives Element deaktiviert wird. Z. B. Wenn Sie den Befehl "Rückgängig" in Ihrem Container-Anwendung unterstützen, können Sie überschreiben diese Funktion, um den Zustand "Rückgängig" zu verwerfen, der angibt, dass es sich bei der letzten Vorgang für das OLE-Element kann nicht rückgängig gemacht werden, nachdem das Element deaktiviert ist.  
  
##  <a name="ondeactivateandundo"></a>  COleClientItem::OnDeactivateAndUndo  
 Wird vom Framework aufgerufen, wenn der Benutzer den Befehl "Rückgängig" aufruft, nach dem Aktivieren der OLE-Element vorhanden.  
  
```  
virtual void OnDeactivateAndUndo();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft [DeactivateUI](#deactivateui) So deaktivieren Sie die Benutzeroberfläche des Servers. Überschreiben Sie diese Funktion, wenn Sie den Befehl "Rückgängig" in Ihrem Container-Anwendung implementieren. Klicken Sie in der Überschreibung Aufrufen der Funktion die Basisklassenversion, und klicken Sie dann rückgängig-mit dem letzten Befehl in Ihrer Anwendung ausgeführt.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::DeactivateAndUndo](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-deactivateandundo) im Windows SDK.  
  
##  <a name="ondeactivateui"></a>  COleClientItem::OnDeactivateUI  
 Wird aufgerufen, wenn der Benutzer ein Element deaktiviert, das direkt aktiviert wurde.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Parameter  
 *bUndoable*  
 Gibt an, ob die Änderungen rückgängig zu machen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion stellt die Benutzeroberfläche für die Container-Anwendung auf den ursprünglichen Zustand, Ausblenden von alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden, wieder her.  
  
 Wenn *bUndoable* "FALSE" ist der Container muss den Befehl "Rückgängig", in Kraft Verwerfen des Containers, wieder rückgängig zu machen, da bedeutet dies, dass der letzte Vorgang, der vom Server ausgeführt werden, nicht annullierbar ist deaktiviert.  
  
##  <a name="ondiscardundostate"></a>  COleClientItem::OnDiscardUndoState  
 Wird vom Framework aufgerufen, wenn der Benutzer eine Aktion, die wieder rückgängig zu machen, die ausführt während der Bearbeitung der OLE-Element werden verworfen.  
  
```  
virtual void OnDiscardUndoState();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, wenn Sie den Befehl "Rückgängig" in Ihrem Container-Anwendung implementieren. Verwerfen Sie Sie in der Überschreibung der containeranwendung Zustand.  
  
 Wenn der Server mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, kann der Server diese Funktion durch den Aufruf aufgerufen werden [COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate).  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::DiscardUndoState](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-discardundostate) im Windows SDK.  
  
##  <a name="ongetclipboarddata"></a>  COleClientItem::OnGetClipboardData  
 Wird aufgerufen, durch das Framework zum Abrufen eine `COleDataSource` -Objekt, enthält alle Daten, die durch einen Aufruf von entweder in der Zwischenablage abgelegt werden die [CopyToClipboard](#copytoclipboard) oder [DoDragDrop](#dodragdrop) Member-Funktion.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>Parameter  
 *bIncludeLink*  
 Legen Sie diese Einstellung auf "true" Verknüpfen von Daten in die Zwischenablage kopiert werden sollen. Legen Sie diese Einstellung auf "false" fest, wenn Ihr Server Links der Anwendung nicht unterstützt.  
  
 *lpOffset*  
 Zeiger auf den Offset des Mauscursors vom Ursprung des Objekts in Pixel.  
  
 *lpSize*  
 Zeiger auf die Größe des Objekts in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [COleDataSource](../../mfc/reference/coledatasource-class.md) -Objekt, das Daten in der Zwischenablage enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion [GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetcliprect"></a>  COleClientItem::OnGetClipRect  
 Das Framework Ruft die `OnGetClipRect` Member-Funktion bei der Einrichtung die Auswahlrechteck Koordinaten des Elements, das gerade bearbeitet wird.  
  
```  
virtual void OnGetClipRect(CRect& rClipRect);
```  
  
### <a name="parameters"></a>Parameter  
 *rClipRect*  
 Zeiger auf ein Objekt der Klasse [CRect](../../atl-mfc-shared/reference/crect-class.md) enthält, die die Auswahlrechteck Koordinaten des Elements.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zum Clientbereich der Anwendungsfenster Container.  
  
 Die Standardimplementierung gibt einfach das Clientrechteck der Ansicht auf der das Element direkt aktiv ist.  
  
##  <a name="ongetitemposition"></a>  COleClientItem:: OnGetItemPosition auf  
 Das Framework Ruft die `OnGetItemPosition` Member-Funktion bei der Einrichtung die Koordinaten des Elements, das gerade bearbeitet wird.  
  
```  
virtual void OnGetItemPosition(CRect& rPosition);
```  
  
### <a name="parameters"></a>Parameter  
 *rposition zurück*  
 Ein Verweis auf die [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das Positionskoordinaten des Elements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zum Clientbereich der Anwendungsfenster Container.  
  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Anwendungen mit Unterstützung für direktes Editieren erfordern die Implementierung.  
  
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
 Zeiger auf einen Zeiger auf das Hauptrahmenfenster.  
  
 *ppDocFrame*  
 Zeiger auf einen Zeiger auf die Dokumentrahmenfenster.  
  
 *lpFrameInfo*  
 Zeiger auf ein [OLEINPLACEFRAMEINFO](/windows/desktop/api/oleidl/ns-oleidl-tagoifi) -Struktur, die Frame-Fensters-Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion dient zum Abrufen von Informationen über die OLE-Element des übergeordneten Fensters.  
  
 Wenn der Container eine MDI-Anwendung ist, wird die Standardimplementierung gibt einen Zeiger auf die [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) im-Objekt *PpMainFrame* und einen Zeiger auf den aktiven [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)im-Objekt *PpDocFrame*. Wenn der Container eine SDI-Anwendung ist, wird die Standardimplementierung gibt einen Zeiger auf die [CFrameWnd](../../mfc/reference/cframewnd-class.md) im-Objekt *PpMainFrame* und gibt Sie NULL-Wert in *PpDocFrame*. Die standardmäßige Implementierung trägt auch die Elemente der *LpFrameInfo*.  
  
 Überschreiben Sie diese Funktion nur, wenn die standardmäßige Implementierung Ihrer Anwendung nicht geeignet ist; beispielsweise wenn Ihre Anwendung eine Sichtweise der Benutzeroberfläche dar, die von SDI- oder MDI-abweicht. Dies ist ein fortschrittlicher überschreibbar.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-getwindowcontext) und [OLEINPLACEFRAMEINFO](/windows/desktop/api/oleidl/ns-oleidl-tagoifi) Struktur im Windows SDK.  
  
##  <a name="oninsertmenus"></a>  COleClientItem::OnInsertMenus  
 Wird vom Framework aufgerufen, während der direkten Aktivierung um Menüs für die Container-Anwendung in ein leeres Menü einzufügen.  
  
```  
virtual void OnInsertMenus(
    CMenu* pMenuShared,  
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```  
  
### <a name="parameters"></a>Parameter  
 *pMenuShared*  
 Verweist auf ein leeres Menü.  
  
 *lpMenuWidths*  
 Verweist auf ein Array von sechs LONG-Werte, der angibt, wie viele Menüs in jeder der folgenden Menügruppen sind: Datei, bearbeiten, Container, Fenster Objekt-Hilfe. Die Container-Anwendung ist verantwortlich für die Datei, Container und Fenster im Menügruppen, für die Elemente 0, 2 und 4 dieses Arrays.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Menü wird dann an den Server übergeben, den eigenen Menüs, erstellen ein zusammengesetztes Menü eingefügt. Diese Funktion kann wiederholt aufgerufen werden, um mehrere zusammengesetzte Menüs zu erstellen.  
  
 Die Standardimplementierung fügt *pMenuShared* die Containermenüs des direktes, d. h. die Datei, Container und Fenster im Menü-Gruppen. [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo) dient zum Festlegen der Menüressource. Die Standardimplementierung weist auch die entsprechenden Werte für die Elemente 0, 2 und 4 im *LpMenuWidths*, je nachdem, auf die Menüressource. Überschreiben Sie diese Funktion, wenn die standardmäßige Implementierung nicht für Ihre Anwendung geeignet ist; Wenn beispielsweise Ihre Anwendung keine Dokumentvorlagen verwendet werden, für das Verknüpfen von Ressourcen mit Dokumenttypen. Wenn Sie diese Funktion überschreiben, sollten Sie auch überschreiben [OnSetMenu](#onsetmenu) und [OnRemoveMenus](#onremovemenus). Dies ist ein fortschrittlicher überschreibbar.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceFrame:: InsertMenus ein](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceframe-insertmenus) im Windows SDK.  
  
##  <a name="onremovemenus"></a>  COleClientItem::OnRemoveMenus  
 Wird aufgerufen, durch das Framework die Menüs des Containers aus dem angegebenen zusammengesetzten Menü zu entfernen, bei der direkten Aktivierung beendet.  
  
```  
virtual void OnRemoveMenus(CMenu* pMenuShared);
```  
  
### <a name="parameters"></a>Parameter  
 *pMenuShared*  
 Verweist auf das zusammengesetzte Menü erstellt, die durch Aufrufe der [OnInsertMenus](#oninsertmenus) Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung entfernt aus *pMenuShared* direktes allen Containermenüs, die, die Datei, Container und Fenster im Menü-Gruppen. Überschreiben Sie diese Funktion, wenn die standardmäßige Implementierung nicht für Ihre Anwendung geeignet ist; Wenn beispielsweise Ihre Anwendung keine Dokumentvorlagen verwendet werden, für das Verknüpfen von Ressourcen mit Dokumenttypen. Wenn Sie diese Funktion überschreiben, sollten Sie wahrscheinlich überschreiben [OnInsertMenus](#oninsertmenus) und [OnSetMenu](#onsetmenu) ebenfalls. Dies ist ein fortschrittlicher überschreibbar.  
  
 Die Untermenüs auf *pMenuShared* kann von mehr als ein zusammengesetztes Menü freigegeben werden, wenn der Server wiederholt aufgerufen hat `OnInsertMenus`. Aus diesem Grund sollten Sie alle Untermenüs nicht löschen, in der Überschreibung der `OnRemoveMenus`; Sie sollten nur trennen.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceFrame::RemoveMenus](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceframe-removemenus) im Windows SDK.  
  
##  <a name="onscrollby"></a>  COleClientItem::OnScrollBy  
 Wird aufgerufen, durch das Framework das OLE-Element als Antwort auf Anforderungen vom Server zu scrollen.  
  
```  
virtual BOOL OnScrollBy(CSize sizeExtent);
```  
  
### <a name="parameters"></a>Parameter  
 *sizeExtent*  
 Gibt die Abstände in Pixel, um die Anweisungen in der x- und y zu scrollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Element ein Bildlauf ausgeführt wurde; 0, wenn das Element kein Bildlauf durchgeführt werden konnte.  
  
### <a name="remarks"></a>Hinweise  
 Beispielsweise wird Wenn das OLE-Element nur teilweise sichtbar ist, und der Benutzer, die außerhalb des sichtbaren Bereichs beim Ausführen des direktes Editieren bewegt, diese Funktion aufgerufen, um den Cursor sichtbar bleiben. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um das Element den angegebenen Betrag zu scrollen. Beachten Sie, dass aufgrund scrollen, der sichtbare Teil der OLE-Element ändern kann. Rufen Sie [SetItemRects](#setitemrects) sichtbares Rechteck des Elements zu aktualisieren.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::Scroll](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-scroll) im Windows SDK.  
  
##  <a name="onsetmenu"></a>  COleClientItem::OnSetMenu  
 Aufgerufen vom Framework doppelt so groß wie bei der direkten Aktivierung beginnt und endet. So installieren Sie das zusammengesetzte Menü und beim zweiten Mal beim ersten (mit *Holemenu* gleich NULL), ihn zu entfernen.  
  
```  
virtual void OnSetMenu(
    CMenu* pMenuShared,  
    HOLEMENU holemenu,  
    HWND hwndActiveObject);
```  
  
### <a name="parameters"></a>Parameter  
 *pMenuShared*  
 Zeiger auf das zusammengesetzte Menü erstellt, die durch Aufrufe der [OnInsertMenus](#oninsertmenus) Member-Funktion und die `InsertMenu` Funktion.  
  
 *holemenu*  
 Handle für den Menü-Deskriptor zurückgegeben werden, indem die `OleCreateMenuDescriptor` Funktion, oder NULL, wenn die Verteilung Code entfernt werden soll.  
  
 *hwndActiveObject*  
 Handle für das Bearbeitungsfenster für das OLE-Element. Dies ist das Fenster, das Befehle zum Bearbeiten von OLE empfangen wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung installiert oder entfernt das zusammengesetzte Menü und ruft dann die [OleSetMenuDescriptor](/windows/desktop/api/ole2/nf-ole2-olesetmenudescriptor) Funktion zu installieren oder entfernen Sie den Code der Verteilung. Überschreiben Sie diese Funktion, wenn die standardmäßige Implementierung nicht für Ihre Anwendung geeignet ist. Wenn Sie diese Funktion überschreiben, sollten Sie wahrscheinlich überschreiben [OnInsertMenus](#oninsertmenus) und [OnRemoveMenus](#onremovemenus) ebenfalls. Dies ist ein fortschrittlicher überschreibbar.  
  
 Weitere Informationen finden Sie unter [OleCreateMenuDescriptor](/windows/desktop/api/ole2/nf-ole2-olecreatemenudescriptor), [OleSetMenuDescriptor](/windows/desktop/api/ole2/nf-ole2-olesetmenudescriptor), und [SetMenu](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceframe-setmenu) im Windows SDK.  
  
##  <a name="onshowcontrolbars"></a>  COleClientItem::OnShowControlBars  
 Wird aufgerufen, durch das Framework zum ein- und Ausblenden von Steuerleisten die Container-Anwendung.  
  
```  
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 *pFrameWnd*  
 Zeiger auf das Rahmenfenster der containeranwendung. Dies kann entweder ein Hauptrahmenfenster oder eines untergeordneten MDI-Fensters sein.  
  
 *bShow*  
 Gibt an, ob Steuerleisten angezeigt oder ausgeblendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Funktionsaufruf bewirkt, eine Änderung in den Steuerleisten-Zustand dass; 0, wenn der Aufruf führt dazu, dass keine Änderung oder *pFrameWnd* Rahmenfenster des Containers nicht auf.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt 0 zurück, wenn die Steuerleisten bereits vom angegebenen Zustand werden *bShow.* Dies würde z. B. auftreten, wenn die Steuerleisten ausgeblendet sind und *bShow* ist "false".  
  
 Die standardmäßige Implementierung entfernt die Symbolleiste im Fenster der obersten Ebene Frame.  
  
##  <a name="onshowitem"></a>  COleClientItem::OnShowItem  
 Wird aufgerufen, durch das Framework zum Anzeigen des OLE-Elements, während der Bearbeitung vollständig sichtbar machen.  
  
```  
virtual void OnShowItem();
```  
  
### <a name="remarks"></a>Hinweise  
 Wird verwendet, wenn Ihre containeranwendung mit Links zu eingebetteten Elemente unterstützt (d. h., wenn Sie die Dokumentklasse von abgeleitet haben [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)). Diese Funktion wird aufgerufen, während der direkten Aktivierung oder wenn das OLE-Element eine Link-Quelle ist und der Benutzer möchte, um sie zu bearbeiten. Die standardmäßige Implementierung wird die erste Ansicht des Dokuments Container aktiviert. Überschreiben Sie diese Funktion, um das Dokument einen Bildlauf durchführen, damit das OLE-Element sichtbar ist.  
  
##  <a name="onupdateframetitle"></a>  COleClientItem::OnUpdateFrameTitle  
 Vom Framework aufgerufen, während der direkten Aktivierung des Rahmenfensters Titelleiste zu aktualisieren.  
  
```  
virtual BOOL OnUpdateFrameTitle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn diese Funktion wurde erfolgreich aktualisiert den Frametitel, andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ändert nicht den Fenstertitel Frame. Überschreiben Sie diese Funktion ggf. einen anderen Frametitel für Ihre Anwendung z. B. " *Serveranwendung* - *Element* in *Docname*" (z. B. "Microsoft Excel - Arbeitsblatt im Bericht. DOKUMENT"). Dies ist ein fortschrittlicher überschreibbar.  
  
##  <a name="reactivateandundo"></a>  COleClientItem::ReactivateAndUndo  
 Rufen Sie diese Funktion zum Reaktivieren des OLE-Elements und den letzten Vorgang, der vom Benutzer ausgeführt werden, während der direkten Bearbeitung rückgängig zu machen.  
  
```  
BOOL ReactivateAndUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die containeranwendung den Befehl "Rückgängig" unterstützt, rufen Sie diese Funktion, wenn der Benutzer den Befehl "Rückgängig" wählt, sofort nach dem Deaktivieren von OLE-Elements.  
  
 Wenn die Server-Anwendung mit die Microsoft Foundation Class-Bibliotheken geschrieben ist, diese Funktion bewirkt, dass die Server Aufrufen [COleServerDoc::OnReactivateAndUndo](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo).  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::ReactivateAndUndo](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) im Windows SDK.  
  
##  <a name="release"></a>  COleClientItem::Release  
 Rufen Sie diese Funktion zum Bereinigen von Ressourcen, die von der OLE-Element verwendet.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Parameter  
 *dwCloseOption*  
 Flag, das angibt, unter welchen Umständen das OLE-Element gespeichert wird, wenn in den geladenen Zustand zurückgegeben. Eine Liste der möglichen Werte, finden Sie unter [COleClientItem::Close](#close).  
  
### <a name="remarks"></a>Hinweise  
 `Release` wird aufgerufen, indem die `COleClientItem` Destruktor.  
  
 Weitere Informationen finden Sie unter [IUnknown:: Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) im Windows SDK.  
  
##  <a name="reload"></a>  COleClientItem::Reload  
 Schließt ein, und lädt das Element.  
  
```  
BOOL Reload();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `Reload` Funktion nach dem Aktivieren des Elements als Element eines anderen Typs durch einen Aufruf von [ActivateAs](#activateas).  
  
##  <a name="run"></a>  COleClientItem::Run  
 Führt die Anwendung, die diesem Element zugeordnet.  
  
```  
void Run();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `Run` Member-Funktion, um die Serveranwendung vor der Aktivierung des Elements starten. Dies erfolgt automatisch durch [aktivieren](#activate) und [DoVerb](#doverb), sodass es in der Regel nicht notwendig, diese Funktion ist. Wenn es erforderlich, auf dem Server ausgeführt wird, um ein Elementattribut, z. B. festgelegt ist, rufen Sie diese Funktion [SetExtent](#setextent), vor der Ausführung [DoVerb](#doverb).  
  
##  <a name="setdrawaspect"></a>  COleClientItem::SetDrawAspect  
 Rufen Sie die `SetDrawAspect` Memberfunktion versucht, die "Aspekt" oder die Ansicht des Elements festgelegt.  
  
```  
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Parameter  
 *nDrawAspect*  
 Ein Wert aus der DVASPECT-Enumeration. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- DVASPECT_CONTENT-Element wird so dargestellt, dass es als eingebettetes Objekt in dessen Container angezeigt werden kann.  
  
- DVASPECT_THUMBNAIL-Element wird in eine "Miniaturansicht" Darstellung gerendert, damit es in einem Browser angezeigt werden kann.  
  
- DVASPECT_ICON-Element wird durch ein Symbol dargestellt.  
  
- DVASPECT_DOCPRINT-Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Der Aspekt gibt an, wie das Element gerendert werden [zeichnen](#draw) Wenn der Standardwert für diese Funktion die *nDrawAspect* Argument wird verwendet.  
  
 Diese Funktion wird automatisch aufgerufen, durch das Symbol ändern (und andere Dialogfelder, die das Dialogfeld "Symbol ändern" direkt aufrufen), aktivieren Sie den Aspekt Symbol angezeigt, wenn vom Benutzer angefordert.  
  
##  <a name="setextent"></a>  COleClientItem::SetExtent  
 Rufen Sie diese Funktion aus, um anzugeben, wie viel Speicherplatz für das OLE-Element verfügbar ist.  
  
```  
void SetExtent(
    const CSize& size,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parameter  
 *size*  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die Größeninformationen enthält.  
  
 *nDrawAspect*  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen sind festgelegt werden. Mögliche Werte finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Serveranwendung über die Microsoft Foundation Class-Library geschrieben wurde, wird dadurch die [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent) -Memberfunktion des entsprechenden `COleServerItem` Objekt aufgerufen werden. Das OLE-Element kann die Anzeige klicken Sie dann entsprechend anpassen. Die Dimensionen müssen in MM_HIMETRIC Einheiten sein. Rufen Sie diese Funktion, wenn der Benutzer das OLE-Element ändert oder wenn Sie eine Form der Layout-Verhandlung unterstützen.  
  
 Weitere Informationen finden Sie unter [IOleObject:: SetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setextent) im Windows SDK.  
  
##  <a name="sethostnames"></a>  COleClientItem::SetHostNames  
 Rufen Sie diese Funktion, um den Namen der Container-Anwendung und des Containers-Namen für einen eingebetteten OLE-Element angeben.  
  
```  
void SetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszHost*  
 Zeiger auf den Benutzer sichtbare Name der Container-Anwendung.  
  
 *lpszHostObj*  
 Zeiger auf eine identifizierende Zeichenfolge des Containers, die das OLE-Element enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Serveranwendung über die Microsoft Foundation Class-Library geschrieben wurde, wird diese Funktion ruft die [OnSetHostNames](../../mfc/reference/coleserverdoc-class.md#onsethostnames) Memberfunktion die `COleServerDoc` Dokument, das das OLE-Element enthält. Diese Informationen werden im Fenstertitel verwendet, wenn das OLE-Element bearbeitet wird. Jedes Mal, wenn ein Containerdokument geladen wird, ruft das Framework diese Funktion, für die OLE-Elemente im Dokument. `SetHostNames` gilt nur für eingebettete Elemente. Es ist nicht erforderlich, die mit dieser Funktion wird jedes Mal, wenn ein eingebettete OLE-Element aktiviert, wird für die Bearbeitung.  
  
 Dies wird auch automatisch mit dem Anwendungsnamen und der Name des Dokuments bezeichnet, wenn ein Objekt geladen wird oder eine Datei unter einem anderen Namen gespeichert wird. Entsprechend ist es normalerweise nicht erforderlich, diese Funktion direkt aufzurufen.  
  
 Weitere Informationen finden Sie unter [IOleObject::SetHostNames](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-sethostnames) im Windows SDK.  
  
##  <a name="seticonicmetafile"></a>  COleClientItem::SetIconicMetafile  
 Speichert die Metadatei, die zum Zeichnen des Symbols.  
  
```  
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```  
  
### <a name="parameters"></a>Parameter  
 *hMetaPict*  
 Ein Handle der Metadatei, die zum Zeichnen des Symbols.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [GetIconicMetafile](#geticonicmetafile) zum Abrufen der Metadatei.  
  
 Die *hMetaPict* Parameter wird in das Element kopiert aus diesem Grund *hMetaPict* muss vom Aufrufer freigegeben werden.  
  
##  <a name="setitemrects"></a>  COleClientItem::SetItemRects  
 Rufen Sie diese Funktion zum Festlegen des umschließenden Rechtecks oder die sichtbares Rechteck des OLE-Elements.  
  
```  
BOOL SetItemRects(
    LPCRECT lpPosRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lprcPosRect*  
 Zeiger auf das Rechteck, das die Begrenzungen des OLE-Elements relativ zum übergeordneten Fensters, in Clientkoordinaten enthält.  
  
 *lprcClipRect*  
 Zeiger auf das Rechteck, das die Grenzen des sichtbaren Teils des OLE-Elements relativ zum übergeordneten Fensters, in Clientkoordinaten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, durch die standardmäßige Implementierung der [OnChangeItemPosition](#onchangeitemposition) Member-Funktion. Sie sollten diese Funktion aufrufen, wenn die Position oder den sichtbaren Teil der OLE-Element geändert wird. In der Regel bedeutet dies, dass Sie sie von Ihrer Ansicht Aufrufen [OnSize](../../mfc/reference/cwnd-class.md#onsize) und [OnScrollBy](../../mfc/reference/cview-class.md#onscrollby) Memberfunktionen.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::SetObjectRects](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) im Windows SDK.  
  
##  <a name="setlinkupdateoptions"></a>  COleClientItem::SetLinkUpdateOptions  
 Rufen Sie diese Funktion, um die Link-Update-Option für die Präsentation von das angegebene verknüpfte Element festgelegt.  
  
```  
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```  
  
### <a name="parameters"></a>Parameter  
 *dwUpdateOpt*  
 Der Wert der Option zur Link-Update für dieses Element. Dieser Wert muss eine der folgenden sein:  
  
- OLEUPDATE_ALWAYS aktualisieren Sie das verknüpfte Element nach Möglichkeit. Diese Option unterstützt das Optionsfeld für die automatische Link-Update im Dialogfeld "Links".  
  
- OLEUPDATE_ONCALL aktualisieren Sie das verknüpfte Element nur auf Anforderung die Container-Anwendung (wenn die [UpdateLink](#updatelink) Memberfunktion aufgerufen wird). Diese Option unterstützt das Optionsfeld für die manuelle Link-Update im Dialogfeld "Links".  
  
### <a name="remarks"></a>Hinweise  
 In der Regel sollten Sie die Updateoptionen, die vom Benutzer im Dialogfeld Links ausgewählten nicht ändern.  
  
 Weitere Informationen finden Sie unter [IOleLink::SetUpdateOptions](/windows/desktop/api/oleidl/nf-oleidl-iolelink-setupdateoptions) im Windows SDK.  
  
##  <a name="setprintdevice"></a>  COleClientItem::SetPrintDevice  
 Rufen Sie diese Funktion, um das Gerät drucken-Ziel für dieses Element zu ändern.  
  
```  
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL SetPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Parameter  
 *ptd*  
 Zeiger auf eine [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) Datenstruktur, die Informationen über das neue Gerät für die Print-Ziel enthält. NULL kann sein.  
  
 *PPD*  
 Zeiger auf eine [PRINTDLG](https://msdn.microsoft.com/library/windows/desktop/ms646940) Datenstruktur, die Informationen über das neue Gerät für die Print-Ziel enthält. NULL kann sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aktualisiert das Gerät drucken-Ziel für das Element jedoch den Presentation-Cache wird nicht aktualisiert. Rufen Sie zum Aktualisieren der Präsentation-Cache nach einem Element [UpdateLink](#updatelink).  
  
 Die Argumente für diese Funktion enthalten Informationen, die das OLE-System verwendet, um das Gerät zu identifizieren. Die `PRINTDLG` Struktur enthält Informationen, die von Windows verwendet, um das allgemeine Drucken-Dialogfeld zu initialisieren. Nachdem der Benutzer das Dialogfeld geschlossen wird, gibt Windows Informationen zu der Auswahl des Benutzers in dieser Struktur zurück. Die `m_pd` Mitglied einer [CPrintDialog](../../mfc/reference/cprintdialog-class.md) Objekt ist ein `PRINTDLG` Struktur.  
  
 Weitere Informationen zu dieser Struktur finden Sie unter [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) im Windows SDK.  
  
##  <a name="updatelink"></a>  COleClientItem::UpdateLink  
 Rufen Sie diese Funktion, um die Präsentationsdaten des OLE-Elements sofort zu aktualisieren.  
  
```  
BOOL UpdateLink();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Für verknüpfte Elemente sucht die Funktion die Linkquelle, um eine neue Präsentation für das OLE-Element zu erhalten. Dieser Prozess kann erforderlich sein, eine oder mehrere Server-Anwendungen ausführen, die zeitaufwändig sein könnte. Für eingebettete Elemente verarbeitet die Funktion rekursiv, überprüfen, ob das eingebettete Element Links enthält, die veraltet sein könnten, und aktualisieren. Der Benutzer kann die einzelnen Links, die Links im Dialogfeld auch manuell aktualisieren.  
  
 Weitere Informationen finden Sie unter [IOleLink::Update](/windows/desktop/api/oleidl/nf-oleidl-iolelink-update) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MFCBIND](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [CDocItem-Klasse](../../mfc/reference/cdocitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)
