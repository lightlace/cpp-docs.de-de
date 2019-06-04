---
title: CPrivateObjectSecurityDesc-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
ms.openlocfilehash: cc726892515ea38a559bdf182affa96f84be3449
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503302"
---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc-Klasse

Diese Klasse stellt ein privates Objekt sicherheitsbeschreibungs-Objekt.

## <a name="syntax"></a>Syntax

```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|Der Konstruktor.|
|[CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|Rufen Sie diese Methode, um eine Sicherheitsbeschreibung und die Zugriffssteuerungslisten (ACLs) in ein Format zu konvertieren, die automatische Übertragung von vererbbar Access-Control-Einträge (ACEs) unterstützt.|
|[CPrivateObjectSecurityDesc::Create](#create)|Rufen Sie diese Methode, um reservieren und initialisieren eine selbstbezogenen Sicherheitsbeschreibung für das private Objekt, das von der aufrufenden Ressourcen-Manager erstellt.|
|[CPrivateObjectSecurityDesc::Get](#get)|Rufen Sie diese Methode zum Abrufen von Informationen aus der Sicherheitsbeschreibung für ein privates Objekt auf.|
|[CPrivateObjectSecurityDesc::Set](#set)|Rufen Sie diese Methode, um die Sicherheitsbeschreibung für ein privates Objekt zu ändern.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Diese Klasse, aus abgeleiteten [CSecurityDesc](../../atl/reference/csecuritydesc-class.md), stellt Methoden zum Erstellen und verwalten die Sicherheitsbeschreibung für ein privates Objekt bereit.

Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](/windows/desktop/SecAuthZ/access-control) im Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)

`CPrivateObjectSecurityDesc`

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="converttoautoinherit"></a>  CPrivateObjectSecurityDesc::ConvertToAutoInherit

Rufen Sie diese Methode, um eine Sicherheitsbeschreibung und die Zugriffssteuerungslisten (ACLs) in ein Format zu konvertieren, die automatische Übertragung von vererbbar Access-Control-Einträge (ACEs) unterstützt.

```
bool ConvertToAutoInherit(
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Parameter

*pParent*<br/>
Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt, das auf den übergeordneten Container des Objekts. Wenn keine übergeordnete Container vorhanden ist, ist dieser Parameter NULL an.

*ObjectType*<br/>
Zeiger auf eine `GUID` Struktur, die den Typ des Objekts mit dem aktuellen Objekt verbundenen bezeichnet. Legen Sie *ObjectType* auf NULL, wenn das Objekt nicht mit eine GUID verfügt.

*bIsDirectoryObject*<br/>
Gibt an, ob das neue Objekt andere Objekte enthalten kann. Der Wert "true" gibt an, dass das neue Objekt ein Container. Der Wert "false" gibt an, dass das neue Objekt kein Container ist.

*GenericMapping*<br/>
Zeiger auf eine [GENERIC_MAPPING](/windows/desktop/api/winnt/ns-winnt-_generic_mapping) Struktur, die die Zuordnung von einzelnen generischen Rechte, bestimmte Rechte für das Objekt angibt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Diese Methode versucht zu bestimmen, ob die ACEs in der Zugriffssteuerungsliste (DACL) auflisten und die System Access Control List (SACL) der aktuellen Sicherheitsbeschreibung wurden aus der Sicherheitsbeschreibung des übergeordneten geerbt. Ruft die [ConvertToAutoInheritPrivateObjectSecurity](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-converttoautoinheritprivateobjectsecurity) Funktion.

##  <a name="cprivateobjectsecuritydesc"></a>  CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc

Der Konstruktor.

```
CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Hinweise

Initialisiert das `CPrivateObjectSecurityDesc`-Objekt.

##  <a name="dtor"></a>  CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc

Der Destruktor.

```
~CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Hinweise

Der Destruktor gibt alle zugeordnete Ressourcen frei und löscht die Sicherheitsbeschreibung des Objekts, auf die private.

##  <a name="create"></a>  CPrivateObjectSecurityDesc::Create

Rufen Sie diese Methode, um reservieren und initialisieren eine selbstbezogenen Sicherheitsbeschreibung für das private Objekt, das von der aufrufenden Ressourcen-Manager erstellt.

```
bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Parameter

*pParent*<br/>
Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt, das auf das übergeordnete Verzeichnis, in dem ein neues Objekt erstellt wird. Auf NULL festgelegt, wenn kein übergeordnetes Verzeichnis vorhanden ist.

*pCreator*<br/>
Zeiger auf eine Sicherheitsbeschreibung, die durch den Ersteller des Objekts angegeben. Wenn der Ersteller des Objekts nicht explizit die Sicherheitsinformationen für das neue Objekt besteht, wird dieser Parameter auf NULL festgelegt.

*bIsDirectoryObject*<br/>
Gibt an, ob das neue Objekt andere Objekte enthalten kann. Der Wert "true" gibt an, dass das neue Objekt ein Container. Der Wert "false" gibt an, dass das neue Objekt kein Container ist.

*Token*<br/>
Ein Verweis auf die [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt für den Clientprozess, in dessen Namen das Objekt erstellt wird.

*GenericMapping*<br/>
Zeiger auf eine [GENERIC_MAPPING](/windows/desktop/api/winnt/ns-winnt-_generic_mapping) Struktur, die die Zuordnung von einzelnen generischen Rechte, bestimmte Rechte für das Objekt angibt.

*ObjectType*<br/>
Zeiger auf eine `GUID` Struktur, die den Typ des Objekts mit dem aktuellen Objekt verbundenen bezeichnet. Legen Sie *ObjectType* auf NULL, wenn das Objekt nicht mit eine GUID verfügt.

*bIsContainerObject*<br/>
Gibt an, ob das neue Objekt andere Objekte enthalten kann. Der Wert "true" gibt an, dass das neue Objekt ein Container. Der Wert "false" gibt an, dass das neue Objekt kein Container ist.

*AutoInheritFlags*<br/>
Ein Satz von Bitflags, die steuern, wie Access Control-Einträge (ACEs) von übernommenen *pParent*. Finden Sie unter [CreatePrivateObjectSecurityEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) Weitere Details.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [CreatePrivateObjectSercurity](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity) oder [CreatePrivateObjectSecurityEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex).

Die zweite Methode ermöglicht das Angeben der GUID des Objekttyp des neuen Objekts oder steuern, wie ACEs geerbt werden.

> [!NOTE]
>  Eine selbstbezogenen Sicherheitsbeschreibung ist eine Sicherheitsbeschreibung, die alle die Sicherheitsinformationen in einen zusammenhängenden Speicherblock gespeichert.

##  <a name="get"></a>  CPrivateObjectSecurityDesc::Get

Rufen Sie diese Methode zum Abrufen von Informationen aus der Sicherheitsbeschreibung für ein privates Objekt auf.

```
bool Get(
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```

### <a name="parameters"></a>Parameter

*si*<br/>
Ein Satz von Bitflags, die angeben, die Teile der Sicherheitsbeschreibung abgerufen werden soll. Dieser Wert kann eine Kombination von werden die [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) Bitflags.

*pResult*<br/>
Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt, das eine Kopie der angeforderten Informationen aus der angegebenen Sicherheitsbeschreibung empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Die Sicherheitsbeschreibung ist eine Struktur und die zugehörigen Daten, die die Sicherheitsinformationen für ein sicherungsfähiges Objekt enthält.

##  <a name="operator_eq"></a>  CPrivateObjectSecurityDesc::operator =

Zuweisungsoperator.

```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Die `CPrivateObjectSecurityDesc` Objekt, das dem aktuellen Objekt zugewiesen.

### <a name="return-value"></a>Rückgabewert

Gibt die aktualisierte `CPrivateObjectSecurityDesc` Objekt.

##  <a name="set"></a>  CPrivateObjectSecurityDesc::Set

Rufen Sie diese Methode, um die Sicherheitsbeschreibung für ein privates Objekt zu ändern.

```
bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```

### <a name="parameters"></a>Parameter

*si*<br/>
Ein Satz von Bitflags, die angeben, die Teile der Sicherheitsbeschreibung fest. Dieser Wert kann eine Kombination von werden die [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) Bitflags.

*Änderung*<br/>
Zeiger auf eine [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) Objekt. Die Teile dieser Sicherheitsbeschreibung angegeben wird, durch die *Si* -Parameters auf die Sicherheitsbeschreibung des Objekts angewendet werden.

*GenericMapping*<br/>
Zeiger auf eine [GENERIC_MAPPING](/windows/desktop/api/winnt/ns-winnt-_generic_mapping) Struktur, die die Zuordnung von einzelnen generischen Rechte, bestimmte Rechte für das Objekt angibt.

*Token*<br/>
Ein Verweis auf die [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt für den Clientprozess, in dessen Namen das Objekt erstellt wird.

*AutoInheritFlags*<br/>
Ein Satz von Bitflags, die steuern, wie Access Control-Einträge (ACEs) von übernommenen *pParent*. Finden Sie unter [CreatePrivateObjectSecurityEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex) Weitere Details.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Die zweite Methode ermöglicht das Angeben des Objekttyp GUID des Objekts oder steuern, wie ACEs geerbt werden.

## <a name="see-also"></a>Siehe auch

[SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)<br/>
[CSecurityDesc-Klasse](../../atl/reference/csecuritydesc-class.md)
