---
title: COleTemplateServer Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90b24d65dbd6f800dda0b25088288bee6fdcf3c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374382"
---
# <a name="coletemplateserver-class"></a>COleTemplateServer-Klasse
Wird für OLE-Server mit direkter Aktivierung, Automatisierungsserver und Linkcontainer verwendet (also in Anwendungen, die Links zu Einbettungen unterstützen).  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|Erstellt ein `COleTemplateServer`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Verbindet eine Dokumentvorlage auf die zugrunde liegende `COleObjectFactory` Objekt.|  
|[COleTemplateServer::Unregister](#unregister)|Hebt die Registrierung der Vorlage zugeordnete Dokument.|  
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Registriert den Dokumenttyp der OLE-systemregistrierung.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird von der Klasse abgeleitet [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); in der Regel können Sie `COleTemplateServer` direkt, anstatt eine eigene Klasse ableiten. `COleTemplateServer` verwendet eine [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt, um die Serverdokumente zu verwalten. Verwendung `COleTemplateServer` bei der Implementierung von eines vollständigen Servers, d. h. ein, die als eigenständige Anwendung ausgeführt werden können. Vollständige Server sind in der Regel mehrere Document Interface (MDI)-Anwendungen, obwohl einzelne Document Interface (SDI)-Anwendungen unterstützt werden. Eine `COleTemplateServer` Objekt ist für jeden Typ von einer Anwendung unterstützt Serverdokument erforderlich; d. h. Wenn Ihre Serveranwendung Arbeitsblätter und Diagramme unterstützt, benötigen Sie zwei `COleTemplateServer` Objekte.  
  
 `COleTemplateServer` überschreibt die `OnCreateInstance` Memberfunktion, die durch definierten `COleObjectFactory`. Diese Memberfunktion wird vom Framework zum Erstellen eines C++-Objekts mit dem richtigen Typ aufgerufen.  
  
 Weitere Informationen zu Servern finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="coletemplateserver"></a>  COleTemplateServer::COleTemplateServer  
 Erstellt ein `COleTemplateServer`-Objekt.  
  
```  
COleTemplateServer();
```  
  
### <a name="remarks"></a>Hinweise  
 Für eine kurze Beschreibung der Verwendung der `COleTemplateServer` Klasse, finden Sie unter der [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) -Klassenübersicht.  
  
##  <a name="connecttemplate"></a>  COleTemplateServer::ConnectTemplate  
 Verbindet die Dokumentvorlage verweist `pDocTemplate` auf die zugrunde liegende [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) Objekt.  
  
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
 Ein Zeiger auf das Dokumentvorlage.  
  
 `bMultiInstance`  
 Gibt an, ob eine einzelne Instanz der Anwendung mehrere Instanziierungen unterstützen kann. Wenn **"true"**, werden mehrere Instanzen der Anwendung, die für jede Anforderung zum Erstellen eines Objekts gestartet.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Schlüssel CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) im Windows SDK.  
  
##  <a name="unregister"></a>  COleTemplateServer::Unregister  
 Hebt die Registrierung der Vorlage zugeordnete Dokument.  
  
```  
BOOL Unregister();
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich, andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 EnterRemarks  
  
##  <a name="updateregistry"></a>  COleTemplateServer::UpdateRegistry  
 Lädt Dateityp Informationen aus den Dokumentvorlagen-Zeichenfolge und speichert diese Informationen in der OLE-systemregistrierung.  
  
```  
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL,  
    BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nAppType`  
 Ein Wert aus der **OLE_APPTYPE** -Enumeration, die in AFXDISP definiert ist. H. Es kann eine der folgenden Werte aufweisen:  
  
- `OAT_INPLACE_SERVER` Server hat vollständige Server-Benutzeroberfläche.  
  
- `OAT_SERVER` Server unterstützt nur einbetten.  
  
- `OAT_CONTAINER` Container unterstützt Links auf eingebettete Objekte.  
  
- `OAT_DISPATCH_OBJECT` Objekt ist `IDispatch`-fähig.  
  
- **OAT_DOC_OBJECT_SERVER** Server unterstützt sowohl das Einbetten von und die Komponentenmodell "Document"-Objekt.  
  
 `rglpszRegister`  
 Eine Liste von Einträgen, die in der Registrierung geschrieben wurde, nur dann, wenn keine Einträge vorhanden sind.  
  
 `rglpszOverwrite`  
 Eine Liste von Einträgen, die geschrieben wird, in der Registrierung, unabhängig davon, ob alle vorherigen Einträge vorhanden sind.  
  
 `bRegister`  
 Bestimmt, ob die Klasse registriert werden. Wenn `bRegister` ist **"true"**, die Klasse bei der Registrierung registriert ist. Andernfalls, hebt die Klasse Registrierung.  
  
### <a name="remarks"></a>Hinweise  
 Die Registrierungsinformationen erfolgt durch einen Aufruf von [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Die Teilzeichenfolgen abgerufen getroffenen identifiziert, die von den Indizes **RegFileTypeId**, **RegFileTypeName**, und **FileNewName**gemäß der Beschreibung in der `GetDocString` Referenzseiten.  
  
 Wenn die **RegFileTypeId** Teilzeichenfolge leer ist oder wenn der Aufruf von `GetDocString` ein Fehler auftritt, für andere Zwecke, diese Funktion schlägt fehl, und die Informationen in der Registrierung nicht eingegeben wird.  
  
 Die Informationen in den Argumenten `rglpszRegister` und `rglpszOverwrite` in der Registrierung durch einen Aufruf von geschrieben [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). Informationen über das Standardformat, die registriert wird, sind die zwei Argumente **NULL**, eignet sich für die meisten Anwendungen. Informationen zur Struktur der Informationen in diesen Argumenten finden Sie unter `AfxOleRegisterServerClass`.  
  
 Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [COleObjectFactory-Klasse](../../mfc/reference/coleobjectfactory-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)   
 [COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)
