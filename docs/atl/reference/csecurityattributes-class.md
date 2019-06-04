---
title: CSecurityAttributes-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: b26de7a2a3426ed2fe86bd7ef50f6c5410fa5364
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503195"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes-Klasse

Diese Klasse ist ein einfacher Wrapper für die Struktur der Sicherheits-Attribute.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSecurityAttributes::Set](#set)|Rufen Sie diese Methode, um die Attribute der Festlegen der `CSecurityAttributes` Objekt.|

## <a name="remarks"></a>Hinweise

Die `SECURITY_ATTRIBUTES` Struktur enthält eine [Sicherheitsbeschreibung](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) für die Erstellung eines Objekts verwendet, und gibt an, ob das Handle abgerufen werden, durch Angeben dieser Struktur geerbt werden kann.

Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](/windows/desktop/SecAuthZ/access-control) im Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes

Der Konstruktor.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>Parameter

*rSecurityDescriptor*<br/>
Verweis auf den Sicherheitsdeskriptor.

*bInheritsHandle*<br/>
Gibt an, ob das zurückgegebene Handle geerbt wird, wenn ein neuer Prozess erstellt wird. Wenn dieses Element auf true festgelegt ist, erbt der neue Prozess das Handle.

##  <a name="set"></a>  CSecurityAttributes:: Set

Rufen Sie diese Methode, um die Attribute der Festlegen der `CSecurityAttributes` Objekt.

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Parameter

*rSecurityDescriptor*<br/>
Verweis auf den Sicherheitsdeskriptor.

*bInheritHandle*<br/>
Gibt an, ob das zurückgegebene Handle geerbt wird, wenn ein neuer Prozess erstellt wird. Wenn dieses Element auf true festgelegt ist, erbt der neue Prozess das Handle.

### <a name="remarks"></a>Hinweise

Diese Methode wird verwendet, durch den Konstruktor zum Initialisieren der `CSecurityAttributes` Objekt.

## <a name="see-also"></a>Siehe auch

[Beispiel für die Sicherheit](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[Sicherheitsbeschreibung](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
