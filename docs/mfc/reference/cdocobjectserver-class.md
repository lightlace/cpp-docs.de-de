---
title: CDocObjectServer Klasse | Microsoft-Dokumentation
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
- document object server
- CDocObjectServer class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 75fb0ba49d105a673e862ed3044e85ac9e990e9c
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cdocobjectserver-class"></a>CDocObjectServer-Klasse
Implementiert die zusätzlichen OLE-Schnittstellen, die erforderlich sind, um aus einem normalen `COleDocument` -Server einen vollständigen DocObject-Server zu machen: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`und `IPrint`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Erstellt ein `CDocObjectServer`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Den Document-Objekt-Server aktiviert, aber wird nicht angezeigt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|Zeigt die DocObject-Ansicht.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|Hiermit wird der Status der DocObject-Ansicht.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|Speichert den Zustand der DocObject-Ansicht.|  
  
## <a name="remarks"></a>Hinweise  
 `CDocObjectServer`stammt von `CCmdTarget` und arbeitet eng mit `COleServerDoc` Schnittstellen verfügbar machen.  
  
 Kann ein DocObject-Server-Dokument enthalten [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) Objekte, die die Serverschnittstelle DocObject-Elemente darstellen.  
  
 Informationen zum Anpassen Ihrer DocObject-Servers leiten Sie eine eigene Klasse von `CDocObjectServer` und seine Ansicht Setup Funktionen überschreiben [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), und [OnSaveViewState](#onsaveviewstate). Sie benötigen, geben Sie eine neue Instanz der Klasse als Antwort auf Framework aufgerufen.  
  
 Weitere Informationen über DocObjects, finden Sie unter [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) und [COleCmdUI](../../mfc/reference/colecmdui-class.md) in der *MFC-Referenz*. Siehe auch [Internetgrundlagen: Aktive Dokumente](../../mfc/active-documents-on-the-internet.md) und [Active Documents](../../mfc/active-documents-on-the-internet.md).  
  
 Siehe auch den folgenden Knowledge Base-Artikel:  
  
-   Q247382: PRB: QuickInfos für Steuerelemente in ActiveX-Dokument-Server sind von der ActiveX-Dokument-Container verborgen  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdocob.h  
  
##  <a name="activatedocobject"></a>CDocObjectServer::ActivateDocObject  
 Rufen Sie diese Funktion, um das Document-Objekt-Server zu aktivieren (jedoch nicht angezeigt).  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Hinweise  
 `ActivateDocObject`Aufrufe `IOleDocumentSite`des **ActivateMe** -Methode, aber nicht die Ansicht angezeigt wird, da er für bestimmte Anweisungen zum wartet erstellen und Anzeigen der Ansicht im Aufruf angegebenen [CDocObjectServer::OnActivateView](#onactivateview).  
  
 Gemeinsam `ActivateDocObject` und `OnActivateView` aktivieren und Anzeigen der DocObject-Ansicht. DocObject Aktivierung unterscheidet sich von anderen Arten von OLE-Ort-Aktivierung. DocObject Aktivierung umgeht direktes Schraffur Rahmen und Objekt Zusatzelemente (z. B. Ziehpunkte) anzeigen, ignoriert Extent-Objekt: Funktionen und zeichnet Bildlaufleisten innerhalb des Rechtecks anzeigen, im Gegensatz zu zeichnen sie außerhalb dieses Rechtecks verwenden (wie normale-Ort-Aktivierung).  
  
##  <a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer  
 Erstellt und initialisiert ein `CDocObjectServer`-Objekt.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pOwner*  
 Ein Zeiger auf das Client-Standort-Dokument, das der Client für die DocObject-Server ist.  
  
 `pDocSite`  
 Ein Zeiger auf die `IOleDocumentSite` Schnittstelle, die vom Container implementiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn DocObject aktiv ist, Standort der Client-OLE-Schnittstelle ( `IOleDocumentSite`) ist, was die DocObject-Server zur Kommunikation mit dem Client (Container) ermöglicht. Wenn ein DocObject-Server aktiviert ist, überprüft zunächst, dass der Container implementiert die `IOleDocumentSite` Schnittstelle. In diesem Fall [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) wird aufgerufen, um festzustellen, ob der Container DocObjects unterstützt. In der Standardeinstellung `GetDocObjectServer` gibt **NULL**. Müssen Sie überschreiben `COleServerDoc::GetDocObjectServer` eine neue `CDocObjectServer` Objekt oder ein abgeleitetes Objekt mit eigenen Zeiger auf die `COleServerDoc` Container und dessen `IOleDocumentSite` Schnittstelle als Argumente an den Konstruktor.  
  
##  <a name="onactivateview"></a>CDocObjectServer::OnActivateView  
 Rufen Sie diese Funktion, um die DocObject anzuzeigen.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Fehler oder Warnungswert. Standardmäßig gibt **NOERROR** Wenn erfolgreich, andernfalls **E_FAIL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion erstellt ein in-Place-Frame-Fenster, zeichnet Bildlaufleisten in der Ansicht, richtet die Menüs, die der Server gemeinsam mit dem Container hinzugefügt Frame-Steuerelementen, legt das aktive Objekt, und klicken Sie dann schließlich zeigt das direkte Rahmenfenster und setzt den Fokus.  
  
##  <a name="onapplyviewstate"></a>CDocObjectServer::OnApplyViewState  
 Überschreiben Sie diese Funktion, um den Status der DocObject-Ansicht wiederherstellen.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein `CArchive` Objekt, um den Ansichtszustand zu serialisieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird aufgerufen, wenn zum ersten Mal nach der Instanziierung die Ansicht angezeigt wird. `OnApplyViewState`weist eine Ansicht automatisch anhand der Daten in neu initialisiert die `CArchive` mit zuvor gespeichertes Objekt [OnSaveViewState](#onsaveviewstate). Die Ansicht muss überprüfen, die Daten in der `CArchive` Objekt, da der Container nicht versucht, die Ansichtszustandsdaten in keiner Weise interpretieren.  
  
 Sie können `OnSaveViewState` permanente Informationen in Ihrer Ansicht Zustand zu speichern. Wenn Sie außer Kraft setzen `OnSaveViewState` zum Speichern von Informationen möchten Sie überschreiben `OnApplyViewState` zum Lesen von Informationen und zur Ansicht anwenden, wenn es neu aktiviert ist.  
  
##  <a name="onsaveviewstate"></a>CDocObjectServer::OnSaveViewState  
 Überschreiben Sie diese Funktion, um zusätzliche Zustandsinformationen zur DocObject-Ansicht speichern.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein `CArchive` -Objekt, in dem der Ansichtszustand serialisiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Status kann Eigenschaften wie den Ansichtstyp, Zoomfaktor, einfügen und Auswahlpunkt usw. enthalten. Der Container ruft diese Funktion in der Regel vor dem Deaktivieren der Ansicht. Der gespeicherte Zustand kann später wiederhergestellt werden, über [OnApplyViewState](#onapplyviewstate).  
  
 Sie können `OnSaveViewState` permanente Informationen in Ihrer Ansicht Zustand zu speichern. Wenn Sie außer Kraft setzen `OnSaveViewState` zum Speichern von Informationen möchten Sie überschreiben `OnApplyViewState` zum Lesen von Informationen und zur Ansicht anwenden, wenn es neu aktiviert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem-Klasse](../../mfc/reference/cdocobjectserveritem-class.md)

