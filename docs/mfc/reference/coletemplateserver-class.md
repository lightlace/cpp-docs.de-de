---
title: COleTemplateServer-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: aef24acf61aae2d6690e5f302822ce52aaa4917a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427159"
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
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Stellt eine Verbindung her einer Dokumentvorlage an den zugrunde liegenden `COleObjectFactory` Objekt.|
|[COleTemplateServer::Unregister](#unregister)|Hebt die Registrierung der Vorlage zugeordnete Dokument.|
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Registriert den Typ der Dokumente mit der Registrierung des OLE-Systems an.|

## <a name="remarks"></a>Hinweise

Diese Klasse wird von der Klasse abgeleitet [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); in der Regel können Sie `COleTemplateServer` direkt, anstatt eine eigene Klasse ableiten. `COleTemplateServer` verwendet eine [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) Objekt, um den Serverdokumenten zu verwalten. Verwendung `COleTemplateServer` bei der Implementierung von eines vollständigen Servers, d. h. ein, die als eigenständige Anwendung ausgeführt werden können. Vollständige Servern sind in der Regel mehrere Dokument Interface (MDI)-Anwendungen, obwohl Anwendungen Schnittstelle (SDI) für einzelne Dokumente unterstützt werden. Eine `COleTemplateServer` Objekt ist erforderlich, für jeden Typ von Server-Dokument, eine Anwendung unterstützt, d. h., wenn die Serveranwendung sowohl Arbeitsblätter und Diagramme unterstützt, benötigen Sie zwei `COleTemplateServer` Objekte.

`COleTemplateServer` überschreibt die `OnCreateInstance` -Memberfunktion von definiert `COleObjectFactory`. Diese Memberfunktion wird durch das Framework zum Erstellen eines C++-Objekts des richtigen Typs aufgerufen.

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

Eine kurze Beschreibung zur Verwendung von der `COleTemplateServer` Klasse, finden Sie unter den [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) Übersicht über die Klasse.

##  <a name="connecttemplate"></a>  COleTemplateServer::ConnectTemplate

Verbindet die Dokumentvorlage zeigt *pDocTemplate* auf den zugrunde liegenden [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) Objekt.

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
Zeiger auf die Dokumentvorlage.

*bMultiInstance*<br/>
Gibt an, ob eine einzelne Instanz der Anwendung mehrere Instanziierungen unterstützt. Wenn "true" werden mehrere Instanzen der Anwendung für jede Anforderung zum Erstellen eines Objekts gestartet.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Schlüssel CLSID](/windows/desktop/com/clsid-key-hklm) im Windows SDK.

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

Lädt Informationen über den Dateityp aus der Dokumentvorlage Zeichenfolge und speichert diese Informationen in der OLE-systemregistrierung.

```
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Parameter

*nAppType*<br/>
Ein Wert aus der OLE_APPTYPE-Enumeration, die in AFXDISP definiert ist. H. Sie können eine der folgenden Werte haben:

- OAT_INPLACE_SERVER-Server verfügt über vollständigen Benutzeroberfläche.

- OAT_SERVER-Server unterstützt nur einbetten.

- OAT_CONTAINER-Container unterstützt Links zu eingebetteten Objekte.

- OAT_DISPATCH_OBJECT-Objekt ist `IDispatch`-fähig.

- OAT_DOC_OBJECT_SERVER-Server unterstützt sowohl einbetten und die Komponentenmodell Document-Objekt.

*rglpszRegister*<br/>
Eine Liste der Einträge, die in die Registrierung geschrieben werden, nur dann, wenn keine Einträge vorhanden sind.

*rglpszOverwrite*<br/>
Eine Liste der Einträge, die geschrieben werden, in die Registrierung, unabhängig davon, ob alle vorherigen Einträge vorhanden sind.

*bRegistrieren Sie sich*<br/>
Bestimmt, ob die Klasse ist, registriert werden. Wenn *bRegistrieren Sie sich* ist "true", die Klasse mit der Registrierung registriert ist. Andernfalls, hebt die Registrierung für sie der Klasse.

### <a name="remarks"></a>Hinweise

Die Registrierungsinformationen erfolgt durch einen Aufruf von [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Die Teilzeichenfolgen, die abgerufen werden die Indizes identifiziert, welche `regFileTypeId`, `regFileTypeName`, und `fileNewName`gemäß der Beschreibung in der `GetDocString` auf den Referenzseiten.

Wenn die `regFileTypeId` Teilzeichenfolge leer ist oder wenn der Aufruf von `GetDocString` ein Fehler auftritt, einem anderen Grund, diese Funktion ein Fehler auftritt, und die Informationen in der Registrierung nicht eingegeben wird.

Die Informationen in den Argumenten *RglpszRegister* und *RglpszOverwrite* richtet sich an der Registrierung durch einen Aufruf von [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). Informationen über das Standardformat, das registriert wird, wenn die beiden Argumente NULL sind, ist für die meisten Anwendungen geeignet. Informationen für die Struktur der Informationen in diesen Argumenten finden Sie unter `AfxOleRegisterServerClass`.

Weitere Informationen finden Sie unter [Implementieren der IDispatch-Schnittstelle](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)<br/>
[COleObjectFactory-Klasse](../../mfc/reference/coleobjectfactory-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleServerItem-Klasse](../../mfc/reference/coleserveritem-class.md)
