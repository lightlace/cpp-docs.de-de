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
ms.openlocfilehash: a9e0eb01608edf29f99209dffc932630ad08807a
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915709"
---
# <a name="csecuritydesc-class"></a>CSecurityDesc-Klasse

Diese Klasse ist ein Wrapper für die `SECURITY_DESCRIPTOR` -Struktur.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

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
|[CSecurityDesc::FromString](#fromstring)|Konvertiert eine Sicherheits Beschreibung für den Zeichen folgen Format in einen gültigen funktionalen Sicherheits Deskriptor.|
|[CSecurityDesc::GetControl](#getcontrol)|Ruft Steuerungsinformationen aus der Sicherheits Beschreibung ab.|
|[CSecurityDesc::GetDacl](#getdacl)|Ruft von der Sicherheits Beschreibung freigegebene DACL-Informationen (Access Control List, Zugriffs Steuerungs Liste) ab.|
|[CSecurityDesc::GetGroup](#getgroup)|Ruft die primären Gruppeninformationen aus der Sicherheits Beschreibung ab.|
|[CSecurityDesc::GetOwner](#getowner)|Ruft die Besitzer Information von der Sicherheits Beschreibung ab.|
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Gibt einen Zeiger auf die `SECURITY_DESCRIPTOR` -Struktur zurück.|
|[CSecurityDesc::GetSacl](#getsacl)|Ruft SACL (System Access Control List)-Informationen aus der Sicherheits Beschreibung ab.|
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|Bestimmt, ob die DACL für die Unterstützung der automatischen Propagierung konfiguriert ist.|
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Bestimmt, ob die Sicherheits Beschreibung mit einer Standard-DACL konfiguriert ist.|
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Bestimmt, ob die Sicherheits Beschreibung eine DACL enthält.|
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|Bestimmt, ob die DACL konfiguriert ist, um Änderungen zu verhindern.|
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Bestimmt, ob die Gruppen Sicherheits-ID (SID) der Sicherheits Beschreibung standardmäßig festgelegt wurde.|
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Bestimmt, ob die Besitzer-SID der Sicherheits Beschreibung standardmäßig festgelegt wurde.|
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|Bestimmt, ob die SACL für die Unterstützung der automatischen Propagierung konfiguriert ist.|
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Bestimmt, ob die Sicherheits Beschreibung mit einer Standard-SACL konfiguriert ist.|
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Bestimmt, ob die Sicherheits Beschreibung eine SACL enthält.|
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|Bestimmt, ob die SACL konfiguriert ist, um Änderungen zu verhindern.|
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Bestimmt, ob die Sicherheits Beschreibung in einem selbst relativen Format vorliegt.|
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Mit dieser Methode wird die Sicherheits Beschreibung in das absolute Format konvertiert.|
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Mit dieser Methode wird die Sicherheits Beschreibung in das selbst relative Format konvertiert.|
|[CSecurityDesc::SetControl](#setcontrol)|Legt die Steuerungsbits einer Sicherheitsbeschreibung fest.|
|[CSecurityDesc::SetDacl](#setdacl)|Legt Informationen in einer DACL fest. Wenn eine DACL bereits in der Sicherheits Beschreibung vorhanden ist, wird Sie ersetzt.|
|[CSecurityDesc::SetGroup](#setgroup)|Legt die primären Gruppeninformationen einer Sicherheits Beschreibung im absoluten Format fest und ersetzt alle bereits vorhandenen primären Gruppeninformationen.|
|[CSecurityDesc::SetOwner](#setowner)|Legt die Besitzer Informationen einer Sicherheits Beschreibung des absoluten Formats fest, wobei alle bereits vorhandenen Besitzer Informationen ersetzt werden.|
|[CSecurityDesc::SetSacl](#setsacl)|Legt Informationen in einer SACL fest. Wenn eine SACL bereits in der Sicherheits Beschreibung vorhanden ist, wird Sie ersetzt.|
|[CSecurityDesc::ToString](#tostring)|Konvertiert eine Sicherheits Beschreibung in ein Zeichen folgen Format.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CSecurityDesc:: Operator Konstanten SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|Gibt einen Zeiger auf die `SECURITY_DESCRIPTOR` -Struktur zurück.|
|[CSecurityDesc::operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Die `SECURITY_DESCRIPTOR` -Struktur enthält die einem Objekt zugeordneten Sicherheitsinformationen. Anwendungen verwenden diese Struktur, um den Sicherheitsstatus eines Objekts festzulegen und abzufragen. Siehe auch [atlgetsecuritydescriptor](security-global-functions.md#atlgetsecuritydescriptor).

Anwendungen sollten die `SECURITY_DESCRIPTOR` Struktur nicht direkt ändern und stattdessen die bereitgestellten Klassen Methoden verwenden.

Eine Einführung zum Zugriffs Steuerungsmodell in Windows finden Sie unter [Access Control](/windows/desktop/SecAuthZ/access-control) in der Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** ATLSecurity. h

##  <a name="csecuritydesc"></a>CSecurityDesc:: CSecurityDesc

Der Konstruktor.

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Das `CSecurityDesc` Objekt oder `SECURITY_DESCRIPTOR` die Struktur, die dem neuen `CSecurityDesc` -Objekt zugewiesen werden soll.

### <a name="remarks"></a>Hinweise

Das `CSecurityDesc` Objekt kann optional mithilfe einer `SECURITY_DESCRIPTOR` Struktur oder eines zuvor definierten `CSecurityDesc` Objekts erstellt werden.

##  <a name="dtor"></a>CSecurityDesc:: ~ CSecurityDesc

Der Destruktor.

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>Hinweise

Der Dekonstruktor gibt alle zugeordneten Ressourcen frei.

##  <a name="fromstring"></a>CSecurityDesc:: FromString

Konvertiert eine Sicherheits Beschreibung für den Zeichen folgen Format in einen gültigen funktionalen Sicherheits Deskriptor.

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>Parameter

*pstr*<br/>
Zeiger auf eine auf NULL endende Zeichenfolge, die die zu konvertierende [Sicherheits Beschreibung](/windows/desktop/SecAuthZ/security-descriptor-string-format) für das Zeichen folgen Format enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück. Löst bei einem Fehler eine Ausnahme aus.

### <a name="remarks"></a>Hinweise

Die Zeichenfolge kann mithilfe von [CSecurityDesc:: destring](#tostring)erstellt werden. Wenn die Sicherheits Beschreibung in eine Zeichenfolge umgewandelt wird, ist Sie leichter zu speichern und zu übertragen.

Diese Methode ruft [convertstringsecuritydescriptortosecuritydescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora)auf.

##  <a name="getcontrol"></a>CSecurityDesc:: GetControl

Ruft Steuerungsinformationen aus der Sicherheits Beschreibung ab.

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>Parameter

*psdc*<br/>
Ein Zeiger auf `SECURITY_DESCRIPTOR_CONTROL` eine-Struktur, die die Steuerungsinformationen des Sicherheits Deskriptors empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Methode erfolgreich ist, andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [getsecuritydescriptorcontrol](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-getsecuritydescriptorcontrol)auf.

##  <a name="getdacl"></a>CSecurityDesc:: GetDacl

Ruft von der Sicherheits Beschreibung freigegebene DACL-Informationen (Access Control List, Zugriffs Steuerungs Liste) ab.

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pDacl*<br/>
Ein Zeiger auf `CDacl` eine-Struktur, in der eine Kopie der DACL der Sicherheits Beschreibung gespeichert werden soll. Wenn eine freigegebene ACL vorhanden ist, legt die-Methode *pdacl* auf die Adresse der freigegebenen ACL der Sicherheits Beschreibung fest. Wenn keine freigegebene ACL vorhanden ist, wird kein Wert gespeichert.

*pbPresent*<br/>
Ein Zeiger auf einen Wert, der das vorhanden sein einer freigegebenen ACL in der angegebenen Sicherheits Beschreibung angibt. Wenn die Sicherheits Beschreibung eine freigegebene ACL enthält, wird dieser Parameter auf "true" festgelegt. Wenn die Sicherheits Beschreibung keine freigegebene ACL enthält, wird dieser Parameter auf "false" festgelegt.

*pbDefaulted*<br/>
Ein Zeiger auf ein Flag, das auf den Wert des SE_DACL_DEFAULTED-Flags `SECURITY_DESCRIPTOR_CONTROL` in der Struktur festgelegt ist, wenn eine freigegebene ACL für die Sicherheits Beschreibung vorhanden ist. Wenn dieses Flag "true" ist, wurde die freigegebene ACL von einem Standardmechanismus abgerufen. false gibt an, dass die freigegebene ACL explizit von einem Benutzer angegeben wurde.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Methode erfolgreich ist, andernfalls false.

##  <a name="getgroup"></a>CSecurityDesc:: GetGroup

Ruft die primären Gruppeninformationen aus der Sicherheits Beschreibung ab.

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Ein Zeiger auf eine [CSID](../../atl/reference/csid-class.md) (Sicherheits-ID), die eine Kopie der in der CDacl gespeicherten Gruppe empfängt.

*pbDefaulted*<br/>
Zeiger auf ein Flag, das auf den Wert des SE_GROUP_DEFAULTED-Flags in `SECURITY_DESCRIPTOR_CONTROL` der-Struktur festgelegt wird, wenn die-Methode zurückgibt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Methode erfolgreich ist, andernfalls false.

##  <a name="getowner"></a>CSecurityDesc:: GetOwner

Ruft die Besitzer Information von der Sicherheits Beschreibung ab.

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Ein Zeiger auf eine [CSID](../../atl/reference/csid-class.md) (Sicherheits-ID), die eine Kopie der in der CDacl gespeicherten Gruppe empfängt.

*pbDefaulted*<br/>
Zeiger auf ein Flag, das auf den Wert des SE_OWNER_DEFAULTED-Flags in `SECURITY_DESCRIPTOR_CONTROL` der-Struktur festgelegt wird, wenn die-Methode zurückgibt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Methode erfolgreich ist, andernfalls false.

##  <a name="getpsecurity_descriptor"></a>CSecurityDesc:: GetPSECURITY_DESCRIPTOR

Gibt einen Zeiger auf die `SECURITY_DESCRIPTOR` -Struktur zurück.

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-security_descriptor) -Struktur zurück.

##  <a name="getsacl"></a>CSecurityDesc:: gezacl

Ruft SACL (System Access Control List)-Informationen aus der Sicherheits Beschreibung ab.

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSacl*<br/>
Ein Zeiger auf `CSacl` eine-Struktur, in der eine Kopie der SACL der Sicherheits Deskriptoren gespeichert werden soll. Wenn eine System-ACL vorhanden ist, legt die-Methode *psacl* auf die Adresse der System-ACL der Sicherheits Beschreibung fest. Wenn keine System-ACL vorhanden ist, wird kein Wert gespeichert.

*pbPresent*<br/>
Zeiger auf ein Flag, das die-Methode festlegt, um das vorhanden sein einer System-ACL in der angegebenen Sicherheits Beschreibung anzugeben. Wenn die Sicherheits Beschreibung eine System-ACL enthält, wird dieser Parameter auf "true" festgelegt. Wenn die Sicherheits Beschreibung keine System-ACL enthält, wird dieser Parameter auf "false" festgelegt.

*pbDefaulted*<br/>
Ein Zeiger auf ein Flag, das auf den Wert des SE_SACL_DEFAULTED-Flags `SECURITY_DESCRIPTOR_CONTROL` in der Struktur festgelegt ist, wenn eine System-ACL für die Sicherheits Beschreibung vorhanden ist.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Methode erfolgreich ist, andernfalls false.

##  <a name="isdaclautoinherited"></a>CSecurityDesc:: isdaclaudegeerbt

Bestimmt, ob die freigegebene Zugriffs Steuerungs Liste (DACL) für die Unterstützung der automatischen Propagierung konfiguriert ist.

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Sicherheits Beschreibung eine DACL enthält, die zur Unterstützung der automatischen Propagierung von vererbbaren Zugriffs Steuerungs Einträgen (ACEs) an vorhandene untergeordnete Objekte eingerichtet ist. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Das System legt dieses Bit fest, wenn es den automatischen Vererbungs Algorithmus für das-Objekt und dessen vorhandene untergeordnete Objekte ausführt.

##  <a name="isdacldefaulted"></a>CSecurityDesc:: isdacldefdefault

Bestimmt, ob die Sicherheits Beschreibung mit einer standardmäßigen freigegebenen Zugriffs Steuerungs Liste (DACL) konfiguriert ist.

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Sicherheits Beschreibung eine standarddacl enthält, andernfalls false.

### <a name="remarks"></a>Hinweise

Dieses Flag kann beeinflussen, wie das System die DACL behandelt, in Bezug auf die ACE-Vererbung (Access Control Entry, Zugriffs Steuerungs Eintrag). Wenn der Ersteller eines Objekts z. b. keine DACL angibt, empfängt das Objekt die Standard-DACL vom Zugriffs Token des Erstellers. Das System ignoriert dieses Flag, wenn das SE_DACL_PRESENT-Flag nicht festgelegt ist.

Dieses Flag wird verwendet, um zu bestimmen, wie die endgültige DACL des Objekts berechnet werden soll, und wird nicht physisch in der Sicherheits beschreibungssteuerung des Sicherungs fähigen Objekts gespeichert.

Um dieses Flag festzulegen, verwenden Sie die [CSecurityDesc:: SetDacl](#setdacl) -Methode.

##  <a name="isdaclpresent"></a>CSecurityDesc:: isdaclpresent

Bestimmt, ob die Sicherheits Beschreibung eine freigegebene Zugriffs Steuerungs Liste (DACL) enthält.

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Sicherheits Beschreibung eine DACL enthält; andernfalls false.

### <a name="remarks"></a>Hinweise

Wenn dieses Flag nicht festgelegt ist oder wenn dieses Flag festgelegt ist und die DACL NULL ist, ermöglicht die Sicherheits Beschreibung den vollständigen Zugriff auf alle.

Dieses Flag wird zum Speichern der von einem Aufrufer angegebenen Sicherheitsinformationen verwendet, bis die Sicherheits Beschreibung einem Sicherungs fähigen Objekt zugeordnet ist. Sobald die Sicherheits Beschreibung einem Sicherungs fähigen Objekt zugeordnet ist, wird das SE_DACL_PRESENT-Flag immer im Sicherheits beschreibungssteuerelement festgelegt.

Um dieses Flag festzulegen, verwenden Sie die [CSecurityDesc:: SetDacl](#setdacl) -Methode.

##  <a name="isdaclprotected"></a>CSecurityDesc:: isdaclprotected

Bestimmt, ob die freigegebene Zugriffs Steuerungs Liste (DACL) konfiguriert ist, um Änderungen zu verhindern.

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die DACL konfiguriert ist, um zu verhindern, dass die Sicherheits Beschreibung durch vererbbare Zugriffs Steuerungs Einträge (ACEs) geändert wird. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Um dieses Flag festzulegen, verwenden Sie die [CSecurityDesc:: SetDacl](#setdacl) -Methode.

Diese Methode unterstützt die Automatische Propagierung von vererbbaren ACEs.

##  <a name="isgroupdefaulted"></a>CSecurityDesc:: isgroupdefdefault

Bestimmt, ob die Gruppen Sicherheits-ID (SID) der Sicherheits Beschreibung standardmäßig festgelegt wurde.

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn ein Standardmechanismus anstelle des ursprünglichen Anbieters der Sicherheits Beschreibung die Gruppen-SID der Sicherheits Beschreibung bereitgestellt hat. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Um dieses Flag festzulegen, verwenden Sie die [CSecurityDesc:: SetGroup](#setgroup) -Methode.

##  <a name="isownerdefaulted"></a>CSecurityDesc:: isownerdefault

Bestimmt, ob die Sicherheits-ID (SID) für den Sicherheits Deskriptor standardmäßig festgelegt wurde.

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn ein Standardmechanismus anstelle des ursprünglichen Anbieters der Sicherheits Beschreibung die Besitzer-SID der Sicherheits Beschreibung bereitgestellt hat. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Um dieses Flag festzulegen, verwenden Sie die [CSecurityDesc:: SetOwner](#setowner) -Methode.

##  <a name="issaclautoinherited"></a>CSecurityDesc:: issaclaudegeerbt

Bestimmt, ob die System Zugriffs Steuerungs Liste (SACL) für die Unterstützung der automatischen Propagierung konfiguriert ist.

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Sicherheits Beschreibung eine SACL enthält, die zur Unterstützung der automatischen Propagierung von vererbbaren Zugriffs Steuerungs Einträgen (ACEs) an vorhandene untergeordnete Objekte eingerichtet ist. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Das System legt dieses Bit fest, wenn es den automatischen Vererbungs Algorithmus für das-Objekt und dessen vorhandene untergeordnete Objekte ausführt.

##  <a name="issacldefaulted"></a>CSecurityDesc:: issacldefdefault

Bestimmt, ob die Sicherheits Beschreibung mit einer standardmäßigen System Zugriffs Steuerungs Liste (SACL) konfiguriert ist.

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Sicherheits Beschreibung eine Standard-SACL enthält; andernfalls false.

### <a name="remarks"></a>Hinweise

Dieses Flag kann beeinflussen, wie das System die SACL behandelt, in Bezug auf die ACE-Vererbung (Access Control Entry, Zugriffs Steuerungs Eintrag). Das System ignoriert dieses Flag, wenn das SE_SACL_PRESENT-Flag nicht festgelegt ist.

Um dieses Flag festzulegen, verwenden Sie die [CSecurityDesc:: setsacl](#setsacl) -Methode.

##  <a name="issaclpresent"></a>CSecurityDesc:: issaclpresent

Bestimmt, ob die Sicherheits Beschreibung eine SACL (System Access-Control List) enthält.

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Sicherheits Beschreibung eine SACL enthält, andernfalls false.

### <a name="remarks"></a>Hinweise

Um dieses Flag festzulegen, verwenden Sie die [CSecurityDesc:: setsacl](#setsacl) -Methode.

##  <a name="issaclprotected"></a>CSecurityDesc:: issaclprotected

Bestimmt, ob die System Zugriffs Steuerungs Liste (SACL) konfiguriert ist, um Änderungen zu verhindern.

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die SACL konfiguriert ist, um zu verhindern, dass die Sicherheits Beschreibung durch vererbbare Zugriffs Steuerungs Einträge (ACEs) geändert wird. Andernfalls wird False zurückgegeben.

### <a name="remarks"></a>Hinweise

Um dieses Flag festzulegen, verwenden Sie die [CSecurityDesc:: setsacl](#setsacl) -Methode.

Diese Methode unterstützt die Automatische Propagierung von vererbbaren ACEs.

##  <a name="isselfrelative"></a>CSecurityDesc:: isselfrelative

Bestimmt, ob die Sicherheits Beschreibung in einem selbst relativen Format vorliegt.

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Sicherheits Beschreibung in einem selbst relativen Format mit allen Sicherheitsinformationen in einem zusammenhängenden Speicherblock vorliegt. Gibt false zurück, wenn die Sicherheits Beschreibung im absoluten Format vorliegt. Weitere Informationen finden Sie unter [absolute und selbst relative Sicherheits Deskriptoren](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="makeabsolute"></a>CSecurityDesc:: makeabsolute

Mit dieser Methode wird die Sicherheits Beschreibung in das absolute Format konvertiert.

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Methode erfolgreich ist, andernfalls false.

### <a name="remarks"></a>Hinweise

Eine Sicherheits Beschreibung im absoluten Format enthält Zeiger auf die enthaltenen Informationen anstelle der Informationen selbst. Eine Sicherheits Beschreibung in einem selbst relativen Format enthält die Informationen in einem zusammenhängenden Speicherblock. In einer selbst relativen Sicherheits Beschreibung werden die Informationen immer `SECURITY_DESCRIPTOR` von einer Struktur gestartet, aber die anderen Komponenten der Sicherheits Beschreibung können der Struktur in beliebiger Reihenfolge folgen. Anstatt Speicheradressen zu verwenden, werden die Komponenten der selbst relativen Sicherheits Beschreibung durch Offsets vom Anfang der Sicherheits Beschreibung identifiziert. Dieses Format ist nützlich, wenn eine Sicherheits Beschreibung auf einem Datenträger gespeichert oder mithilfe eines Kommunikationsprotokolls übertragen werden muss. Weitere Informationen finden Sie unter [absolute und selbst relative Sicherheits Deskriptoren](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="makeselfrelative"></a>CSecurityDesc:: MakeSelfRelative

Mit dieser Methode wird die Sicherheits Beschreibung in das selbst relative Format konvertiert.

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Methode erfolgreich ist, andernfalls false.

### <a name="remarks"></a>Hinweise

Eine Sicherheits Beschreibung im absoluten Format enthält Zeiger auf die enthaltenen Informationen, anstatt die Informationen selbst zu enthalten. Eine Sicherheits Beschreibung in einem selbst relativen Format enthält die Informationen in einem zusammenhängenden Speicherblock. In einer selbst relativen Sicherheits Beschreibung werden die Informationen immer `SECURITY_DESCRIPTOR` von einer Struktur gestartet, aber die anderen Komponenten der Sicherheits Beschreibung können der Struktur in beliebiger Reihenfolge folgen. Anstatt Speicheradressen zu verwenden, werden die Komponenten der Sicherheits Beschreibung durch Offsets vom Anfang der Sicherheits Beschreibung identifiziert. Dieses Format ist nützlich, wenn eine Sicherheits Beschreibung auf einem Datenträger gespeichert oder mithilfe eines Kommunikationsprotokolls übertragen werden muss. Weitere Informationen finden Sie unter [absolute und selbst relative Sicherheits Deskriptoren](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="operator_eq"></a>CSecurityDesc:: Operator =

Zuweisungsoperator.

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Die `SECURITY_DESCRIPTOR` Struktur oder `CSecurityDesc` das Objekt, das dem `CSecurityDesc` -Objekt zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CSecurityDesc` Objekt zurück.

##  <a name="operator_const_security_descriptor__star"></a>CSecurityDesc:: Operator Konstanten SECURITY_DESCRIPTOR *

Wandelt einen Wert in einen Zeiger auf die `SECURITY_DESCRIPTOR` -Struktur um.

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

##  <a name="setcontrol"></a>CSecurityDesc:: setcontrol

Legt die Steuerungsbits einer Sicherheitsbeschreibung fest.

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest,
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>Parameter

*ControlBitsOfInterest*<br/>
Eine SECURITY_DESCRIPTOR_CONTROL-Maske, die die festzulegenden Steuerungs Bits angibt. Eine Liste der Flags, die festgelegt werden können, finden Sie unter [SETSECURITYDESCRIPTOR Control](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol).

*ControlBitsToSet*<br/>
Eine SECURITY_DESCRIPTOR_CONTROL-Maske, die die neuen Werte für die von der *controlbitsofinterest* -Maske angegebenen Steuer Bits angibt. Dieser Parameter kann eine Kombination der Flags sein, die für den Parameter " *controlbitsofinterest* " aufgeführt sind.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [setsecuritydescriptorcontrol](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)auf.

##  <a name="setdacl"></a>CSecurityDesc:: SetDacl

Legt Informationen in einer freigegebenen Zugriffs Steuerungs Liste (DACL) fest. Wenn eine DACL bereits in der Sicherheits Beschreibung vorhanden ist, wird Sie ersetzt.

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
Verweis auf ein `CDacl` -Objekt, das die DACL für die Sicherheits Beschreibung angibt. Dieser Parameter darf nicht NULL sein. Um eine NULL-DACL in der Sicherheits Beschreibung festzulegen, sollte die erste Form der-Methode verwendet werden, wobei *bpresent* auf false festgelegt ist.

*bPresent*<br/>
Gibt ein Flag an, das angibt, dass eine DACL in der Sicherheits Beschreibung vorhanden ist. Wenn dieser Parameter auf true festgelegt ist, legt die-Methode das `SECURITY_DESCRIPTOR_CONTROL` SE_DACL_PRESENT-Flag in der-Struktur fest und verwendet die Werte in den *DACL* -und *bdefdefault* -Parametern. Wenn der Wert false ist, löscht die-Methode das SE_DACL_PRESENT-Flag, und *bdefdefault* wird ignoriert.

*bDefaulted*<br/>
Gibt ein Flag an, das die Quelle der DACL angibt. Wenn dieses Flag "true" ist, wurde die DACL von einem Standardmechanismus abgerufen. False gibt an, dass die DACL explizit von einem Benutzer angegeben wurde. Die-Methode speichert diesen Wert im SE_DACL_DEFAULTED-Flag der `SECURITY_DESCRIPTOR_CONTROL` -Struktur. Wenn dieser Parameter nicht angegeben wird, wird das SE_DACL_DEFAULTED-Flag gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Es gibt einen wichtigen Unterschied zwischen einer leeren und einer nicht vorhandenen DACL. Wenn eine DACL leer ist, enthält Sie keine Zugriffs Steuerungs Einträge, und es wurden keine Zugriffsrechte explizit erteilt. Der Zugriff auf das Objekt wird daher implizit verweigert. Wenn ein Objekt über keine DACL verfügt, wird dem Objekt dagegen kein Schutz zugewiesen, und es wird eine beliebige Zugriffs Anforderung erteilt.

##  <a name="setgroup"></a>CSecurityDesc:: SetGroup

Legt die primären Gruppeninformationen einer Sicherheits Beschreibung im absoluten Format fest und ersetzt alle bereits vorhandenen primären Gruppeninformationen.

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parameter

*Sid*<br/>
Verweis auf ein [CSID](../../atl/reference/csid-class.md) -Objekt für die neue primäre Gruppe der Sicherheits Beschreibung. Dieser Parameter darf nicht NULL sein. Eine Sicherheits Beschreibung kann so gekennzeichnet werden, dass Sie keine DACL oder eine SACL hat, aber Sie muss über eine Gruppe und einen Besitzer verfügen, selbst wenn es sich hierbei um die NULL-sid handelt (bei der es sich um eine integrierte sid mit einer speziellen Bedeutung handelt).

*bDefaulted*<br/>
Gibt an, ob die Informationen zur primären Gruppe von einem Standardmechanismus abgeleitet wurden. Wenn dieser Wert true ist, handelt es sich um Standardinformationen, und die-Methode speichert diesen Wert als SE_GROUP_DEFAULTED- `SECURITY_DESCRIPTOR_CONTROL` Flag in der-Struktur. Wenn dieser Parameter 0 (null) ist, wird das SE_GROUP_DEFAULTED-Flag gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

##  <a name="setowner"></a>CSecurityDesc:: seetowner

Legt die Besitzer Informationen eines Sicherheits Deskriptors mit absoluter Formatierung fest. Alle Besitzer Informationen, die bereits vorhanden sind, werden ersetzt.

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parameter

*Sid*<br/>
Das [CSID](../../atl/reference/csid-class.md) -Objekt für den neuen primären Besitzer der Sicherheits Beschreibung. Dieser Parameter darf nicht NULL sein.

*bDefaulted*<br/>
Gibt an, ob die Besitzer Informationen von einem Standardmechanismus abgeleitet werden. Wenn dieser Wert true ist, werden die Standardinformationen angezeigt. Die-Methode speichert diesen Wert als SE_OWNER_DEFAULTED-Flag in `SECURITY_DESCRIPTOR_CONTROL` der-Struktur. Wenn dieser Parameter 0 (null) ist, wird das SE_OWNER_DEFAULTED-Flag gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

##  <a name="setsacl"></a>CSecurityDesc:: s-ACL

Legt Informationen in einer System Zugriffs Steuerungs Liste (SACL) fest. Wenn eine SACL bereits in der Sicherheits Beschreibung vorhanden ist, wird Sie ersetzt.

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Parameter

*SACL*<br/>
Zeiger auf ein `CSacl` -Objekt, das die SACL für die Sicherheits Beschreibung angibt. Dieser Parameter darf nicht NULL sein und muss ein CSacl-Objekt sein. Im Gegensatz zu DACLs gibt es keinen Unterschied zwischen null und einer leeren SACL, da von SACL-Objekten keine Zugriffsrechte angegeben werden, sondern nur Überwachungsinformationen.

*bDefaulted*<br/>
Gibt ein Flag an, das die Quelle der SACL angibt. Wenn dieses Flag "true" ist, wurde die SACL von einem Standardmechanismus abgerufen. False gibt an, dass die SACL explizit von einem Benutzer angegeben wurde. Die-Methode speichert diesen Wert im SE_SACL_DEFAULTED-Flag der `SECURITY_DESCRIPTOR_CONTROL` -Struktur. Wenn dieser Parameter nicht angegeben wird, wird das SE_SACL_DEFAULTED-Flag gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

##  <a name="tostring"></a>CSecurityDesc::-Zeichenfolge

Konvertiert eine Sicherheits Beschreibung in ein Zeichen folgen Format.

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>Parameter

*pstr*<br/>
Zeiger auf eine auf NULL endenden Zeichenfolge, die die [Sicherheits Beschreibung des Zeichen folgen Formats](/windows/desktop/SecAuthZ/security-descriptor-string-format)empfängt.

*si*<br/>
Gibt eine Kombination von SECURITY_INFORMATION-Bitflags an, um die Komponenten der Sicherheits Beschreibung anzugeben, die in die Ausgabe Zeichenfolge eingeschlossen werden sollen.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg true zurück, bei einem Fehler false.

### <a name="remarks"></a>Hinweise

Wenn die Sicherheits Beschreibung im Zeichen folgen Format vorliegt, kann Sie leichter gespeichert oder übertragen werden. Verwenden Sie `CSecurityDesc::FromString` die-Methode, um die Zeichenfolge wieder in eine Sicherheits Beschreibung zu konvertieren.

Der *Si* -Parameter kann die folgenden SECURITY_INFORMATION-Flags enthalten:

|Wert|Bedeutung|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|Fügen Sie den Besitzer ein.|
|GROUP_SECURITY_INFORMATION|Fügen Sie die primäre Gruppe ein.|
|DACL_SECURITY_INFORMATION|Fügen Sie die DACL ein.|
|SACL_SECURITY_INFORMATION|Schließen Sie die SACL ein.|

Wenn die DACL NULL ist und das SE_DACL_PRESENT-Steuerelement Bit in der Eingabe Sicherheits Beschreibung festgelegt ist, schlägt die Methode fehl.

Wenn die DACL NULL ist und das SE_DACL_PRESENT-Steuerelement Bit nicht in der Eingabe Sicherheits Beschreibung festgelegt ist, hat die resultierende Sicherheits Beschreibungszeichenfolge keine D:-Komponente. Weitere Informationen finden Sie unter [Sicherheits Deskriptor-Zeichen folgen Format](/windows/desktop/SecAuthZ/security-descriptor-string-format) .

Diese Methode ruft [convertstringsecuritydescriptortosecuritydescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora)auf.

## <a name="see-also"></a>Siehe auch

[Sicherheits Beispiel](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-security_descriptor)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
