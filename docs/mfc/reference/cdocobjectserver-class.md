---
title: CDocObjectServer-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 701cfc2f8a88f57a1c50c9c4310ecd21154ef09a
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337865"
---
# <a name="cdocobjectserver-class"></a>CDocObjectServer-Klasse
Implementiert die zusätzlichen OLE-Schnittstellen, die erforderlich sind, um aus einem normalen `COleDocument` -Server einen vollständigen DocObject-Server zu machen: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`und `IPrint`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Erstellt ein `CDocObjectServer`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Den Document-Objekt-Server aktiviert, aber es wird nicht angezeigt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|Zeigt die DocObject-Ansicht.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|Stellt den Zustand der DocObject-Ansicht.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|Speichert den Zustand der DocObject-Ansicht.|  
  
## <a name="remarks"></a>Hinweise  
 `CDocObjectServer` stammt aus `CCmdTarget` und arbeitet eng mit `COleServerDoc` Schnittstellen verfügbar machen.  
  
 Ein DocObject-Server-Dokument enthalten kann [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) Objekte, die die Serverschnittstelle DocObject-Elemente darstellen.  
  
 Informationen zum Anpassen Ihrer DocObject-Servers leiten Sie eine eigene Klasse von `CDocObjectServer` und überschreiben seine Ansicht Setupfunktionen [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), und [OnSaveViewState ](#onsaveviewstate). Sie benötigen, geben Sie eine neue Instanz der Klasse als Reaktion auf Framework-Aufrufe.  
  
 Weitere Informationen zu DocObjects, finden Sie unter [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) und [COleCmdUI](../../mfc/reference/colecmdui-class.md) in die *MFC-Referenz*. Siehe auch [Internetgrundlagen: Aktive Dokumente](../../mfc/active-documents-on-the-internet.md) und [aktive Dokumente](../../mfc/active-documents-on-the-internet.md).  
  
 Außerdem finden Sie im folgenden Knowledge Base-Artikel:  
  
-   Q247382: PRB: QuickInfos für Steuerelemente in ActiveX-Dokument-Server werden ausgeblendet, durch den Container für ActiveX-Dokument  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdocob.h  
  
##  <a name="activatedocobject"></a>  CDocObjectServer::ActivateDocObject  
 Mit dieser Funktion können den Document-Objekt-Server zu aktivieren (jedoch nicht angezeigt).  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Hinweise  
 `ActivateDocObject` Aufrufe `IOleDocumentSite`des `ActivateMe` -Methode, aber nicht die Ansicht angezeigt wird, da er wartet für spezifische Anweisungen zum Einrichten und zeigen Sie die Sicht, auf die im Aufruf angegebenen [CDocObjectServer::OnActivateView](#onactivateview).  
  
 Zusammen `ActivateDocObject` und `OnActivateView` aktivieren und Anzeigen der DocObject-Ansicht. DocObject-Aktivierung unterscheidet sich von anderen Arten von OLE direkte Aktivierung. DocObject-Aktivierung umgangen wird, zum Anzeigen von direkten Schraffur Rahmen und Objekt Zusatzelemente (z. B. Ziehpunkten), ignoriert der Funktionen der Object-Block und zeichnet Bildlaufleisten innerhalb des Rechtecks anzeigen, im Gegensatz zu zeichnen sie außerhalb dieses Rechteck (wie bei normalen direkte Aktivierung).  
  
##  <a name="cdocobjectserver"></a>  CDocObjectServer::CDocObjectServer  
 Erstellt und initialisiert ein `CDocObjectServer`-Objekt.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pOwner*  
 Ein Zeiger auf das Client-Standort-Dokument, das der Client für die DocObject-Server ist.  
  
 *pDocSite*  
 Ein Zeiger auf die `IOleDocumentSite` Schnittstelle, die vom Container implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn DocObject aktiv ist, Standort der Client-OLE-Schnittstelle ( `IOleDocumentSite`) ist, was die DocObject-Server für die Kommunikation mit dem Client (Container) ermöglicht. Wenn ein DocObject-Server aktiviert ist, überprüft zunächst, dass der Container implementiert die `IOleDocumentSite` Schnittstelle. Wenn dies der Fall ist, [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) wird aufgerufen, um festzustellen, ob der Container DocObjects unterstützt. In der Standardeinstellung `GetDocObjectServer` gibt NULL zurück. Sie überschreiben müssen `COleServerDoc::GetDocObjectServer` um neue `CDocObjectServer` Objekt oder ein abgeleitetes Objekt von Ihrem eigenen, mit Zeigern auf die `COleServerDoc` Container und dessen `IOleDocumentSite` Schnittstelle als Argumente an den Konstruktor.  
  
##  <a name="onactivateview"></a>  CDocObjectServer::OnActivateView  
 Mit dieser Funktion können DocObject-Ansicht anzeigen.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Fehler oder Warnungswert. Standardmäßig gibt noError zurück Wenn erfolgreich; andernfalls E_FAIL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt ein in-Place-Frame-Fenster, zeichnet der Bildlaufleisten in der Ansicht, richtet die Menüs, die der Server gemeinsam mit seinem Container, Frame-Steuerelemente hinzugefügt, legt das aktive Objekt ist, und klicken Sie dann schließlich zeigt das Fenster in-Place-Frame- und legt den Fokus fest.  
  
##  <a name="onapplyviewstate"></a>  CDocObjectServer::OnApplyViewState  
 Überschreiben Sie diese Funktion, um den Zustand der DocObject-Ansicht wiederherzustellen.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 *ar*  
 Ein `CArchive` Objekt aus, das den Ansichtszustand zu serialisieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, wenn zum ersten Mal nach der Instanziierung die Ansicht angezeigt wird. `OnApplyViewState` weist eine Ansicht für die neuinitialisierung anhand der Daten in die `CArchive` Objekt zuvor gespeichert haben, mit [OnSaveViewState](#onsaveviewstate). Die Ansicht muss überprüfen, dass die Daten in die `CArchive` Objekt, da der Container nicht versucht, die Ansichtszustandsdaten in keiner Weise interpretieren.  
  
 Sie können `OnSaveViewState` zum Speichern von persistenten Informationen, die spezifisch für die Ansicht des Status. Wenn Sie außer Kraft setzen `OnSaveViewState` um Informationen zu speichern, möchten Sie außer Kraft setzen `OnApplyViewState` , lesen Sie diese Informationen, und klicken Sie auf die Ansicht angewendet wird, wenn es neu aktiviert ist.  
  
##  <a name="onsaveviewstate"></a>  CDocObjectServer::OnSaveViewState  
 Überschreiben Sie diese Funktion, um zusätzliche Informationen über die DocObject-Ansicht zu speichern.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 *ar*  
 Ein `CArchive` Objekt, in dem der Ansichtszustand serialisiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Ihr Status kann es sich um Eigenschaften wie die Ansicht, Zoomfaktor, einfügen und Auswahlpunkt und So weiter enthalten. Der Container ruft diese Funktion in der Regel vor dem Deaktivieren der Ansicht. Der gespeicherte Zustand kann später wiederhergestellt werden, über [OnApplyViewState](#onapplyviewstate).  
  
 Sie können `OnSaveViewState` zum Speichern von persistenten Informationen, die spezifisch für die Ansicht des Status. Wenn Sie außer Kraft setzen `OnSaveViewState` um Informationen zu speichern, möchten Sie außer Kraft setzen `OnApplyViewState` , lesen Sie diese Informationen, und klicken Sie auf die Ansicht angewendet wird, wenn es neu aktiviert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem-Klasse](../../mfc/reference/cdocobjectserveritem-class.md)
