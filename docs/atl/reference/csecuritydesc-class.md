---
title: CSecurityDesc-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
ms.openlocfilehash: d06ec86b4a049daba945c347f4b424b5987010f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605803"
---
# <a name="csecuritydesc-class"></a>CSecurityDesc-Klasse

Diese Klasse ist ein Wrapper für die `SECURITY_DESCRIPTOR` Struktur.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CSecurityDesc
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|Der Konstruktor.|
|[CSecurityDesc::~CSecurityDesc](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSecurityDesc::FromString](#fromstring)|Konvertiert eine Sicherheitsbeschreibung Zeichenfolgenformat in eine gültige, eine funktionale Sicherheitsbeschreibung.|
|[CSecurityDesc::GetControl](#getcontrol)|Ruft Informationen aus der Sicherheitsbeschreibung zu steuern.|
|[CSecurityDesc::GetDacl](#getdacl)|Discretionary Access Control List (DACL)-Informationen aus der Sicherheitsbeschreibung abgerufen.|
|[CSecurityDesc::GetGroup](#getgroup)|Ruft die primäre Gruppen-Informationen aus der Sicherheitsbeschreibung ab.|
|[CSecurityDesc::GetOwner](#getowner)|Ruft den Besitzer Informationen aus der Sicherheitsbeschreibung ab.|
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Gibt einen Zeiger auf die `SECURITY_DESCRIPTOR` Struktur.|
|[CSecurityDesc::GetSacl](#getsacl)|Ruft die Informationen, System Access Control List (SACL) aus der Sicherheitsbeschreibung ab.|
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|Bestimmt, ob die DACL konfiguriert ist, um automatische Übertragung zu unterstützen.|
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Bestimmt, ob die Sicherheitsbeschreibung mit einer Standard-DACL konfiguriert ist.|
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Bestimmt, ob die Sicherheitsbeschreibung eine DACL enthält.|
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|Bestimmt, ob die DACL konfiguriert ist, um Änderungen zu verhindern.|
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Bestimmt, ob die Sicherheitsbeschreibung Gruppensicherheits-ID (SID) in der Standardeinstellung festgelegt wurde.|
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Bestimmt, ob standardmäßig die Besitzer-SID für die Sicherheitsbeschreibung festgelegt wurde.|
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|Bestimmt, ob die SACL konfiguriert ist, um automatische Übertragung zu unterstützen.|
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Bestimmt, ob die Sicherheitsbeschreibung hat den Standardwert SACL konfiguriert ist.|
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Bestimmt, ob die Sicherheitsbeschreibung eine SACL enthält.|
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|Bestimmt, ob die SACL konfiguriert ist, um Änderungen zu verhindern.|
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Bestimmt, ob die Sicherheitsbeschreibung im selbstbezogenen Format ist.|
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Rufen Sie diese Methode, um die Sicherheitsbeschreibung in das absolute Format zu konvertieren.|
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Rufen Sie diese Methode, um die Sicherheitsbeschreibung in selbstbezogenen Format zu konvertieren.|
|[CSecurityDesc::SetControl](#setcontrol)|Legt die Steuerungsbits einer Sicherheitsbeschreibung fest.|
|[CSecurityDesc::SetDacl](#setdacl)|Legt die Informationen in eine DACL fest. Wenn eine DACL bereits in der Sicherheitsbeschreibung vorhanden ist, wird es ersetzt.|
|[CSecurityDesc::SetGroup](#setgroup)|Legt fest, die eine Sicherheitsbeschreibung absolutes Format, und Ersetzen Sie dabei alle primäre Gruppen-Informationen, die bereits primäre Gruppe.|
|[CSecurityDesc::SetOwner](#setowner)|Legt fest, die Informationen zum Besitzer einer Sicherheitsbeschreibung absolutes Format, und Ersetzen Sie dabei alle Besitzerinformationen, die noch nicht vorhanden sind.|
|[CSecurityDesc::SetSacl](#setsacl)|Legt die Informationen in einer SACL fest. Wenn eine SACL bereits in der Sicherheitsbeschreibung vorhanden ist, wird es ersetzt.|
|[CSecurityDesc::ToString](#tostring)|Eine Sicherheitsbeschreibung konvertiert in ein Zeichenfolgenformat.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Const SECURITY_DESCRIPTOR CSecurityDesc::operator *](#operator_const_security_descriptor__star)|Gibt einen Zeiger auf die `SECURITY_DESCRIPTOR` Struktur.|
|[CSecurityDesc::operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Die `SECURITY_DESCRIPTOR` Struktur enthält die Sicherheitsinformationen, die einem Objekt zugeordnet. Anwendungen verwenden diese Struktur festlegen und Abfragen von Sicherheitsstatus eines Objekts an. Siehe auch [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor).

Anwendungen sollten nicht ändern, die `SECURITY_DESCRIPTOR` Struktur direkt aus, und stattdessen sollte die bereitgestellten Klassenmethoden verwenden.

Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](/windows/desktop/SecAuthZ/access-control) im Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="csecuritydesc"></a>  CSecurityDesc::CSecurityDesc

Der Konstruktor.

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*RS*<br/>
Die `CSecurityDesc` Objekt oder `SECURITY_DESCRIPTOR` Struktur, die dem neuen Server `CSecurityDesc` Objekt.

### <a name="remarks"></a>Hinweise

Die `CSecurityDesc` Objekt kann optional mit erstellt eine `SECURITY_DESCRIPTOR` Struktur oder eine zuvor definierte `CSecurityDesc` Objekt.

##  <a name="dtor"></a>  CSecurityDesc:: ~ CSecurityDesc

Der Destruktor.

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>Hinweise

Der Destruktor gibt alle zugeordnete Ressourcen frei.

##  <a name="fromstring"></a>  CSecurityDesc::FromString

Konvertiert eine Sicherheitsbeschreibung Zeichenfolgenformat in eine gültige, eine funktionale Sicherheitsbeschreibung.

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>Parameter

*pStr*<br/>
Zeiger auf eine auf Null endende Zeichenfolge, enthält die [Zeichenfolgenformat Sicherheitsbeschreibung](/windows/desktop/SecAuthZ/security-descriptor-string-format) konvertiert werden.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg True zurück. Löst eine Ausnahme bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die Zeichenfolge kann erstellt werden, mithilfe von [CSecurityDesc::ToString](#tostring). Die Sicherheitsbeschreibung in einer Zeichenfolge konvertieren erleichtert das Speichern und übertragen.

Diese Methode ruft [wurde von ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora).

##  <a name="getcontrol"></a>  CSecurityDesc:: Getcontrol

Ruft Informationen aus der Sicherheitsbeschreibung zu steuern.

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>Parameter

*psdc*<br/>
Zeiger auf eine `SECURITY_DESCRIPTOR_CONTROL` -Struktur, die die Sicherheitsbeschreibung des Control Informationen empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [GetSecurityDescriptorControl](https://msdn.microsoft.com/library/windows/desktop/aa446647).

##  <a name="getdacl"></a>  CSecurityDesc::GetDacl

Discretionary Access Control List (DACL)-Informationen aus der Sicherheitsbeschreibung abgerufen.

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pDacl*<br/>
Zeiger auf ein `CDacl` Struktur, in der zum Speichern einer Kopie der Sicherheitsdeskriptor-DACL. Wenn eine discretionary ACL vorhanden ist, legt die Methode *pDacl* an die Adresse des discretionary ACL die Sicherheitsbeschreibung. Wenn eine discretionary ACL nicht vorhanden ist, wird kein Wert gespeichert.

*pbPresent*<br/>
Zeiger auf einen Wert, der das Vorhandensein einer discretionary ACL in der angegebenen Sicherheitsbeschreibung angibt. Dieser Parameter wird festgelegt, wenn die Sicherheitsbeschreibung eine discretionary ACL enthält, auf "true". Wenn eine discretionary ACL die Sicherheitsbeschreibung nicht enthält, wird dieser Parameter auf "false" festgelegt.

*pbDefaulted*<br/>
Zeiger auf ein Flag festgelegt wird, auf den Wert des Flags SE_DACL_DEFAULTED in die `SECURITY_DESCRIPTOR_CONTROL` Struktur, wenn eine discretionary ACL für die Sicherheitsbeschreibung vorhanden ist. Wenn dieses Flag auf "true" festgelegt ist, wurde die discretionary ACL durch einen Standardmechanismus abgerufen; False gibt an, wurde die discretionary ACL von einem Benutzer explizit angegeben.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.

##  <a name="getgroup"></a>  CSecurityDesc::GetGroup

Ruft die primäre Gruppen-Informationen aus der Sicherheitsbeschreibung ab.

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf eine [CSid](../../atl/reference/csid-class.md) (Sicherheits-ID), empfängt eine Kopie der Gruppe, die in der CDacl gespeichert.

*pbDefaulted*<br/>
Zeiger auf ein Flag festgelegt wird, auf den Wert des Flags SE_GROUP_DEFAULTED in die `SECURITY_DESCRIPTOR_CONTROL` Struktur, wenn die Methode zurückgibt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.

##  <a name="getowner"></a>  CSecurityDesc::GetOwner

Ruft den Besitzer Informationen aus der Sicherheitsbeschreibung ab.

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf eine [CSid](../../atl/reference/csid-class.md) (Sicherheits-ID), empfängt eine Kopie der Gruppe, die in der CDacl gespeichert.

*pbDefaulted*<br/>
Zeiger auf ein Flag festgelegt wird, auf den Wert des Flags SE_OWNER_DEFAULTED in die `SECURITY_DESCRIPTOR_CONTROL` Struktur, wenn die Methode zurückgibt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.

##  <a name="getpsecurity_descriptor"></a>  CSecurityDesc::GetPSECURITY_DESCRIPTOR

Gibt einen Zeiger auf die `SECURITY_DESCRIPTOR` Struktur.

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) Struktur.

##  <a name="getsacl"></a>  CSecurityDesc::GetSacl

Ruft die Informationen, System Access Control List (SACL) aus der Sicherheitsbeschreibung ab.

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSacl*<br/>
Zeiger auf ein `CSacl` Struktur, in dem eine Kopie der Sicherheitsbeschreibung SACL gespeichert. Wenn ein ACL-System vorhanden ist, legt die Methode *pSacl* an die Adresse des System-ACL die Sicherheitsbeschreibung. Wenn ein ACL-System nicht vorhanden ist, wird kein Wert gespeichert.

*pbPresent*<br/>
Zeiger auf ein Flag die-Methode legt fest, das Vorhandensein eines ACL-Systems in der angegebenen Sicherheitsbeschreibung. Dieser Parameter wird festgelegt, wenn die Sicherheitsbeschreibung ein Systems ACL enthält, auf "true". Wenn die Sicherheitsbeschreibung ein Systems ACL nicht enthält, wird dieser Parameter auf "false" festgelegt.

*pbDefaulted*<br/>
Zeiger auf ein Flag festgelegt wird, auf den Wert des Flags SE_SACL_DEFAULTED in die `SECURITY_DESCRIPTOR_CONTROL` Struktur, wenn ein ACL-System für die Sicherheitsbeschreibung vorhanden ist.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.

##  <a name="isdaclautoinherited"></a>  CSecurityDesc::IsDaclAutoInherited

Bestimmt, ob die DACL (discretionary Access Control List) konfiguriert ist, um automatische Übertragung zu unterstützen.

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Sicherheitsbeschreibung eine DACL das eingerichtet wird enthält, um automatische Übertragung von vererbbar Access-Control-Einträge (ACEs) an vorhandenen untergeordneten Objekte zu unterstützen. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Dieses Bit setzt das System, bei der Vererbung von automatischen Algorithmus für das Objekt und seine untergeordneten Objekte.

##  <a name="isdacldefaulted"></a>  CSecurityDesc::IsDaclDefaulted

Bestimmt, ob die Sicherheitsbeschreibung mit einer Standardliste Zugriffssteuerungsliste (DACL) konfiguriert ist.

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt True zurück, wenn die Sicherheitsbeschreibung eine Standard-DACL, enthält.

### <a name="remarks"></a>Hinweise

Dieses Flag kann beeinflussen, wie das System die DACL, in Bezug auf Vererbung von Access Control Entry (ACE) behandelt. Wenn ein Objekt der Ersteller nicht über eine DACL angibt, empfängt das Objekt z. B. die Standard-DACL aus den der Ersteller des Zugangs-Token. Das System ignoriert dieses Flag an, wenn das SE_DACL_PRESENT-Flag nicht festgelegt ist.

Dieses Flag wird verwendet, um zu bestimmen, wie die endgültige DACL für das Objekt ist, berechnet werden soll, und es werden nicht physisch im Security Descriptor-Steuerelement des sicherungsfähigen Objekts gespeichert.

Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: SetDacl](#setdacl) Methode.

##  <a name="isdaclpresent"></a>  CSecurityDesc::IsDaclPresent

Bestimmt, ob die Sicherheitsbeschreibung eine DACL (discretionary Access Control List) enthält.

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Sicherheitsbeschreibung eine DACL, enthält.

### <a name="remarks"></a>Hinweise

Wenn dieses Flag nicht festgelegt ist, oder wenn dieses Flag wird festgelegt, und die DACL NULL ist, kann die Sicherheitsbeschreibung Vollzugriff auf alle Benutzer.

Dieses Flag wird verwendet, zum Speichern der Sicherheitsinformationen, die von einem Aufrufer angegeben werden, bis die Sicherheitsbeschreibung einem sicherungsfähigen Objekt zugeordnet ist. Sobald die Sicherheitsbeschreibung einem sicherungsfähigen Objekt zugeordnet ist, ist das Flag SE_DACL_PRESENT immer im Security Descriptor-Steuerelement festgelegt.

Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: SetDacl](#setdacl) Methode.

##  <a name="isdaclprotected"></a>  CSecurityDesc::IsDaclProtected

Bestimmt, ob die DACL (discretionary Access Control List) konfiguriert ist, um Änderungen zu verhindern.

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die DACL konfiguriert ist, um zu verhindern, dass die Sicherheitsbeschreibung vererbbar Access-Control-Einträge (ACEs) geändert wird. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: SetDacl](#setdacl) Methode.

Diese Methode unterstützt die automatische Übertragung von vererbbare ACEs.

##  <a name="isgroupdefaulted"></a>  CSecurityDesc::IsGroupDefaulted

Bestimmt, ob die Sicherheitsbeschreibung Gruppensicherheits-ID (SID) in der Standardeinstellung festgelegt wurde.

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>Rückgabewert

"Wahr" zurückgegeben, sofern ein Standardmechanismus, anstatt der ursprüngliche Anbieter der Sicherheitsbeschreibung, der Sicherheitsbeschreibung SID gruppieren. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: setGroup](#setgroup) Methode.

##  <a name="isownerdefaulted"></a>  CSecurityDesc::IsOwnerDefaulted

Bestimmt, ob die Sicherheitsbeschreibung Besitzer-Sicherheits-ID (SID) in der Standardeinstellung festgelegt wurde.

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt True zurück, sofern ein Standardmechanismus, anstatt der ursprüngliche Anbieter der Sicherheitsbeschreibung, die Sicherheitsbeschreibung Besitzer-SID. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: setowner](#setowner) Methode.

##  <a name="issaclautoinherited"></a>  CSecurityDesc::IsSaclAutoInherited

Bestimmt, ob das System eine Zugriffssteuerungsliste (SACL) konfiguriert ist, um automatische Übertragung zu unterstützen.

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Sicherheitsbeschreibung eine SACL das eingerichtet wird enthält, um automatische Übertragung von vererbbar Access-Control-Einträge (ACEs) an vorhandenen untergeordneten Objekte zu unterstützen. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Dieses Bit setzt das System, bei der Vererbung von automatischen Algorithmus für das Objekt und seine untergeordneten Objekte.

##  <a name="issacldefaulted"></a>  CSecurityDesc::IsSaclDefaulted

Bestimmt, ob die Sicherheitsbeschreibung eine standardmäßige System Access Control List (SACL) konfiguriert ist.

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt True zurück, wenn die Sicherheitsbeschreibung eine Standard-SACL, enthält.

### <a name="remarks"></a>Hinweise

Dieses Flag kann beeinflussen, wie das System die SACL, in Bezug auf Vererbung von Access Control Entry (ACE) behandelt. Das System ignoriert dieses Flag an, wenn das SE_SACL_PRESENT-Flag nicht festgelegt ist.

Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: Setsacl](#setsacl) Methode.

##  <a name="issaclpresent"></a>  CSecurityDesc::IsSaclPresent

Bestimmt, ob die Sicherheitsbeschreibung eine System Access Control List, (Systemzugriffssteuerungsliste SACL) enthält.

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Sicherheitsbeschreibung eine SACL, enthält.

### <a name="remarks"></a>Hinweise

Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: Setsacl](#setsacl) Methode.

##  <a name="issaclprotected"></a>  CSecurityDesc::IsSaclProtected

Bestimmt, ob das System eine Zugriffssteuerungsliste (SACL) konfiguriert ist, um Änderungen zu verhindern.

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die SACL konfiguriert ist, um zu verhindern, dass die Sicherheitsbeschreibung vererbbar Access-Control-Einträge (ACEs) geändert wird. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: Setsacl](#setsacl) Methode.

Diese Methode unterstützt die automatische Übertragung von vererbbare ACEs.

##  <a name="isselfrelative"></a>  CSecurityDesc::IsSelfRelative

Bestimmt, ob die Sicherheitsbeschreibung im selbstbezogenen Format ist.

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Sicherheitsbeschreibung im selbstbezogenen Format mit alle Sicherheitsinformationen in einem zusammenhängenden Block Arbeitsspeicher ist. Gibt False zurück, wenn die Sicherheitsbeschreibung im absoluten Format ist. Weitere Informationen finden Sie unter [Absolute und Self-Relative Sicherheitsbeschreibungen](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="makeabsolute"></a>  CSecurityDesc::MakeAbsolute

Rufen Sie diese Methode, um die Sicherheitsbeschreibung in das absolute Format zu konvertieren.

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Methode erfolgreich ist, "false" andernfalls.

### <a name="remarks"></a>Hinweise

Eine Sicherheitsbeschreibung im absoluten Format enthält Zeiger auf die darin enthaltenen Informationen, die anstatt die Informationen selbst. Eine Sicherheitsbeschreibung im selbstbezogenen Format enthält die Informationen in einem zusammenhängenden Speicherblock. Im selbstbezogenen Sicherheitsdeskriptoren eine `SECURITY_DESCRIPTOR` Struktur beginnt immer die Informationen, aber die Sicherheitsbeschreibung der anderen Komponenten können die Struktur in einer beliebigen Reihenfolge folgen. Anstatt Speicheradressen zu verwenden, werden die Komponenten der selbstbezogenen Sicherheitsbeschreibung von Offsets vom Anfang der Sicherheitsbeschreibung identifiziert. Dieses Format ist nützlich, wenn eine Sicherheitsbeschreibung muss auf einem Datenträger gespeichert oder über ein Kommunikationsprotokoll übertragen. Weitere Informationen finden Sie unter [Absolute und Self-Relative Sicherheitsbeschreibungen](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="makeselfrelative"></a>  CSecurityDesc::MakeSelfRelative

Rufen Sie diese Methode, um die Sicherheitsbeschreibung in selbstbezogenen Format zu konvertieren.

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Methode erfolgreich ist, "false" andernfalls.

### <a name="remarks"></a>Hinweise

Eine Sicherheitsbeschreibung im absoluten Format enthält Zeiger auf die darin enthaltenen Informationen, anstatt mit den Informationen selbst. Eine Sicherheitsbeschreibung im selbstbezogenen Format enthält die Informationen in einem zusammenhängenden Speicherblock. Im selbstbezogenen Sicherheitsdeskriptoren eine `SECURITY_DESCRIPTOR` Struktur beginnt immer die Informationen, aber die Sicherheitsbeschreibung der anderen Komponenten können die Struktur in einer beliebigen Reihenfolge folgen. Anstatt Speicheradressen zu verwenden, werden die Komponenten der Sicherheitsbeschreibung von Offsets vom Anfang der Sicherheitsbeschreibung identifiziert. Dieses Format ist nützlich, wenn eine Sicherheitsbeschreibung muss auf einem Datenträger gespeichert oder über ein Kommunikationsprotokoll übertragen. Weitere Informationen finden Sie unter [Absolute und Self-Relative Sicherheitsbeschreibungen](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="operator_eq"></a>  CSecurityDesc::operator =

Zuweisungsoperator.

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*RS*<br/>
Die `SECURITY_DESCRIPTOR` Struktur oder `CSecurityDesc` Objekt, das Zuweisen der `CSecurityDesc` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt die aktualisierte `CSecurityDesc` Objekt.

##  <a name="operator_const_security_descriptor__star"></a>  Const SECURITY_DESCRIPTOR CSecurityDesc::operator *

Wandelt einen Wert in einen Zeiger auf die `SECURITY_DESCRIPTOR` Struktur.

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

##  <a name="setcontrol"></a>  CSecurityDesc::SetControl

Legt die Steuerungsbits einer Sicherheitsbeschreibung fest.

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest,
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>Parameter

*ControlBitsOfInterest*<br/>
Eine SECURITY_DESCRIPTOR_CONTROL-Maske, die die festzulegenden Steuerungsbits angibt. Eine Liste der Flags, die festgelegt werden können, finden Sie unter [SetSecurityDescriptorControl](https://msdn.microsoft.com/library/windows/desktop/aa379582).

*ControlBitsToSet*<br/>
Eine SECURITY_DESCRIPTOR_CONTROL-Maske, die die neuen Werte für die Steuerbits gemäß gibt an die *ControlBitsOfInterest* Maske. Dieser Parameter kann eine Kombination der Flags für aufgeführt sein der *ControlBitsOfInterest* Parameter.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [SetSecurityDescriptorControl](https://msdn.microsoft.com/library/windows/desktop/aa379582).

##  <a name="setdacl"></a>  CSecurityDesc:: SetDacl

Legt die Informationen in eine DACL (discretionary Access Control List) fest. Wenn eine DACL bereits in der Sicherheitsbeschreibung vorhanden ist, wird es ersetzt.

```
inline void SetDacl(
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parameter

*DACL*<br/>
Ein Verweis auf eine `CDacl` Objekt, das die DACL für die Sicherheitsbeschreibung angibt. Dieser Parameter darf nicht NULL sein. Um eine NULL-DACL in der Sicherheitsbeschreibung festgelegt wird, sollte die erste Form der Methode mit verwendet werden *bPresent* auf "false" festgelegt.

*bPresent*<br/>
Gibt ein Flag, der angibt, des Vorhandenseins eine DACL in der Sicherheitsbeschreibung. Wenn dieser Parameter auf "true" festgelegt ist, bestimmt die Methode die SE_DACL_PRESENT-Flag in der `SECURITY_DESCRIPTOR_CONTROL` strukturieren und verwendet die Werte in der *Dacl* und *bDefaulted* Parameter. Wenn sie falsch ist, wird die Methode löscht das Flag SE_DACL_PRESENT und *bDefaulted* wird ignoriert.

*bDefaulted*<br/>
Gibt ein Flag, das die Quelle des der DACL angibt. Wenn dieses Flag auf "true" festgelegt ist, hat die DACL über einen Standardmechanismus abgerufen wurde. False gibt an, wurde die DACL explizit von einem Benutzer angegeben. Die Methode speichert diesen Wert in das Flag SE_DACL_DEFAULTED des der `SECURITY_DESCRIPTOR_CONTROL` Struktur. Wenn dieser Parameter nicht angegeben ist, wird das Flag SE_DACL_DEFAULTED gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Es ist ein wichtiger Unterschied zwischen einer leeren und eine nicht vorhandene DACL. Wenn eine DACL leer ist, er enthält keine Access-Control-Einträge und keine Zugriffsrechte explizit erteilt wurde. Zugriff auf das Objekt wird daher implizit verweigert. Wenn ein Objekt keine DACL verfügt, auf der anderen Seite ist kein Schutz auf das Objekt zugewiesen, und wird jede zugriffsanforderung gewährt.

##  <a name="setgroup"></a>  CSecurityDesc:: setGroup

Legt fest, die eine Sicherheitsbeschreibung absolutes Format, und Ersetzen Sie dabei alle primäre Gruppen-Informationen, die bereits primäre Gruppe.

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parameter

*SID*<br/>
Ein Verweis auf eine [CSid](../../atl/reference/csid-class.md) -Objekt für die Sicherheitsbeschreibung neue primäre Gruppe. Dieser Parameter darf nicht NULL sein. Eine Sicherheitsbeschreibung kann gekennzeichnet werden, ohne eine DACL oder eine SACL, jedoch muss eine Gruppe und Besitzer kann es dazu sogar werden die NULL-SID (die eine integrierte SID mit einer speziellen Bedeutung).

*bDefaulted*<br/>
Gibt an, ob ein Standardmechanismus für die primäre Gruppeninformationen abgeleitet wurde. Wenn dieser Wert "true ist" Standardinformationen, und es die Methode diesen Wert als das SE_GROUP_DEFAULTED-Kennzeichen in speichert der `SECURITY_DESCRIPTOR_CONTROL` Struktur. Wenn dieser Parameter 0 (null) ist, wird das Flag SE_GROUP_DEFAULTED gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

##  <a name="setowner"></a>  CSecurityDesc:: SetOwner

Legt fest, die Informationen zum Besitzer der Sicherheitsbeschreibung ein absolutes Format. Alle bereits vorhandenen Besitzerinformationen ersetzt.

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parameter

*SID*<br/>
Die [CSid](../../atl/reference/csid-class.md) -Objekt für die Sicherheitsbeschreibung des neuen primären Besitzer. Dieser Parameter darf nicht NULL sein.

*bDefaulted*<br/>
Gibt an, ob ein Standardmechanismus für die Informationen zum Besitzer abgeleitet wird. Wenn dieser Wert auf "true" festgelegt ist, ist es Standardinformationen an. Die Methode speichert diesen Wert als das SE_OWNER_DEFAULTED-Kennzeichen in der `SECURITY_DESCRIPTOR_CONTROL` Struktur. Wenn dieser Parameter 0 (null) ist, wird das Flag SE_OWNER_DEFAULTED gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

##  <a name="setsacl"></a>  CSecurityDesc:: Setsacl

Legt die Informationen in eine System Access Control List, (Systemzugriffssteuerungsliste SACL) fest. Wenn eine SACL bereits in der Sicherheitsbeschreibung vorhanden ist, wird es ersetzt.

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parameter

*SACL*<br/>
Zeiger auf ein `CSacl` Objekt, das die SACL für das die Sicherheitsbeschreibung angibt. Dieser Parameter darf nicht NULL sein und muss ein CSacl-Objekt sein. Im Gegensatz zu den DACLs besteht kein Unterschied zwischen NULL und einem leeren SACL, wie die SACL-Objekte nicht nur Überwachungsinformationen Zugriffsrechte angeben.

*bDefaulted*<br/>
Gibt ein Flag zur Angabe der Quelle von der SACL an. Wenn dieses Flag auf "true" festgelegt ist, wurde die SACL über einen Standardmechanismus abgerufen. False gibt an, wurde die SACL explizit von einem Benutzer angegeben. Die Methode speichert diesen Wert in das Flag SE_SACL_DEFAULTED des der `SECURITY_DESCRIPTOR_CONTROL` Struktur. Wenn dieser Parameter nicht angegeben ist, wird das Flag SE_SACL_DEFAULTED gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

##  <a name="tostring"></a>  CSecurityDesc::ToString

Eine Sicherheitsbeschreibung konvertiert in ein Zeichenfolgenformat.

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>Parameter

*pStr*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge, die erhält die [Zeichenfolgenformat Sicherheitsbeschreibung](/windows/desktop/SecAuthZ/security-descriptor-string-format).

*SI*<br/>
Gibt eine Kombination von Bitflags SECURITY_INFORMATION, an die Komponenten der Sicherheitsbeschreibung aus, in die Ausgabezeichenfolge einzuschließen.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Sobald die Sicherheitsbeschreibung im Zeichenfolgenformat ist, kann es einfacher gespeichert oder übertragen werden. Verwenden der `CSecurityDesc::FromString` Methode, um die Zeichenfolge in eine Sicherheitsbeschreibung zurück konvertieren.

Die *Si* Parameter kann die folgenden SECURITY_INFORMATION Flags enthalten:

|Wert|Bedeutung|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|Sind Sie des Besitzers.|
|GROUP_SECURITY_INFORMATION|Enthalten Sie die primäre Gruppe.|
|DACL_SECURITY_INFORMATION|Enthalten Sie die DACL.|
|SACL_SECURITY_INFORMATION|Enthalten Sie die SACL.|

Wenn die DACL NULL ist, und die SE_DACL_PRESENT-Steuerelement-Bit, in der Sicherheitsbeschreibung für die Eingabe gesetzt ist, schlägt die Methode fehl.

Wenn die DACL NULL ist, und die SE_DACL_PRESENT Steuerbit ist nicht in der Eingabe Sicherheitsbeschreibung festgelegt, muss die resultierende sicherheitsbeschreibungs-Zeichenfolge eine Komponente "d:" nicht. Finden Sie unter [Sicherheitsbeschreibungsformat Zeichenfolge](/windows/desktop/SecAuthZ/security-descriptor-string-format) Weitere Details.

Diese Methode ruft [wurde von ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora).

## <a name="see-also"></a>Siehe auch

[Beispiel für die Sicherheit](../../visual-cpp-samples.md)<br/>
[SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
