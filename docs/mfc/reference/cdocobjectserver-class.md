---
title: CDocObjectServer Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 912262c4f1ba85c181bb30ee5d6f38a0defe5d5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Den Document-Objekt-Server aktiviert werden, jedoch nicht angezeigt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|Zeigt die DocObject an.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|Stellt den Status der DocObject-Ansicht an.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|Speichert den Zustand der DocObject-Ansicht.|  
  
## <a name="remarks"></a>Hinweise  
 `CDocObjectServer`stammt aus `CCmdTarget` und arbeitet eng mit `COleServerDoc` Schnittstellen verfügbar machen.  
  
 Serverdokument DocObject darf [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) Objekte, die die Serverschnittstelle für DocObject-Elemente darstellen.  
  
 Leiten Sie zum Anpassen Ihrer DocObject-Servers eine eigene Klasse von `CDocObjectServer` und seine Ansicht Setup Funktionen überschreiben [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), und [OnSaveViewState ](#onsaveviewstate). Sie benötigen, um eine neue Instanz der Klasse als Antwort auf Framework Aufrufe bereitzustellen.  
  
 Weitere Informationen zu DocObjects, finden Sie unter [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) und [COleCmdUI](../../mfc/reference/colecmdui-class.md) in der *MFC-Referenz*. Siehe auch [Internetgrundlagen: Aktive Dokumente](../../mfc/active-documents-on-the-internet.md) und [aktive Dokumente](../../mfc/active-documents-on-the-internet.md).  
  
 Außerdem finden Sie im folgenden Knowledge Base-Artikel:  
  
-   Q247382: PRB: QuickInfos für Steuerelemente im Dokument ActiveX-Server werden vom Container für ActiveX-Dokument ausgeblendet  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdocob.h  
  
##  <a name="activatedocobject"></a>CDocObjectServer::ActivateDocObject  
 Mit dieser Funktion wird zum Aktivieren den Document-Objekt-Server (jedoch nicht angezeigt).  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Hinweise  
 `ActivateDocObject`Aufrufe `IOleDocumentSite`des **ActivateMe** -Methode, aber nicht die Ansicht angezeigt wird, da es für bestimmte Anweisungen zum Einrichten und zeigen Sie die Sicht auf die im Aufruf angegebenen wartet [CDocObjectServer::OnActivateView](#onactivateview).  
  
 Zusammen `ActivateDocObject` und `OnActivateView` aktivieren und die DocObject-Ansicht anzuzeigen. DocObject-Aktivierung unterscheidet sich von anderen Arten von OLE direkte Aktivierung. Umgeht, Anzeigen von direkten Schraffur Rahmen und Objekt Zusatzelemente (z. B. Ziehpunkten), Objekt Block Funktionen ignoriert und zeichnet Bildlaufleisten innerhalb des Rechtecks Sicht im Gegensatz zum Zeichnen von außerhalb dieses Rechteck (wie bei normalen DocObject-Aktivierung direkte Aktivierung).  
  
##  <a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer  
 Erstellt und initialisiert ein `CDocObjectServer`-Objekt.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pOwner*  
 Ein Zeiger auf das Client-Standort-Dokument, das der Client für den DocObject-Server ist.  
  
 `pDocSite`  
 Ein Zeiger auf die `IOleDocumentSite` Schnittstelle, die vom Container implementiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn DocObject aktiv ist, Standort der Client-OLE-Schnittstelle ( `IOleDocumentSite`) wird die DocObject-Server für die Kommunikation mit dem Client (Container) ermöglicht. Bei ein DocObject-Server aktiviert ist, prüft zunächst, dass der Container implementiert die `IOleDocumentSite` Schnittstelle. Wenn dies der Fall ist, [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) wird aufgerufen, um festzustellen, ob der Container DocObjects unterstützt. Standardmäßig `GetDocObjectServer` gibt **NULL**. Sie überschreiben müssen `COleServerDoc::GetDocObjectServer` So erstellen Sie ein neues `CDocObjectServer` Objekt oder ein abgeleitetes Objekt von Ihrem eigenen, mit Zeigern auf die `COleServerDoc` Container und dessen `IOleDocumentSite` Schnittstelle als Argumente an den Konstruktor.  
  
##  <a name="onactivateview"></a>CDocObjectServer::OnActivateView  
 Mit dieser Funktion können DocObject-Ansicht anzuzeigen.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Fehler oder Warnungswert. Standardmäßig gibt **NOERROR** Wenn erfolgreich, andernfalls **E_FAIL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt ein in-Place-Frame-Fenster, zeichnet Bildlaufleisten innerhalb der Ansicht, richtet die Menüs, die des Servers gemeinsam mit seinem Container, fügt Frame Steuerelemente hinzu, legt das aktive Objekt dann schließlich zeigt das direkte Rahmenfenster und legt den Fokus.  
  
##  <a name="onapplyviewstate"></a>CDocObjectServer::OnApplyViewState  
 Überschreiben Sie diese Funktion, um den Status der DocObject-Ansicht wiederherzustellen.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein `CArchive` Objekt aus, das den Ansichtszustand zu serialisieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, wenn zum ersten Mal nach seiner Instanziierung der Ansicht angezeigt wird. `OnApplyViewState`weist eine Sicht selbst laut den Daten im erneut initialisieren der `CArchive` mit zuvor gespeicherten Objekt [OnSaveViewState](#onsaveviewstate). Die Sicht muss überprüfen, die Daten in der `CArchive` Objekt, da der Container nicht versucht, die Ansichtszustandsdaten in keiner Weise interpretieren.  
  
 Sie können `OnSaveViewState` zum persistenten spezifische Informationen zum Status Ihrer Ansicht speichern. Wenn Sie außer Kraft setzen `OnSaveViewState` um Informationen zu speichern, möchten Sie außer Kraft setzen `OnApplyViewState` zu lesen, die Informationen auf die Ansicht anzuwenden, wenn sie neu aktiviert wird.  
  
##  <a name="onsaveviewstate"></a>CDocObjectServer::OnSaveViewState  
 Überschreiben Sie diese Funktion, um zusätzliche Zustandsinformationen zu DocObject-Ansicht zu speichern.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein `CArchive` -Objekt, in dem der Ansichtszustand serialisiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Status kann Eigenschaften wie den Ansichtstyp, Zoomfaktor, einfügen und Auswahlpunkt usw. enthalten. Der Container ruft diese Funktion in der Regel vor dem Deaktivieren der Ansicht. Der gespeicherte Zustand kann später wiederhergestellt werden, über [OnApplyViewState](#onapplyviewstate).  
  
 Sie können `OnSaveViewState` zum persistenten spezifische Informationen zum Status Ihrer Ansicht speichern. Wenn Sie außer Kraft setzen `OnSaveViewState` um Informationen zu speichern, möchten Sie außer Kraft setzen `OnApplyViewState` zu lesen, die Informationen auf die Ansicht anzuwenden, wenn sie neu aktiviert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem-Klasse](../../mfc/reference/cdocobjectserveritem-class.md)
