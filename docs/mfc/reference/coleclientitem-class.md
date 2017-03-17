---
title: COleClientItem Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- OLE containers, client items
- COleClientItem class
- OLE client item class
- container interface class
- OLE containers, interface class
- client items and OLE containers
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a200da03305c20eaf2d9c1de1ea585c82410c570
ms.lasthandoff: 02/24/2017

---
# <a name="coleclientitem-class"></a>COleClientItem-Klasse
Definiert die Containerschnittstelle zu OLE-Elementen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleClientItem : public CDocItem  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleClientItem::COleClientItem](#coleclientitem)|Erstellt ein `COleClientItem`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleClientItem::Activate](#activate)|Öffnet das OLE-Element für einen Vorgang, und führt dann das angegebene Verb.|  
|[COleClientItem::ActivateAs](#activateas)|Aktiviert das Element als anderer Typ.|  
|[COleClientItem::AttachDataObject](#attachdataobject)|Greift auf die Daten in das OLE-Objekt.|  
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|Gibt an, ob eine Container-Anwendung ein eingebettetes Objekt erstellen kann.|  
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|Gibt an, ob eine Container-Anwendung ein verknüpftes Objekt erstellen kann.|  
|[COleClientItem::CanPaste](#canpaste)|Gibt an, ob die Zwischenablage ein OLE-Element eingebettet werden oder statische enthält.|  
|[COleClientItem::CanPasteLink](#canpastelink)|Gibt an, ob die Zwischenablage verknüpfbares OLE-Element enthält.|  
|[COleClientItem::Close](#close)|Schließt einen Link zu einem Server, jedoch nicht das OLE-Element zerstört.|  
|[COleClientItem::ConvertTo](#convertto)|Konvertiert das Element in einen anderen Typ.|  
|[COleClientItem::CopyToClipboard](#copytoclipboard)|Das OLE-Element kopiert in die Zwischenablage.|  
|[COleClientItem::CreateCloneFrom](#createclonefrom)|Erstellt ein Duplikat eines vorhandenen Elements.|  
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|Erstellt ein eingebettetes Element aus der Zwischenablage.|  
|[COleClientItem::CreateFromData](#createfromdata)|Erstellt ein eingebettetes Element aus einem Datenobjekt.|  
|[CreateFromFile](#createfromfile)|Erstellt ein eingebettetes Element aus einer Datei.|  
|[COleClientItem::CreateLinkFromClipboard](#createlinkfromclipboard)|Erstellt ein verknüpftes Element aus der Zwischenablage.|  
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|Erstellt ein verknüpftes Element aus einem Datenobjekt.|  
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|Erstellt ein verknüpftes Element aus einer Datei.|  
|[COleClientItem::CreateNewItem](#createnewitem)|Erstellt ein neues eingebettetes Element durch die Server-Anwendung zu starten.|  
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|Erstellt ein statisches Element aus der Zwischenablage.|  
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|Erstellt ein statisches Element aus einem Datenobjekt.|  
|[COleClientItem::Deactivate](#deactivate)|Wird das Element deaktiviert.|  
|[COleClientItem::DeactivateUI](#deactivateui)|Wird die Benutzeroberfläche der containeranwendung in seinen ursprünglichen Zustand wiederhergestellt.|  
|[COleClientItem::Delete](#delete)|Löscht oder das OLE-Element geschlossen wird, wenn es sich um ein verknüpftes Element war.|  
|[COleClientItem::DoDragDrop](#dodragdrop)|Führt eine Drag & Drop-Operation.|  
|[COleClientItem::DoVerb](#doverb)|Führt das angegebene Verb.|  
|[COleClientItem::Draw](#draw)|Zeichnet das OLE-Element.|  
|[COleClientItem::GetActiveView](#getactiveview)|Ruft die Ansicht, auf der das Element direkt aktiviert wird.|  
|[COleClientItem::GetCachedExtent](#getcachedextent)|Gibt die Grenzen des Rechtecks des OLE-Elements zurück.|  
|[COleClientItem::GetClassID](#getclassid)|Ruft das vorhanden Element Klassen-ID|  
|[COleClientItem::GetClipboardData](#getclipboarddata)|Ruft die Daten ab, die in der Zwischenablage durch Aufrufen von platziert werden, würde der `CopyToClipboard` Member-Funktion.|  
|[COleClientItem::GetDocument](#getdocument)|Gibt die `COleDocument` -Objekt, das vorhandene Element enthält.|  
|[COleClientItem::GetDrawAspect](#getdrawaspect)|Ruft die aktuelle Elementansicht für das Rendering.|  
|[COleClientItem::GetExtent](#getextent)|Gibt die Grenzen des Rechtecks des OLE-Elements zurück.|  
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|Ruft ein Handle für ein Symbol mit dem Server eine bestimmte CLSID verknüpft.|  
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|Ruft die Metadatei, die zum Zeichnen des Symbols ab.|  
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|Gibt einen Zeiger auf das Element in-Place-Fenster.|  
|[COleClientItem::GetItemState](#getitemstate)|Ruft das Element des aktuellen Status ab.|  
|[COleClientItem::GetLastStatus](#getlaststatus)|Gibt den Status der letzten OLE-Vorgang zurück.|  
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|Gibt den Aktualisierungsmodus für ein verknüpftes Element (erweiterte Funktion).|  
|[COleClientItem::GetType](#gettype)|Gibt den Typ des OLE-Elements (embedded, verknüpfte oder statisch).|  
|[COleClientItem::GetUserType](#getusertype)|Ruft eine Zeichenfolge, die den Typ des Elements ab.|  
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|Gibt `TRUE` Wenn das Element direkt aktiv ist.|  
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|Gibt **TRUE** ist ein verknüpftes Element mit dem Quelldokument.|  
|[COleClientItem::IsModified](#ismodified)|Gibt `TRUE` , wenn das Element geändert wurde, seit es zuletzt gespeichert wurde.|  
|[COleClientItem::IsOpen](#isopen)|Gibt `TRUE` , sofern das Element in der Serveranwendung geöffnet ist.|  
|[COleClientItem::IsRunning](#isrunning)|Gibt `TRUE` , wenn das Element Server-Anwendung ausgeführt wird.|  
|[COleClientItem::OnActivate](#onactivate)|Aufgerufen, um dem Element zu benachrichtigen, dass es aktiviert ist.|  
|[COleClientItem::OnActivateUI](#onactivateui)|Aufgerufen, um dem Element zu benachrichtigen, dass er aktiviert ist und die Benutzeroberfläche anzeigen.|  
|[COleClientItem:: OnChange](#onchange)|Wird aufgerufen, wenn der Server das OLE-Element geändert wird. Die Implementierung erforderlich sind.|  
|[COleClientItem::OnDeactivate](#ondeactivate)|Vom Framework aufgerufen, wenn ein Element deaktiviert ist.|  
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|Wird vom Framework aufgerufen, wenn der Server die direkte Benutzeroberfläche entfernt wurde.|  
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|Vom Framework aufgerufen wird zum Abrufen der Daten in die Zwischenablage kopiert werden soll.|  
|[COleClientItem::OnInsertMenus](#oninsertmenus)|Aufgerufen, um eine zusammengesetzte Menü zu erstellen.|  
|[COleClientItem::OnRemoveMenus](#onremovemenus)|Aufgerufen, um die Menüs des Containers von einem zusammengesetzten Menü zu entfernen.|  
|[COleClientItem::OnSetMenu](#onsetmenu)|Vom Framework aufgerufen wird, installieren und Entfernen von einem zusammengesetzten Menü.|  
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|Vom Framework aufgerufen wird, ein- und Ausblenden von Steuerleisten.|  
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|Wird aufgerufen, durch das Framework das Rahmenfenster Titelleiste zu aktualisieren.|  
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|Reaktiviert das Element, und macht den letzten Bearbeitungsvorgang an.|  
|[COleClientItem::Release](#release)|Die Verbindung mit einer OLE-Element verknüpfte frei und wieder geschlossen, wenn er geöffnet war. Die Client-Element wird nicht zerstört werden.|  
|[COleClientItem::Reload](#reload)|Lädt das Element nach einem Aufruf von `ActivateAs`.|  
|[COleClientItem::Run](#run)|Führt die Anwendung, die dem Element zugeordnet.|  
|[COleClientItem::SetDrawAspect](#setdrawaspect)|Aktuelle Ansicht des Elements, für das Rendering festgelegt.|  
|[COleClientItem::SetExtent](#setextent)|Legt das umschließende Rechteck des OLE-Elements fest.|  
|[COleClientItem::SetHostNames](#sethostnames)|Legt die Namen des Servers angezeigt, wenn das OLE-Element zu bearbeiten.|  
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|Speichert die Metadatei, die zum Zeichnen des Symbols.|  
|[COleClientItem::SetItemRects](#setitemrects)|Legt die umschließende Rechteck für das Element fest.|  
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|Legt den Aktualisierungsmodus für ein verknüpftes Element (erweiterte Funktion).|  
|[COleClientItem::SetPrintDevice](#setprintdevice)|Legt das Drucken-Zielgerät für diese Client-Element fest.|  
|[COleClientItem::UpdateLink](#updatelink)|Aktualisiert den Cache Darstellung eines Elements.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleClientItem:: CanActivate](#canactivate)|Aufgerufen, um festzustellen, ob die direkte Aktivierung zulässig ist.|  
|[COleClientItem:: OnChangeItemPosition auf](#onchangeitemposition)|Vom Framework aufgerufen, wenn die Position eines Elements geändert wird.|  
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|Vom Framework aufgerufen wird, nach der Aktivierung rückgängig zu machen.|  
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|Vom Framework aufgerufen, des Elements rückgängig Zustandsinformationen zu verwerfen.|  
|[COleClientItem::OnGetClipRect](#ongetcliprect)|Aufgerufen, um das Element Clippingrechteck Koordinaten abzurufen.|  
|[COleClientItem:: OnGetItemPosition auf](#ongetitemposition)|Vom Framework aufgerufen wird an der Position des Elements relativ zu der Ansicht zu erhalten.|  
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|Wird vom Framework aufgerufen, wenn ein Element direkt aktiviert wird.|  
|[COleClientItem::OnScrollBy](#onscrollby)|Vom Framework aufgerufen wird, das Element ein Bildlauf.|  
|[COleClientItem::OnShowItem](#onshowitem)|Aufgerufen, um das OLE-Element anzuzeigen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein OLE-Element stellt Daten dar, erstellt und verwaltet eine Server-Anwendung, die in ein Dokument "nahtlos" integriert werden können, sodass es dem Benutzer zu einem einzelnen Dokument angezeigt wird. Das Ergebnis ist ein "Verbunddokument" das OLE-Element und einem Containerdokument besteht.  
  
 Ein OLE-Element kann eingebettet oder verknüpft werden. Wenn es eingebettet ist, werden seine Daten als Teil des Verbunddokuments gespeichert. Verknüpft ist, werden seine Daten als Teil einer separaten Datei erstellt, indem der Server-Anwendung gespeichert und nur ein Link zu dieser Datei werden im Verbunddokument gespeichert. Alle OLE-Elemente enthalten Informationen, die Angabe der Server-Anwendung, die aufgerufen werden muss, um sie zu bearbeiten.  
  
 `COleClientItem`definiert mehrere überschreibbare-Funktionen, die aufgerufen werden als Antwort auf Anforderungen von Server-Anwendung. Diese Overridables dienen in der Regel als Benachrichtigungen. Dadurch wird die Server-Anwendung, um den Container der Änderungen zu informieren der Benutzer vornimmt, wenn das OLE-Element zu bearbeiten oder zum Abrufen von Informationen, die während der Bearbeitung erforderlich.  
  
 `COleClientItem`kann verwendet werden, entweder mit der [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), oder [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) Klasse. Mit `COleClientItem`, eine Klasse ableiten und Implementieren der [OnChange](#onchange) -Memberfunktion, die definiert, wie der Container an einem Element vorgenommenen Änderungen reagiert. Überschreiben, um die direkte Aktivierung unterstützen, die [OnGetItemPosition](#ongetitemposition) Member-Funktion. Diese Funktion bietet Informationen zur Position des OLE-Elements angezeigt.  
  
 Weitere Informationen über die Containerschnittstelle finden Sie in den Artikeln [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md) und [Activation](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  Die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] verweist auf eingebettete und verknüpfte Elemente als "Objekte" und bezieht sich auf die Typen von Elementen als "Classes". Dieser Verweis wird der Begriff "Item" verwendet, die entsprechende C++-Objekt und der Begriff "Type" der C++-Klasse die Kategorie OLE unterscheiden die OLE-Entität unterscheiden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="activate"></a>COleClientItem::Activate  
 Rufen Sie diese Funktion zum Ausführen des angegebenen Verbs anstelle von [DoVerb](#doverb) , damit Sie tun können eigene Verarbeitung, wenn eine Ausnahme ausgelöst wird.  
  
```  
void Activate(
    LONG nVerb,  
    CView* pView,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nVerb`  
 Gibt das Verb ausführen. Es kann eine der folgenden sein:  
  
|Wert|Bedeutung|Symbol|  
|-----------|-------------|------------|  
|– 0|Primäres Verb|`OLEIVERB_PRIMARY`|  
|– 1|Sekundäre verb|(Keine)|  
|– 1|Artikel für die Bearbeitung anzeigen|`OLEIVERB_SHOW`|  
|– 2|Bearbeiten des Konfigurationselements in separaten Fenster|`OLEIVERB_OPEN`|  
|– 3|Element ausblenden|`OLEIVERB_HIDE`|  
  
 Der Wert –&1; ist in der Regel ein Alias für ein anderes Verb. Wenn Bearbeiten öffnen nicht unterstützt wird, hat –&2; die gleiche Auswirkung wie –&1;. Zusätzliche Werte finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pView`  
 Zeiger auf die Container-Ansichtsfenster, das das OLE-Element enthält; Dies wird durch die Server-Anwendung für die direkte Aktivierung verwendet. Dieser Parameter sollte sein **NULL** Wenn der Container-Ort-Aktivierung nicht unterstützt.  
  
 `lpMsg`  
 Ein Zeiger auf die Meldung, die das Element, das aktiviert werden, verursacht.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Server-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben wurde, wird diese Funktion die [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb) -Memberfunktion des entsprechenden `COleServerItem` Objekt, das ausgeführt werden.  
  
 Wenn das primäre Verb bearbeiten ist und&0; (null), in angegeben wird der `nVerb` -Parameter, die Server-Anwendung wird gestartet, um das OLE-Element bearbeitet werden kann. Wenn die Container-Anwendung, direkte Aktivierung unterstützt, kann bearbeiten an Stelle vorgenommen werden. Wenn der Container nicht unterstützt wird, die direkte Aktivierung (oder wenn das Verb "Open" angegeben ist), der Server in einem separaten Fenster gestartet und bearbeiten kann erfolgen vorhanden. In der Regel der Benutzer der containeranwendung doppelklickt das OLE-Element den Wert für das primäre Verb in der `nVerb` Parameter bestimmt, welche Aktion der Benutzer ausführen kann. Jedoch, wenn der Server nur eine Aktion unterstützt wird, dauert es diese Aktion aus, unabhängig davon, welche-Wert, in angegeben wird der `nVerb` Parameter.  
  
 Weitere Informationen finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="activateas"></a>COleClientItem::ActivateAs  
 OLE Objekt Konvertierung Funktionen verwendet, um das Element zu aktivieren, als wäre es ein Element vom angegebenen Typ `clsidNew`.  
  
```  
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,  
    REFCLSID clsidOld,  
    REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszUserType*  
 Zeiger auf eine Zeichenfolge mit des Benutzer-Zieltyps, z. B. "Word-Dokument".  
  
 *clsidOld*  
 Ein Verweis auf die aktuelle Klasse für das Element-ID. Die Klassen-ID muss den Typ des eigentlichen Objekts darstellen, wie gespeichert, wenn es sich um einen Link handelt. In diesem Fall sollten sie die CLSID des Elements sein, auf die der Link verweist. Die [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md) automatisch die richtigen Klassen-ID für den Artikel bereitstellt.  
  
 `clsidNew`  
 Ein Verweis auf das Ziel-ID-Klasse  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Dies wird als automatisch vom [COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert). Es ist nicht in der Regel direkt aufgerufen.  
  
##  <a name="attachdataobject"></a>COleClientItem::AttachDataObject  
 Rufen Sie diese Funktion zum Initialisieren einer [COleDataObject](../../mfc/reference/coledataobject-class.md) für den Zugriff auf die Daten in das OLE-Element.  
  
```  
void AttachDataObject(COleDataObject& rDataObject) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *rDataObject*  
 Ein Verweis auf ein `COleDataObject` -Objekt, das für den Zugriff auf die Daten in das OLE-Element initialisiert werden.  
  
##  <a name="canactivate"></a>COleClientItem:: CanActivate  
 Vom Framework aufgerufen, wenn der Benutzer die direkte Aktivierung des OLE-Elements anfordert. Rückgabewert dieser Funktion bestimmt, ob die direkte Aktivierung zulässig ist.  
  
```  
virtual BOOL CanActivate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die direkte Aktivierung ist zulässig sind. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ermöglicht direkte Aktivierung, wenn der Container ein gültiges Fenster verfügt. Überschreiben Sie diese Funktion, um spezielle Logik zum annehmen oder Ablehnen der Aktivierungsanfrage implementieren. Beispielsweise kann eine Anfrage zur Aktivierung abgelehnt werden, wenn das OLE-Element zu klein oder derzeit nicht sichtbar ist.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::CanInPlaceActivate](http://msdn.microsoft.com/library/windows/desktop/ms691236) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="cancreatefromdata"></a>COleClientItem::CanCreateFromData  
 Überprüft, ob eine containeranwendung ein eingebettetes Objekt erstellen, können die bestimmten `COleDataObject` Objekt.  
  
```  
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt, von dem das OLE-Element erstellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Container ein eingebettetes Objekt erstellen, kann die `COleDataObject` -Objekt, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleDataObject` -Klasse wird in Datenübertragungen zum Abrufen von Daten in unterschiedlichen Formaten aus der Zwischenablage, per Drag & Drop oder von einem eingebetteten OLE-Element verwendet.  
  
 Container können diese Funktion aktivieren oder deaktivieren die Befehle einfügen bearbeiten und einfügen bearbeiten möchten.  
  
 Weitere Informationen finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="cancreatelinkfromdata"></a>COleClientItem::CanCreateLinkFromData  
 Überprüft, ob eine Steuerelementcontainer-Anwendung Erstellen eines verknüpften Objekts aus kann der angegebenen `COleDataObject` Objekt.  
  
```  
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt, von dem das OLE-Element erstellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn ein verknüpftes Objekt aus der Container erstellen, kann die `COleDataObject` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleDataObject` -Klasse wird in Datenübertragungen zum Abrufen von Daten in unterschiedlichen Formaten aus der Zwischenablage, per Drag & Drop oder von einem eingebetteten OLE-Element verwendet.  
  
 Container können diese Funktion aktivieren oder deaktivieren die Befehle für die Inhalte bearbeiten und verknüpfen bearbeiten möchten.  
  
 Weitere Informationen finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
##  <a name="canpaste"></a>COleClientItem::CanPaste  
 Rufen Sie diese Funktion, um festzustellen, ob es sich bei ein eingebettetes OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
static BOOL PASCAL CanPaste();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein eingebettetes OLE-Element aus der Zwischenablage eingefügt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) und [OleQueryCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms683739) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="canpastelink"></a>COleClientItem::CanPasteLink  
 Rufen Sie diese Funktion, um festzustellen, ob ein verknüpftes OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
static BOOL PASCAL CanPasteLink();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein verknüpftes OLE-Element aus der Zwischenablage eingefügt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778) und [OleQueryLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms690244) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="close"></a>COleClientItem::Close  
 Rufen Sie diese Funktion zum Ändern des Status der ein OLE-Element vom laufenden Zustand in den geladenen Zustand, d. h. geladen, mit dem entsprechenden Handler im Arbeitsspeicher jedoch mit dem Server nicht ausgeführt.  
  
```  
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCloseOption`  
 Flag, das angibt, unter welchen Umständen das OLE-Element gespeichert wird, wenn in den geladenen Zustand zurückgegeben. Die folgenden Werte sind möglich:  
  
- `OLECLOSE_SAVEIFDIRTY`Speichern Sie das OLE-Element.  
  
- `OLECLOSE_NOSAVE`Speichern Sie das OLE-Element.  
  
- `OLECLOSE_PROMPTSAVE`Fordert den Benutzer auf, ob das OLE-Element gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion hat keine Auswirkung, wenn das OLE-Element nicht ausgeführt wird.  
  
 Weitere Informationen finden Sie unter [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="coleclientitem"></a>COleClientItem::COleClientItem  
 Erstellt ein `COleClientItem` -Objekt und fügt dieses an das Containerdokument Auflistung von Dokumentelemente, die das C++-Objekt erstellt und führt keine OLE-Initialisierung.  
  
```  
COleClientItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pContainerDoc`  
 Ein Zeiger auf das Containerdokument, das dieses Element enthält. Dies kann eine [COleDocument](../../mfc/reference/coledocument-class.md) Ableitung.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie übergeben ein **NULL** -Zeiger ist, erfolgt keine Addition mit dem Containerdokument. Sie müssen explizit aufrufen [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem).  
  
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
  
##  <a name="convertto"></a>COleClientItem::ConvertTo  
 Rufen Sie diese Memberfunktion, um das Element in den vom angegebenen Typ konvertieren `clsidNew`.  
  
```  
virtual BOOL ConvertTo(REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>Parameter  
 `clsidNew`  
 Die Klassen-ID des Zieltyps.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Dies wird als automatisch vom [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md). Es ist nicht erforderlich, direkt aufgerufen.  
  
##  <a name="copytoclipboard"></a>COleClientItem::CopyToClipboard  
 Rufen Sie diese Funktion, um das OLE-Element in die Zwischenablage zu kopieren.  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bIncludeLink`  
 **True,** Wenn Informationen in die Zwischenablage kopiert werden sollen, ermöglicht ein verknüpftes Element eingefügten andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Normalerweise rufen Sie diese Funktion beim Schreiben der Meldungshandler für die Befehle Kopieren oder Ausschneiden im Menü Bearbeiten. Sie müssen die Elementauswahl in Ihrem Container-Anwendung implementieren, wenn Sie die Befehle Kopieren oder Ausschneiden implementieren möchten.  
  
 Weitere Informationen finden Sie unter [von OleSetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms686623) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createclonefrom"></a>COleClientItem::CreateCloneFrom  
 Rufen Sie diese Funktion zum Erstellen einer Kopie des angegebenen OLE-Elements.  
  
```  
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```  
  
### <a name="parameters"></a>Parameter  
 *pSrcItem*  
 Ein Zeiger auf das OLE-Element dupliziert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Kopie ist identisch mit dem Quellelement. Diese Funktion können Sie die um Rückgängig-Vorgängen zu unterstützen.  
  
##  <a name="createfromclipboard"></a>COleClientItem::CreateFromClipboard  
 Rufen Sie diese Funktion, um ein eingebettetes Element aus dem Inhalt der Zwischenablage zu erstellen.  
  
```  
BOOL CreateFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn das OLE-Element zu erstellen.  
  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion von der Message-Handler, für den Befehl Einfügen im Menü Bearbeiten. (Der Befehl Einfügen wird vom Framework aktiviert, wenn die [CanPaste](#canpaste) Member-Funktion gibt einen Wert ungleich NULL zurück.)  
  
 Weitere Informationen finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createfromdata"></a>COleClientItem::CreateFromData  
 Rufen Sie diese Funktion zum Erstellen eines eingebetteten Elements aus einem `COleDataObject` Objekt.  
  
```  
BOOL CreateFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt, von dem das OLE-Element erstellt werden.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn das OLE-Element zu erstellen.  
  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Vorgänge, z. B. Einfügen von Daten aus der Zwischenablage oder Drag & Drop-Vorgängen bieten `COleDataObject` Objekte mit den Informationen von einer Server-Anwendung bereitgestellt. Es wird normalerweise verwendet, in der Überschreibung der [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop).  
  
 Weitere Informationen finden Sie unter [OleCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms691211), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createfromfile"></a>CreateFromFile  
 Rufen Sie diese Funktion, um ein eingebettetes OLE-Element aus einer Datei zu erstellen.  
  
```  
BOOL CreateFromFile(
    LPCTSTR lpszFileName,  
    REFCLSID clsid = CLSID_NULL,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Ein Zeiger auf den Namen der Datei, aus der das OLE-Element erstellt werden soll.  
  
 `clsid`  
 Für zukünftige Verwendung reserviert.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn das OLE-Element zu erstellen.  
  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion von [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem) Wenn wählt der Benutzer OK im Dialogfeld "Objekt einfügen", wenn das Erstellen von Datei-Schaltfläche aktiviert ist.  
  
 Weitere Informationen finden Sie unter [OleCreateFromFile](http://msdn.microsoft.com/library/windows/desktop/ms690116), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createlinkfromclipboard"></a>COleClientItem::CreateLinkFromClipboard  
 Rufen Sie diese Funktion zum Erstellen eines verknüpften Elements aus dem Inhalt der Zwischenablage ein.  
  
```  
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn das OLE-Element zu erstellen.  
  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion von der Message-Handler, für den Befehl Einfügen im Menü Bearbeiten. (Der Verknüpfung einfügen-Befehl ist in der Standardimplementierung von aktiviert [COleDocument](../../mfc/reference/coledocument-class.md) , wenn die Zwischenablage ein OLE-Element enthält, die mit verknüpft werden können.)  
  
 Weitere Informationen finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createlinkfromdata"></a>COleClientItem::CreateLinkFromData  
 Rufen Sie diese Funktion zum Erstellen eines verknüpften Elements aus einem `COleDataObject` Objekt.  
  
```  
BOOL CreateLinkFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt, von dem das OLE-Element erstellt werden.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn das OLE-Element zu erstellen.  
  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese während eines Drop-Vorgangs, wenn der Benutzer zeigt an, dass eine Verknüpfung erstellt werden soll. Es kann auch verwendet werden, behandeln Sie den Befehl einfügen bearbeiten. Es wird vom Framework aufgerufen wird in `COleClientItem::CreateLinkFromClipboard` und [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) Wenn die Link-Option ausgewählt wurde.  
  
 Weitere Informationen finden Sie unter [OleCreateLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms680731), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createlinkfromfile"></a>COleClientItem::CreateLinkFromFile  
 Rufen Sie diese Funktion, um ein verknüpftes OLE-Element aus einer Datei zu erstellen.  
  
```  
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFileName`  
 Ein Zeiger auf den Namen der Datei, aus der das OLE-Element erstellt werden soll.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn das OLE-Element zu erstellen.  
  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion auf, wenn der Benutzer OK im Dialogfeld "Objekt einfügen" beim Erstellen von Datei-Schaltfläche aktiviert ist, und aktivieren Sie das Kontrollkästchen Verknüpfung aktiviert ist. Aufruf in [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem).  
  
 Weitere Informationen finden Sie unter [OleCreateLinkToFile](http://msdn.microsoft.com/library/windows/desktop/ms678434), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createnewitem"></a>COleClientItem::CreateNewItem  
 Rufen Sie diese Funktion, um ein eingebettetes Element zu erstellen. Diese Funktion startet die Serveranwendung, die dem Benutzer ermöglicht, die das OLE-Element zu erstellen.  
  
```  
BOOL CreateNewItem(
    REFCLSID clsid,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 ID, die den Typ des zu erstellenden OLE-Elements eindeutig identifiziert.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn das OLE-Element zu erstellen.  
  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion auf, wenn der Benutzer wählt OK im Dialogfeld "Objekt einfügen", wenn die Schaltfläche neu erstellen ausgewählt ist.  
  
 Weitere Informationen finden Sie unter [OleCreate](http://msdn.microsoft.com/library/windows/desktop/ms678409), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createstaticfromclipboard"></a>COleClientItem::CreateStaticFromClipboard  
 Rufen Sie diese Funktion, um ein statisches Element aus dem Inhalt der Zwischenablage zu erstellen.  
  
```  
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn das OLE-Element zu erstellen.  
  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ein statisches Element enthält die Präsentationsdaten jedoch nicht die systemeigenen Daten. Daher kann er bearbeitet werden. Diese Funktion wird in der Regel aufzurufen, wenn die [CreateFromClipboard](#createfromclipboard) Member-Funktion fehlschlägt.  
  
 Weitere Informationen finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createstaticfromdata"></a>COleClientItem::CreateStaticFromData  
 Rufen Sie diese Funktion zum Erstellen eines statischen Elements aus einem `COleDataObject` Objekt.  
  
```  
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataObject`  
 Zeiger auf die [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt, von dem das OLE-Element erstellt werden.  
  
 *Rendern*  
 Flag, das angibt, wie der Server das OLE-Element gerendert wird. Die möglichen Werte finden Sie unter [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `cfFormat`  
 Gibt das Format der Zwischenablage Daten zwischengespeichert werden, wenn das OLE-Element zu erstellen.  
  
 `lpFormatEtc`  
 Zeiger auf eine [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Struktur verwendet, wenn *Rendern* ist **OLERENDER_FORMAT** oder **OLERENDER_DRAW**. Geben Sie einen Wert für diesen Parameter nur, wenn Sie weitere Informationen über das Format der Zwischenablage durch angegebene angeben möchten `cfFormat`. Wenn Sie diesen Parameter weglassen, werden Standardwerte verwendet, für die anderen Felder in der **FORMATETC** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ein statisches Element enthält die Präsentationsdaten jedoch nicht die systemeigenen Daten. Daher kann er bearbeitet werden. Dies ist im Wesentlichen identisch mit [CreateStaticFromClipboard](#createstaticfromclipboard) abgesehen davon, dass ein statisches Element kann, aus einem beliebigen erstellt werden `COleDataObject`, nicht nur aus der Zwischenablage.  
  
 Verwendet [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) Wenn statische aktiviert ist.  
  
 Weitere Informationen finden Sie unter [OleCreateStaticFromData](http://msdn.microsoft.com/library/windows/desktop/ms687290), [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507), und [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="deactivate"></a>COleClientItem::Deactivate  
 Rufen Sie diese Funktion, um das OLE-Element zu deaktivieren und alle zugeordneten Ressourcen frei.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein direktes active OLE-Element wird in der Regel deaktivieren, klickt der Benutzer die Maus im Clientbereich außerhalb der Grenzen des Elements. Beachten Sie, dass das OLE-Element deaktivieren Zustand rückgängig machen es unmöglich, rufen Sie Verwerfen der [ReactivateAndUndo](#reactivateandundo) Member-Funktion.  
  
 Wenn Ihre Anwendung rückgängig unterstützt, rufen Sie `Deactivate`stattdessen rufen [DeactivateUI](#deactivateui).  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="deactivateui"></a>COleClientItem::DeactivateUI  
 Rufen Sie diese Funktion, wenn der Benutzer ein Element deaktiviert, das direkt aktiviert wurde.  
  
```  
void DeactivateUI();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion stellt die Benutzeroberfläche der containeranwendung Originalzustand ausblenden alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden, wieder her.  
  
 Diese Funktion leert die rückgängig-Statusinformationen für das Element. Dass Informationen beibehalten werden, damit [ReactivateAndUndo](#reactivateandundo) später auszuführende einen Rückgängig-Befehl in der Serveranwendung verwendet werden, für den Fall, dass die Container Befehl "Rückgängig" ausgewählt ist, sofort nach dem Deaktivieren des Elements.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="delete"></a>COleClientItem::Delete  
 Rufen Sie diese Funktion, um das OLE-Element aus dem Containerdokument zu löschen.  
  
```  
void Delete(BOOL bAutoDelete = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bAutoDelete`  
 Gibt an, ob das Element aus dem Dokument entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft die [Version](#release) Memberfunktion auf, wodurch wiederum das C++-Objekt für das Element, dauerhaft entfernen des OLE-Elements aus dem Dokument gelöscht. Wenn das OLE-Element eingebettet ist, werden die systemeigenen Daten für das Element gelöscht. Es schließt immer einen laufenden Server; aus diesem Grund schließt diese Funktion ist das Element über einen Link öffnen, es.  
  
##  <a name="dodragdrop"></a>COleClientItem::DoDragDrop  
 Rufen Sie die `DoDragDrop` Memberfunktion zum Ausführen einer Drag & Drop-Operation.  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpItemRect,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpItemRect`  
 Das Element Rechteck auf dem Bildschirm in Clientkoordinaten (in Pixel).  
  
 `ptOffset`  
 Der Offset vom `lpItemRect` , bei denen die Position des Mauszeigers war zum Zeitpunkt des Ziehvorgangs.  
  
 `bIncludeLink`  
 Legen Sie den **TRUE** , wenn die Daten in die Zwischenablage kopiert werden sollen. Legen Sie es auf **FALSE** Wenn die Server-Anwendung Links nicht unterstützt.  
  
 `dwEffects`  
 Bestimmt die Effekte, die die Quelle des Ziehvorgangs des Ziehvorgangs zugelassen werden.  
  
 `lpRectStartDrag`  
 Ein Zeiger auf das Rechteck, das definiert, in dem der Ziehvorgang beginnt. Weitere Informationen finden Sie im folgenden Abschnitt "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DROPEFFECT`-Wert. Es ist `DROPEFFECT_MOVE`, die ursprünglichen Daten entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der Drag & Drop-Vorgang wird nicht sofort gestartet. Es wartet, bis der Cursor die durch angegebene Rechteck verlässt `lpRectStartDrag` oder eine angegebene Anzahl an Millisekunden verstrichen sind. Wenn `lpRectStartDrag` ist **NULL**, die Größe des Rechtecks beträgt ein Pixel.  
  
 Die Verzögerungszeit wird durch eine Einstellung des Registrierungsschlüssels angegeben. Sie können die Verzögerung ändern, durch Aufrufen von [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) oder [CWinApp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint). Wenn Sie nicht die Verzögerung angeben, wird ein Standardwert von 200 Millisekunden verwendet. Ziehen Sie Verzögerungszeit wird wie folgt gespeichert:  
  
-   Ziehen Sie die Windows NT-Verzögerungszeit wird in HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay gespeichert.  
  
-   Windows 3.x Drag-Verzögerungszeit wird in der WIN gespeichert. INI-Datei im Abschnitt [Windows}.  
  
-   Windows 95/98 Drag-Verzögerungszeit wird in eine zwischengespeicherte Version der Windows-Taste gespeichert. INI.  
  
 Für Weitere Informationen ziehen ist Verzögerung Informationen in der Registrierung gespeicherten oder. INI-Datei finden Sie unter [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="doverb"></a>COleClientItem::DoVerb  
 Rufen Sie `DoVerb` auf das angegebene Verb aufzurufen.  
  
```  
virtual BOOL DoVerb(
    LONG nVerb,  
    CView* pView,
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nVerb`  
 Gibt das Verb ausführen. Sie können eine der folgenden enthalten:  
  
|Wert|Bedeutung|Symbol|  
|-----------|-------------|------------|  
|– 0|Primäres Verb|`OLEIVERB_PRIMARY`|  
|– 1|Sekundäre verb|(Keine)|  
|– 1|Artikel für die Bearbeitung anzeigen|`OLEIVERB_SHOW`|  
|– 2|Bearbeiten des Konfigurationselements in separaten Fenster|`OLEIVERB_OPEN`|  
|– 3|Element ausblenden|`OLEIVERB_HIDE`|  
  
 Der Wert –&1; ist in der Regel ein Alias für ein anderes Verb. Wenn Bearbeiten öffnen nicht unterstützt wird, hat –&2; die gleiche Auswirkung wie –&1;. Zusätzliche Werte finden Sie unter [IOleObject](http://msdn.microsoft.com/library/windows/desktop/ms694508) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pView`  
 Zeiger auf das Ansichtsfenster; Dies wird vom Server für die direkte Aktivierung verwendet. Dieser Parameter sollte sein **NULL** Wenn die Container-Anwendung keine direkte Aktivierung zulässt.  
  
 `lpMsg`  
 Ein Zeiger auf die Meldung, die das Element, das aktiviert werden, verursacht.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Verb erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft die [aktivieren](#activate) Memberfunktion, die das Verb ausgeführt. Auch Ausnahmen erfasst, und zeigt ein Meldungsfeld für den Benutzer, sofern eine ausgelöst wird.  
  
 Wenn das primäre Verb bearbeiten ist und&0; (null), in angegeben wird der `nVerb` -Parameter, die Server-Anwendung wird gestartet, um das OLE-Element bearbeitet werden kann. Wenn die Container-Anwendung, direkte Aktivierung unterstützt, kann bearbeiten an Stelle vorgenommen werden. Wenn der Container nicht unterstützt wird, die direkte Aktivierung (oder wenn das Verb "Open" angegeben ist), der Server in einem separaten Fenster gestartet und bearbeiten kann erfolgen vorhanden. In der Regel der Benutzer der containeranwendung doppelklickt das OLE-Element den Wert für das primäre Verb in der `nVerb` Parameter bestimmt, welche Aktion der Benutzer ausführen kann. Jedoch, wenn der Server nur eine Aktion unterstützt wird, dauert es diese Aktion aus, unabhängig davon, welche-Wert, in angegeben wird der `nVerb` Parameter.  
  
##  <a name="draw"></a>COleClientItem::Draw  
 Rufen Sie diese Funktion, um das OLE-Element in das angegebene umgebende Rechteck mit den angegebenen Gerätekontext zu zeichnen.  
  
```  
BOOL Draw(
    CDC* pDC,  
    LPCRECT lpBounds,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Zeiger auf eine [CDC](../../mfc/reference/cdc-class.md) Objekt, das zum Zeichnen von OLE-Elements verwendet.  
  
 `lpBounds`  
 Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder `RECT` -Struktur, die das umschließende Rechteck in der zum Zeichnen des OLE-Elements (in logischen Einheiten, die durch den Gerätekontext bestimmt) definiert.  
  
 `nDrawAspect`  
 Gibt der Aspekt des OLE-Elements, d. h., wie er angezeigt werden soll. Wenn `nDrawAspect` ist-1, der letzte Aspekt mithilfe [SetDrawAspect](#setdrawaspect) verwendet wird. Weitere Informationen zu den möglichen Werten für dieses Flag finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion können die Metadateidarstellung des OLE-Elements erstellt, indem die [OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw) Memberfunktion `COleServerItem`.  
  
 Normalerweise verwenden Sie **zeichnen** für die Bildschirmanzeige, übergeben Sie den Bildschirm-Gerätekontext als `pDC`. In diesem Fall müssen Sie nur die ersten beiden Parameter angeben.  
  
 Die `lpBounds` Parameter identifiziert das Rechteck in der Ziel-Gerätekontext (relativ zum aktuellen Zuordnungsmodus). Rendering müssen Sie eventuell das Bild skalieren und kann von Container-Anwendungen verwendet werden, um eine Ansicht zu erzwingen, die zwischen der angezeigten Ansicht und der endgültigen gedruckten Bildes skaliert.  
  
 Weitere Informationen finden Sie unter [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getactiveview"></a>COleClientItem::GetActiveView  
 Gibt die Ansicht, auf der das Element aktiviert ist.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Ansicht; andernfalls **NULL** , wenn das Element nicht aktiviert ist.  
  
##  <a name="getcachedextent"></a>COleClientItem::GetCachedExtent  
 Mit dieser Funktion wird das OLE-Element abzurufen.  
  
```  
BOOL GetCachedExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 `lpSize`  
 Zeiger auf eine **Größe** Struktur oder ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die Informationen zu erhalten.  
  
 `nDrawAspect`  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen abgerufen werden sollen. Mögliche Werte finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn das OLE-Element leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bietet die gleiche Informationen wie [GetExtent](#getextent). Sie können jedoch aufrufen `GetCachedExtent` Erweiterungsinformationen während der Verarbeitung der anderen OLE-Handler abgerufen, wie z. B. [OnChange](#onchange). Die Dimensionen sind `MM_HIMETRIC` Einheiten.  
  
 Dies ist möglich, da `GetCachedExtent` verwendet die [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) Schnittstelle anstelle der [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) Schnittstelle, um das Ausmaß der dieses Element abzurufen. Die **IViewObject2** COM-Objekt speichert die Umfang Informationen in den vorherigen Aufruf [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655).  
  
 Weitere Informationen finden Sie unter [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclassid"></a>COleClientItem::GetClassID  
 Gibt die Klassen-ID des Elements in den Arbeitsspeicher auf den `pClassID`.  
  
```  
void GetClassID(CLSID* pClassID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pClassID`  
 Zeiger auf ein Bezeichner vom Typ [CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) zum Abrufen der Klassen-ID Informationen zu **CLSID**, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Die Klassen-ID ist eine 128-Bit-Zahl, die eindeutig von der Anwendung, die das Element bearbeitet.  
  
 Weitere Informationen finden Sie unter [IPersist:: GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclipboarddata"></a>COleClientItem::GetClipboardData  
 Rufen Sie diese Funktion zum Abrufen einer `COleDataSource` Objekt mit allen Daten, die durch einen Aufruf in der Zwischenablage platziert werden würde die [CopyToClipboard](#copytoclipboard) Member-Funktion.  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDataSource`  
 Zeiger auf eine [COleDataSource](../../mfc/reference/coledatasource-class.md) -Objekt, das die Daten in das OLE-Element erhält.  
  
 `bIncludeLink`  
 **True,** Wenn Verknüpfungsdaten, andernfalls enthalten werden sollen **FALSE**.  
  
 `lpOffset`  
 Der Offset des Mauszeigers auf den Ursprung des-Objekts in Pixeln.  
  
 `lpSize`  
 Die Größe des Objekts in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 `GetClipboardData`wird aufgerufen, als die standardmäßige Implementierung des [OnGetClipboardData](#ongetclipboarddata). Überschreiben Sie `OnGetClipboardData` nur, wenn Sie zusätzlich zu den angebotenen Formate anbieten möchten `CopyToClipboard`. Platzieren Sie diese Formate in der `COleDataSource` Objekt vor oder nach dem Aufruf von `CopyToClipboard`, und übergeben Sie dann die `COleDataSource` -Objekt an die [COleDataSource](../../mfc/reference/coledatasource-class.md#setclipboard) Funktion. Z. B. Wenn Sie das OLE-Element Position in dessen Containerdokument beiliegenden in die Zwischenablage kopieren möchten, Sie würden definieren ein eigenes Format für die Weitergabe von Informationen und platzieren Sie es in der `COleDataSource` vor dem Aufruf von `CopyToClipboard`.  
  
##  <a name="getdocument"></a>COleClientItem::GetDocument  
 Rufen Sie diese Funktion, um einen Zeiger auf das Dokument, das das OLE-Element enthält.  
  
```  
COleDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument, das OLE-Element enthält. **NULL** ist das Element nicht Teil eines Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Zeiger ermöglicht den Zugriff auf die `COleDocument` -Objekt, das Sie als Argument übergeben der `COleClientItem` Konstruktor.  
  
##  <a name="getdrawaspect"></a>COleClientItem::GetDrawAspect  
 Rufen Sie die `GetDrawAspect` Member-Funktion, um die aktuellen "Aspekt" oder die Ansicht des Elements zu bestimmen.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der `DVASPECT` Enumeration, deren Werte in der Referenz für aufgelisteten [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Hinweise  
 Der Aspekt gibt an, wie das Element gerendert werden soll.  
  
##  <a name="getextent"></a>COleClientItem::GetExtent  
 Mit dieser Funktion wird das OLE-Element abzurufen.  
  
```  
BOOL GetExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```  
  
### <a name="parameters"></a>Parameter  
 `lpSize`  
 Zeiger auf eine **Größe** Struktur oder ein `CSize` -Objekt, das die Informationen zu erhalten.  
  
 `nDrawAspect`  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen abgerufen werden sollen. Mögliche Werte finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn das OLE-Element leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Server-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben wurde, wird diese Funktion die [OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent) -Memberfunktion des entsprechenden `COleServerItem` Objekt aufgerufen werden. Beachten Sie, dass die abgerufene Größe die Größe, die zuletzt festgelegten unterscheidet sich möglicherweise die [SetExtent](#setextent) -Memberfunktion, die durch angegebene Größe `SetExtent` als einen Vorschlag behandelt. Die Dimensionen sind `MM_HIMETRIC` Einheiten.  
  
> [!NOTE]
>  Rufen Sie `GetExtent` während der Verarbeitung einen OLE-Handler, wie z. B. [OnChange](#onchange). Rufen Sie [GetCachedExtent](#getcachedextent) stattdessen.  
  
 Weitere Informationen finden Sie unter [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="geticonfromregistry"></a>COleClientItem::GetIconFromRegistry  
 Rufen Sie diese Memberfunktion rufen Sie ein Handle für eine Symbolressource mit dem Server eine bestimmte CLSID verknüpft.  
  
```  
HICON GetIconFromRegistry() const;  
  
static HICON GetIconFromRegistry(CLSID& clsid);
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 Ein Verweis auf die CLSID für den Server, die dem Symbol zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiges Handle für die Symbolressource oder **NULL** Wenn das Symbol des Servers oder ein Standardsymbol gefunden werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion den Server gestartet wird oder ein Symbol dynamisch erhalten, selbst wenn der Server bereits ausgeführt wird. Stattdessen wird diese Memberfunktion ausführbares Abbild des Servers öffnet und ruft die statische Symbol mit dem Server, der registriert wurde.  
  
##  <a name="geticonicmetafile"></a>COleClientItem::GetIconicMetafile  
 Ruft die Metadatei, die zum Zeichnen des Symbols ab.  
  
```  
HGLOBAL GetIconicMetafile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle auf die Metadatei, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine aktuelle Symbol vorhanden ist, wird ein Standardsymbol zurückgegeben. Dies wird automatisch aufgerufen, indem Sie die MFC/OLE-Dialogfelder und wird normalerweise nicht direkt aufgerufen.  
  
 Diese Funktion ruft auch [SetIconicMetafile](#seticonicmetafile) die Metadatei für die spätere Verwendung zwischengespeichert.  
  
##  <a name="getinplacewindow"></a>COleClientItem::GetInPlaceWindow  
 Rufen Sie die `GetInPlaceWindow` Memberfunktion, die einen Zeiger auf das Fenster, in dem das Element geöffnet wurde, für die direkte Bearbeitung zu erhalten.  
  
```  
CWnd* GetInPlaceWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Element in-Place-Bearbeitungsfenster; **NULL** , wenn das Element nicht aktiv ist oder der Server nicht verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nur für Elemente aufgerufen werden, die in-Place aktiv sind.  
  
##  <a name="getitemstate"></a>COleClientItem::GetItemState  
 Rufen Sie diese Funktion, um den aktuellen Zustand des OLE-Elements abzurufen.  
  
```  
UINT GetItemState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COleClientItem:: ItemState** Enumerationswert, der die folgenden Werte sind möglich: `emptyState`, **LoadedState**, `openState`, `activeState`, `activeUIState`. Informationen zu diesen Statuswerten finden Sie im Artikel [Container: Client-Element-Zustände](../../mfc/containers-client-item-states.md).  
  
### <a name="remarks"></a>Hinweise  
 Um benachrichtigt zu werden, wenn das OLE-Element Zustandsänderungen verwenden die [OnChange](#onchange) Member-Funktion.  
  
 Weitere Informationen finden Sie im Artikel [Container: Client-Element-Zustände](../../mfc/containers-client-item-states.md).  
  
##  <a name="getlaststatus"></a>COleClientItem::GetLastStatus  
 Gibt den Statuscode von der letzten OLE-Vorgang.  
  
```  
SCODE GetLastStatus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `SCODE`-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Für Member-Funktionen zurückgegebene ein **BOOL** Wert der **FALSE**, oder andere Memberfunktionen zurückgegebene **NULL**, `GetLastStatus` ausführlichere Fehlerinformationen zurückgegeben. Denken Sie daran, dass die meisten OLE-Memberfunktionen Ausnahmen für schwerwiegende Fehler auslösen. Informationen zur Interpretation von der `SCODE` hängt von der zugrunde liegenden OLE-Aufruf, der zuletzt zurückgegebene ein `SCODE` Wert.  
  
 Weitere Informationen zu `SCODE`, finden Sie unter [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Dokumentation.  
  
##  <a name="getlinkupdateoptions"></a>COleClientItem::GetLinkUpdateOptions  
 Rufen Sie diese Funktion, um den aktuellen Wert der Option Link-Update für das OLE-Element abzurufen.  
  
```  
OLEUPDATE GetLinkUpdateOptions();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- `OLEUPDATE_ALWAYS`Aktualisieren Sie das verknüpfte Element nach Möglichkeit. Diese Option unterstützt das automatische Link-Update-Optionsfeld im Dialogfeld Links.  
  
- `OLEUPDATE_ONCALL`Aktualisieren Sie das verknüpfte Element nur auf Anforderung von der Container-Anwendung (wenn der [UpdateLink](#updatelink) -Memberfunktion aufgerufen wird). Diese Option unterstützt das Optionsfeld manuelle Link-Aktualisierung im Dialogfeld Links.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein erweiterter Vorgang.  
  
 Diese Funktion aufgerufen wird, automatisch von der [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) Klasse.  
  
 Weitere Informationen finden Sie unter [IOleLink::GetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680100) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettype"></a>COleClientItem::GetType  
 Rufen Sie diese Funktion, um zu bestimmen, ob das OLE-Element eingebettet oder verknüpft ist, oder Static.  
  
```  
OLE_OBJTYPE GetType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ganze Zahl ohne Vorzeichen mit einer der folgenden Werte:  
  
- `OT_LINK`Das OLE-Element ist ein Link.  
  
- `OT_EMBEDDED`Das OLE-Element eingebettet ist.  
  
- `OT_STATIC`Das OLE-Element ist statisch, d. h. es enthält nur Präsentationsdaten nicht systemeigen, und kann daher nicht bearbeitet werden.  
  
##  <a name="getusertype"></a>COleClientItem::GetUserType  
 Mit dieser Funktion können die Benutzer sichtbare Zeichenfolge beschreibt das OLE-Element-Typ, z. B. "Word-Dokument" zu erhalten  
  
```  
void GetUserType(
    USERCLASSTYPE nUserClassType,  
    CString& rString);
```  
  
### <a name="parameters"></a>Parameter  
 *nUserClassType*  
 Ein Wert, der angibt, der gewünschte Variante der Zeichenfolge, die das OLE-Element-Typ beschreibt. Dies kann einen der folgenden Werte aufweisen:  
  
- `USERCLASSTYPE_FULL`Der vollständige Name für den Benutzer angezeigt.  
  
- `USERCLASSTYPE_SHORT`Ein kurzer Name (maximal&15; Zeichen) für die Verwendung in Popup-Menüs und das Dialogfeld "Verknüpfungen bearbeiten".  
  
- `USERCLASSTYPE_APPNAME`Der Name der Anwendung, die Wartung der-Klasse.  
  
 `rString`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, dem die Zeichenfolge, die das OLE-Element-Typ beschreibt, die zurückgegeben werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist häufig der Eintrag in der Registrierung-Systemdatenbank.  
  
 Wenn der vollständige Typname angeforderte jedoch nicht verfügbar ist, wird stattdessen der kurze Name verwendet. Das OLE-Element wird verwendet, wenn kein Eintrag für den Typ des OLE-Element in der Registrierungsdatenbank gefunden wird, oder wenn keine Typen registriert, die für den Typ des OLE-Elements vorhanden sind, dann Benutzertyp derzeit in gespeichert. Wenn dieser Typ-Benutzername eine leere Zeichenfolge ist, wird "Unbekannte Object" verwendet.  
  
 Weitere Informationen finden Sie unter [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isinplaceactive"></a>COleClientItem::IsInPlaceActive  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element direkt aktiv ist.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das OLE-Element direkt aktiviert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Es ist üblich, führen Sie eine unterschiedliche Logik abhängig davon, ob das Element direkt bearbeitet wird. Die Funktion überprüft, ob der aktuelle Zustand des Elements entweder gleich der `activeState` oder `activeUIState`.  
  
##  <a name="islinkuptodate"></a>COleClientItem::IsLinkUpToDate  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element auf dem neuesten Stand ist.  
  
```  
BOOL IsLinkUpToDate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das OLE-Element auf dem neuesten Stand ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein verknüpftes Element kann veraltet sein, wenn dem Quelldokument aktualisiert wurde. Ein eingebettetes Element, das Links in diesem enthält kann auf ähnliche Weise veralten. Die Funktion ist eine rekursive Überprüfung des OLE-Elements. Beachten Sie, dass bestimmen, ob ein OLE-Element nicht mehr aktuell ist so teuer wie ein Update ausführen kann.  
  
 Dies wird als automatisch von der [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) Implementierung.  
  
 Weitere Informationen finden Sie unter [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ismodified"></a>COleClientItem::IsModified  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element geändert wurde (wird geändert, seit es zuletzt gespeichert wurde).  
  
```  
BOOL IsModified() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das OLE-Element geändert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isopen"></a>COleClientItem::IsOpen  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element geöffnet ist. d. h. in einer Instanz von der Server-Anwendung ausgeführt wird, in einem separaten Fenster geöffnet.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das OLE-Element geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Es wird verwendet, um zu bestimmen, wann das Objekt mit einem Schraffurmuster, das Zeichnen. Ein offenes-Objekt sollte eine Schraffur über das Objekt gezeichnet haben. Sie können eine [CRectTracker](../../mfc/reference/crecttracker-class.md) Objekt, dies zu erreichen.  
  
##  <a name="isrunning"></a>COleClientItem::IsRunning  
 Rufen Sie diese Funktion, um festzustellen, ob das OLE-Element ausgeführt wird. Gibt an, ob das Element geladen und ausgeführt, in der Serveranwendung ist.  
  
```  
BOOL IsRunning() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das OLE-Element ausgeführt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [OleIsRunning](http://msdn.microsoft.com/library/windows/desktop/ms688705) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onactivate"></a>COleClientItem::OnActivate  
 Aufgerufen, um dem Element zu benachrichtigen, dass er nur an aktiviert wurde.  
  
```  
virtual void OnActivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass diese Funktion aufgerufen wird, um anzugeben, dass der Server ausgeführt wird, nicht, um anzugeben, dass die Benutzeroberfläche in der Container-Anwendung installiert wurde, ein. Zu diesem Zeitpunkt das Objekt keine aktive Benutzeroberfläche (nicht `activeUIState`). Sie hat nicht die Menüs oder Symbolleisten installiert. Die [OnActivateUI](#onactivateui) Member-Funktion wird aufgerufen, wenn dies geschieht.  
  
 Die standardmäßige Implementierung ruft die [OnChange](#onchange) Memberfunktion mit **OLE_CHANGEDSTATE** als Parameter. Überschreiben Sie diese Funktion, um benutzerdefinierte Verarbeitung, wenn ein Element direkt aktiviert wird.  
  
##  <a name="onactivateui"></a>COleClientItem::OnActivateUI  
 Das Framework ruft `OnActivateUI` Wenn das Objekt den aktiven Zustand der Benutzeroberfläche eingegeben hat.  
  
```  
virtual void OnActivateUI();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt hat nun die Symbolleiste und Menüs installiert.  
  
 Die standardmäßige Implementierung des Servers speichert `HWND` für die spätere **GetServerWindow** aufrufen.  
  
##  <a name="onchange"></a>COleClientItem:: OnChange  
 Wird vom Framework aufgerufen, wenn der Benutzer ändert, speichert und das OLE-Element schließt.  
  
```  
virtual void OnChange(
    OLE_NOTIFICATION nCode,  
    DWORD dwParam);
```  
  
### <a name="parameters"></a>Parameter  
 `nCode`  
 Der Grund der Server wurde dieses Element geändert. Die folgenden Werte sind möglich:  
  
- `OLE_CHANGED`Darstellung für das OLE-Element wurde geändert.  
  
- `OLE_SAVED`Das OLE-Element wurde gespeichert.  
  
- `OLE_CLOSED`Das OLE-Element wurde geschlossen.  
  
- `OLE_CHANGED_STATE`Das OLE-Element wurde von einem Zustand in einen anderen geändert.  
  
 `dwParam`  
 Wenn `nCode` ist `OLE_SAVED` oder `OLE_CLOSED`, dieser Parameter wird nicht verwendet. Wenn `nCode` ist `OLE_CHANGED`, dieser Parameter gibt den Aspekt des OLE-Elements, das geändert wurde. Mögliche Werte finden Sie in der `dwParam` Parameter der [COleClientItem::Draw](#draw). Wenn `nCode` ist `OLE_CHANGED_STATE`, dieser Parameter ist ein **COleClientItem:: ItemState** Enumerationswert und beschreibt den Status eingegeben werden. Es kann einen der folgenden Werte aufweisen: `emptyState`, **LoadedState**, `openState`, `activeState`, oder `activeUIState`.  
  
### <a name="remarks"></a>Hinweise  
 (Wenn die Server-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben, wird diese Funktion wird als Reaktion auf die `Notify` Memberfunktionen der `COleServerDoc` oder `COleServerItem`.) Die standardmäßige Implementierung markiert das Containerdokument, als wenn geändert `nCode` ist `OLE_CHANGED` oder `OLE_SAVED`.  
  
 Für `OLE_CHANGED_STATE`, den aktuellen Status von zurückgegebenen [GetItemState](#getitemstate) werden die alten Zustands, d. h. des Zustands, der vor dieser Änderung aktuell war.  
  
 Überschreiben Sie diese Funktion, um auf das OLE-Element statusänderungen reagieren. In der Regel aktualisieren Sie die Darstellung des Elements durch das Ungültigmachen des Bereichs, in dem das Element angezeigt wird. Rufen Sie am Anfang der überschriebenen Implementierung der Basisklasse.  
  
##  <a name="onchangeitemposition"></a>COleClientItem:: OnChangeItemPosition auf  
 Vom Framework aufgerufen wird, den Container zu benachrichtigen, den dass das OLE-Element-Block während der direkten Aktivierung geändert hat.  
  
```  
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```  
  
### <a name="parameters"></a>Parameter  
 *rectPos*  
 Gibt an der Position des Elements relativ zum Clientbereich der Container-Anwendung.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Position des Elements erfolgreich geändert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung bestimmt das neue sichtbare Rechteck des OLE-Elements und ruft [SetItemRects](#setitemrects) mit den neuen Werten. Die standardmäßige Implementierung berechnet das sichtbare Rechteck für das Element, und übergibt diese Informationen an den Server.  
  
 Überschreiben Sie diese Funktion, um die Größe/Move-Vorgangs gelten. Wenn die Anwendung in MFC geschrieben ist, wird dieser Aufruf führt, da der Server aufgerufen [COleServerDoc::RequestPositionChange](../../mfc/reference/coleserverdoc-class.md#requestpositionchange).  
  
##  <a name="ondeactivate"></a>COleClientItem::OnDeactivate  
 Vom Framework aufgerufen, wenn das OLE-Element aus der in-Place aktiv ( `activeState`) in den geladenen Zustand, was bedeutet, dass es eine direkte Aktivierung deaktiviert wird.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass diese Funktion aufgerufen wird, um anzugeben, dass das OLE-Element, nicht geschlossen wird, die die Benutzeroberfläche von der Container-Anwendung entfernt wurde. In diesem Fall die [OnDeactivateUI](#ondeactivateui) -Memberfunktion aufgerufen wird.  
  
 Die standardmäßige Implementierung ruft die [OnChange](#onchange) Memberfunktion mit **OLE_CHANGEDSTATE** als Parameter. Überschreiben Sie diese Funktion, um benutzerdefinierte Verarbeitung beim ein direktes aktives Element deaktiviert wird. Z. B. Wenn Sie den Befehl "Rückgängig" in der containeranwendung unterstützen, können Sie überschreiben diese Funktion zum Verwerfen von Rückgängig-Zustand, der angibt, dass der letzte Vorgang für das OLE-Element ausgeführt rückgängig gemacht werden kann, nachdem das Element deaktiviert wird.  
  
##  <a name="ondeactivateandundo"></a>COleClientItem::OnDeactivateAndUndo  
 Vom Framework aufgerufen, wenn der Benutzer den Befehl "Rückgängig" aufruft, nach der Aktivierung des OLE-Elements an.  
  
```  
virtual void OnDeactivateAndUndo();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft [DeactivateUI](#deactivateui) der Server-Benutzeroberfläche zu deaktivieren. Überschreiben Sie diese Funktion, wenn Sie den Befehl "Rückgängig" in der containeranwendung implementieren. In der Überschreibung der Funktion die Basisklassenversion aufrufen, und klicken Sie dann rückgängig-mit dem letzten Befehl in der Anwendung ausgeführt.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::DeactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms683743) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondeactivateui"></a>COleClientItem::OnDeactivateUI  
 Wird aufgerufen, wenn der Benutzer ein Element deaktiviert, das direkt aktiviert wurde.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Parameter  
 `bUndoable`  
 Gibt an, ob die Bearbeitung rückgängig gemacht werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion stellt die Benutzeroberfläche der containeranwendung Originalzustand ausblenden alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden, wieder her.  
  
 Wenn `bUndoable` ist **FALSE**, Container sollte den Befehl Rückgängig deaktivieren, wirksam rückgängig-Zustand des Containers, verwerfen, da es bedeutet, dass der letzte Vorgang vom Server ausgeführt kann nicht rückgängig gemacht werden.  
  
##  <a name="ondiscardundostate"></a>COleClientItem::OnDiscardUndoState  
 Wird vom Framework aufgerufen, wenn der Benutzer eine Aktion, die den Rückgängig-Status ausführt während der Bearbeitung von OLE-Element ignoriert.  
  
```  
virtual void OnDiscardUndoState();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, wenn Sie den Befehl "Rückgängig" in der containeranwendung implementieren. Verwerfen Sie Sie in der Überschreibung der Container-Anwendung rückgängig Zustand ein.  
  
 Wenn der Server mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, kann der Server diese Funktion vom Aufruf aufgerufen werden [COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate).  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::DiscardUndoState](http://msdn.microsoft.com/library/windows/desktop/ms688642) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ongetclipboarddata"></a>COleClientItem::OnGetClipboardData  
 Aufgerufen, zum Abrufen einer `COleDataSource` Objekt mit allen Daten, die durch einen Aufruf von in der Zwischenablage platziert werden würde die [CopyToClipboard](#copytoclipboard) oder [DoDragDrop](#dodragdrop) Member-Funktion.  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>Parameter  
 `bIncludeLink`  
 Legen Sie den **TRUE** Wenn Verknüpfen von Daten in die Zwischenablage kopiert werden soll. Legen Sie den **FALSE** Wenn die Server-Anwendung Links nicht unterstützt.  
  
 `lpOffset`  
 Zeiger auf den Offset des Mauszeigers auf den Ursprung des-Objekts in Pixeln.  
  
 `lpSize`  
 Zeiger auf die Größe des Objekts in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [COleDataSource](../../mfc/reference/coledatasource-class.md) Objekt, das Daten in der Zwischenablage enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die standardmäßige Implementierung dieser Funktion [GetClipboardData](#getclipboarddata).  
  
##  <a name="ongetcliprect"></a>COleClientItem::OnGetClipRect  
 Das Framework ruft der `OnGetClipRect` Member-Funktion bei der Einrichtung der Auswahlrechteck Koordinaten des Elements, das gerade bearbeitet wird.  
  
```  
virtual void OnGetClipRect(CRect& rClipRect);
```  
  
### <a name="parameters"></a>Parameter  
 *rClipRect*  
 Zeiger auf ein Objekt der Klasse [CRect](../../atl-mfc-shared/reference/crect-class.md) , die die Auswahlrechteck Koordinaten des Elements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten sind relativ zum Clientbereich des Anwendungsfensters die Container in Pixel.  
  
 Die standardmäßige Implementierung gibt einfach das Clientrechteck der Ansicht, auf der das Element direkt aktiv ist.  
  
##  <a name="ongetitemposition"></a>COleClientItem:: OnGetItemPosition auf  
 Das Framework ruft der `OnGetItemPosition` Member-Funktion bei der Einrichtung die Koordinaten des Elements, das gerade bearbeitet wird.  
  
```  
virtual void OnGetItemPosition(CRect& rPosition);
```  
  
### <a name="parameters"></a>Parameter  
 `rPosition`  
 Ein Verweis auf die [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekts, das Element Positionskoordinaten enthält.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten sind relativ zum Clientbereich des Anwendungsfensters die Container in Pixel.  
  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Clientanwendungen, die direkte Bearbeitung unterstützen erfordern die Implementierung.  
  
##  <a name="ongetwindowcontext"></a>COleClientItem::OnGetWindowContext  
 Wird vom Framework aufgerufen, wenn ein Element direkt aktiviert wird.  
  
```  
virtual BOOL OnGetWindowContext(
    CFrameWnd** ppMainFrame,  
    CFrameWnd** ppDocFrame,  
    LPOLEINPLACEFRAMEINFO lpFrameInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `ppMainFrame`  
 Zeiger auf einen Zeiger auf das Hauptrahmenfenster.  
  
 `ppDocFrame`  
 Zeiger auf einen Zeiger auf das Dokumentrahmenfenster.  
  
 `lpFrameInfo`  
 Zeiger auf eine [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) -Struktur, die Frame-Fensters-Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird verwendet, um Informationen über das OLE-Element des übergeordneten Fensters abzurufen.  
  
 Wenn der Container eine MDI-Anwendung ist, wird die standardmäßige Implementierung gibt einen Zeiger auf die [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) -Objekt in `ppMainFrame` und einen Zeiger auf den aktiven [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) -Objekt in `ppDocFrame`. Wenn der Container eine SDI-Anwendung ist, wird die standardmäßige Implementierung gibt einen Zeiger auf die [CFrameWnd](../../mfc/reference/cframewnd-class.md) -Objekt in `ppMainFrame` und gibt **NULL** in `ppDocFrame`. Die standardmäßige Implementierung füllt auch die Elemente der `lpFrameInfo`.  
  
 Überschreiben Sie diese Funktion nur, wenn die standardmäßige Implementierung nicht mit Ihrer Anwendung passt. Beispielsweise verfügt die Anwendung eine Sichtweise der Benutzeroberfläche, die von SDI- oder MDI-abweicht. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms694366) und [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="oninsertmenus"></a>COleClientItem::OnInsertMenus  
 Vom Framework aufgerufen, während die direkte Aktivierung der Container-Anwendung Menüs in ein leeres Menü eingefügt.  
  
```  
virtual void OnInsertMenus(
    CMenu* pMenuShared,  
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```  
  
### <a name="parameters"></a>Parameter  
 `pMenuShared`  
 Verweist auf ein leeres Menü.  
  
 `lpMenuWidths`  
 Zeigt auf ein Array von sechs **lang** Werte, der angibt, wie viele Menüs in jeder der folgenden Menügruppen sind: Datei, bearbeiten, Container, Fenster Objekt-Hilfe. Die Container-Anwendung ist verantwortlich für die Datei, Container und Fenster Menügruppen, Elemente, 0, 2 und 4 dieses Arrays entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Menü wird dann an den Server eine eigene Menüs, die beim Erstellen eines zusammengesetzten Menüs fügt übergeben. Diese Funktion kann wiederholt aufgerufen werden, um mehrere zusammengesetzte Menüs zu erstellen.  
  
 Fügt die Implementierung der `pMenuShared` der in-Place-Containermenüs, d. h. Gruppen im Menü Datei, Container und Fenster. [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo) zum Festlegen dieser Ressource verwendet wird. Die standardmäßige Implementierung weist auch die entsprechenden Werte auf die Elemente 0, 2 und 4 im `lpMenuWidths`, abhängig von der Ressource. Überschreiben Sie diese Funktion, wenn die standardmäßige Implementierung nicht für Ihre Anwendung geeignet ist. Wenn beispielsweise Ihre Anwendung keine Dokumentvorlagen verwendet werden, zum Zuordnen von Ressourcen zu Dokumenttypen. Wenn Sie diese Funktion überschreiben, sollten Sie auch überschreiben [OnSetMenu](#onsetmenu) und [OnRemoveMenus](#onremovemenus). Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceFrame::InsertMenus](http://msdn.microsoft.com/library/windows/desktop/ms683987) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onremovemenus"></a>COleClientItem::OnRemoveMenus  
 Vom Framework aufgerufen wird, entfernen die Menüs des Containers aus dem angegebenen zusammengesetzten Menü, wenn direkte Aktivierung beendet.  
  
```  
virtual void OnRemoveMenus(CMenu* pMenuShared);
```  
  
### <a name="parameters"></a>Parameter  
 `pMenuShared`  
 Verweist auf das zusammengesetzte Menü erstellt, die durch Aufrufe der [OnInsertMenus](#oninsertmenus) Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung entfernt aus `pMenuShared` die Containermenüs, die in-Place-, Gruppen im Menü Datei, Container und Fenster. Überschreiben Sie diese Funktion, wenn die standardmäßige Implementierung nicht für Ihre Anwendung geeignet ist. Wenn beispielsweise Ihre Anwendung keine Dokumentvorlagen verwendet werden, zum Zuordnen von Ressourcen zu Dokumenttypen. Wenn Sie diese Funktion überschreiben, müssen Sie wahrscheinlich überschreiben [OnInsertMenus](#oninsertmenus) und [OnSetMenu](#onsetmenu) ebenfalls. Dies ist eine erweiterte überschrieben.  
  
 Die Untermenüs auf `pMenuShared` kann von mehr als einem zusammengesetzten Menü freigegeben werden, wenn der Server wiederholt aufgerufen hat `OnInsertMenus`. Aus diesem Grund sollten Sie Untermenüs nicht löschen, in der Überschreibung der `OnRemoveMenus`; Sie sollten nur trennen.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceFrame::RemoveMenus](http://msdn.microsoft.com/library/windows/desktop/ms688685) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onscrollby"></a>COleClientItem::OnScrollBy  
 Vom Framework aufgerufen wird das OLE-Element als Antwort auf Anforderungen vom Server zu navigieren.  
  
```  
virtual BOOL OnScrollBy(CSize sizeExtent);
```  
  
### <a name="parameters"></a>Parameter  
 *sizeExtent*  
 Gibt die Abstände in Pixel, um die x- und y Richtung scrollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Element ein Bildlauf durchgeführt wurde; 0, wenn das Element kein Bildlauf durchgeführt werden konnte.  
  
### <a name="remarks"></a>Hinweise  
 Beispielsweise wird, wenn das OLE-Element nur teilweise sichtbar ist, und der Benutzer, die außerhalb des sichtbaren Bereichs beim Ausführen einer in-Place-Bearbeitung bewegt, diese Funktion aufgerufen, um den Cursor sichtbar bleiben. Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um das Element mit dem angegebenen Betrag zu blättern. Beachten Sie, dass als Ergebnis der Bildlauf der sichtbare Teil des OLE-Elements ändern kann. Rufen Sie [SetItemRects](#setitemrects) sichtbar Rechtecks des Elements zu aktualisieren.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceSite::Scroll](http://msdn.microsoft.com/library/windows/desktop/ms690291) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onsetmenu"></a>COleClientItem::OnSetMenu  
 Aufgerufen vom Framework zweimal Wenn direkte Aktivierung beginnt und endet. So installieren Sie das zusammengesetzte Menü und das zweite Mal beim ersten (mit `holemenu` gleich **NULL**) zu entfernen.  
  
```  
virtual void OnSetMenu(
    CMenu* pMenuShared,  
    HOLEMENU holemenu,  
    HWND hwndActiveObject);
```  
  
### <a name="parameters"></a>Parameter  
 `pMenuShared`  
 Zeiger auf das zusammengesetzte Menü erstellt, die durch Aufrufe der [OnInsertMenus](#oninsertmenus) -Memberfunktion und die `InsertMenu` Funktion.  
  
 `holemenu`  
 Handle für das Menü Deskriptor zurückgegeben werden, indem Sie die **OleCreateMenuDescriptor** -Funktion oder **NULL** ist die Verteilung Code entfernt werden soll.  
  
 *hwndActiveObject*  
 Handle für das Fenster für das OLE-Element. Dies ist das Fenster, das Befehle zum Bearbeiten von OLE erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung installiert oder entfernt das zusammengesetzte Menü und ruft dann die [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831) Funktion zu installieren oder entfernen Sie den Code verteilen. Überschreiben Sie diese Funktion, wenn die standardmäßige Implementierung nicht für Ihre Anwendung geeignet ist. Wenn Sie diese Funktion überschreiben, müssen Sie wahrscheinlich überschreiben [OnInsertMenus](#oninsertmenus) und [OnRemoveMenus](#onremovemenus) ebenfalls. Dies ist eine erweiterte überschrieben.  
  
 Weitere Informationen finden Sie unter [OleCreateMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms691415), [OleSetMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms692831), und [SetMenu](http://msdn.microsoft.com/library/windows/desktop/ms693713) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onshowcontrolbars"></a>COleClientItem::OnShowControlBars  
 Vom Framework aufgerufen wird, ein- und Ausblenden von Steuerleisten der Container-Anwendung.  
  
```  
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 `pFrameWnd`  
 Ein Zeiger auf den Steuerelementcontainer-Anwendung Rahmenfenster. Dies kann entweder ein Hauptrahmenfenster oder ein untergeordnetes MDI-Fenster sein.  
  
 `bShow`  
 Gibt an, ob Steuerleisten angezeigt oder ausgeblendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Aufruf der Funktion bewirkt, dass eine Änderung in den Steuerleisten Status; 0, wenn der Aufruf bewirkt, dass keine Änderung oder `pFrameWnd` nicht auf die Container-Rahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt 0 zurück, wenn die Steuerleisten bereits im angegebenen Zustand *bShow.* Dies würde z. B. auftreten, wenn die Steuerleisten ausgeblendet sind und `bShow` ist **FALSE**.  
  
 Die standardmäßige Implementierung entfernt die Symbolleiste im Fenster der obersten Ebene Frame.  
  
##  <a name="onshowitem"></a>COleClientItem::OnShowItem  
 Vom Framework aufgerufen wird zum Anzeigen des OLE-Elements, die während der Bearbeitung vollständig sichtbar machen.  
  
```  
virtual void OnShowItem();
```  
  
### <a name="remarks"></a>Hinweise  
 Wird verwendet, wenn der containeranwendung Links zu eingebetteten Elementen unterstützt (d. h., wenn Sie die Dokumentklasse von abgeleitet haben [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)). Diese Funktion wird aufgerufen, während die direkte Aktivierung oder wenn das OLE-Element eine Quelle der Verknüpfung ist und der Benutzer möchte, um ihn zu bearbeiten. Die standardmäßige Implementierung wird die erste Ansicht auf Containerdokument aktiviert. Überschreiben Sie diese Funktion das Dokument einen Bildlauf durchführen, damit das OLE-Element sichtbar ist.  
  
##  <a name="onupdateframetitle"></a>COleClientItem::OnUpdateFrameTitle  
 Vom Framework aufgerufen, während die direkte Aktivierung des Rahmenfensters Titelleiste zu aktualisieren.  
  
```  
virtual BOOL OnUpdateFrameTitle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn diese Funktion aktualisiert die Frametitel, andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ändert nicht den Fenstertitel Frame. Überschreiben Sie Sie ggf. einen anderen Frametitel für Ihre Anwendung z. B. " *app Server* - *Element* in *Docname*" (wie "Microsoft Excel - Arbeitsblatt im Bericht. DOC"). Dies ist eine erweiterte überschrieben.  
  
##  <a name="reactivateandundo"></a>COleClientItem::ReactivateAndUndo  
 Rufen Sie diese Funktion zum Reaktivieren des OLE-Elements und Rückgängigmachen des letzten Vorgangs, der vom Benutzer ausgeführt werden, während die direkte Bearbeitung.  
  
```  
BOOL ReactivateAndUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die containeranwendung den Befehl Rückgängig unterstützt, rufen Sie diese Funktion, wenn der Benutzer den Befehl Rückgängig unmittelbar auf das OLE-Element zu deaktivieren.  
  
 Wenn die Server-Anwendung durch die Microsoft Foundation Class-Bibliotheken geschrieben werden, diese Funktion bewirkt, dass der Server Aufrufen [COleServerDoc::OnReactivateAndUndo](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo).  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="release"></a>COleClientItem::Release  
 Rufen Sie diese Funktion zum Bereinigen von Ressourcen, die durch das OLE-Element verwendet.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCloseOption`  
 Flag, das angibt, unter welchen Umständen das OLE-Element gespeichert wird, wenn in den geladenen Zustand zurückgegeben. Eine Liste der möglichen Werte finden Sie unter [COleClientItem::Close](#close).  
  
### <a name="remarks"></a>Hinweise  
 **Version** wird aufgerufen, indem die `COleClientItem` Destruktor.  
  
 Weitere Informationen finden Sie unter [IUnknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="reload"></a>COleClientItem::Reload  
 Wird geschlossen, und lädt das Element.  
  
```  
BOOL Reload();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `Reload` Funktion nach Aktivierung des Elements als Element eines anderen Typs durch einen Aufruf von [ActivateAs](#activateas).  
  
##  <a name="run"></a>COleClientItem::Run  
 Führt die Anwendung, die diesem Element zugeordnet.  
  
```  
void Run();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die **ausführen** Member-Funktion zum Starten der Serveranwendung vor der Aktivierung des Elements. Dies erfolgt automatisch durch [aktivieren](#activate) und [DoVerb](#doverb), daher ist es in der Regel nicht erforderlich, diese Funktion aufzurufen. Mit dieser Funktion wird bei Bedarf auf dem Server ausgeführt werden, um ein Elementattribut festzulegen, z. B. [SetExtent](#setextent), vor dem Ausführen [DoVerb](#doverb).  
  
##  <a name="setdrawaspect"></a>COleClientItem::SetDrawAspect  
 Rufen Sie die `SetDrawAspect` Memberfunktion, die "Aspekt" oder die Ansicht des Elements festgelegt.  
  
```  
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>Parameter  
 `nDrawAspect`  
 Ein Wert aus der `DVASPECT`-Enumeration. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt innerhalb des Containers angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Element wird in einer "Miniaturansicht"-Darstellung dargestellt, damit sie in einem Browser angezeigt werden kann.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mithilfe des Befehls Drucken im Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Der Aspekt gibt an, wie das Element gerendert werden [zeichnen](#draw) Wenn der Standardwert für diese Funktion `nDrawAspect` verwendet wird.  
  
 Diese Funktion wird automatisch aufgerufen, durch das Symbol ändern (und andere Dialogfelder, die im Dialogfeld "Symbol ändern" direkt aufrufen) ermöglichen den Aspekt iconic anzeigen, wenn vom Benutzer angefordert.  
  
##  <a name="setextent"></a>COleClientItem::SetExtent  
 Rufen Sie diese Funktion, um anzugeben, wie viel Speicherplatz für das OLE-Element verfügbar ist.  
  
```  
void SetExtent(
    const CSize& size,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, die Informationen enthält.  
  
 `nDrawAspect`  
 Gibt den Aspekt des OLE-Elements, dessen Grenzen festgelegt werden sollen. Mögliche Werte finden Sie unter [SetDrawAspect](#setdrawaspect).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Server-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben wurde, wird dadurch die [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent) -Memberfunktion des entsprechenden `COleServerItem` Objekt aufgerufen werden. Das OLE-Element kann die Anzeige entsprechend anpassen. Die Dimensionen sein `MM_HIMETRIC` Einheiten. Rufen Sie diese Funktion, wenn der Benutzer das OLE-Element ändert oder wenn Sie eine Form der Layout-Aushandlung unterstützen.  
  
 Weitere Informationen finden Sie unter [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="sethostnames"></a>COleClientItem::SetHostNames  
 Rufen Sie diese Funktion, um den Namen der containeranwendung, und der Containername für ein eingebettetes OLE-Element angeben.  
  
```  
void SetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszHost`  
 Ein Zeiger auf den Benutzer sichtbare Name der containeranwendung.  
  
 `lpszHostObj`  
 Ein Zeiger auf eine identifizierende Zeichenfolge des Containers, die das OLE-Element enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Server-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben wurde, wird diese Funktion ruft die [OnSetHostNames](../../mfc/reference/coleserverdoc-class.md#onsethostnames) Memberfunktion die `COleServerDoc` Dokument, das das OLE-Element enthält. Diese Informationen werden im Fenstertitel verwendet, wenn das OLE-Element bearbeitet wird. Jedes Mal, wenn ein anderes Dokument geladen wird, ruft das Framework diese Funktion für alle OLE-Elemente im Dokument. `SetHostNames`gilt nur für eingebettete Elemente. Es ist nicht notwendig, rufen Sie diese Funktion jedes Mal, wenn ein eingebettetes OLE-Element aktiviert ist, für die Bearbeitung.  
  
 Dies wird auch automatisch mit dem Anwendungsnamen und der Name des Dokuments aufgerufen, wenn ein Objekt geladen wird oder wenn eine Datei unter einem anderen Namen gespeichert wird. Entsprechend ist es normalerweise nicht erforderlich, diese Funktion direkt aufzurufen.  
  
 Weitere Informationen finden Sie unter [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="seticonicmetafile"></a>COleClientItem::SetIconicMetafile  
 Speichert die Metadatei, die zum Zeichnen des Symbols.  
  
```  
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```  
  
### <a name="parameters"></a>Parameter  
 `hMetaPict`  
 Ein Handle für die Metadatei, die zum Zeichnen des Symbols.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [GetIconicMetafile](#geticonicmetafile) die Metadatei abrufen.  
  
 Die `hMetaPict` Parameter in das Element kopiert wird daher `hMetaPict` muss vom Aufrufer freigegeben werden.  
  
##  <a name="setitemrects"></a>COleClientItem::SetItemRects  
 Rufen Sie diese Funktion, um das umschließende Rechteck oder das sichtbare Rechteck des OLE-Elements festgelegt.  
  
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
 Diese Funktion wird aufgerufen, durch die standardmäßige Implementierung der von der [OnChangeItemPosition](#onchangeitemposition) Member-Funktion. Sie sollten diese Funktion aufrufen, wenn die Position oder den sichtbaren Teil des OLE-Element geändert wird. Normalerweise bedeutet dies, dass Sie sie aus der Ansicht Aufrufen [OnSize](../../mfc/reference/cwnd-class.md#onsize) und [OnScrollBy](../../mfc/reference/cview-class.md#onscrollby) Memberfunktionen.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setlinkupdateoptions"></a>COleClientItem::SetLinkUpdateOptions  
 Rufen Sie diese Funktion, um die Link-Update-Option für die Darstellung von das angegebene verknüpfte Element festgelegt.  
  
```  
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```  
  
### <a name="parameters"></a>Parameter  
 *dwUpdateOpt*  
 Der Wert der Option Link-Update für diesen Artikel. Dieser Wert muss eine der folgenden sein:  
  
- `OLEUPDATE_ALWAYS`Aktualisieren Sie das verknüpfte Element nach Möglichkeit. Diese Option unterstützt das automatische Link-Update-Optionsfeld im Dialogfeld Links.  
  
- `OLEUPDATE_ONCALL`Aktualisieren Sie das verknüpfte Element nur auf Anforderung von der Container-Anwendung (wenn der [UpdateLink](#updatelink) -Memberfunktion aufgerufen wird). Diese Option unterstützt das Optionsfeld manuelle Link-Aktualisierung im Dialogfeld Links.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel sollten Sie die Update-Optionen, die der Benutzer im Dialogfeld "Links" nicht ändern.  
  
 Weitere Informationen finden Sie unter [IOleLink::SetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680120) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setprintdevice"></a>COleClientItem::SetPrintDevice  
 Rufen Sie diese Funktion, um das Drucken-Zielgerät für dieses Element zu ändern.  
  
```  
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL SetPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Parameter  
 `ptd`  
 Zeiger auf eine [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Datenstruktur, die Informationen über das neue Ziel drucken Gerät enthält. Kann **NULL**.  
  
 `ppd`  
 Zeiger auf eine [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646940) Datenstruktur, die Informationen über das neue Ziel drucken Gerät enthält. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aktualisiert das Drucken-Zielgerät für das Element jedoch nicht die Präsentation Cache aktualisiert. Um die Präsentation-Cache nach einem Element zu aktualisieren, rufen [UpdateLink](#updatelink).  
  
 Die Argumente für diese Funktion enthalten Informationen, die das OLE-System verwendet wird, um das Gerät zu identifizieren. Die **PRINTDLG** Struktur enthält Informationen, die Windows verwendet, um das Standarddialogfeld Drucken zu initialisieren. Nachdem der Benutzer das Dialogfeld geschlossen wird, gibt Windows Informationen zur Auswahl des Benutzers in dieser Struktur zurück. Die `m_pd` Mitglied einer [CPrintDialog](../../mfc/reference/cprintdialog-class.md) -Objekt ist ein **PRINTDLG** Struktur.  
  
 Weitere Informationen zu dieser Struktur finden Sie unter [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="updatelink"></a>COleClientItem::UpdateLink  
 Rufen Sie diese Funktion, um die Darstellung des OLE-Elements sofort zu aktualisieren.  
  
```  
BOOL UpdateLink();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Verknüpfter Elemente enthält sucht die Funktion der Quelle der Verknüpfung um eine neue Präsentation für das OLE-Element zu erhalten. Dieser Vorgang kann eine, die eine oder mehrere serveranwendungen, die zeitaufwändig sein kann. Für eingebettete Elemente arbeitet die Funktion rekursiv, überprüfen, ob das eingebettete Element Links enthält, die möglicherweise veraltet und aktualisiert diese. Der Benutzer kann einzelne Links, die Links im Dialogfeld auch manuell aktualisieren.  
  
 Weitere Informationen finden Sie unter [IOleLink::Update](http://msdn.microsoft.com/library/windows/desktop/ms692660) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MFCBIND](../../visual-cpp-samples.md)   
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [CDocItem-Klasse](../../mfc/reference/cdocitem-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)

