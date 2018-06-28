---
title: COleServerDoc Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
dev_langs:
- C++
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7df4ea13313758c517188e1c4ce0441618a99b4
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039057"
---
# <a name="coleserverdoc-class"></a>COleServerDoc-Klasse
Die Basisklasse für OLE-Serverdokumente.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](#coleserverdoc)|Erstellt ein `COleServerDoc`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](#activatedocobject)|Aktiviert das zugeordnete DocObject-Dokument.|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|Aktiviert das Dokument für die direkte Bearbeitung an.|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Deaktiviert das Server-Benutzeroberfläche.|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|Verwirft die rückgängig-Statusinformationen.|  
|[COleServerDoc::GetClientSite](#getclientsite)|Ruft einen Zeiger auf die zugrunde liegende `IOleClientSite` Schnittstelle.|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Gibt einen Zeiger auf ein Element, das das gesamte Dokument darstellt.|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Gibt den aktuellen das Auswahlrechteck für die direkte Bearbeitung zurück.|  
|[COleServerDoc::GetItemPosition](#getitemposition)|Gibt die aktuelle Positionsrechteck relativ zum Clientbereich der Steuerelementcontainer-Anwendung, für die direkte Bearbeitung.|  
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Gibt den Zoomfaktor in Pixel zurück.|  
|[COleServerDoc::IsDocObject](#isdocobject)|Bestimmt, ob das Dokument DocObject ist.|  
|[COleServerDoc::IsEmbedded](#isembedded)|Gibt an, ob das Dokument in einem Containerdokument eingebettet oder ausgeführten eigenständig ist.|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Gibt `TRUE` , wenn das Element derzeit festliegen aktiviert ist.|  
|[COleServerDoc::NotifyChanged](#notifychanged)|Benachrichtigt Container, dass der Benutzer das Dokument geändert hat.|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|Benachrichtigt Container, dass der Benutzer das Dokument geschlossen wurde.|  
|[COleServerDoc::NotifyRename](#notifyrename)|Benachrichtigt Container, dass der Benutzer das Dokument umbenannt wurde.|  
|[COleServerDoc::NotifySaved](#notifysaved)|Benachrichtigt Container, dass der Benutzer das Dokument gespeichert wurde.|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|Vom Framework aufgerufen, wenn der Benutzer ein Element deaktiviert, die direkt aktiviert wurde.|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Vom Framework aufgerufen, Steuerelemente und andere Elemente der Benutzeroberfläche für die direkte Aktivierung erstellt zu zerstören.|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Vom Framework aufgerufen, wenn der Container Dokumentrahmenfenster aktiviert oder deaktiviert ist.|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Vom Framework aufgerufen, wenn Rahmenfenster der Steuerelementcontainer-Anwendung oder ein Dokumentfenster angepasst wird.|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Wird aufgerufen, durch das Framework anzeigen oder Ausblenden von Steuerleisten für die direkte Bearbeitung.|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Vom Framework aufgerufen, wenn ein Serverdokument, das ein eingebettetes Element Aktualisieren des Containers Kopie des Elements gespeichert wird, wird.|  
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Ändert die Position des direkten Bearbeitungsrahmen.|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|Weist die Steuerelementcontainer-Anwendung zum Speichern des Dokuments an.|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Ermöglicht das Scrollen Containerdokument.|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|Benachrichtigt Container, dass der Benutzer das Dokument geändert hat.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Wird aufgerufen, durch das Framework zum Erstellen eines Rahmenfensters für die direkte Bearbeitung.|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Vom Framework aufgerufen, für die direkte Bearbeitung ein Rahmenfensters zu zerstören.|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Überschreiben Sie diese Funktion zum Erstellen eines neuen `CDocObjectServer` Objekt, und um anzugeben, dass dieses Dokument ein DocObject-Container ist.|  
|[COleServerDoc::OnClose](#onclose)|Vom Framework aufgerufen, wenn ein Container anfordert, um das Dokument zu schließen.|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Führt einen angegebenen Befehl aus, oder zeigt die Hilfe für den Befehl.|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Vom Framework aufgerufen, wenn das Rahmenfenster des Containers aktiviert oder deaktiviert wird.|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Wird aufgerufen, um das Abrufen einer `COleServerItem` , die das gesamte Dokument darstellt; verwendet, um ein eingebettetes Element abzurufen. Die Implementierung erforderlich sind.|  
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Vom Framework aufgerufen, während die direkte Bearbeitung vorgenommenen Änderungen rückgängig zu machen.|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Vom Framework aufgerufen, wenn ein Container den Fenstertitel für ein eingebettetes Objekt festlegt.|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Wird aufgerufen, durch das Framework das Rahmenfenster der direkte Bearbeitung innerhalb der containeranwendung Fenster positioniert wird.|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|Wird aufgerufen, durch das Framework anzeigen oder Ausblenden des Dokuments.|  
  
## <a name="remarks"></a>Hinweise  
 Serverdokument darf [COleServerItem](../../mfc/reference/coleserveritem-class.md) Objekte, die die Serverschnittstelle zu eingebettete oder verknüpfte Elemente darstellen. Wenn eine Serveranwendung, die von einem Container so bearbeiten Sie ein eingebettetes Element gestartet wird, wird das Element als sein eigenes Serverdokument geladen. die `COleServerDoc` Objekt enthält nur einen `COleServerItem` -Objekt, das gesamte Dokument besteht. Wenn eine Serveranwendung, die von einem Container so bearbeiten Sie ein verknüpftes Element gestartet wird, wird ein vorhandenes Dokument vom Datenträger geladen. ein Teil der Inhalt des Dokuments wird hervorgehoben, um das verknüpfte Element anzugeben.  
  
 `COleServerDoc` -Objekte können auch Elemente enthalten die [COleClientItem](../../mfc/reference/coleclientitem-class.md) Klasse. Dadurch können Sie die Container-Server-Anwendungen zu erstellen. Das Framework bietet Funktionen zum Speichern von ordnungsgemäß der `COleClientItem` Elemente während der Wartung der `COleServerItem` Objekte.  
  
 Wenn Ihre Serveranwendung Links nicht unterstützt wird, enthält Serverdokument immer nur ein Serverelement, das gesamte eingebettete Objekt als ein Dokument dar. Ihre Serveranwendung Links unterstützt, müssen sie ein Serverelement jedes Mal erstellen, wenn eine Auswahl in die Zwischenablage kopiert wird.  
  
 Mit `COleServerDoc`, eine Klasse ableiten und Implementieren der [OnGetEmbeddedItem](#ongetembeddeditem) Memberfunktion, die der Server zur Unterstützung von eingebetteten Elemente zulässt. Leiten Sie eine Klasse von `COleServerItem` implementieren die Elemente in Ihren Dokumenten und Zurückgeben von Objekten dieser Klasse aus `OnGetEmbeddedItem`.  
  
 Zur Unterstützung von verknüpfter Elementen `COleServerDoc` bietet die [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) Memberfunktion. Sie können die standardmäßige Implementierung oder haben eine eigene Möglichkeit der Verwaltung von Dokumentelemente zu überschreiben.  
  
 Sie benötigen ein `COleServerDoc`-Klasse abgeleitet, für die verschiedenen Servertypen dokumentieren Sie die Anwendung unterstützt. Beispielsweise, wenn die Server-Anwendung Arbeitsblätter und Diagramme unterstützt, benötigen Sie zwei `COleServerDoc`-abgeleitete Klassen.  
  
 Weitere Informationen zu Servern finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="activatedocobject"></a>  COleServerDoc::ActivateDocObject  
 Aktiviert das zugeordnete DocObject-Dokument.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `COleServerDoc` aktive Dokumente (auch als DocObjects bezeichnet) nicht unterstützt. Zum Aktivieren dieser Unterstützung finden Sie unter [GetDocObjectServer](#getdocobjectserver) und Klasse [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).  
  
##  <a name="activateinplace"></a>  COleServerDoc::ActivateInPlace  
 Aktiviert das Element für die direkte Bearbeitung an.  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0, die angibt, dass das Element vollständig geöffnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion führt alle Vorgänge, die für die direkte Aktivierung erforderlich. Er erstellt ein in-Place-Frame-Fenster, aktiviert und Größe von des Elements, richtet freigegebene Menüs und anderen Steuerelementen, verschiebt das Element in der Ansicht und setzt den Fokus auf das direkte Rahmenfenster.  
  
 Diese Funktion wird aufgerufen, indem Sie die standardmäßige Implementierung des [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Rufen Sie diese Funktion, wenn Ihre Anwendung eine andere Verb für die direkte Aktivierung (z. B. Play) unterstützt.  
  
##  <a name="coleserverdoc"></a>  COleServerDoc::COleServerDoc  
 Erstellt ein `COleServerDoc` Objekt, ohne dass eine Verbindung mit der OLE-System-DLLs.  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) Kommunikation mit OLE zu öffnen. Bei Verwendung von [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) in Ihrer Anwendung `COleLinkingDoc::Register` wird aufgerufen, für Sie von `COleLinkingDoc`der Implementierung von `OnNewDocument`, `OnOpenDocument`, und `OnSaveDocument`.  
  
##  <a name="createinplaceframe"></a>  COleServerDoc::CreateInPlaceFrame  
 Das Framework ruft diese Funktion zum Erstellen eines Rahmenfensters für die direkte Bearbeitung.  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Ein Zeiger auf die containeranwendung übergeordneten Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das direkte Rahmenfenster oder **NULL** Wenn Fehler auftreten.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung verwendet die in der Dokumentvorlage angegebenen Informationen zum Erstellen des Rahmens. Die Sicht, wird die erste Ansicht, die für das Dokument erstellt. In dieser Ansicht wird vorübergehend aus der ursprünglichen Rahmen getrennt und an den neu erstellten Frame angefügt.  
  
 Dies ist eine erweiterte überschrieben.  
  
##  <a name="deactivateandundo"></a>  COleServerDoc::DeactivateAndUndo  
 Rufen Sie diese Funktion, wenn die Anwendung unterstützt rückgängig zu machen, und der Benutzer rückgängig, die nach dem Aktivieren eines Elements, jedoch vor dem Bearbeiten wählt.  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben wird, das Aufrufen dieser Funktion bewirkt, dass [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) um aufgerufen werden, die Benutzeroberfläche der Server deaktiviert.  
  
##  <a name="destroyinplaceframe"></a>  COleServerDoc::DestroyInPlaceFrame  
 Das Framework ruft diese Funktion zum Zerstören eines Fensters in-Place-Frame und zum Zurückgeben von Anwendung Dokumentfenster in dem Zustand vor der direkten Aktivierung für des Servers.  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pFrameWnd*  
 Ein Zeiger auf das direkte Rahmenfenster zerstört werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine erweiterte überschrieben.  
  
##  <a name="discardundostate"></a>  COleServerDoc::DiscardUndoState  
 Wenn der Benutzer einen Bearbeitungsvorgang, der rückgängig gemacht werden kann ausführt, rufen Sie diese Funktion zum Erzwingen der Steuerelementcontainer-Anwendung, die rückgängig-Zustandsinformationen zu verwerfen.  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird bereitgestellt, sodass Server, die zum Rückgängigmachen unterstützen Ressourcen freigegeben werden können, die andernfalls von Rückgängig-Statusinformationen verwendet werden würde, die verwendet werden kann.  
  
##  <a name="getclientsite"></a>  COleServerDoc::GetClientSite  
 Ruft einen Zeiger auf die zugrunde liegende `IOleClientSite` Schnittstelle.  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft einen Zeiger auf die zugrunde liegende [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706) Schnittstelle.  
  
##  <a name="getdocobjectserver"></a>  COleServerDoc::GetDocObjectServer  
 Überschreiben Sie diese Funktion zum Erstellen eines neuen `CDocObjectServer` Element und einen Zeiger darauf zurückgeben.  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>Parameter  
 *pDocSite*  
 Zeiger auf die `IOleDocumentSite` -Schnittstelle, die diesem Dokument mit dem Server hergestellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CDocObjectServer`; **NULL** bei fehlgeschlagenem Vorgang.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein DocObject-Server aktiviert ist, die Rückgabe von einer nicht - **NULL** Zeiger zeigt an, dass der Client DocObjects unterstützen können. Gibt die standardmäßige Implementierung **NULL**.  
  
 Eine typische Implementierung für ein Dokument, das DocObjects unterstützt belegt einfach ein neues `CDocObjectServer` -Objekt erstellt und an den Aufrufer zurückgegeben. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="getembeddeditem"></a>  COleServerDoc::GetEmbeddedItem  
 Mit dieser Funktion wird zum Abrufen eines Zeigers auf ein Element, das das gesamte Dokument darstellt.  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Element, das das gesamte Dokument darstellt; **NULL** bei fehlgeschlagenem Vorgang.  
  
### <a name="remarks"></a>Hinweise  
 Sie ruft [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), eine virtuelle Funktion mit keine Standardimplementierung.  
  
##  <a name="getitemcliprect"></a>  COleServerDoc::GetItemClipRect  
 Rufen Sie die `GetItemClipRect` Memberfunktion versucht, erhalten das Clippingrechteck Koordinaten des Elements, das gerade bearbeitet wird, vorhanden.  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpClipRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das Clippingrechteck Koordinaten des Elements zu erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zum Clientbereich im Container Anwendungsfenster angezeigt.  
  
 Zeichnung soll nicht außerhalb der Clippingrechteck ausgeführt werden. Zeichnung ist in der Regel automatisch beschränkt. Verwenden Sie diese Funktion, um zu bestimmen, ob der Benutzer einen Bildlauf außerhalb des sichtbaren Bereichs des Dokuments durchgeführt wurde; Wenn dies der Fall ist, führen Sie einen Bildlauf Containerdokument nach Bedarf durch einen Aufruf von [ScrollContainerBy](#scrollcontainerby).  
  
##  <a name="getitemposition"></a>  COleServerDoc::GetItemPosition  
 Rufen Sie die `GetItemPosition` Member-Funktion zum Abrufen der Koordinaten des Elements an Stelle bearbeitet wird.  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpPosRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das die Koordinaten des Elements zu erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zum Clientbereich im Container Anwendungsfenster angezeigt.  
  
 Position des Elements verglichen werden kann, mit der aktuellen Clippingrechteck, um den Umfang zu ermitteln, zu dem das Element sichtbar (oder nicht sichtbar) ist, auf dem Bildschirm.  
  
##  <a name="getzoomfactor"></a>  COleServerDoc::GetZoomFactor  
 Die `GetZoomFactor` Memberfunktion bestimmt den "Zoomfaktor" eines Elements, das für die direkte Bearbeitung aktiviert wurde.  
  
```  
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,  
    LPSIZE lpSizeDenom = NULL,  
    LPCRECT lpPosRect = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpSizeNum*  
 Zeiger auf ein Objekt der Klasse `CSize` , wird der Zoomfaktor Zähler aufnehmen. Kann **NULL**.  
  
 *lpSizeDenom*  
 Zeiger auf ein Objekt der Klasse `CSize` , wird der Zoomfaktor Nenner aufnehmen. Kann **NULL**.  
  
 *lpPosRect*  
 Zeiger auf ein Objekt der Klasse `CRect` , die neue Position des Elements beschreibt. Wenn dieses Argument **NULL**, der die Funktion verwendet die aktuelle Position des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Element aktiviert ist, für die direkte Bearbeitung und der Zoomfaktor wird als 100 % (1:1). andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Zoomfaktor in Pixel, ist der Anteil der Elementgröße in seiner aktuellen Umfang. Wenn die containeranwendung nicht das Element Block sein natürliche Wertebereich festgelegt hat (gemäß [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) verwendet wird.  
  
 Die Funktion setzt die ersten beiden Argumente auf Zähler und Nenner, der das Element "Zoomfaktor." Wenn das Element nicht direkt bearbeitet wird, wird die Funktion legt diese Argumente auf einen Standardwert von 100 % (oder 1:1) und gibt 0 (null) zurück. Weitere Informationen finden Sie im technischen Hinweis 40 [MFC/OLE direkte Größenanpassung und Zoomen](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
##  <a name="isdocobject"></a>  COleServerDoc::IsDocObject  
 Bestimmt, ob das Dokument DocObject ist.  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** ist das Dokument DocObject; andernfalls **"false"**.  
  
##  <a name="isembedded"></a>  COleServerDoc::IsEmbedded  
 Rufen Sie die `IsEmbedded` Member-Funktion, um zu bestimmen, ob das Dokument in einem Container eingebetteten Objekts darstellt.  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `COleServerDoc` Objekt ist ein Dokument, das ein Objekt handelt, in einem Container eingebettet ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Dokument aus einer Datei geladen wird nicht eingebettet werden, obwohl es durch eine Steuerelementcontainer-Anwendung als Link bearbeitet werden kann. Ein Dokument, das in einem Containerdokument eingebettet ist, gilt als eingebettet werden.  
  
##  <a name="isinplaceactive"></a>  COleServerDoc::IsInPlaceActive  
 Rufen Sie die `IsInPlaceActive` Memberfunktion zu bestimmen, ob das Element im aktiven Zustand direktes aktuell ist.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `COleServerDoc` Objekt aktiv ist erfüllt; andernfalls 0.  
  
##  <a name="notifychanged"></a>  COleServerDoc::NotifyChanged  
 Mit dieser Funktion können Sie benachrichtigen alle verknüpften Elemente, die verbunden werden, um das Dokument, das das Dokument geändert hat.  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion auf, nachdem der Benutzer einige globales Attribut z. B. die Dimensionen des Serverdokuments ändert. Wenn ein OLE-Element auf das Dokument mit einer automatischen Verknüpfung verknüpft ist, wird das Element aktualisiert, um die Änderungen wiederzugeben. In containeranwendungen, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
> [!NOTE]
>  Diese Funktion ist aus Gründen der Kompatibilität mit OLE-1. Neue Anwendungen sollten verwenden [UpdateAllItems](#updateallitems).  
  
##  <a name="notifyclosed"></a>  COleServerDoc::NotifyClosed  
 Rufen Sie diese Funktion, um den Container zu benachrichtigen, dass das Dokument geschlossen wurde.  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer den Befehl "Schließen" über das Menü Datei auswählt `NotifyClosed` wird aufgerufen, indem `COleServerDoc`der Implementierung von der [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) Memberfunktion. In containeranwendungen, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
##  <a name="notifyrename"></a>  COleServerDoc::NotifyRename  
 Mit dieser Funktion werden, nachdem der Benutzer das Serverdokument umbenannt.  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszNewName*  
 Zeiger auf eine Zeichenfolge, die den neuen Namen des Serverdokuments angibt; Dies ist in der Regel einen vollqualifizierten Pfad.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer den Befehl "Speichern als" über das Menü Datei auswählt `NotifyRename` wird aufgerufen, indem Sie `COleServerDoc`Implementierung der [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) Memberfunktion. Diese Funktion benachrichtigt die OLE-System-DLLs, die wiederum die Container zu benachrichtigen. In containeranwendungen, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
##  <a name="notifysaved"></a>  COleServerDoc::NotifySaved  
 Mit dieser Funktion werden, nachdem der Benutzer das Serverdokument speichert.  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer über das Menü Datei Befehls "Speichern" auswählt `NotifySaved` wird aufgerufen, für Sie von `COleServerDoc`der Implementierung von [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Diese Funktion benachrichtigt die OLE-System-DLLs, die wiederum die Container zu benachrichtigen. In containeranwendungen, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
##  <a name="onclose"></a>  COleServerDoc::OnClose  
 Vom Framework aufgerufen, wenn ein Container anfordert, dass die Serverdokument geschlossen werden.  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>Parameter  
 *dwCloseOption*  
 Ein Wert aus der Enumeration `OLECLOSE`. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `OLECLOSE_SAVEIFDIRTY` Die Datei wird gespeichert, wenn er geändert wurde.  
  
- `OLECLOSE_NOSAVE` Die Datei ist geschlossen, ohne gespeichert zu werden.  
  
- `OLECLOSE_PROMPTSAVE` Wenn die Datei geändert wurde, wird der Benutzer aufgefordert, zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft `CDocument::OnCloseDocument`.  
  
 Weitere Informationen und weitere Werte finden Sie unter [OLECLOSE](http://msdn.microsoft.com/library/windows/desktop/ms680623) im Windows SDK.  
  
##  <a name="ondeactivate"></a>  COleServerDoc::OnDeactivate  
 Vom Framework aufgerufen, wenn der Benutzer eine eingebettete oder verknüpfte Element deaktiviert, die derzeit in-Place aktiv ist.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion die containeranwendung-Benutzeroberfläche in seinen ursprünglichen Zustand wiederhergestellt, und zerstört alle Menüs und anderen Steuerelementen, die für die direkte Aktivierung erstellt wurden.  
  
 Die Statusinformationen zum Rückgängigmachen sollte unbedingt zu diesem Zeitpunkt freigegeben werden.  
  
 Weitere Informationen finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md)...  
  
##  <a name="ondeactivateui"></a>  COleServerDoc::OnDeactivateUI  
 Wird aufgerufen, wenn der Benutzer ein Element deaktiviert, die direkt aktiviert wurde.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Parameter  
 *bUndoable*  
 Gibt an, ob die Bearbeitung rückgängig gemacht werden können.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion stellt die Benutzeroberfläche der Steuerelementcontainer-Anwendung in den Originalzustand, Ausblenden von alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden wieder her.  
  
 Legt das Framework *bUndoable* auf **"false"**. Wenn der Server rückgängig unterstützt, und es wird ein Vorgang, der rückgängig gemacht werden kann, rufen Sie die Implementierung der Basisklasse mit *bUndoable* festgelegt **"true"**.  
  
##  <a name="ondocwindowactivate"></a>  COleServerDoc::OnDocWindowActivate  
 Das Framework ruft diese Funktion aktivieren oder Deaktivieren von einem Dokumentfenster für die direkte Bearbeitung.  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 *bActivate*  
 Gibt an, ob das Dokumentfenster ist aktiviert oder deaktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung entfernt oder die Frame-Ebene Benutzeroberflächenelemente nach Bedarf hinzugefügt. Überschreiben Sie diese Funktion, wenn Sie möchten zusätzliche Aktionen ausführen, wenn das Dokument, enthält das Element aktiviert oder deaktiviert ist.  
  
 Weitere Informationen finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md)...  
  
##  <a name="onexecolecmd"></a>  COleServerDoc::OnExecOleCmd  
 Das Framework ruft diese Funktion, um einen angegebenen Befehl ausführen oder Anzeigen der Hilfe für den Befehl.  
  
```  
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,  
    DWORD nCmdID,  
    DWORD nCmdExecOpt,  
    VARIANTARG* pvarargIn,  
    VARIANTARG* pvarargOut);
```  
  
### <a name="parameters"></a>Parameter  
 *pguidCmdGroup*  
 Ein Zeiger auf eine GUID, die eine Reihe von Befehlen identifiziert. Kann **NULL** an Standardeinstellung Befehlsgruppe.  
  
 *nCmdID*  
 Der auszuführende Befehl. Muss in der identifizierten Gruppe *PguidCmdGroup*.  
  
 *nCmdExecOut*  
 Die Methode das Objekt ausgeführt werden soll der Befehl, eine oder mehrere der folgenden Werte aus der **OLECMDEXECOPT** Enumeration:  
  
 **OLECMDEXECOPT_DODEFAULT**  
  
 **OLECMDEXECOPT_PROMPTUSER**  
  
 **OLECMDEXECOPT_DONTPROMPTUSER**  
  
 **OLECMDEXECOPT_SHOWHELP**  
  
 *pvarargIn*  
 Zeiger auf eine **VARIANTARG** mit Eingabeargumenten für den Befehl. Kann **NULL**.  
  
 *pvarargOut*  
 Zeiger auf eine **VARIANTARG** die Rückgabewerte für die Ausgabe des Befehls erhalten. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` Wenn erfolgreich, andernfalls einer der folgenden Fehlercodes:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Unerwarteter Fehler aufgetreten ist.|  
|**E_FAIL**|Fehler|  
|**E_NOTIMPL**|Gibt an MFC selbst sollten versuchen, übersetzen und verteilen den Befehl|  
|**OLECMDERR_E_UNKNOWNGROUP**|*PguidCmdGroup* nicht **NULL** aber nicht an eine Gruppe Befehl erkannt|  
|**OLECMDERR_E_NOTSUPPORTED**|*nCmdID* wird nicht als gültiger Befehl in der Gruppe erkannt *PguidCmdGroup*|  
|**OLECMDERR_DISABLED**|Der Befehl identifizierte *nCmdID* ist deaktiviert und kann nicht ausgeführt werden|  
|**OLECMDERR_NOHELP**|Aufrufer aufgefordert Hilfe zum Befehl "identifizierte" *nCmdID* , aber es ist keine Hilfe verfügbar|  
|**OLECMDERR_CANCELED**|Die Ausführung wurde vom Benutzer abgebrochen.|  
  
### <a name="remarks"></a>Hinweise  
 `COleCmdUI` kann verwendet werden, zum Aktivieren, aktualisieren und andere Eigenschaften des DocObject Benutzeroberflächenbefehlen festzulegen. Nachdem die Befehle initialisiert werden, können Sie sie mit ausführen `OnExecOleCmd`.  
  
 Das Framework Ruft die Funktion, bevor Sie versuchen, übersetzen und verteilen einen OLE-Dokument-Befehl. Sie müssen diese Funktion zum Behandeln von OLE-Dokument-Standardbefehle überschrieben, aber eine Überschreibung dieser Funktion müssen Sie angeben, sollten Sie eine eigene benutzerdefinierte Befehle zu behandeln oder Behandeln von Befehlen, die Parameter akzeptieren oder geben Ergebnisse zurück.  
  
 Die meisten Befehle verwenden Argumente oder Rückgabewerte nicht. Für die Mehrheit der Befehle kann der Aufrufer übergeben **NULL**s für *PvarargIn* und *PvarargOut*. Der Aufrufer kann für Befehle, die Eingabewerte zu erwarten, deklarieren und Initialisieren einer **VARIANTARG** Variable, und übergeben Sie einen Zeiger auf die Variable in *PvarargIn*. Für Befehle, die einen einzelnen Wert erfordern, das Argument gespeichert werden kann direkt in die **VARIANTARG** und an die Funktion übergeben. Mehrere Argumente verpackt werden müssen, in der **VARIANTARG** mithilfe einer der unterstützten Typen (z. B. `IDispatch` und **SAFEARRAY** ).  
  
 Auf ähnliche Weise bei einem Befehl Argumente den Aufrufer zurückgegeben wird erwartet, dass Deklarieren einer **VARIANTARG**, initialisieren Sie sie mit `VT_EMPTY`, und übergeben Sie die Adresse in *PvarargOut*. Wenn ein Befehl einen einzelnen Wert zurückgibt, kann das Objekt direkt im Wert speichern *PvarargOut*. Mehrere Ausgabewerte müssen folglich validierungsmodi verpackt werden die **VARIANTARG**.  
  
 Die basisklassenimplementierung dieser Funktion führt den **OLE_COMMAND_MAP** Strukturen, die den Befehlsziel und es wurde versucht, verteilen den Befehl aus, um einem entsprechenden Handler zugeordnet. Die basisklassenimplementierung funktioniert nur mit Befehlen, die keine Argumente akzeptieren oder Werte zurück. Wenn Sie Befehle zu behandeln, die Argumente annehmen oder Werte zurückgeben möchten, müssen Sie überschreiben diese Funktion und Arbeiten mit der *PvarargIn* und *PvarargOut* Parameter selbst.  
  
##  <a name="onframewindowactivate"></a>  COleServerDoc::OnFrameWindowActivate  
 Das Framework ruft diese Funktion auf, wenn Rahmenfenster der Steuerelementcontainer-Anwendung aktiviert oder deaktiviert ist.  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 *bActivate*  
 Gibt an, ob das Rahmenfenster aktiviert oder deaktiviert wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung bricht alle Hilfemodi zur das Rahmenfenster in möglicherweise ab. Überschreiben Sie diese Funktion, wenn Sie besondere Verarbeitung, wenn das Rahmenfenster aktiviert oder deaktiviert wird ausführen möchten.  
  
 Weitere Informationen finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md)...  
  
##  <a name="ongetembeddeditem"></a>  COleServerDoc::OnGetEmbeddedItem  
 Vom Framework aufgerufen, wenn eine Steuerelementcontainer-Anwendung aufruft, die Server-Anwendung erstellen oder bearbeiten ein eingebettetes Element.  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Element, das das gesamte Dokument darstellt; **NULL** bei fehlgeschlagenem Vorgang.  
  
### <a name="remarks"></a>Hinweise  
 Es ist keine Standardimplementierung vorhanden. Überschreiben Sie diese Funktion, um ein Element zurück, das das gesamte Dokument darstellt. Dieser Rückgabewert muss ein Objekt von einem `COleServerItem`-abgeleitete Klasse.  
  
##  <a name="onreactivateandundo"></a>  COleServerDoc::OnReactivateAndUndo  
 Das Framework ruft diese Funktion auf, wenn der Benutzer entscheidet, vorgenommenen ein Element, das in direkten aktiviert, geändert und anschließend deaktiviert wurde.  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung nichts außer Return **"false"** um einen Fehler anzugeben.  
  
 Überschreiben Sie diese Funktion, wenn Ihre Anwendung zum Rückgängigmachen unterstützt. In der Regel würden Sie die Rückgängig-Vorgang ausführen und dann aktivieren Sie das Element durch Aufrufen von `ActivateInPlace`. Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wurde, Aufrufen `COleClientItem::ReactivateAndUndo` bewirkt, dass diese Funktion aufgerufen werden.  
  
##  <a name="onresizeborder"></a>  COleServerDoc::OnResizeBorder  
 Das Framework ruft diese Funktion aus, wenn die containeranwendung Rahmenfenster Größe zu ändern.  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>Parameter  
 *lpRectBorder*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das die Koordinaten des Rahmens angibt.  
  
 *lpUIWindow*  
 Zeiger auf ein Objekt der Klasse **IOleInPlaceUIWindow** , die die aktuelle bearbeitungssitzung direktes besitzt.  
  
 *bFrame*  
 **"True"** Wenn *LpUIWindow* verweist auf die containeranwendung Rahmenfenster der obersten Ebene, oder **"false"** Wenn *LpUIWindow* verweist auf den Container der Anwendung auf Dokumentebene Rahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ändert die Größe und Symbolleisten und andere Benutzeroberflächenelemente in Übereinstimmung mit der Größe des neuen Fensters anpasst.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) im Windows SDK.  
  
 Dies ist eine erweiterte überschrieben.  
  
##  <a name="onsethostnames"></a>  COleServerDoc::OnSetHostNames  
 Vom Framework aufgerufen, wenn der Container legt fest oder die Hostnamen für dieses Dokument ändert.  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszHost*  
 Ein Zeiger auf eine Zeichenfolge, die den Namen der containeranwendung angibt.  
  
 *lpszHostObj*  
 Ein Zeiger auf eine Zeichenfolge, die Container-Namen für das Dokument angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ändert den Titel des Dokuments für alle Ansichten verweisen zu diesem Dokument.  
  
 Überschreiben Sie diese Funktion, wenn Ihre Anwendung die Titel mithilfe eines anderen Mechanismus festlegt.  
  
##  <a name="onsetitemrects"></a>  COleServerDoc::OnSetItemRects  
 Das Framework ruft diese Funktion, um das Rahmenfenster der direkte Bearbeitung in Steuerelementcontainer-Anwendung Rahmenfensters zu positionieren.  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Parameter  
 *lpPosRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das direkte Rahmenfenster Position relativ zum Clientbereich der Steuerelementcontainer-Anwendung angibt.  
  
 *lpClipRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das direkte Rahmenfenster Clippingrechteck relativ zum Clientbereich der Steuerelementcontainer-Anwendung angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um den Zoomfaktor der Ansicht, aktualisieren, bei Bedarf.  
  
 Diese Funktion wird in der Regel aufgerufen, als Antwort auf eine `RequestPositionChange` aufzurufen, obwohl es durch den Container an eine Position für das direkte Element änderungsanforderung zu einem beliebigen Zeitpunkt aufgerufen werden kann.  
  
##  <a name="onshowcontrolbars"></a>  COleServerDoc::OnShowControlBars  
 Das Framework ruft diese Funktion zum ein- oder Ausblenden der Serveranwendung Steuerleisten das Rahmenfenster identifizierte zugeordnet *pFrameWnd*.  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 *pFrameWnd*  
 Ein Zeiger auf das Rahmenfenster, deren Steuerleisten ausgeblendet oder angezeigt werden soll.  
  
 *bShow*  
 Bestimmt, ob die Steuerleisten angezeigt oder ausgeblendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung Listet alle Steuerleisten, die im Besitz dieses Rahmenfenster und blendet Sie aus oder zeigt diese.  
  
##  <a name="onshowdocument"></a>  COleServerDoc::OnShowDocument  
 Das Framework Ruft die `OnShowDocument` -Funktion, wenn die Serverdokument ausgeblendet oder angezeigt werden muss.  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 *bShow*  
 Gibt an, ob die Benutzeroberfläche für das Dokument oder ausgeblendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *bShow* ist **"true"**, die standardmäßige Implementierung aktiviert die Serveranwendung bei Bedarf, und bewirkt, dass die Container-Anwendung das Fenster einen Bildlauf durchführen, damit das Element sichtbar ist. Wenn *bShow* ist **"false"**, die standardmäßige Implementierung deaktiviert das Element durch einen Aufruf von `OnDeactivate`, zerstört, oder blendet Sie aus allen Rahmenfenster, die für das Dokument, mit Ausnahme des ersten erstellt wurden ein. Wenn die Dokumente nicht sichtbar bleiben, blendet die standardmäßige Implementierung die Serveranwendung aus.  
  
##  <a name="onupdatedocument"></a>  COleServerDoc::OnUpdateDocument  
 Beim Speichern eines Dokuments, die ein eingebettetes Element in einem Verbunddokument wird vom Framework aufgerufen.  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Dokument wurde erfolgreich aktualisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung Ruft die [COleServerDoc::NotifySaved](#notifysaved) und [COleServerDoc::SaveEmbedding](#saveembedding) Memberfunktionen dar, und klicken Sie dann das Dokument als sauber markiert. Überschreiben Sie diese Funktion, wenn Sie besondere Verarbeitung, wenn ein eingebettetes Element aktualisieren ausführen möchten.  
  
##  <a name="requestpositionchange"></a>  COleServerDoc::RequestPositionChange  
 Rufen Sie diese Memberfunktion zum Steuerelementcontainer-Anwendung, die Position des Elements geändert haben.  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>Parameter  
 *lpPosRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das neue Position des Elements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen (in Verbindung mit `UpdateAllItems`) Wenn die Daten in eine direkte aktive Element geändert hat. Nach diesem Aufruf der Container kann oder die Änderung kann nicht durch den Aufruf ausführen `OnSetItemRects`. Die resultierende Position möglicherweise andere als die angeforderte.  
  
##  <a name="saveembedding"></a>  COleServerDoc::SaveEmbedding  
 Mit dieser Funktion wird zum Teilen der Steuerelementcontainer-Anwendung zum Speichern des eingebetteten Objekts.  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird automatisch aufgerufen, von `OnUpdateDocument`. Beachten Sie, dass diese Funktion bewirkt, dass das Element, das auf dem Datenträger aktualisiert werden, damit sie in der Regel nur als Reaktion auf eine bestimmte Benutzeraktion aufgerufen wird.  
  
##  <a name="scrollcontainerby"></a>  COleServerDoc::ScrollContainerBy  
 Rufen Sie die `ScrollContainerBy` Member-Funktion, um den Betrag in Pixel Containerdokument Scrollen erkennbar `sizeScroll`.  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>Parameter  
 *sizeScroll*  
 Gibt an, wie weit Containerdokument Bildlauf durchgeführt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Positive Werte geben einen Bildlauf nach unten und rechts; negative Werte geben Sie einen Bildlauf nach oben und nach links an.  
  
##  <a name="updateallitems"></a>  COleServerDoc::UpdateAllItems  
 Mit dieser Funktion können Sie benachrichtigen alle verknüpften Elemente, die verbunden werden, um das Dokument, das das Dokument geändert hat.  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parameter  
 *pSender*  
 Zeiger auf das Element, das das Dokument geändert oder **NULL** Wenn alle Elemente aktualisiert werden.  
  
 *lHint*  
 Enthält Informationen über die Änderung.  
  
 *pHint*  
 Zeiger auf ein Objekt, das Informationen über die Änderung zu speichern.  
  
 *nDrawAspect*  
 Bestimmt, wie das Element, gezeichnet werden soll. Dies ist ein Wert aus der `DVASPECT` Enumeration. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT` Element wird so dargestellt, als eingebettetes Objekt in dessen Container angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL` Damit es in einem Browser angezeigt werden kann, wird in eine Darstellung "Miniaturansicht" Element gerendert.  
  
- `DVASPECT_ICON` Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT` Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufrufen, nachdem der Benutzer das Serverdokument ändert. Wenn ein OLE-Element auf das Dokument mit einer automatischen Verknüpfung verknüpft ist, wird das Element aktualisiert, um die Änderungen wiederzugeben. In containeranwendungen, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
 Diese Funktion ruft die `OnUpdate` Memberfunktion für jede Dokumentelemente außer dem sendenden Element, das Übergeben von *pHint*, *lHint*, und *nDrawAspect*. Verwenden Sie diese Parameter, um Informationen zu den Elementen zu den Änderungen an den das Dokument zu übergeben. Können Sie codieren, Informationen mit *lHint* oder definieren Sie eine `CObject`-abgeleitete Klasse zum Speichern von Informationen zu den Änderungen, und übergeben Sie ein Objekt der Klasse verwenden *pHint*. Überschreiben der `OnUpdate` Memberfunktion in Ihrem `COleServerItem`-abgeleitete Klasse zu optimieren, die Aktualisierung der einzelnen Elemente abhängig davon, ob deren Präsentation geändert hat.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [COleLinkingDoc-Klasse](../../mfc/reference/colelinkingdoc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)   
 [COleLinkingDoc-Klasse](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer-Klasse](../../mfc/reference/coletemplateserver-class.md)
