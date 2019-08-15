---
title: Csecurityattribute-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: ebffbea120101a77450a5e8da3cdb6e34723e7be
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496497"
---
# <a name="csecurityattributes-class"></a>Csecurityattribute-Klasse

Diese Klasse ist ein schlanker Wrapper für die Struktur der Sicherheits Attribute.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Csecurityattribute:: csecurityattribute](#csecurityattributes)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Csecurityattribute:: Set](#set)|Ruft diese Methode auf, um die Attribute des `CSecurityAttributes` -Objekts festzulegen.|

## <a name="remarks"></a>Hinweise

Die `SECURITY_ATTRIBUTES` -Struktur enthält eine [Sicherheits Beschreibung](/windows/win32/api/winnt/ns-winnt-security_descriptor) , die für die Erstellung eines-Objekts verwendet wird, und gibt an, ob das durch Angeben dieser Struktur abgerufene handle vererbbar ist.

Eine Einführung zum Zugriffs Steuerungsmodell in Windows finden Sie unter [Access Control](/windows/win32/SecAuthZ/access-control) in der Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Anforderungen

**Header:** ATLSecurity. h

##  <a name="csecurityattributes"></a>Csecurityattribute:: csecurityattribute

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

##  <a name="set"></a>Csecurityattribute:: Set

Ruft diese Methode auf, um die Attribute des `CSecurityAttributes` -Objekts festzulegen.

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Parameter

*rSecurityDescriptor*<br/>
Verweis auf den Sicherheitsdeskriptor.

*bInheritHandle*<br/>
Gibt an, ob das zurückgegebene Handle geerbt wird, wenn ein neuer Prozess erstellt wird. Wenn dieses Element auf true festgelegt ist, erbt der neue Prozess das Handle.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Konstruktor verwendet, um das `CSecurityAttributes` Objekt zu initialisieren.

## <a name="see-also"></a>Siehe auch

[Sicherheits Beispiel](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[Sicherheits Beschreibung](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
