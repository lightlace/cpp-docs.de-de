---
title: COleServerDoc-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 67920590979c4b9bf3099e8c64c142aeb813b1ce
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851657"
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
|[COleServerDoc::ActivateDocObject](#activatedocobject)|Aktiviert das zugehörige DocObject-Dokument.|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|Wird das Dokument für direktes Editieren aktiviert.|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Deaktiviert die Benutzeroberfläche des Servers.|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|Verwirft die rückgängig-Statusinformationen.|  
|[COleServerDoc::GetClientSite](#getclientsite)|Ruft einen Zeiger auf die zugrunde liegende `IOleClientSite` Schnittstelle.|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Gibt einen Zeiger auf ein Element, das das gesamte Dokument darstellt.|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Gibt das aktuelle Auswahlrechteck für die direkte Bearbeitung zurück.|  
|[COleServerDoc::GetItemPosition](#getitemposition)|Gibt die aktuelle Positionsrechteck, relativ zum Clientbereich der Container-Anwendung, für die direkte Bearbeitung zurück.|  
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Gibt den Zoomfaktor in Pixel zurück.|  
|[COleServerDoc::IsDocObject](#isdocobject)|Bestimmt, ob das Dokument DocObject ist.|  
|[COleServerDoc::IsEmbedded](#isembedded)|Gibt an, ob das Dokument in einem Containerdokument eingebettete oder Ausführung eigenständig ist.|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Gibt TRUE zurück, wenn das Element direkt derzeit aktiviert ist.|  
|[COleServerDoc::NotifyChanged](#notifychanged)|Benachrichtigt Container, dass der Benutzer das Dokument geändert hat.|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|Benachrichtigt Container, dass der Benutzer das Dokument geschlossen wurde.|  
|[COleServerDoc::NotifyRename](#notifyrename)|Benachrichtigt Container, dass der Benutzer das Dokument umbenannt wurde.|  
|[COleServerDoc::NotifySaved](#notifysaved)|Benachrichtigt Container, dass der Benutzer das Dokument gespeichert wurde.|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|Vom Framework aufgerufen, wenn der Benutzer ein Element deaktiviert, das direkt aktiviert wurde.|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Wird aufgerufen, durch das Framework zum Zerstören von Steuerelementen und andere Elemente der Benutzeroberfläche für die direkte Aktivierung erstellt werden.|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Vom Framework aufgerufen, wenn der Frame-Dokumentfenster des Containers aktiviert oder deaktiviert wird.|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Wird von Framework aufgerufen, beim Ändern der Größe der containeranwendung Rahmenfenster oder Dokumentfenster.|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Wird aufgerufen, durch das Framework anzeigen oder Ausblenden des Schiebeleisten-Steuerelemente für direktes Editieren.|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Vom Framework aufgerufen, wenn ein Serverdokument, das ist ein eingebettetes Element Aktualisieren des Containers Kopie des Elements gespeichert wird, wird.|  
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Ändert die Position des direktes Bearbeitungsrahmens.|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|Teilt die Container-Anwendung zum Speichern des Dokuments.|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Der Container ein Bildlauf.|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|Benachrichtigt Container, dass der Benutzer das Dokument geändert hat.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Wird aufgerufen, durch das Framework um ein Rahmenfenster für direktes Editieren zu erstellen.|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Wird aufgerufen, durch das Framework zerstört ein Rahmenfenster für direktes Editieren.|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Überschreiben Sie diese Funktion zum Erstellen eines neuen `CDocObjectServer` Objekt aus, und um anzugeben, dass dieses Dokument einen DocObject-Container ist.|  
|[COleServerDoc::OnClose](#onclose)|Vom Framework aufgerufen, wenn ein Container zum Schließen des Dokuments anfordert.|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Führt den angegebenen Befehl aus, oder zeigt die Hilfe für den Befehl.|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Vom Framework aufgerufen, wenn das Rahmenfenster des Containers aktiviert oder deaktiviert wird.|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Wird aufgerufen, um das Abrufen einer `COleServerItem` , das Sie das gesamte Dokument darstellt, verwendet, um ein eingebettetes Element abzurufen. Die Implementierung erforderlich sind.|  
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Vom Framework aufgerufen, während der Bearbeitung des direktes vorgenommenen Änderungen rückgängig zu machen.|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Vom Framework aufgerufen, wenn ein Container, den Titel des Fensters für ein eingebettetes Objekt festlegt.|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Wird aufgerufen, durch das Framework das Rahmenfenster der direkten Bearbeitung im Fenster für die Container-Anwendung zu positionieren.|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|Wird aufgerufen, durch das Framework anzeigen oder Ausblenden des Dokuments.|  
  
## <a name="remarks"></a>Hinweise  
 Serverdokument darf [COleServerItem](../../mfc/reference/coleserveritem-class.md) Objekte, die die Serverschnittstelle zu eingebetteten oder verknüpften Elementen darstellen. Wenn eine Serveranwendung, die von einem Container so bearbeiten Sie ein eingebettetes Element gestartet wird, wird das Element als einen eigenen Serverdokument geladen. die `COleServerDoc` Objekt enthält nur eine `COleServerItem` -Objekt, das gesamte Dokument aus. Wenn eine Serveranwendung, die von einem Container so bearbeiten Sie ein verknüpftes Element gestartet wird, wird ein vorhandenes Dokument vom Datenträger geladen. ein Teil die Inhalte des Dokuments wird hervorgehoben, um das verknüpfte Element anzuzeigen.  
  
 `COleServerDoc` Objekte können auch Elemente enthalten die [COleClientItem](../../mfc/reference/coleclientitem-class.md) Klasse. Dadurch können Sie Container / Server-Anwendungen zu erstellen. Das Framework bietet Funktionen zum Speichern von ordnungsgemäß die `COleClientItem` Elemente bei der Wartung der `COleServerItem` Objekte.  
  
 Wenn Ihre Serveranwendung nicht Links unterstützt wird, enthält Serverdokument immer nur ein Serverelement, steht für das gesamte eingebetteten Objekt als ein Dokument. Wenn Ihre Serveranwendung Links unterstützt wird, müssen sie einen jedes Mal erstellen, die eine Auswahl in die Zwischenablage kopiert wird.  
  
 Verwendung von `COleServerDoc`, eine Klasse ableiten und Implementieren der [OnGetEmbeddedItem](#ongetembeddeditem) Memberfunktion, die Ihre Server zur Unterstützung von eingebetteten Elemente ermöglicht. Leiten Sie eine Klasse von `COleServerItem` implementieren die Elemente in Ihren Dokumenten und Zurückgeben von Objekten dieser Klasse von `OnGetEmbeddedItem`.  
  
 Zur Unterstützung von verknüpfter Elementen `COleServerDoc` bietet die [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) Member-Funktion. Können Sie die standardmäßige Implementierung verwenden oder ihn zu überschreiben, wenn Sie Ihre eigenen Verfahren zum Verwalten von Dokumentelemente verfügen.  
  
 Sie benötigen ein `COleServerDoc`-Klasse für jeden Servertyp dokumentieren Sie die Anwendung unterstützt. Z. B. wenn die Serveranwendung Arbeitsblätter und Diagramme unterstützt, benötigen Sie zwei `COleServerDoc`-abgeleiteten Klassen.  
  
 Weitere Informationen zu Servern, finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="activatedocobject"></a>  COleServerDoc::ActivateDocObject  
 Aktiviert das zugehörige DocObject-Dokument.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `COleServerDoc` aktive Dokumente (auch als DocObjects bezeichnet) wird nicht unterstützt. Zum Aktivieren dieser Unterstützung finden Sie unter [GetDocObjectServer](#getdocobjectserver) und Klasse [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).  
  
##  <a name="activateinplace"></a>  COleServerDoc::ActivateInPlace  
 Wird das Element für direktes Editieren aktiviert.  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL Wenn erfolgreich; andernfalls 0, die angibt, dass das Element vollständig geöffnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion führt alle Vorgänge, die für die direkte Aktivierung erforderlich. Erstellt ein in-Place-Frame-Fenster, wird aktiviert und Größen es auf das Element, werden freigegebene Menüs und andere Steuerelemente festgelegt, führt einen Bildlauf durch das Element in der Ansicht, und setzt den Fokus auf das direkte Rahmenfenster.  
  
 Diese Funktion wird aufgerufen, indem Sie die standardmäßige Implementierung des [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Rufen Sie diese Funktion, wenn Ihre Anwendung ein anderes Verb für die direkte Aktivierung (z. B. Wiedergabe) unterstützt.  
  
##  <a name="coleserverdoc"></a>  COleServerDoc::COleServerDoc  
 Erstellt eine `COleServerDoc` Objekt ohne Herstellen einer Verbindung mit der OLE-System-DLLs.  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) Kommunikation mit OLE zu öffnen. Bei Verwendung von [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) in Ihrer Anwendung `COleLinkingDoc::Register` heißt für Sie von `COleLinkingDoc`Implementierung von `OnNewDocument`, `OnOpenDocument`, und `OnSaveDocument`.  
  
##  <a name="createinplaceframe"></a>  COleServerDoc::CreateInPlaceFrame  
 Das Framework ruft diese Funktion, um ein Rahmenfenster für direktes Editieren zu erstellen.  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Zeiger auf die Container-Anwendung des übergeordneten Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den in-Place-Frame-Fensters, oder NULL, wenn dies nicht möglich.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung verwendet die in die Dokumentvorlage angegebenen Informationen zum Erstellen des Rahmens. Die Sicht, wird die erste Ansicht, die für das Dokument erstellt. In dieser Ansicht wird vorübergehend getrennt vom ursprünglichen Rahmen und an den neu erstellten Frame angefügt.  
  
 Dies ist ein fortschrittlicher überschreibbar.  
  
##  <a name="deactivateandundo"></a>  COleServerDoc::DeactivateAndUndo  
 Rufen Sie diese Funktion, wenn der Benutzer, rückgängig, die nach dem Aktivieren eines Elements, jedoch vor dem Bearbeiten auswählt und die Anwendung unterstützt rückgängig zu machen.  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben, das Aufrufen dieser Funktion bewirkt, dass [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) um aufgerufen werden, deaktiviert die Benutzeroberfläche des Servers.  
  
##  <a name="destroyinplaceframe"></a>  COleServerDoc::DestroyInPlaceFrame  
 Das Framework ruft diese Funktion, um ein direktes Rahmenfenster zu zerstören, und der Server Dokumentfenster für die Anwendung in den Zustand vor der Aktivierung des direktes zurückzusetzen.  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pFrameWnd*  
 Zeiger auf das direkte Rahmenfenster zerstört werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein fortschrittlicher überschreibbar.  
  
##  <a name="discardundostate"></a>  COleServerDoc::DiscardUndoState  
 Wenn der Benutzer einen Bearbeitungsvorgang ausgeführt wird, der nicht rückgängig gemacht werden kann, rufen Sie dieser Funktion können Sie die containeranwendung zum Verwerfen von Rückgängig-Zustandsinformationen zu erzwingen.  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird bereitgestellt, sodass Server, die zum Rückgängigmachen unterstützen Ressourcen freigegeben werden können, die andernfalls von Rückgängig-Statusinformationen genutzt werden würde, die nicht verwendet werden kann.  
  
##  <a name="getclientsite"></a>  COleServerDoc::GetClientSite  
 Ruft einen Zeiger auf die zugrunde liegende `IOleClientSite` Schnittstelle.  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft einen Zeiger auf die zugrunde liegende [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706) Schnittstelle.  
  
##  <a name="getdocobjectserver"></a>  COleServerDoc::GetDocObjectServer  
 Überschreiben Sie diese Funktion zum Erstellen eines neuen `CDocObjectServer` Element aus, und geben Sie einen Zeiger darauf zurück.  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>Parameter  
 *pDocSite*  
 Zeiger auf die `IOleDocumentSite` -Schnittstelle, die in diesem Dokument mit dem Server hergestellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CDocObjectServer`; NULL, wenn der Vorgang fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein DocObject-Server aktiviert ist, zeigt die Rückgabe von einer nicht-NULL-Zeiger an, dass der Client DocObjects unterstützen kann. Die Standardimplementierung gibt NULL zurück.  
  
 Eine typische Implementierung für ein Dokument, das DocObjects unterstützt, wird einfach Zuweisen eines neuen `CDocObjectServer` Objekt aus, und es an den Aufrufer zurückgeben. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="getembeddeditem"></a>  COleServerDoc::GetEmbeddedItem  
 Rufen Sie diese Funktion zum Abrufen eines Zeigers auf ein Element, das das gesamte Dokument darstellt.  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Element, das das gesamte Dokument darstellt; NULL, wenn der Vorgang fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Ruft [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), eine virtuelle Funktion mit keine Standardimplementierung.  
  
##  <a name="getitemcliprect"></a>  COleServerDoc::GetItemClipRect  
 Rufen Sie die `GetItemClipRect` Member-Funktion bei der Einrichtung die Auswahlrechteck Koordinaten des Elements, das gerade bearbeitet wird.  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpClipRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das die Auswahlrechteck Koordinaten des Elements zu erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zum Clientbereich der Anwendungsfenster Container.  
  
 Zeichnung soll nicht außerhalb der Auswahlrechteck ausgeführt werden. In der Regel ist die Zeichnung automatisch beschränkt. Verwenden Sie diese Funktion, um festzustellen, ob der Benutzer einen Bildlauf außerhalb des sichtbaren Bereichs des Dokuments durchgeführt hat; Wenn dies der Fall ist, führen Sie einen Bildlauf Containerdokument nach Bedarf durch einen Aufruf von [ScrollContainerBy](#scrollcontainerby).  
  
##  <a name="getitemposition"></a>  COleServerDoc::GetItemPosition  
 Rufen Sie die `GetItemPosition` Memberfunktion, um die Koordinaten des direktes bearbeiteten Elements abzurufen.  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpPosRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das die Koordinaten des Elements zu erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zum Clientbereich der Anwendungsfenster Container.  
  
 Der Position des Elements verglichen werden kann, mit dem aktuellen Clippingrechteck um den Umfang zu ermitteln, zu dem das Element ist (oder nicht sichtbar) auf dem Bildschirm.  
  
##  <a name="getzoomfactor"></a>  COleServerDoc::GetZoomFactor  
 Die `GetZoomFactor` Memberfunktion bestimmt den "Zoomfaktor" eines Elements, das für direktes Editieren aktiviert wurde.  
  
```  
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,  
    LPSIZE lpSizeDenom = NULL,  
    LPCRECT lpPosRect = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpSizeNum*  
 Zeiger auf ein Objekt der Klasse `CSize` , wird der Zoomfaktor Zähler aufnehmen. NULL kann sein.  
  
 *lpSizeDenom*  
 Zeiger auf ein Objekt der Klasse `CSize` , wird der Zoomfaktor Nenner aufnehmen. NULL kann sein.  
  
 *lpPosRect*  
 Zeiger auf ein Objekt der Klasse `CRect` , die neue Position des Elements beschreibt. Wenn dieses Argument NULL ist, verwendet die Funktion die aktuelle Position des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Element aktiviert ist, für die direkte Bearbeitung und der Zoomfaktor wird als 100 % (1:1). andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Zoomfaktor, in Pixel, ist der Anteil der die Größe des Elements in der aktuellen Umfang. Wenn die Container-Anwendung des Elements Block den natürlichen Umfang nicht festgelegt ist (gemäß [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) verwendet wird.  
  
 Die Funktion setzt die ersten zwei Argumente auf den Zähler und Nenner des Elements "Zoomfaktor." Wenn das Element nicht an Ort bearbeitet wird, wird die Funktion wird von diesen Argumenten auf einen Standardwert von 100 % (oder 1:1) und gibt NULL zurück. Weitere Informationen finden Sie unter technischer Hinweis 40 [MFC/OLE direkte Größenanpassung und Zoomen](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
##  <a name="isdocobject"></a>  COleServerDoc::IsDocObject  
 Bestimmt, ob das Dokument DocObject ist.  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Dokument DocObject. andernfalls "false".  
  
##  <a name="isembedded"></a>  COleServerDoc::IsEmbedded  
 Rufen Sie die `IsEmbedded` Memberfunktion, um zu bestimmen, ob das Dokument in einem Container eingebetteten Objekts darstellt.  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `COleServerDoc` Objekt ist ein Dokument, das ein Objekt darstellt. in einem Container eingebettet sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Dokument aus einer Datei geladen wird nicht eingebettet werden, obwohl es von einer containeranwendung als Link bearbeitet werden kann. Ein Dokument, das in einem Containerdokument eingebettet ist gilt, die eingebettet werden.  
  
##  <a name="isinplaceactive"></a>  COleServerDoc::IsInPlaceActive  
 Rufen Sie die `IsInPlaceActive` Member-Funktion, um zu bestimmen, ob das Element derzeit in den aktiven Status des direktes ist.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `COleServerDoc` Objekt aktiv ist vorhanden; andernfalls 0.  
  
##  <a name="notifychanged"></a>  COleServerDoc::NotifyChanged  
 Mit dieser Funktion können Sie benachrichtigen alle verknüpften Elemente, die verbunden werden, um das Dokument, das das Dokument geändert wurde.  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion auf, nachdem der Benutzer einige globales Attribut z. B. die Abmessungen des Serverdokuments ändert. Wenn ein OLE-Element mit der eine automatische Verknüpfung zum Dokument verknüpft ist, wird das Element aktualisiert, um die Änderungen widerzuspiegeln. In containeranwendungen, die mit der Microsoft Foundation Class-Library geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
> [!NOTE]
>  Diese Funktion ist aus Gründen der Kompatibilität mit OLE 1. Neue Anwendungen sollten verwenden [UpdateAllItems](#updateallitems).  
  
##  <a name="notifyclosed"></a>  COleServerDoc::NotifyClosed  
 Rufen Sie diese Funktion, um den Container zu benachrichtigen, dass das Dokument geschlossen wurde.  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer die Close-Befehl im Menü Datei auswählt `NotifyClosed` wird aufgerufen, indem `COleServerDoc`die Implementierung der [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) Member-Funktion. In containeranwendungen, die mit der Microsoft Foundation Class-Library geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
##  <a name="notifyrename"></a>  COleServerDoc::NotifyRename  
 Rufen Sie diese Funktion aus, nachdem der Benutzer das Serverdokument umbenennt.  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszNewName*  
 Zeiger auf eine Zeichenfolge, die den neuen Namen des Serverdokuments angibt; Dies ist normalerweise ein vollqualifizierter Pfad.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer den Befehl Speichern unter im Menü Datei auswählt `NotifyRename` wird aufgerufen, indem `COleServerDoc`die Implementierung der [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) Member-Funktion. Diese Funktion teilt die OLE-System-DLLs, die wiederum die Container mitteilen. In containeranwendungen, die mit der Microsoft Foundation Class-Library geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
##  <a name="notifysaved"></a>  COleServerDoc::NotifySaved  
 Rufen Sie diese Funktion aus, nachdem der Benutzer das Serverdokument speichert.  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer den Befehl "Speichern" klicken Sie im Menü "Datei" auswählt `NotifySaved` heißt für Sie von `COleServerDoc`Implementierung von [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Diese Funktion teilt die OLE-System-DLLs, die wiederum die Container mitteilen. In containeranwendungen, die mit der Microsoft Foundation Class-Library geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
##  <a name="onclose"></a>  COleServerDoc::OnClose  
 Vom Framework aufgerufen, wenn ein Container anfordert, dass der Server-Dokument geschlossen werden.  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>Parameter  
 *dwCloseOption*  
 Ein Wert aus der Enumeration OLECLOSE. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- OLECLOSE_SAVEIFDIRTY wird die Datei gespeichert, wenn es geändert wurde.  
  
- OLECLOSE_NOSAVE die Datei wird geschlossen, ohne gespeichert zu werden.  
  
- OLECLOSE_PROMPTSAVE, wenn die Datei geändert wurde, die der Benutzer wird aufgefordert, zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft `CDocument::OnCloseDocument`.  
  
 Weitere Informationen und weitere Werte finden Sie unter [OLECLOSE](http://msdn.microsoft.com/library/windows/desktop/ms680623) im Windows SDK.  
  
##  <a name="ondeactivate"></a>  COleServerDoc::OnDeactivate  
 Vom Framework aufgerufen, wenn der Benutzer ein eingebettetes oder verknüpftes Element deaktiviert, die derzeit direkt aktiv ist.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird die Benutzeroberfläche für die Container-Anwendung in seinen ursprünglichen Zustand wiederhergestellt, und löscht alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden.  
  
 Die rückgängig-Statusinformationen sollte an diesem Punkt bedingungslos freigegeben werden.  
  
 Weitere Informationen finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md)...  
  
##  <a name="ondeactivateui"></a>  COleServerDoc::OnDeactivateUI  
 Wird aufgerufen, wenn der Benutzer ein Element deaktiviert, das direkt aktiviert wurde.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Parameter  
 *bUndoable*  
 Gibt an, ob die Änderungen rückgängig gemacht werden können.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion stellt die Benutzeroberfläche für die Container-Anwendung auf den ursprünglichen Zustand, Ausblenden von alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden, wieder her.  
  
 Das Framework legt *bUndoable* auf "false". Wenn der Server rückgängig unterstützt, und es ist ein Vorgang, der nicht rückgängig gemacht werden kann, rufen Sie die Implementierung der Basisklasse mit *bUndoable* auf "true" festgelegt.  
  
##  <a name="ondocwindowactivate"></a>  COleServerDoc::OnDocWindowActivate  
 Das Framework ruft diese Funktion aktivieren oder deaktivieren ein Dokumentfenster für direktes Editieren.  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 *bActivate*  
 Gibt an, ob das Dokumentfenster aktiviert oder deaktiviert wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung entfernt oder die Frame-Ebene Elemente der Benutzeroberfläche nach Bedarf hinzugefügt. Überschreiben Sie diese Funktion, sollten Sie zusätzliche Aktionen ausführen, wenn das Dokument mit das Element aktiviert oder deaktiviert wird.  
  
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
 Ein Zeiger auf eine GUID, die eine Reihe von Befehlen identifiziert. NULL an, dass die Standard-Befehlsgruppe kann sein.  
  
 *nCmdID*  
 Der auszuführende Befehl. Muss in der Gruppe identifizierte *PguidCmdGroup*.  
  
 *nCmdExecOut*  
 Die Methode das Objekt sollte der Befehl, eine oder mehrere der folgenden Werte aus der Enumeration OLECMDEXECOPT ausführen:  
  
 OLECMDEXECOPT_DODEFAULT  
  
 OLECMDEXECOPT_PROMPTUSER  
  
 OLECMDEXECOPT_DONTPROMPTUSER  
  
 OLECMDEXECOPT_SHOWHELP  
  
 *pvarargIn*  
 Zeiger auf eine VARIANTARG, die Eingabeargumente für den Befehl enthält. NULL kann sein.  
  
 *pvarargOut*  
 Die Rückgabewerte für eine Zeiger auf eine VARIANTARG erhalten Sie die Ausgabe des Befehls. NULL kann sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn erfolgreich; andernfalls, eine der folgenden Fehlercodes:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|E_UNEXPECTED|Unerwarteter Fehler aufgetreten ist.|  
|E_FAIL|Fehler|  
|E_NOTIMPL|Gibt an MFC selbst sollten versuchen, zu übersetzen, und verteilen den Befehl|  
|OLECMDERR_E_UNKNOWNGROUP|*PguidCmdGroup* ungleich NULL ist, aber gibt keine bekannte Befehlsgruppe an|  
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* wird nicht als gültiger Befehl in der Gruppe erkannt *PguidCmdGroup*|  
|OLECMDERR_DISABLED|Der Befehl identifizierte *nCmdID* ist deaktiviert und kann nicht ausgeführt werden|  
|OLECMDERR_NOHELP|Aufrufer aufgefordert Hilfe zum Befehl "identifizierte" *nCmdID* , aber es ist keine Hilfe verfügbar|  
|OLECMDERR_CANCELED|Die Ausführung wurde vom Benutzer abgebrochen.|  
  
### <a name="remarks"></a>Hinweise  
 `COleCmdUI` kann verwendet werden, zu aktivieren, aktualisieren und Festlegen anderer Eigenschaften des DocObject Befehlen der Benutzeroberfläche. Nachdem die Befehle initialisiert werden, können Sie sie durch Ausführen `OnExecOleCmd`.  
  
 Das Framework Ruft die Funktion, bevor Sie versuchen, übersetzen und senden eine OLE-Befehl "Dokument". Müssen Sie nicht diese Funktion zur Verarbeitung der Standardbefehle für OLE-Dokument zu überschreiben. allerdings müssen Sie eine Außerkraftsetzung für diese Funktion angeben, wenn Sie Ihre eigenen benutzerdefinierten Befehle verarbeiten, oder behandeln Befehle, die Parameter akzeptieren oder Ergebnisse zurückgeben möchten.  
  
 Die meisten Befehle keine Argumente oder Werte zurückzugeben. Bei einem Großteil von Befehlen der Aufrufer kann NULL-Werte für *PvarargIn* und *PvarargOut*. Für Befehle, die Eingabewerte zu erwarten, der Aufrufer kann deklarieren und initialisieren eine VARIANTARG-Variable und übergeben Sie einen Zeiger auf die Variable in *PvarargIn*. Für Befehle, die einen einzelnen Wert erfordern, kann das Argument direkt in die VARIANTARG gespeichert und an die Funktion übergeben werden. Mehrere Argumente müssen innerhalb der mit einem der unterstützten Typen VARIANTARG verpackt werden (z. B. `IDispatch` und SAFEARRAY).  
  
 Wenn Argumente von einem Befehl wird erwartet, dass der Aufrufer eine VARIANTARG deklarieren zurückgegeben, initialisieren Sie es auf VT_EMPTY, und übergeben Sie die Adresse in *PvarargOut*. Wenn ein Befehl einen einzelnen Wert zurückgibt, kann das Objekt direkt im Wert speichern *PvarargOut*. Mehrere Ausgabewerte müssen auf irgendeine Weise für die VARIANTARG verpackt werden.  
  
 Die basisklassenimplementierung dieser Funktion wird Schritt für Schritt die OLE_COMMAND_MAP-Strukturen, die das Ziel des Befehls zugeordnet, und wiederholen Sie den Befehl aus, um ein entsprechender Handler zu senden. Die Implementierung der Basisklasse funktioniert nur mit Befehlen, die keine Argumente annehmen oder Werte zurück. Wenn Sie Befehle zu verarbeiten, die Argumente annehmen oder Werte zurückgeben möchten, müssen überschreiben Sie diese Funktion und Arbeiten mit der *PvarargIn* und *PvarargOut* Parameter selbst.  
  
##  <a name="onframewindowactivate"></a>  COleServerDoc::OnFrameWindowActivate  
 Das Framework ruft diese Funktion auf, wenn das Rahmenfenster der containeranwendung aktiviert oder deaktiviert wird.  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 *bActivate*  
 Gibt an, ob das Rahmenfenster aktiviert oder deaktiviert wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung bricht alle Hilfemodi, in denen das Rahmenfenster möglicherweise ab. Überschreiben Sie diese Funktion, sollten Sie durchführen, besondere Bearbeitung, wenn das Rahmenfenster aktiviert oder deaktiviert ist.  
  
 Weitere Informationen finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md)...  
  
##  <a name="ongetembeddeditem"></a>  COleServerDoc::OnGetEmbeddedItem  
 Vom Framework aufgerufen, wenn eine Container-Anwendung aufruft, die Server-Anwendung erstellen oder bearbeiten ein eingebettetes Element.  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Element, das das gesamte Dokument darstellt; NULL, wenn der Vorgang fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Es ist keine Standardimplementierung vorhanden. Sie müssen angeben, überschreiben diese Funktion, um ein Element zurückgeben, die das gesamte Dokument darstellt. Dieser Rückgabewert sollte es sich um ein Objekt von einem `COleServerItem`-abgeleitete Klasse.  
  
##  <a name="onreactivateandundo"></a>  COleServerDoc::OnReactivateAndUndo  
 Das Framework ruft diese Funktion auf, wenn der Benutzer auswählt, rückgängig machen von Änderungen an ein Element, das aktiviert wird, vorhanden, geändert und anschließend deaktiviert wurde.  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung nichts mit der Ausnahme zurückgegeben "false", um einen Fehler anzuzeigen.  
  
 Überschreiben Sie diese Funktion, wenn Ihre Anwendung zum Rückgängigmachen unterstützt. In der Regel würden Sie den Rückgängig-Vorgang ausführen und dann aktivieren Sie das Element durch Aufrufen von `ActivateInPlace`. Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wird, wird beim Aufrufen `COleClientItem::ReactivateAndUndo` bewirkt, dass diese Funktion aufgerufen werden.  
  
##  <a name="onresizeborder"></a>  COleServerDoc::OnResizeBorder  
 Das Framework ruft diese Funktion auf, wenn das Rahmenfenster der containeranwendung Größe zu ändern.  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>Parameter  
 *lpRectBorder*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das die Koordinaten des Rahmens angibt.  
  
 *lpUIWindow*  
 Zeiger auf ein Objekt der Klasse `IOleInPlaceUIWindow` , der die aktuelle bearbeitungssitzung des direktes besitzt.  
  
 *bFrame*  
 TRUE, wenn *LpUIWindow* verweist auf der Container-Anwendung Rahmenfenster der obersten Ebene oder "false", wenn *LpUIWindow* verweist auf Dokumentebene-Rahmenfenster der containeranwendung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ändert die Größe und passt Symbolleisten und andere Elemente der Benutzeroberfläche in Übereinstimmung mit der neuen Fenstergröße.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) im Windows SDK.  
  
 Dies ist ein fortschrittlicher überschreibbar.  
  
##  <a name="onsethostnames"></a>  COleServerDoc::OnSetHostNames  
 Vom Framework aufgerufen, wenn der Container legt fest oder die Hostnamen für dieses Dokument ändert.  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszHost*  
 Zeiger auf eine Zeichenfolge, die den Namen der Container-Anwendung angibt.  
  
 *lpszHostObj*  
 Zeiger auf eine Zeichenfolge, die Namen des Containers, für das Dokument angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ändert den Titel des Dokuments für alle Ansichten, die in diesem Dokument auf.  
  
 Überschreiben Sie diese Funktion aus, wenn Ihre Anwendung mithilfe eines anderen Mechanismus Titel legt diese fest.  
  
##  <a name="onsetitemrects"></a>  COleServerDoc::OnSetItemRects  
 Das Framework ruft diese Funktion, um das Rahmenfenster der direkten Bearbeitung in Rahmenfenster der containeranwendung zu positionieren.  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Parameter  
 *lpPosRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das für ein direktes Rahmenfenster Position relativ zum Clientbereich der containeranwendung angibt.  
  
 *lpClipRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das Auswahlrechteck für das direkte Rahmenfenster relativ zum Clientbereich der containeranwendung angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um den Zoomfaktor der Ansicht, aktualisieren, wenn erforderlich.  
  
 Diese Funktion heißt in der Regel als Reaktion auf eine `RequestPositionChange` aufzurufen, obwohl sie jederzeit vom Container zum Anfordern einer positionsänderung für das direkte-Element aufgerufen werden kann.  
  
##  <a name="onshowcontrolbars"></a>  COleServerDoc::OnShowControlBars  
 Das Framework ruft diese Funktion zum Anzeigen oder Ausblenden der Serveranwendung Schiebeleisten-Steuerelemente das Rahmenfenster identifizierte zugeordnet *pFrameWnd*.  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 *pFrameWnd*  
 Zeiger auf das Rahmenfenster, deren Steuerleisten ausgeblendet oder angezeigt werden soll.  
  
 *bShow*  
 Bestimmt, ob die Steuerleisten angezeigt oder ausgeblendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung Listet alle Schiebeleisten-Steuerelemente im Besitz dieses Rahmenfenster und blendet Sie aus oder zeigt diese.  
  
##  <a name="onshowdocument"></a>  COleServerDoc::OnShowDocument  
 Das Framework Ruft die `OnShowDocument` funktionieren, wenn das Serverdokument ausgeblendet oder angezeigt werden muss.  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 *bShow*  
 Gibt an, ob die Benutzeroberfläche des Dokuments angezeigt oder ausgeblendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *bShow* ist "true", die standardmäßige Implementierung der Serveranwendung, aktiviert, falls erforderlich, und führt dazu, dass die Container-Anwendung, um das Fenster scrollen, damit das Element sichtbar ist. Wenn *bShow* ist "false", die standardmäßige Implementierung deaktiviert das Element durch einen Aufruf von `OnDeactivate`, und zerstört, oder blendet alle Rahmenfenster, die für das Dokument, mit Ausnahme des ersten erstellt wurden. Wenn keine Dokumente sichtbar bleiben, blendet die standardmäßige Implementierung die Serveranwendung aus.  
  
##  <a name="onupdatedocument"></a>  COleServerDoc::OnUpdateDocument  
 Vom Framework aufgerufen, wenn ein Dokument gespeichert, die ein eingebettetes Element in einem Verbunddokument ist.  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Dokument wurde erfolgreich aktualisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung Ruft die [COleServerDoc::NotifySaved](#notifysaved) und [COleServerDoc::SaveEmbedding](#saveembedding) Member-Funktionen und markiert anschließend das Dokument als bereinigen. Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung bei der Aktualisierung eines eingebetteten Elements ausführen möchten.  
  
##  <a name="requestpositionchange"></a>  COleServerDoc::RequestPositionChange  
 Rufen Sie diese Memberfunktion, um die Container-Anwendung, die der Position des Elements zu ändern.  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>Parameter  
 *lpPosRect*  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das neue Position des Elements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen (in Verbindung mit `UpdateAllItems`) Wenn die Daten in ein direktes aktives Element geändert hat. Nach diesem Aufruf ist der Container kann, oder kann nicht ausgeführt werden, die Änderung durch den Aufruf `OnSetItemRects`. Die resultierende Position möglicherweise anderen angefordert.  
  
##  <a name="saveembedding"></a>  COleServerDoc::SaveEmbedding  
 Mit dieser Funktion können Sie teilen Sie die Container-Anwendung, um das eingebettete Objekt zu speichern.  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird automatisch aufgerufen, von `OnUpdateDocument`. Beachten Sie, dass diese Funktion führt dazu, dass das Element, das auf dem Datenträger aktualisiert werden, damit sie in der Regel nur als Reaktion auf eine bestimmte Benutzeraktion aufgerufen wird.  
  
##  <a name="scrollcontainerby"></a>  COleServerDoc::ScrollContainerBy  
 Rufen Sie die `ScrollContainerBy` Memberfunktion Containerdokument Scrollen Sie durch die Menge, in Pixel angegeben werden, durch `sizeScroll`.  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>Parameter  
 *sizeScroll*  
 Gibt an, wie weit ist auf das Containerdokument einen Bildlauf durchführen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Positive Werte geben an, einen Bildlauf nach unten und nach rechts; negative Werte geben an, ein diagonaler Bildlauf nach oben auf der linken Seite.  
  
##  <a name="updateallitems"></a>  COleServerDoc::UpdateAllItems  
 Mit dieser Funktion können Sie benachrichtigen alle verknüpften Elemente, die verbunden werden, um das Dokument, das das Dokument geändert wurde.  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parameter  
 *pSender*  
 Zeiger auf das Element, das das Dokument, geändert oder NULL, wenn alle Elemente sind, aktualisiert werden.  
  
 *lHint*  
 Enthält Informationen über die Änderung.  
  
 *pHint*  
 Zeiger auf ein Objekt, das Informationen über die Änderung zu speichern.  
  
 *nDrawAspect*  
 Bestimmt, wie das Element gezeichnet werden soll. Dies ist ein Wert aus der DVASPECT-Enumeration. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- DVASPECT_CONTENT-Element wird so dargestellt, dass es als eingebettetes Objekt in dessen Container angezeigt werden kann.  
  
- DVASPECT_THUMBNAIL-Element wird in eine "Miniaturansicht" Darstellung gerendert, damit es in einem Browser angezeigt werden kann.  
  
- DVASPECT_ICON-Element wird durch ein Symbol dargestellt.  
  
- DVASPECT_DOCPRINT-Element dargestellt, als würde es mit dem Befehl "Drucken" über das Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion nach dem der Benutzer das Serverdokument ändert. Wenn ein OLE-Element mit der eine automatische Verknüpfung zum Dokument verknüpft ist, wird das Element aktualisiert, um die Änderungen widerzuspiegeln. In containeranwendungen, die mit der Microsoft Foundation Class-Library geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
 Diese Funktion ruft die `OnUpdate` Member-Funktion für jedes der Elemente des Dokuments ab, mit Ausnahme von Element übergeben, der das Senden *pHint*, *lHint*, und *nDrawAspect*. Verwenden Sie diese Parameter, um Informationen zu den Elementen zu den Änderungen auf das Dokument zu übergeben. Können Sie codieren, Informationen mit *lHint* oder Definieren einer `CObject`-abgeleitete Klasse zum Speichern von Informationen zu den Änderungen, und übergeben Sie ein Objekt dieser Klasse mit *pHint*. Überschreiben der `OnUpdate` Member-Funktion in Ihrer `COleServerItem`-abgeleitete Klasse, um die Aktualisierung der einzelnen Elemente, abhängig davon, ob dessen Darstellung geändert zu optimieren.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [COleLinkingDoc-Klasse](../../mfc/reference/colelinkingdoc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)   
 [COleLinkingDoc-Klasse](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer-Klasse](../../mfc/reference/coletemplateserver-class.md)
