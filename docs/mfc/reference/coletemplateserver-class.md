---
title: COleTemplateServer Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [C++], implementing
- servers, OLE
- OLE server applications, managing server documents
- link containers [C++]
- visual editing, servers
- OLE link containers
- COleTemplateServer class
- OLE server applications, COleTemplateServer class
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ea82939cd0e8a8ba5612c65d238be8ae9996ef08
ms.lasthandoff: 02/24/2017

---
# <a name="coletemplateserver-class"></a>COleTemplateServer-Klasse
Wird für OLE-Server mit direkter Aktivierung, Automatisierungsserver und Linkcontainer verwendet (also in Anwendungen, die Links zu Einbettungen unterstützen).  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|Erstellt ein `COleTemplateServer`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Verbindet eine Dokumentvorlage in die zugrunde liegende `COleObjectFactory` Objekt.|  
|[COleTemplateServer::Unregister](#unregister)|Hebt die Registrierung der zugeordneten Dokumentvorlage.|  
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Den Dokumenttyp der OLE-System-Registrierung registriert.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird von der Klasse abgeleitet [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); in der Regel können Sie `COleTemplateServer` direkt, anstatt eine eigene Klasse ableiten. `COleTemplateServer`verwendet einen [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt, um die Serverdokumente zu verwalten. Verwendung `COleTemplateServer` bei der Implementierung von eines vollständigen Servers, d. h. ein, die als eigenständige Anwendung ausgeführt werden können. Vollständiger Server sind in der Regel mehrere Document Interface (MDI) Applications, obwohl einzelne Document Interface (SDI) Anwendung unterstützt werden. Ein `COleTemplateServer` Objekt ist erforderlich, für jeden Typ von Server-Dokument, die von einer Anwendung unterstützt, d. h., wenn die Server-Anwendung Arbeitsblätter und Diagramme unterstützt, benötigen Sie zwei `COleTemplateServer` Objekte.  
  
 `COleTemplateServer`überschreibt die `OnCreateInstance` Memberfunktion definiert `COleObjectFactory`. Diese Member-Funktion wird vom Framework zum Erstellen eines C++-Objekts mit dem richtigen Typ aufgerufen.  
  
 Weitere Informationen zu erhalten, finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="coletemplateserver"></a>COleTemplateServer::COleTemplateServer  
 Erstellt ein `COleTemplateServer`-Objekt.  
  
```  
COleTemplateServer();
```  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung der Verwendung der `COleTemplateServer` Klasse, finden Sie unter der [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) Übersicht über die Klasse.  
  
##  <a name="connecttemplate"></a>COleTemplateServer::ConnectTemplate  
 Verbindet die Dokumentvorlage zeigt `pDocTemplate` in die zugrunde liegende [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) Objekt.  
  
```  
void ConnectTemplate(
    REFCLSID clsid,  
    CDocTemplate* pDocTemplate,  
    BOOL bMultiInstance);
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 Verweis auf die OLE-Klassen-ID, die die Vorlage anfordert.  
  
 `pDocTemplate`  
 Ein Zeiger auf die Dokumentvorlage aus.  
  
 `bMultiInstance`  
 Gibt an, ob eine einzelne Instanz der Anwendung mehrere Instanziierungen unterstützen kann. Wenn **TRUE**, mehrere Instanzen der Anwendung werden für jede Anforderung zum Erstellen eines Objekts gestartet.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [CLSID-Schlüssel](http://msdn.microsoft.com/library/windows/desktop/ms691424) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="unregister"></a>COleTemplateServer::Unregister  
 Hebt die Registrierung der zugeordneten Dokumentvorlage.  
  
```  
BOOL Unregister();
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich, andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 EnterRemarks  
  
##  <a name="updateregistry"></a>COleTemplateServer::UpdateRegistry  
 Lädt Informationen über den Dateityp aus der Dokumentvorlage Zeichenfolge und speichert diese Informationen in der Registrierung des OLE-Systems.  
  
```  
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL,  
    BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nAppType`  
 Ein Wert aus der **OLE_APPTYPE** -Enumeration, die in AFXDISP definiert ist. H. Einer der folgenden Werte sind möglich:  
  
- `OAT_INPLACE_SERVER`Server hat vollständige Server-Benutzeroberfläche.  
  
- `OAT_SERVER`Server unterstützt nur einbetten.  
  
- `OAT_CONTAINER`Container unterstützt Links zu eingebetteten Objekten.  
  
- `OAT_DISPATCH_OBJECT`Objekt ist `IDispatch`-fähig.  
  
- **OAT_DOC_OBJECT_SERVER** Server unterstützt sowohl das Einbetten von und das Komponentenmodell Document-Objekt.  
  
 `rglpszRegister`  
 Eine Liste der Einträge, die in die Registrierung geschrieben wird, nur dann, wenn keine Einträge vorhanden sind.  
  
 `rglpszOverwrite`  
 Eine Liste der Einträge, die geschrieben wird, in der Registrierung, unabhängig davon, ob alle vorherigen Einträge vorhanden sind.  
  
 `bRegister`  
 Bestimmt, ob die Klasse registriert werden. Wenn `bRegister` ist **TRUE**, die Klasse wird mit der Registrierung registriert. Andernfalls hebt es die-Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Die Registrierungsinformationen erfolgt durch einen Aufruf von [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Die Teilzeichenfolgen abgerufen werden Indizes identifiziert **RegFileTypeId**, **RegFileTypeName**, und **FileNewName**, wie in beschrieben die `GetDocString` auf den Referenzseiten.  
  
 Wenn die **RegFileTypeId** Teilzeichenfolge leer ist oder wenn der Aufruf von `GetDocString` ein Fehler auftritt, einem anderen Grund, diese Funktion schlägt fehl, und die Informationen in der Registrierung nicht eingegeben wird.  
  
 Die Informationen in den Argumenten `rglpszRegister` und `rglpszOverwrite` bezieht sich auf die Registrierung durch einen Aufruf von [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). Die Standardinformationen, der registriert wird, wenn die beiden Argumente sind **NULL**, eignet sich für die meisten Anwendungen. Informationen zur Struktur der Informationen in diesen Argumenten finden Sie unter `AfxOleRegisterServerClass`.  
  
 Weitere Informationen finden Sie unter [die IDispatch-Schnittstelle implementieren](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [COleObjectFactory-Klasse](../../mfc/reference/coleobjectfactory-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)

