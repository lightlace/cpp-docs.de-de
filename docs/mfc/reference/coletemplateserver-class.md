---
title: COleTemplateServer-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
helpviewer_keywords:
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
ms.openlocfilehash: 4a1997497f3bddb405b712b5534f76e577dabfa8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503094"
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
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Verbindet eine Dokument Vorlage mit dem zugrunde `COleObjectFactory` liegenden-Objekt.|
|[COleTemplateServer::Unregister](#unregister)|Hebt die Registrierung der zugeordneten Dokument Vorlage auf.|
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Registriert den Dokumenttyp bei der OLE-Systemregistrierung.|

## <a name="remarks"></a>Hinweise

Diese Klasse wird von der [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)-Klasse abgeleitet. Normalerweise können Sie direkt `COleTemplateServer` verwenden, anstatt eine eigene Klasse abzuleiten. `COleTemplateServer`verwendet ein [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) -Objekt zum Verwalten der Server Dokumente. Verwenden `COleTemplateServer` Sie bei der Implementierung eines vollständigen Servers, d. h. eines Servers, der als eigenständige Anwendung ausgeführt werden kann. Vollständige Server sind in der Regel Multiple Document Interface (MDI)-Anwendungen, auch wenn SDI-Anwendungen (Single Document Interface) unterstützt werden. Ein `COleTemplateServer` -Objekt wird für jeden Typ von Server Dokument benötigt, das von einer Anwendung unterstützt wird. das heißt, wenn die Serveranwendung sowohl Arbeitsblätter als auch `COleTemplateServer` Diagramme unterstützt, müssen Sie über zwei-Objekte verfügen.

`COleTemplateServer`überschreibt die `OnCreateInstance` von `COleObjectFactory`definierte Element Funktion. Diese Member-Funktion wird vom Framework aufgerufen, um ein C++ -Objekt des richtigen Typs zu erstellen.

Weitere Informationen zu Servern finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="coletemplateserver"></a>COleTemplateServer:: COleTemplateServer

Erstellt ein `COleTemplateServer`-Objekt.

```
COleTemplateServer();
```

### <a name="remarks"></a>Hinweise

Eine kurze Beschreibung der Verwendung `COleTemplateServer` der-Klasse finden Sie in der Übersicht über die [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) -Klasse.

##  <a name="connecttemplate"></a>COleTemplateServer:: ConnectTemplate

Verbindet die Dokument Vorlage, auf die von *pdoctemplate* verwiesen wird, mit dem zugrunde liegenden [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) -Objekt.

```
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Verweis auf die OLE-Klassen-ID, die die Vorlage anfordert.

*pDocTemplate*<br/>
Zeiger auf die Dokument Vorlage.

*bMultiInstance*<br/>
Gibt an, ob eine einzelne Instanz der Anwendung mehrere Instanziierungen unterstützen kann. TRUE gibt an, dass für jede Anforderung zum Erstellen eines Objekts mehrere Instanzen der Anwendung gestartet werden.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [CLSID-Schlüssel](/windows/win32/com/clsid-key-hklm) in der Windows SDK.

##  <a name="unregister"></a>COleTemplateServer:: Unregister

Hebt die Registrierung der zugeordneten Dokument Vorlage auf.

```
BOOL Unregister();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Enterprise-Hinweise

##  <a name="updateregistry"></a>COleTemplateServer:: UpdateRegistry

Lädt Dateityp Informationen aus der Zeichenfolge der Dokument Vorlage und legt diese Informationen in der OLE-Systemregistrierung ab.

```
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Parameter

*nAppType*<br/>
Ein Wert aus der OLE_APPTYPE-Enumeration, der in AFXDISP definiert ist. Micha. Sie kann einen der folgenden Werte aufweisen:

- Der OAT_INPLACE_SERVER-Server verfügt über eine vollständige Server Benutzeroberfläche.

- OAT_SERVER Server unterstützt nur Einbettungen.

- Der OAT_CONTAINER-Container unterstützt Verknüpfungen zu eingebetteten Objekten.

- OAT_DISPATCH_OBJECT-Objekt `IDispatch`ist-fähig.

- OAT_DOC_OBJECT_SERVER Server unterstützt sowohl Einbettungen als auch das Dokument Objekt-Komponentenmodell.

*rglpszRegister*<br/>
Eine Liste von Einträgen, die nur in die Registrierung geschrieben werden, wenn keine Einträge vorhanden sind.

*rglpszOverwrite*<br/>
Eine Liste von Einträgen, die in die Registrierung geschrieben werden, unabhängig davon, ob vorherige Einträge vorhanden sind.

*bRegister*<br/>
Bestimmt, ob die Klasse registriert werden soll. Wenn *bregister* den Wert true hat, wird die-Klasse bei der Systemregistrierung registriert. Andernfalls wird die Registrierung der-Klasse aufgehoben.

### <a name="remarks"></a>Hinweise

Die Registrierungsinformationen werden mithilfe eines Aufrufens von [CDocTemplate:: getdocstring](../../mfc/reference/cdoctemplate-class.md#getdocstring)geladen. Die abgerufenen Teil Zeichenfolgen sind die, `regFileTypeId`die `regFileTypeName`von den `fileNewName`Indizes, und identifiziert werden `GetDocString` , wie in den Referenzseiten beschrieben.

Wenn die `regFileTypeId` Teil Zeichenfolge leer ist oder der- `GetDocString` Aufrufvorgang aus einem anderen Grund fehlschlägt, schlägt diese Funktion fehl, und die Dateiinformationen werden nicht in die Registrierung eingegeben.

Die Informationen in den Argumenten *rglpszregister* und *rglpszüberschreibung* werden über einen aufzurufenden [afxoleregisterserverclass](application-control.md#afxoleregisterserverclass)-Befehl in die Registrierung geschrieben. Die Standardinformationen, die registriert werden, wenn die beiden Argumente NULL sind, eignen sich für die meisten Anwendungen. Informationen zur Struktur der Informationen in diesen Argumenten finden `AfxOleRegisterServerClass`Sie unter.

Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel Hierarchien](../../overview/visual-cpp-samples.md)<br/>
[COleObjectFactory-Klasse](../../mfc/reference/coleobjectfactory-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)
