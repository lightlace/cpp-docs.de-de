---
title: COleServerDoc Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- servers, OLE
- OLE server applications, managing server documents
- container/server applications
- OLE server documents
- COleServerDoc class
- server documents, OLE
- OLE containers, server documents
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
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
ms.openlocfilehash: db50c2a5709fbc07d0e0db99a4cffc733c4b6ead
ms.lasthandoff: 02/24/2017

---
# <a name="coleserverdoc-class"></a>COleServerDoc-Klasse
Die Basisklasse für OLE-Serverdokumente.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](#coleserverdoc)|Erstellt ein `COleServerDoc`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](#activatedocobject)|Aktiviert das zugehörige DocObject-Dokument.|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|Wird das Dokument für die direkte Bearbeitung aktiviert.|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Deaktiviert das Server-Benutzeroberfläche.|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|Verwirft die rückgängig-Statusinformationen.|  
|[COleServerDoc::GetClientSite](#getclientsite)|Ruft einen Zeiger auf die zugrunde liegende `IOleClientSite` Schnittstelle.|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Gibt einen Zeiger auf ein Element, das gesamte Dokument darstellt.|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Gibt das aktuelle Auswahlrechteck für die direkte Bearbeitung.|  
|[COleServerDoc::GetItemPosition](#getitemposition)|Gibt die aktuelle Positionsrechteck relativ zum Clientbereich der Container-Anwendung, für die direkte Bearbeitung.|  
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Gibt den Zoomfaktor in Pixel zurück.|  
|[COleServerDoc::IsDocObject](#isdocobject)|Bestimmt, ob das Dokument DocObject ist.|  
|[COleServerDoc::IsEmbedded](#isembedded)|Gibt an, ob das Dokument in ein anderes Dokument eingebettet oder laufenden eigenständig ist.|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Gibt `TRUE` , wenn das Element derzeit direkt aktiviert wird.|  
|[COleServerDoc::NotifyChanged](#notifychanged)|Benachrichtigt Container, dass der Benutzer das Dokument geändert hat.|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|Benachrichtigt Container, dass der Benutzer das Dokument geschlossen wurde.|  
|[COleServerDoc::NotifyRename](#notifyrename)|Benachrichtigt Container, dass der Benutzer das Dokument umbenannt wurde.|  
|[COleServerDoc::NotifySaved](#notifysaved)|Benachrichtigt Container, der Benutzer das Dokument gespeichert wurde.|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|Wird vom Framework aufgerufen, wenn der Benutzer ein Element deaktiviert, das direkt aktiviert wurde.|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Vom Framework aufgerufen wird, Steuerelemente und andere Elemente der Benutzeroberfläche für die direkte Aktivierung erstellt zu zerstören.|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Wird vom Framework aufgerufen, wenn der Container Dokumentrahmenfenster aktiviert oder deaktiviert wird.|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Wird vom Framework aufgerufen, wenn Rahmenfenster der Container-Anwendungsverzeichnis oder ein Dokumentfenster geändert wird.|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Vom Framework aufgerufen wird, ein- oder Ausblenden der Steuerleisten für die direkte Bearbeitung.|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Wenn ein Serverdokument, das ist ein eingebettetes Element Aktualisieren des Containers Kopie des Elements gespeichert wird, vom Framework aufgerufen.|  
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Ändert die Position des Bearbeitungsrahmens an.|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|Der die containeranwendung zum Speichern des Dokuments informiert.|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Der Container ein Bildlauf.|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|Benachrichtigt Container, dass der Benutzer das Dokument geändert hat.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Vom Framework zum Erstellen eines Rahmenfensters für die direkte Bearbeitung aufgerufen.|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Vom Framework aufgerufen wird, zerstören ein Rahmenfensters für die direkte Bearbeitung.|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Überschreiben Sie diese Funktion zum Erstellen eines neuen `CDocObjectServer` -Objekt und anzugeben, dass dieses Dokument ein DocObject-Container ist.|  
|[COleServerDoc::OnClose](#onclose)|Vom Framework aufgerufen, wenn ein Container zum Schließen des Dokuments anfordert.|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Führt einen angegebenen Befehl aus oder zeigt die Hilfe für den Befehl.|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Vom Framework aufgerufen, wenn der Container Rahmenfenster aktiviert oder deaktiviert wird.|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Wird aufgerufen, um das Abrufen einer `COleServerItem` , das Sie das gesamte Dokument darstellt, verwendet, um ein eingebettetes Element abzurufen. Die Implementierung erforderlich sind.|  
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Vom Framework aufgerufen wird, während der direkten Bearbeitung vorgenommenen Änderungen rückgängig zu machen.|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Wird vom Framework aufgerufen, wenn ein Container legt den Fenstertitel für ein eingebettetes Objekt fest.|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Aufgerufen, um im in-Place-Frame Fenster in der Container-Anwendung zu positionieren.|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|Vom Framework aufgerufen wird, ein- oder Ausblenden des Dokuments.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Serverdokument kann enthalten [COleServerItem](../../mfc/reference/coleserveritem-class.md) Objekte, die die Server-Schnittstelle, die eingebettete oder verknüpfte Elemente darstellen. Wenn eine Anwendung von einem Container so bearbeiten Sie ein eingebettetes Element gestartet wird, wird das Element als eigene Server-Dokument geladen. die `COleServerDoc` Objekt enthält nur ein `COleServerItem` -Objekt, das gesamte Dokument aus. Wenn eine Anwendung von einem Container so bearbeiten Sie ein verknüpftes Element gestartet wird, wird ein vorhandenes Dokument vom Datenträger geladen. ein Teil des Inhalts des Dokuments wird hervorgehoben, um anzugeben, dass das verknüpfte Element.  
  
 `COleServerDoc`-Objekte können auch Elemente enthalten, die [COleClientItem](../../mfc/reference/coleclientitem-class.md) Klasse. Dadurch können Sie die Container-Server-Anwendung zu erstellen. Das Framework bietet Funktionen zum Speichern von ordnungsgemäß der `COleClientItem` Elemente während der Wartung der `COleServerItem` Objekte.  
  
 Wenn die Server-Anwendung Links nicht unterstützt, enthält Serverdokument immer nur ein Serverelement, das gesamte eingebetteten Objekts als Dokument darstellt. Wenn die Server-Anwendung Links unterstützt wird, müssen sie ein Serverelement jedes Mal erstellen, wenn eine Auswahl in die Zwischenablage kopiert wird.  
  
 Mit `COleServerDoc`, eine Klasse ableiten und Implementieren der [OnGetEmbeddedItem](#ongetembeddeditem) Memberfunktion, die der Server zur Unterstützung von eingebetteten Elemente zulässt. Leiten Sie eine Klasse von `COleServerItem` die Elemente in Ihren Dokumenten implementieren und Zurückgeben von Objekten dieser Klasse von `OnGetEmbeddedItem`.  
  
 Zur Unterstützung der verknüpften Elemente `COleServerDoc` bietet die [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) Member-Funktion. Die standardmäßige Implementierung verwenden können oder, wenn Sie eine eigene Methode zum Verwalten von Dokumentelemente haben überschreiben.  
  
 Sie benötigen ein `COleServerDoc`-abgeleitete Klasse für jeden Servertyp Dokument, die die Anwendung unterstützt. Zum Beispiel wenn die Server-Anwendung Arbeitsblätter und Diagramme unterstützt, benötigen Sie zwei `COleServerDoc`-abgeleitete Klassen.  
  
 Weitere Informationen zu Servern finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="activatedocobject"></a>COleServerDoc::ActivateDocObject  
 Aktiviert das zugehörige DocObject-Dokument.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `COleServerDoc` aktive Dokumente (auch als DocObjects bezeichnet) nicht unterstützt. Zum Aktivieren dieser Unterstützung finden Sie unter [GetDocObjectServer](#getdocobjectserver) und [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).  
  
##  <a name="activateinplace"></a>COleServerDoc::ActivateInPlace  
 Aktiviert das Element für die direkte Bearbeitung.  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0, die angibt, dass das Element vollständig geöffnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion führt alle Vorgänge für die direkte Aktivierung erforderlich. Es erstellt ein in-Place-Frame-Fenster, aktiviert und Größe für das Element, richtet freigegebene Menüs und andere Steuerelemente, verschiebt das Element in der Ansicht und setzt den Fokus auf das direkte Rahmenfenster.  
  
 Diese Funktion wird aufgerufen, durch die standardmäßige Implementierung des [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Rufen Sie diese Funktion, wenn Ihre Anwendung ein anderes Verb für die direkte Aktivierung (z. B. Wiedergabe) unterstützt.  
  
##  <a name="coleserverdoc"></a>COleServerDoc::COleServerDoc  
 Erstellt ein `COleServerDoc` Objekt ohne Herstellen einer Verbindung mit der OLE-System-DLLs.  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) Kommunikation mit OLE zu öffnen. Bei Verwendung von [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) in Ihrer Anwendung `COleLinkingDoc::Register` heißt vom `COleLinkingDoc`der Implementierung von `OnNewDocument`, `OnOpenDocument`, und `OnSaveDocument`.  
  
##  <a name="createinplaceframe"></a>COleServerDoc::CreateInPlaceFrame  
 Das Framework ruft diese Funktion zum Erstellen eines Rahmenfensters für die direkte Bearbeitung.  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Zeiger auf die containeranwendung übergeordnetes Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das direkte Rahmenfenster oder **NULL** gelingt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung verwendet in der Dokumentvorlage angegebenen Informationen zum Erstellen des Rahmens. Die Ansicht, ist die erste Ansicht, die für das Dokument erstellt wurde. In dieser Ansicht wird vorübergehend getrennt vom ursprünglichen Rahmen und auf den neu erstellten Frame angefügt.  
  
 Dies ist eine erweiterte überschrieben.  
  
##  <a name="deactivateandundo"></a>COleServerDoc::DeactivateAndUndo  
 Rufen Sie diese Funktion, wenn die Anwendung unterstützt rückgängig zu machen, und der Benutzer "Rückgängig wählt" nach dem Aktivieren eines Elements, jedoch vor dem Bearbeiten.  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Container-Anwendung mithilfe der Microsoft Foundation Class-Bibliothek geschrieben, das Aufrufen dieser Funktion bewirkt, dass [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) um aufgerufen werden, die Benutzeroberfläche des Servers deaktiviert.  
  
##  <a name="destroyinplaceframe"></a>COleServerDoc::DestroyInPlaceFrame  
 Das Framework ruft diese Funktion, um eine direkte Rahmenfenster zerstört und wieder den Server Anwendung Dokumentfenster seinen Zustand vor-Ort-Aktivierung.  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pFrameWnd`  
 Ein Zeiger auf das direkte Rahmenfenster zerstört werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine erweiterte überschrieben.  
  
##  <a name="discardundostate"></a>COleServerDoc::DiscardUndoState  
 Wenn der Benutzer einen Bearbeitungsvorgang, der rückgängig gemacht werden kann ausführt, rufen Sie diese Funktion zum Erzwingen der Container-Anwendung, die rückgängig-Zustandsinformationen zu verwerfen.  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird bereitgestellt, sodass Server, rückgängig unterstützen, Ressourcen freigegeben werden können, die andernfalls von Rückgängig-Statusinformationen genutzt würde, die verwendet werden kann.  
  
##  <a name="getclientsite"></a>COleServerDoc::GetClientSite  
 Ruft einen Zeiger auf die zugrunde liegende `IOleClientSite` Schnittstelle.  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft einen Zeiger auf die zugrunde liegende [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706) Schnittstelle.  
  
##  <a name="getdocobjectserver"></a>COleServerDoc::GetDocObjectServer  
 Überschreiben Sie diese Funktion zum Erstellen eines neuen `CDocObjectServer` Element und einen Zeiger darauf zurückgeben.  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>Parameter  
 `pDocSite`  
 Zeiger auf die `IOleDocumentSite` -Schnittstelle, die diesem Dokument mit dem Server hergestellt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CDocObjectServer`; **NULL** , wenn der Vorgang fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein DocObject-Server aktiviert ist, die Rückgabe von nicht **NULL** Zeiger zeigt, dass der Client DocObjects unterstützen kann. Die standardmäßige Implementierung gibt **NULL**.  
  
 Eine typische Implementierung für ein Dokument, das DocObjects unterstützt einfach Zuweisen eines neuen `CDocObjectServer` -Objekt und an den Aufrufer zurückgeben. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCOleServer&3;](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="getembeddeditem"></a>COleServerDoc::GetEmbeddedItem  
 Rufen Sie diese Funktion zum Abrufen eines Zeigers auf ein Element, das gesamte Dokument darstellt.  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Element, das gesamte Dokument darstellt; **NULL** , wenn der Vorgang fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Sie ruft [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), eine virtuelle Funktion ohne Standard-Implementierung.  
  
##  <a name="getitemcliprect"></a>COleServerDoc::GetItemClipRect  
 Rufen Sie die `GetItemClipRect` Memberfunktion, die bei der Einrichtung der Auswahlrechteck Koordinaten des Elements, das gerade bearbeitet wird.  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpClipRect`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das die Auswahlrechteck Koordinaten des Elements zu erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten sind relativ zum Clientbereich des Anwendungsfensters die Container in Pixel.  
  
 Zeichnung sollte nicht außerhalb der Auswahlrechteck auftreten. In der Regel ist die Zeichnung automatisch eingeschränkt. Verwenden Sie diese Funktion, um festzustellen, ob der Benutzer einen Bildlauf außerhalb des sichtbaren Bereichs des Dokuments durchgeführt hat; In diesem Fall das Containerdokument Bedarf Blättern durch einen Aufruf von [ScrollContainerBy](#scrollcontainerby).  
  
##  <a name="getitemposition"></a>COleServerDoc::GetItemPosition  
 Rufen Sie die `GetItemPosition` -Memberfunktion, die Koordinaten der zu bearbeitenden an Ort abgerufen.  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpPosRect`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das die Koordinaten des Elements zu erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten sind relativ zum Clientbereich des Anwendungsfensters die Container in Pixel.  
  
 Der Position des Elements verglichen werden kann, mit das aktuelle Auswahlrechteck, um den Umfang zu ermitteln, der das Element ist (oder nicht sichtbar) auf dem Bildschirm.  
  
##  <a name="getzoomfactor"></a>COleServerDoc::GetZoomFactor  
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
  
 `lpPosRect`  
 Zeiger auf ein Objekt der Klasse `CRect` , die neue Position des Elements beschreibt. Wenn dieses Argument **NULL**, verwendet die Funktion die aktuelle Position des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Element aktiviert ist, für die direkte Bearbeitung und den Zoomfaktor ist als 100 % (1:1). andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Zoomfaktor in Pixel ist der Anteil von die Größe des Elements in der aktuellen Umfang. Wenn die Container-Anwendung des Artikels Umfang seiner natürlichen Ausdehnung nicht festgelegt wurde (laut [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) verwendet wird.  
  
 Die Funktion setzt die ersten beiden Argumente auf den Zähler und Nenner des Artikels "Zoomfaktor." Wenn das Element nicht direkt bearbeitet wird, wird die Funktion legt diese Argumente auf einen Standardwert von 100 % (oder 1:1) und gibt 0 (null) zurück. Weitere Informationen finden Sie unter Technische Hinweis 40, [MFC/OLE direkte Größenanpassung und Zoomen](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
##  <a name="isdocobject"></a>COleServerDoc::IsDocObject  
 Bestimmt, ob das Dokument DocObject ist.  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** ist das Dokument DocObject; andernfalls **FALSE**.  
  
##  <a name="isembedded"></a>COleServerDoc::IsEmbedded  
 Rufen Sie die `IsEmbedded` Member-Funktion, um festzustellen, ob das Dokument in einem Container eingebetteten Objekts darstellt.  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `COleServerDoc` -Objekt ist ein Dokument, das ein Objekt darstellt, in einem Container eingebettet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Dokument aus einer Datei geladen wird nicht eingebettet werden, obwohl es durch eine Container-Anwendung als Link geändert werden kann. Ein Dokument, das in ein anderes Dokument eingebettet ist, gilt als eingebettet werden.  
  
##  <a name="isinplaceactive"></a>COleServerDoc::IsInPlaceActive  
 Rufen Sie die `IsInPlaceActive` Member-Funktion, um zu bestimmen, ob das Element derzeit im aktiven Zustand an.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `COleServerDoc` Objekt aktiv ist vorhanden; andernfalls 0.  
  
##  <a name="notifychanged"></a>COleServerDoc::NotifyChanged  
 Rufen Sie diese Funktion, um benachrichtigt zu werden alle verknüpften Elemente, die Verbindung mit dem Dokument, das das Dokument geändert wurde.  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion auf, nachdem der Benutzer einige globales Attribut z. B. die Dimensionen des Serverdokuments ändert. Wenn ein OLE-Element mit automatischen Verknüpfung mit dem Dokument verknüpft ist, wird das Element die Änderungen entsprechend aktualisiert. In Container-Anwendung, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
> [!NOTE]
>  Diese Funktion ist für die Kompatibilität mit OLE 1 enthalten. Neue Anwendungen sollten verwenden [UpdateAllItems](#updateallitems).  
  
##  <a name="notifyclosed"></a>COleServerDoc::NotifyClosed  
 Rufen Sie diese Funktion, um den Container zu benachrichtigen, dass das Dokument geschlossen wurde.  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer den Befehl Schließen im Menü Datei `NotifyClosed` wird aufgerufen, indem `COleServerDoc`Implementierung der [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) Member-Funktion. In Container-Anwendung, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
##  <a name="notifyrename"></a>COleServerDoc::NotifyRename  
 Rufen Sie diese Funktion aus, nachdem der Benutzer das Serverdokument umbenennt.  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszNewName`  
 Zeiger auf eine Zeichenfolge, die den neuen Namen des Server-Dokument angibt; Dies ist i. d. r. ein vollqualifizierter Pfad.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer den Befehl Speichern unter im Menü Datei `NotifyRename` wird aufgerufen, indem `COleServerDoc`Implementierung der [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) Member-Funktion. Diese Funktion teilt die OLE-System-DLLs, die wiederum die Container zu benachrichtigen. In Container-Anwendung, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
##  <a name="notifysaved"></a>COleServerDoc::NotifySaved  
 Rufen Sie diese Funktion aus, nachdem der Benutzer das Serverdokument gespeichert.  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer den Befehl Speichern im Menü Datei `NotifySaved` heißt vom `COleServerDoc`der Implementierung von [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Diese Funktion teilt die OLE-System-DLLs, die wiederum die Container zu benachrichtigen. In Container-Anwendung, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
##  <a name="onclose"></a>COleServerDoc::OnClose  
 Wird vom Framework aufgerufen, wenn ein Container angefordert wird, dass der Server-Dokument geschlossen werden.  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCloseOption`  
 Ein Wert aus der Enumeration `OLECLOSE`. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `OLECLOSE_SAVEIFDIRTY`Die Datei wird gespeichert, wenn es geändert wurde.  
  
- `OLECLOSE_NOSAVE`Die Datei wird geschlossen, ohne gespeichert wird.  
  
- `OLECLOSE_PROMPTSAVE`Wenn die Datei geändert wurde, wird der Benutzer aufgefordert, zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft `CDocument::OnCloseDocument`.  
  
 Weitere Informationen und zusätzliche Werte finden Sie unter [OLECLOSE](http://msdn.microsoft.com/library/windows/desktop/ms680623) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondeactivate"></a>COleServerDoc::OnDeactivate  
 Wird vom Framework aufgerufen, wenn der Benutzer ein Element eingebettete oder verknüpfte deaktiviert, die derzeit in-Place aktiv ist.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird die Benutzeroberfläche der containeranwendung in seinen ursprünglichen Zustand wiederhergestellt und löscht alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden.  
  
 Informationen über den Zustand "Rückgängig" sollten unbedingt an diesem Punkt freigegeben werden.  
  
 Weitere Informationen finden Sie im Artikel [Activation](../../mfc/activation-cpp.md)...  
  
##  <a name="ondeactivateui"></a>COleServerDoc::OnDeactivateUI  
 Wird aufgerufen, wenn der Benutzer ein Element deaktiviert, das direkt aktiviert wurde.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Parameter  
 `bUndoable`  
 Gibt an, ob die Bearbeitung rückgängig gemacht werden können.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion stellt die Benutzeroberfläche der containeranwendung Originalzustand ausblenden alle Menüs und andere Steuerelemente, die für die direkte Aktivierung erstellt wurden, wieder her.  
  
 Setzt das Framework immer `bUndoable` auf **FALSE**. Wenn der Server rückgängig unterstützt, und es ist ein Vorgang, der rückgängig gemacht werden kann, rufen Sie die Implementierung der Basisklasse mit `bUndoable` festgelegt **TRUE**.  
  
##  <a name="ondocwindowactivate"></a>COleServerDoc::OnDocWindowActivate  
 Das Framework ruft diese Funktion zum Aktivieren oder deaktivieren ein Dokumentfenster für die direkte Bearbeitung.  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `bActivate`  
 Gibt an, ob das Dokumentfenster aktiviert oder deaktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung entfernt oder die Frame-Ebene Benutzeroberflächenelemente nach Bedarf hinzugefügt. Überschreiben Sie diese Funktion, wenn zusätzliche Aktionen durchzuführen, wenn das Dokument mit Ihren Artikel aktiviert oder deaktiviert werden soll.  
  
 Weitere Informationen finden Sie im Artikel [Activation](../../mfc/activation-cpp.md)...  
  
##  <a name="onexecolecmd"></a>COleServerDoc::OnExecOleCmd  
 Das Framework ruft diese Funktion, um einen bestimmten Befehl ausführen oder Anzeigen der Hilfe für den Befehl.  
  
```  
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,  
    DWORD nCmdID,  
    DWORD nCmdExecOpt,  
    VARIANTARG* pvarargIn,  
    VARIANTARG* pvarargOut);
```  
  
### <a name="parameters"></a>Parameter  
 `pguidCmdGroup`  
 Ein Zeiger auf eine GUID, die eine Reihe von Befehlen identifiziert. Kann **NULL** an, dass der Befehl Standardgruppe.  
  
 `nCmdID`  
 Der auszuführende Befehl. Muss in der identifizierten Gruppe `pguidCmdGroup`.  
  
 *nCmdExecOut*  
 Wie das Objekt sollte ausgeführt werden, mit dem Befehl, eine oder mehrere der folgenden Werte aus der **OLECMDEXECOPT** Enumeration:  
  
 **OLECMDEXECOPT_DODEFAULT**  
  
 **OLECMDEXECOPT_PROMPTUSER**  
  
 **OLECMDEXECOPT_DONTPROMPTUSER**  
  
 **OLECMDEXECOPT_SHOWHELP**  
  
 `pvarargIn`  
 Zeiger auf eine **VARIANTARG** Eingabeargumente für den Befehl enthält. Kann **NULL**.  
  
 `pvarargOut`  
 Zeiger auf eine **VARIANTARG** die Rückgabewerte für die Ausgabe des Befehls zu empfangen. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` Wenn erfolgreich, andernfalls eine der folgenden Fehlercodes:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Unerwarteter Fehler ist aufgetreten|  
|**E_FAIL**|Fehler|  
|**E_NOTIMPL**|Gibt an MFC selbst sollten versuchen, übersetzen und verteilen den Befehl|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`ist ungleich **NULL** , aber eine Gruppe bekannter Befehl angeben|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`als ein gültiger Befehl in der Gruppe wird nicht erkannt werden.`pguidCmdGroup`|  
|**OLECMDERR_DISABLED**|Der Befehl identifizierten `nCmdID` ist deaktiviert und kann nicht ausgeführt werden|  
|**OLECMDERR_NOHELP**|Aufrufer aufgefordert Hilfe zum Befehl identifizierten `nCmdID` , aber es ist keine Hilfe verfügbar|  
|**OLECMDERR_CANCELED**|Die Ausführung wurde vom Benutzer abgebrochen.|  
  
### <a name="remarks"></a>Hinweise  
 `COleCmdUI`kann verwendet werden, zu aktivieren, aktualisieren und andere Eigenschaften des DocObject Benutzeroberflächenbefehlen festzulegen. Nachdem die Befehle initialisiert werden, können Sie sie mit ausführen `OnExecOleCmd`.  
  
 Das Framework Ruft die Funktion vor dem Versuch, übersetzen und dispatch-Befehl ein OLE-Dokument. Sie müssen diese Funktion, um die standardmäßigen OLE Dokument Befehlen außer Kraft setzen, aber eine Überschreibung dieser Funktion müssen Sie angeben, wenn Sie eigene benutzerdefinierte Befehle behandeln oder verarbeiten Befehle, die Parameter akzeptieren oder Ergebnisse zurückgeben möchten.  
  
 Die meisten Befehle Argumente oder Rückgabewerte nicht. Für die Mehrheit der Befehle der Aufrufer kann **NULL**s für `pvarargIn` und `pvarargOut`. Der Aufrufer kann für Befehle, die Eingabewerte zu erwarten, deklarieren und Initialisieren einer **VARIANTARG** Variablen, und übergeben Sie einen Zeiger auf die Variable in `pvarargIn`. Für Befehle, die einen einzelnen Wert erfordern, das Argument gespeichert werden direkt in die **VARIANTARG** und an die Funktion übergeben. Mehrere Argumente verpackt werden müssen, in der **VARIANTARG** mithilfe einer der unterstützten Typen (z. B. `IDispatch` und **SAFEARRAY** ).  
  
 Auf ähnliche Weise ein Befehl Argumente den Aufrufer zurückgegeben soll Deklarieren einer **VARIANTARG**, initialisieren Sie es mit `VT_EMPTY`, und übergeben Sie die Adresse in `pvarargOut`. Wenn ein Befehl einen einzelnen Wert zurückgibt, kann das Objekt direkt im Wert speichern `pvarargOut`. Mehrere Ausgabewerte verpackt in irgendeiner Form für die **VARIANTARG**.  
  
 Die Implementierung der Basisklasse dieser Funktion führt die **OLE_COMMAND_MAP** Strukturen zugeordnet, die Befehlsziel und versuchen Sie den Befehl aus, um einen entsprechenden Handler zu senden. Die Implementierung der Basisklasse funktioniert nur mit Befehlen, die keine Argumente akzeptieren oder Werte zurück. Sie müssen Befehle zu verarbeiten, die Argumente akzeptieren oder Rückgabewerte, überschreiben Sie diese Funktion und müssen arbeiten mit der `pvarargIn` und `pvarargOut` Parameter selbst.  
  
##  <a name="onframewindowactivate"></a>COleServerDoc::OnFrameWindowActivate  
 Das Framework ruft diese Funktion auf, wenn der Container-Anwendung Rahmenfenster aktiviert oder deaktiviert wird.  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 `bActivate`  
 Gibt an, ob das Rahmenfenster aktiviert oder deaktiviert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung bricht alle Hilfemodi, denen das Rahmenfenster möglicherweise ab. Überschreiben Sie diese Funktion, wenn auszuführenden besondere Verarbeitung durch, wenn das Rahmenfenster aktiviert oder deaktiviert wird.  
  
 Weitere Informationen finden Sie im Artikel [Activation](../../mfc/activation-cpp.md)...  
  
##  <a name="ongetembeddeditem"></a>COleServerDoc::OnGetEmbeddedItem  
 Wird vom Framework aufgerufen, wenn eine Steuerelementcontainer-Anwendung ruft die Serveranwendung erstellen oder bearbeiten ein eingebettetes Element.  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Element, das gesamte Dokument darstellt; **NULL** , wenn der Vorgang fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Es ist keine Standardimplementierung vorhanden. Überschreiben Sie diese Funktion, um ein Element zurück, das gesamte Dokument darstellt. Dieser Rückgabewert sollte es sich um ein Objekt von einem `COleServerItem`-abgeleiteten Klasse.  
  
##  <a name="onreactivateandundo"></a>COleServerDoc::OnReactivateAndUndo  
 Das Framework ruft diese Funktion auf, wenn der Benutzer vorgenommenen ein Element, das in der direkten aktiviert, geändert und anschließend deaktiviert wurde.  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung nichts außer Return **FALSE** um einen Fehler anzugeben.  
  
 Überschreiben Sie diese Funktion, wenn Ihre Anwendung rückgängig unterstützt. Normalerweise würden Sie die Rückgängig-Vorgang ausführen und dann aktivieren Sie das Element durch Aufrufen von `ActivateInPlace`. Wenn die Container-Anwendung mit der Microsoft Foundation Class-Bibliothek geschrieben wird, der Aufruf von `COleClientItem::ReactivateAndUndo` bewirkt, dass diese Funktion aufgerufen werden.  
  
##  <a name="onresizeborder"></a>COleServerDoc::OnResizeBorder  
 Das Framework ruft diese Funktion Rahmenfenster der Container-Anwendung ändern.  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRectBorder`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das die Koordinaten des Rahmens angibt.  
  
 `lpUIWindow`  
 Zeiger auf ein Objekt der Klasse **IOleInPlaceUIWindow** , die die aktuelle bearbeitungssitzung direkte besitzt.  
  
 *bFrame*  
 **True,** Wenn `lpUIWindow` verweist auf die containeranwendung auf der obersten Ebene Rahmenfenster oder **FALSE** Wenn `lpUIWindow` verweist auf die containeranwendung auf Dokumentebene Rahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ändert die Größe und Symbolleisten und andere Elemente der Benutzeroberfläche in Übereinstimmung mit der neuen Größe angepasst.  
  
 Weitere Informationen finden Sie unter [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Dies ist eine erweiterte überschrieben.  
  
##  <a name="onsethostnames"></a>COleServerDoc::OnSetHostNames  
 Wird vom Framework aufgerufen, wenn der Container legt fest oder die Hostnamen für dieses Dokument ändert.  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszHost`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen der der Container-Anwendung angibt.  
  
 `lpszHostObj`  
 Ein Zeiger auf eine Zeichenfolge, die Container-Namen für das Dokument angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ändert den Titel des Dokuments für alle Ansichten für dieses Dokument verweisen.  
  
 Überschreiben Sie diese Funktion, wenn Ihre Anwendung die Titel mithilfe eines anderen Mechanismus festlegt.  
  
##  <a name="onsetitemrects"></a>COleServerDoc::OnSetItemRects  
 Das Framework ruft diese Funktion, um die direkte Bearbeitung Rahmenfenster in Rahmenfenster der Container-Anwendung zu positionieren.  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPosRect`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das direkte Rahmenfenster Position relativ zum Clientbereich der Container-Anwendung angibt.  
  
 `lpClipRect`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, das direkte Rahmenfenster Auswahlrechteck relativ zum Clientbereich der Container-Anwendung angibt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um den Zoomfaktor der Ansicht, zu aktualisieren, wenn erforderlich.  
  
 Diese Funktion ist in der Regel als Reaktion auf eine `RequestPositionChange` aufzurufen, obwohl sie jederzeit vom Container zum Beantragen einer positionsänderung für das direkte Element aufgerufen werden kann.  
  
##  <a name="onshowcontrolbars"></a>COleServerDoc::OnShowControlBars  
 Das Framework ruft diese Funktion zum ein- oder Ausblenden der Server-Anwendung Steuerleisten identifizierten Rahmenfenster zugeordnet `pFrameWnd`.  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 `pFrameWnd`  
 Ein Zeiger auf das Rahmenfenster, deren Steuerleisten ein- oder ausgeblendet werden soll.  
  
 `bShow`  
 Bestimmt, ob das Steuerelement Bildlaufleisten angezeigt oder ausgeblendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung Listet alle Steuerleisten, die im Besitz dieser Rahmenfenster und blendet oder diese.  
  
##  <a name="onshowdocument"></a>COleServerDoc::OnShowDocument  
 Das Framework Ruft die `OnShowDocument` funktionieren, wenn der Server-Dokument ein- oder ausgeblendet werden muss.  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 `bShow`  
 Gibt an, ob die Benutzeroberfläche für das Dokument angezeigt oder ausgeblendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bShow` ist **TRUE**, die standardmäßige Implementierung die Server-Anwendung aktiviert, falls erforderlich, und bewirkt, dass die Container-Anwendung, um den Fensterinhalt so, dass das Element sichtbar ist. Wenn `bShow` ist **FALSE**, die standardmäßige Implementierung deaktiviert das Element durch einen Aufruf von `OnDeactivate`, zerstört, oder blendet alle Rahmenfenster, die für das Dokument, mit Ausnahme des ersten erstellt wurden. Wenn keine Dokumente sichtbar bleiben, blendet die standardmäßige Implementierung die Server-Anwendung.  
  
##  <a name="onupdatedocument"></a>COleServerDoc::OnUpdateDocument  
 Beim Speichern eines Dokuments, die ein eingebettetes Element in einem Verbunddokument wird vom Framework aufgerufen.  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument erfolgreich aktualisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft die [COleServerDoc::NotifySaved](#notifysaved) und [COleServerDoc::SaveEmbedding](#saveembedding) Memberfunktionen dar, und klicken Sie dann das Dokument als sauber markiert. Überschreiben Sie diese Funktion, wenn Sie spezielle Verarbeitung bei der Aktualisierung eines eingebetteten Elements ausführen möchten.  
  
##  <a name="requestpositionchange"></a>COleServerDoc::RequestPositionChange  
 Rufen Sie diese Memberfunktion zum Ändern der Position des Elements die Container-Anwendung haben.  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPosRect`  
 Zeiger auf eine `RECT` Struktur oder ein `CRect` -Objekt, die neue Position des Elements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen (in Verbindung mit `UpdateAllItems`) Wenn die Daten in ein aktives in-Place-Element geändert hat. Nach diesem Aufruf der Container kann oder möglicherweise nicht die Änderung durch Aufrufen von `OnSetItemRects`. Die resultierende Position möglicherweise anders angefordert.  
  
##  <a name="saveembedding"></a>COleServerDoc::SaveEmbedding  
 Mit dieser Funktion können Container zum Speichern des eingebetteten Objekts festzulegen.  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird automatisch aufgerufen, von `OnUpdateDocument`. Beachten Sie, dass diese Funktion wird das Element auf dem Datenträger aktualisiert werden, damit sie in der Regel nur durch eine bestimmte Benutzeraktion aufgerufen wird.  
  
##  <a name="scrollcontainerby"></a>COleServerDoc::ScrollContainerBy  
 Rufen Sie die `ScrollContainerBy` Memberfunktion Containerdokument Betrag in Pixel Scrollen durch angegebene `sizeScroll`.  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>Parameter  
 `sizeScroll`  
 Gibt an, wie weit das Containerdokument blättern.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Positive Werte geben einen Bildlauf nach unten und rechts; negative Werte geben Sie einen Bildlauf nach oben und nach links an.  
  
##  <a name="updateallitems"></a>COleServerDoc::UpdateAllItems  
 Rufen Sie diese Funktion, um benachrichtigt zu werden alle verknüpften Elemente, die Verbindung mit dem Dokument, das das Dokument geändert wurde.  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parameter  
 `pSender`  
 Zeiger auf das Element, das das Dokument geändert oder **NULL** Wenn alle Elemente aktualisiert werden.  
  
 `lHint`  
 Enthält Informationen über die Änderung.  
  
 `pHint`  
 Ein Zeiger auf ein Objekt, das Informationen über die Änderung zu speichern.  
  
 `nDrawAspect`  
 Bestimmt, wie das Element gezeichnet werden. Dies ist ein Wert aus der `DVASPECT` Enumeration. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
- `DVASPECT_CONTENT`Element wird so dargestellt, als eingebettetes Objekt innerhalb des Containers angezeigt werden können.  
  
- `DVASPECT_THUMBNAIL`Element wird in einer "Miniaturansicht"-Darstellung dargestellt, damit sie in einem Browser angezeigt werden kann.  
  
- `DVASPECT_ICON`Element wird durch ein Symbol dargestellt.  
  
- `DVASPECT_DOCPRINT`Element dargestellt, als würde es mithilfe des Befehls Drucken im Menü Datei gedruckt wurden.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel rufen Sie diese Funktion nach der Benutzer das Serverdokument geändert wird. Wenn ein OLE-Element mit automatischen Verknüpfung mit dem Dokument verknüpft ist, wird das Element die Änderungen entsprechend aktualisiert. In Container-Anwendung, die mit der Microsoft Foundation Class-Bibliothek geschrieben wurden die [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) Memberfunktion `COleClientItem` aufgerufen wird.  
  
 Diese Funktion ruft die `OnUpdate` -Memberfunktion des Dokuments Elemente mit Ausnahme der sendende Element, das Übergeben von `pHint`, `lHint`, und `nDrawAspect`. Verwenden Sie diese Parameter, um Informationen zu den Elementen zu Änderungen an das Dokument übergeben. Können Sie codieren, Informationen mit `lHint` oder Definieren einer `CObject`-abgeleiteten Klasse zum Speichern von Informationen zu den Änderungen, und übergeben Sie ein Objekt dieser Klasse mit `pHint`. Überschreiben der `OnUpdate` Member-Funktion in Ihrer `COleServerItem`-abgeleitete Klasse, um die Aktualisierung der einzelnen Elemente, je nachdem, ob dessen Darstellung geändert zu optimieren.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [COleLinkingDoc-Klasse](../../mfc/reference/colelinkingdoc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)   
 [COleLinkingDoc-Klasse](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer-Klasse](../../mfc/reference/coletemplateserver-class.md)

