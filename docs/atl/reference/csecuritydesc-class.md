---
title: CSecurityDesc-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords: CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1a46a501c443baa65ab4c6da8bc4524c53e44989
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="csecuritydesc-class"></a>CSecurityDesc-Klasse
Diese Klasse ist ein Wrapper für die **SECURITY_DESCRIPTOR** Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CSecurityDesc
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|Der Konstruktor.|  
|[CSecurityDesc:: ~ CSecurityDesc](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSecurityDesc::FromString](#fromstring)|Konvertiert eine Sicherheitsbeschreibung Format der Zeichenfolge in einen gültigen, funktionale Sicherheitsdeskriptor.|  
|[CSecurityDesc:: Getcontrol](#getcontrol)|Ruft Informationen aus dem Sicherheitsdeskriptor zu steuern.|  
|[CSecurityDesc::GetDacl](#getdacl)|Ruft die Zugriffssteuerungsliste (DACL) Informationen aus dem Sicherheitsdeskriptor ab.|  
|[CSecurityDesc::GetGroup](#getgroup)|Ruft die primäre Gruppeninformationen aus dem Sicherheitsdeskriptor ab.|  
|[CSecurityDesc::GetOwner](#getowner)|Ruft den Besitzer Informationen aus dem Sicherheitsdeskriptor ab.|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Gibt einen Zeiger auf die **SECURITY_DESCRIPTOR** Struktur.|  
|[CSecurityDesc::GetSacl](#getsacl)|Ruft die Systeminformationen für Access Control List (SACL) aus dem Sicherheitsdeskriptor ab.|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|Bestimmt, ob die DACL konfiguriert ist, um automatische Weitergabe zu unterstützen.|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Bestimmt, ob der Sicherheitsbeschreibung hat den Standardwert DACL konfiguriert ist.|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Bestimmt, ob die Sicherheitsbeschreibung eine DACL enthält.|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|Bestimmt, ob die DACL konfiguriert ist, um Änderungen zu verhindern.|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Bestimmt, ob die Sicherheitsbeschreibung Gruppensicherheits-ID (SID) standardmäßig festgelegt wurde.|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Bestimmt, ob die Sicherheitsbeschreibung Besitzer SID standardmäßig festgelegt wurde.|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|Bestimmt, ob die SACL konfiguriert ist, um automatische Weitergabe zu unterstützen.|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Bestimmt, ob der Sicherheitsbeschreibung hat den Standardwert SACL konfiguriert ist.|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Bestimmt, ob die Sicherheitsbeschreibung eine SACL enthält.|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|Bestimmt, ob die SACL konfiguriert ist, um Änderungen zu verhindern.|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Bestimmt, ob die Sicherheitsbeschreibung im selbstbezogenen Format ist.|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Rufen Sie diese Methode, um die Sicherheitsbeschreibung in absoluten Format zu konvertieren.|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Rufen Sie diese Methode, um die Sicherheitsbeschreibung in das selbstbezogene Format konvertiert.|  
|[CSecurityDesc::SetControl](#setcontrol)|Legt die Steuerungsbits einer Sicherheitsbeschreibung fest.|  
|[CSecurityDesc:: SetDacl](#setdacl)|Legt die Informationen in eine DACL fest. Wenn eine DACL bereits in der Sicherheitsbeschreibung vorhanden ist, wird es ersetzt.|  
|[CSecurityDesc:: setGroup](#setgroup)|Legt fest, den primären Gruppeninformationen des ein absolutes Format Sicherheitsbeschreibung, und Ersetzen Sie dabei alle primären Gruppeninformationen bereits vorhanden.|  
|[CSecurityDesc:: SetOwner](#setowner)|Legt die Informationen zum Besitzer der ein absolutes Format Sicherheitsbeschreibung, ersetzen alle Informationen zum Geräteeigentümer bereits vorhanden.|  
|[CSecurityDesc:: Setsacl](#setsacl)|Legt die Informationen in einer SACL fest. Wenn eine SACL bereits in der Sicherheitsbeschreibung vorhanden ist, wird es ersetzt.|  
|[CSecurityDesc::ToString](#tostring)|Eine Sicherheitsbeschreibung konvertiert in ein Zeichenfolgenformat.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Const SECURITY_DESCRIPTOR CSecurityDesc::operator *](#operator_const_security_descriptor__star)|Gibt einen Zeiger auf die **SECURITY_DESCRIPTOR** Struktur.|  
|[CSecurityDesc::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Die **SECURITY_DESCRIPTOR** Struktur enthält die Sicherheitsinformationen, die einem Objekt zugeordnet. Anwendungen verwenden diese Struktur zum Festlegen und Abfragen von Sicherheitsstatus des Objekts. Siehe auch [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor).  
  
 Anwendungen sollten nicht ändern, die **SECURITY_DESCRIPTOR** Struktur direkt und stattdessen sollte die bereitgestellten Klassenmethoden verwenden.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Access Control](http://msdn.microsoft.com/library/windows/desktop/aa374860) im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="csecuritydesc"></a>CSecurityDesc::CSecurityDesc  
 Der Konstruktor.  
  
```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );  
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CSecurityDesc` Objekt oder **SECURITY_DESCRIPTOR** Zuweisen der neuen Struktur `CSecurityDesc` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CSecurityDesc` Objekt kann optional mit erstellt werden ein **SECURITY_DESCRIPTOR** Struktur oder eine zuvor definierte `CSecurityDesc` Objekt.  
  
##  <a name="dtor"></a>CSecurityDesc:: ~ CSecurityDesc  
 Der Destruktor.  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="fromstring"></a>CSecurityDesc::FromString  
 Konvertiert eine Sicherheitsbeschreibung Format der Zeichenfolge in einen gültigen, funktionale Sicherheitsdeskriptor.  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pstr`  
 Zeiger auf eine auf Null endende Zeichenfolge, enthält die [Zeichenfolgenformat Sicherheitsbeschreibung](http://msdn.microsoft.com/library/windows/desktop/aa379570) konvertiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg True zurück. Löst eine Ausnahme bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge kann erstellt werden, mithilfe von [CSecurityDesc::ToString](#tostring). Die Sicherheits-ID in einer Zeichenfolge konvertieren erleichtert das Speichern und übertragen.  
  
 Diese Methode ist nur verfügbar, mit Windows 2000 und höher da aufruft [ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
##  <a name="getcontrol"></a>CSecurityDesc:: Getcontrol  
 Ruft Informationen aus dem Sicherheitsdeskriptor zu steuern.  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *psdc*  
 Zeiger auf eine **SECURITY_DESCRIPTOR_CONTROL** -Struktur, die Informationen über die die Sicherheitsbeschreibung empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist nur sinnvoll, wenn mithilfe von Windows 2000 oder höher, wie er ruft [GetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa446647).  
  
##  <a name="getdacl"></a>CSecurityDesc::GetDacl  
 Ruft die Zugriffssteuerungsliste (DACL) Informationen aus dem Sicherheitsdeskriptor ab.  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pDacl`  
 Zeiger auf eine `CDacl` Struktur, in der zum Speichern einer Kopie der Sicherheitsdeskriptor-DACL. Wenn eine freigegebene **ACL** vorhanden ist, handelt es sich bei der Methode wird `pDacl` an die Adresse der Sicherheit des Deskriptors discretionary **ACL**. Wenn eine freigegebene **ACL** nicht vorhanden ist, kein Wert gespeichert ist.  
  
 `pbPresent`  
 Zeiger auf einen Wert, der das Vorhandensein einer freigegebenen Zugriffssteuerungsliste angibt **ACL** in der angegebenen Sicherheitsbeschreibung. Enthält die Sicherheitsbeschreibung freigegebene **ACL**, dieser Parameter festgelegt ist auf "true". Wenn die Sicherheitsbeschreibung nicht freigegebene enthält **ACL**, dieser Parameter auf "false" festgelegt ist.  
  
 `pbDefaulted`  
 Zeiger auf ein Flag festgelegt wird, auf den Wert des Flags SE_DACL_DEFAULTED in der **SECURITY_DESCRIPTOR_CONTROL** Wenn freigegebene Struktur **ACL** für die Sicherheitsbeschreibung ist vorhanden. Wenn dieses Kennzeichen auf "true" festgelegt ist die besitzerverwaltete **ACL** wurde durch einen Standardmechanismus abgerufen, wenn "false" den besitzverwalteten **ACL** wurde von einem Benutzer explizit angegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
##  <a name="getgroup"></a>CSecurityDesc::GetGroup  
 Ruft die primäre Gruppeninformationen aus dem Sicherheitsdeskriptor ab.  
  
```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSid`  
 Zeiger auf eine [CSid](../../atl/reference/csid-class.md) (Sicherheits-ID), empfängt eine Kopie der Gruppe in der CDacl gespeichert.  
  
 `pbDefaulted`  
 Zeiger auf ein Flag festgelegt wird, auf den Wert des Flags SE_GROUP_DEFAULTED in der **SECURITY_DESCRIPTOR_CONTROL** Struktur, wenn die Methode zurückkehrt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
##  <a name="getowner"></a>CSecurityDesc::GetOwner  
 Ruft den Besitzer Informationen aus dem Sicherheitsdeskriptor ab.  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSid`  
 Zeiger auf eine [CSid](../../atl/reference/csid-class.md) (Sicherheits-ID), empfängt eine Kopie der Gruppe in der CDacl gespeichert.  
  
 `pbDefaulted`  
 Zeiger auf ein Flag festgelegt wird, auf den Wert des Flags SE_OWNER_DEFAULTED in der **SECURITY_DESCRIPTOR_CONTROL** Struktur, wenn die Methode zurückkehrt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
##  <a name="getpsecurity_descriptor"></a>CSecurityDesc::GetPSECURITY_DESCRIPTOR  
 Gibt einen Zeiger auf die **SECURITY_DESCRIPTOR** Struktur.  
  
```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) Struktur.  
  
##  <a name="getsacl"></a>CSecurityDesc::GetSacl  
 Ruft die Systeminformationen für Access Control List (SACL) aus dem Sicherheitsdeskriptor ab.  
  
```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSacl`  
 Zeiger auf eine `CSacl` Struktur, in dem eine Kopie der Sicherheitsdeskriptor SACL gespeichert. Wenn ein System **ACL** vorhanden ist, handelt es sich bei der Methode wird `pSacl` an die Adresse des Systems für die Sicherheitsbeschreibung **ACL**. Wenn ein System **ACL** nicht vorhanden ist, kein Wert gespeichert ist.  
  
 `pbPresent`  
 Zeiger auf ein Flag, das die-Methode legt fest, um anzugeben, das Vorhandensein eines Systems **ACL** in der angegebenen Sicherheitsbeschreibung. Wenn die Sicherheitsbeschreibung ein Systems enthält **ACL**, dieser Parameter festgelegt ist auf "true". Wenn die Sicherheitsbeschreibung nicht über ein System enthält **ACL**, dieser Parameter auf "false" festgelegt ist.  
  
 `pbDefaulted`  
 Zeiger auf ein Flag festgelegt wird, auf den Wert des Flags SE_SACL_DEFAULTED in der **SECURITY_DESCRIPTOR_CONTROL** Struktur, wenn ein System **ACL** für die Sicherheitsbeschreibung ist vorhanden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
##  <a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoInherited  
 Bestimmt, ob die DACL (discretionary Access Control List) konfiguriert ist, um automatische Weitergabe zu unterstützen.  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Sicherheitsbeschreibung eine DACL, die eingerichtet ist enthält, um automatische Weitergabe von vererbbar Zugriff-Zugriffssteuerungseinträge (ACEs) zu vorhandenen untergeordneten Objekten zu unterstützen. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn sie die automatische Vererbung Algorithmus für das Objekt und seine untergeordneten Objekte ausführt, setzt das System dieses Bit.  
  
##  <a name="isdacldefaulted"></a>CSecurityDesc::IsDaclDefaulted  
 Bestimmt, ob die Sicherheitsbeschreibung mit einer Standardliste Zugriffssteuerungsliste (DACL) konfiguriert ist.  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Sicherheitsbeschreibung eine Standard-DACL, enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag kann beeinflussen, wie das System die DACL, in Bezug auf Vererbung von Access Control Entry (ACE) behandelt. Wenn der Ersteller für ein Objekt keine DACL angibt, empfängt das Objekt die Standard-DACL z. B. von Zugriffstoken für den Ersteller. Das System ignoriert dieses Flag an, wenn das SE_DACL_PRESENT-Flag nicht festgelegt ist.  
  
 Dieses Flag wird verwendet, um zu bestimmen, wie die endgültigen DACL für das Objekt ist, berechnet werden soll, und nicht physisch in der Sicherheitskontrolle Deskriptor des sicherungsfähigen Objekts gespeichert.  
  
 Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: SetDacl](#setdacl) Methode.  
  
##  <a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent  
 Bestimmt, ob die Sicherheitsbeschreibung eine DACL (discretionary Access Control List) enthält.  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Sicherheitsbeschreibung eine DACL enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Flag nicht festgelegt ist, oder wenn dieses Flag festgelegt ist und die DACL NULL ist, kann die Sicherheitsbeschreibung Vollzugriff auf "Jeder".  
  
 Dieses Flag wird verwendet, zum Speichern der Sicherheitsinformationen, die von einem Aufrufer angegeben wird, bis die Sicherheitsbeschreibung ein sicherungsfähiges Objekt zugeordnet ist. Sobald die Sicherheitsbeschreibung ein sicherungsfähiges Objekt zugeordnet ist, ist das Flag SE_DACL_PRESENT immer in der Sicherheitskontrolle Deskriptor festgelegt.  
  
 Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: SetDacl](#setdacl) Methode.  
  
##  <a name="isdaclprotected"></a>CSecurityDesc::IsDaclProtected  
 Bestimmt, ob die DACL (discretionary Access Control List) konfiguriert ist, um Änderungen zu verhindern.  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die DACL konfiguriert ist, um zu verhindern, dass die Sicherheitsbeschreibung durch vererbbare Zugriff-Zugriffssteuerungseinträge (ACEs) geändert wird. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: SetDacl](#setdacl) Methode.  
  
 Diese Methode ist nur sinnvoll, für Windows 2000 oder höher, als nur Windows 2000 automatische Weitergabe von vererbbaren ACEs unterstützt.  
  
##  <a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted  
 Bestimmt, ob die Sicherheitsbeschreibung Gruppensicherheits-ID (SID) standardmäßig festgelegt wurde.  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 "Wahr" zurückgegeben, wenn ein Standardmechanismus statt der ursprünglichen Anbieter der Sicherheitsbeschreibung, der sicherheitsbeschreibungs bereitgestellt Gruppen-SID. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: setGroup](#setgroup) Methode.  
  
##  <a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted  
 Bestimmt, ob die Sicherheitsbeschreibung Besitzer Sicherheits-ID (SID) standardmäßig festgelegt wurde.  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn eine Standardmechanismus statt der ursprünglichen Anbieter der Sicherheitsbeschreibung, die Sicherheitsbeschreibung Besitzer SID angegeben. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: setowner](#setowner) Methode.  
  
##  <a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoInherited  
 Bestimmt, ob das System Access Control List (SACL) konfiguriert ist, um automatische Weitergabe zu unterstützen.  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Sicherheitsbeschreibung eine SACL, die eingerichtet ist enthält, um automatische Weitergabe von vererbbar Zugriff-Zugriffssteuerungseinträge (ACEs) zu vorhandenen untergeordneten Objekten zu unterstützen. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn sie die automatische Vererbung Algorithmus für das Objekt und seine untergeordneten Objekte ausführt, setzt das System dieses Bit.  
  
##  <a name="issacldefaulted"></a>CSecurityDesc::IsSaclDefaulted  
 Bestimmt, ob die Sicherheitsbeschreibung eine Standardeinstellung System Access Control List (SACL) konfiguriert ist.  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Sicherheitsbeschreibung eine Standard-SACL, enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag kann beeinflussen, wie das System die SACL in Bezug auf Vererbung von Access Control Entry (ACE) behandelt. Das System ignoriert dieses Flag an, wenn das SE_SACL_PRESENT-Flag nicht festgelegt ist.  
  
 Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: Setsacl](#setsacl) Methode.  
  
##  <a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent  
 Bestimmt, ob die Sicherheitsbeschreibung eine System Access Control List (SACL) enthält.  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Sicherheitsbeschreibung eine SACL enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: Setsacl](#setsacl) Methode.  
  
##  <a name="issaclprotected"></a>CSecurityDesc::IsSaclProtected  
 Bestimmt, ob das System Access Control List (SACL) konfiguriert ist, um Änderungen zu verhindern.  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die SACL konfiguriert ist, um zu verhindern, dass die Sicherheitsbeschreibung durch vererbbare Zugriff-Zugriffssteuerungseinträge (ACEs) geändert wird. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flag die [CSecurityDesc:: Setsacl](#setsacl) Methode.  
  
 Diese Methode ist nur sinnvoll, für Windows 2000 oder höher, als nur Windows 2000 automatische Weitergabe von vererbbaren ACEs unterstützt.  
  
##  <a name="isselfrelative"></a>CSecurityDesc::IsSelfRelative  
 Bestimmt, ob die Sicherheitsbeschreibung im selbstbezogenen Format ist.  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Sicherheitsbeschreibung im selbstbezogenen Format mit alle Sicherheitsinformationen in einen zusammenhängenden Block von Arbeitsspeicher ist. Gibt False zurück, wenn die Sicherheitsbeschreibung im absoluten Format ist. Weitere Informationen finden Sie unter [Absolute und Self-Relative Sicherheitsbeschreibungen](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="makeabsolute"></a>CSecurityDesc::MakeAbsolute  
 Rufen Sie diese Methode, um die Sicherheitsbeschreibung in absoluten Format zu konvertieren.  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Methode erfolgreich ist, "false" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Eine Sicherheitsbeschreibung im absoluten Format enthält Zeiger auf die enthaltenen Informationen, anstatt die Informationen selbst. Eine Sicherheitsbeschreibung im selbstbezogenen Format enthält die Informationen in einen zusammenhängenden Block von Arbeitsspeicher. In einem selbstbezogenen Sicherheitsbeschreibung eine **SECURITY_DESCRIPTOR** Struktur beginnt immer die Informationen, aber die Sicherheitsbeschreibung des anderen Komponenten können die Struktur in beliebiger Reihenfolge folgen. Anstatt Speicheradressen zu verwenden, werden die Komponenten der selbstbezogenen Sicherheitsbeschreibung durch Offsets vom Anfang der Sicherheitsbeschreibung identifiziert. Dieses Format ist nützlich, wenn eine Sicherheitsbeschreibung auf einem Datenträger gespeichert oder über ein Kommunikationsprotokoll übertragen werden muss. Weitere Informationen finden Sie unter [Absolute und Self-Relative Sicherheitsbeschreibungen](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="makeselfrelative"></a>CSecurityDesc::MakeSelfRelative  
 Rufen Sie diese Methode, um die Sicherheitsbeschreibung in das selbstbezogene Format konvertiert.  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Methode erfolgreich ist, "false" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Eine Sicherheitsbeschreibung im absoluten Format enthält Zeiger auf die darin enthaltenen Informationen, anstatt mit Informationen über das selbst. Eine Sicherheitsbeschreibung im selbstbezogenen Format enthält die Informationen in einen zusammenhängenden Block von Arbeitsspeicher. In einem selbstbezogenen Sicherheitsbeschreibung eine **SECURITY_DESCRIPTOR** Struktur beginnt immer die Informationen, aber die Sicherheitsbeschreibung des anderen Komponenten können die Struktur in beliebiger Reihenfolge folgen. Anstatt Speicheradressen zu verwenden, werden die Komponenten der Sicherheitsbeschreibung durch Offsets vom Anfang der Sicherheitsbeschreibung identifiziert. Dieses Format ist nützlich, wenn eine Sicherheitsbeschreibung auf einem Datenträger gespeichert oder über ein Kommunikationsprotokoll übertragen werden muss. Weitere Informationen finden Sie unter [Absolute und Self-Relative Sicherheitsbeschreibungen](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="operator_eq"></a>CSecurityDesc::operator =  
 Zuweisungsoperator.  
  
```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);  
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die **SECURITY_DESCRIPTOR** Struktur oder `CSecurityDesc` Objekt zuweisen der `CSecurityDesc` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CSecurityDesc` Objekt.  
  
##  <a name="operator_const_security_descriptor__star"></a>Const SECURITY_DESCRIPTOR CSecurityDesc::operator *  
 Wandelt einen Wert in einen Zeiger auf die **SECURITY_DESCRIPTOR** Struktur.  
  
```  
operator const SECURITY_DESCRIPTOR *() const throw();
```  
  
##  <a name="setcontrol"></a>CSecurityDesc::SetControl  
 Legt die Steuerungsbits einer Sicherheitsbeschreibung fest.  
  
```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest, 
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ControlBitsOfInterest`  
 Ein **SECURITY_DESCRIPTOR_CONTROL** Maske, die die festzulegenden Steuerungsbits angibt. Eine Liste der Flags, die festgelegt werden können, finden Sie unter [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
 `ControlBitsToSet`  
 Eine `SECURITY_DESCRIPTOR_CONTROL`-Maske, die die neuen Werten für die Steuerbits angibt, die durch die `ControlBitsOfInterest`-Maske angegeben werden. Dieser Parameter kann eine Kombination der Flags sein, die für den Parameter `ControlBitsOfInterest` aufgeführt sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist nur unter Windows 2000 und höher, als er ruft [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
##  <a name="setdacl"></a>CSecurityDesc:: SetDacl  
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
 *DACL*  
 Ein Verweis auf ein `CDacl` Objekt, das die DACL für die Sicherheitsbeschreibung angibt. Dieser Parameter darf nicht NULL sein. Um eine NULL-DACL in die Sicherheitsbeschreibung festgelegt werden, sollte die erste Form der Methode mit verwendet werden `bPresent` auf "false" festgelegt.  
  
 `bPresent`  
 Gibt ein Flag, der angibt, des Vorhandensein einer DACL in der Sicherheitsbeschreibung. Wenn dieser Parameter auf "true" festgelegt ist, legt die Methode das SE_DACL_PRESENT-Flag in der **SECURITY_DESCRIPTOR_CONTROL** Struktur und verwendet die Werte in der *Dacl* und `bDefaulted` Parameter. Wenn sie falsch ist, wird die Methode löscht das Flag SE_DACL_PRESENT und `bDefaulted` wird ignoriert.  
  
 `bDefaulted`  
 Gibt ein Flag, der die Quelle der DACL angibt. Wenn dieses Flag auf "true" festgelegt ist, hat die DACL über einen Standardmechanismus abgerufen wurde. Wenn "false", wurde die DACL explizit von einem Benutzer angegeben. Die Methode speichert diesen Wert in das Flag SE_DACL_DEFAULTED des der **SECURITY_DESCRIPTOR_CONTROL** Struktur. Wenn dieser Parameter nicht angegeben ist, wird das Flag SE_DACL_DEFAULTED gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Es ist ein wichtiger Unterschied zwischen einer leeren und eine nicht vorhandene DACL. Wenn eine DACL leer ist, er enthält keine Einträge für die Zugriffssteuerung und keine Zugriffsrechte explizit erteilt wurde. Zugriff auf das Objekt wird daher implizit verweigert. Wenn ein Objekt keine DACL verfügt, andererseits, keinen Schutz ist mit dem Objekt zugewiesen, und jede zugriffsanforderung gewährt wird.  
  
##  <a name="setgroup"></a>CSecurityDesc:: setGroup  
 Legt fest, den primären Gruppeninformationen des ein absolutes Format Sicherheitsbeschreibung, und Ersetzen Sie dabei alle primären Gruppeninformationen bereits vorhanden.  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `Sid`  
 Ein Verweis auf eine [CSid](../../atl/reference/csid-class.md) Objekt für die neue primäre Gruppe für den Sicherheitsdeskriptor. Dieser Parameter darf nicht NULL sein. Eine Sicherheitsbeschreibung kann z. B. eine DACL oder eine SACL ohne markiert werden, jedoch muss es diese auch eine Gruppe und einen Besitzer sind die NULL-SID (Dies ist eine integrierte SID mit eine besondere Bedeutung hat).  
  
 `bDefaulted`  
 Gibt an, ob eine Standardmechanismus für die primäre Gruppeninformationen abgeleitet wurde. Wenn dieser Wert ist "true", wird standardmäßig die Methode speichert diesen Wert als das SE_GROUP_DEFAULTED-Flag in der **SECURITY_DESCRIPTOR_CONTROL** Struktur. Wenn dieser Parameter auf 0 (null) ist, wird das Flag SE_GROUP_DEFAULTED gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="setowner"></a>CSecurityDesc:: SetOwner  
 Legt die Informationen zum Besitzer der ein absolutes Format Sicherheitsbeschreibung fest. Er ersetzt alle Informationen zum Geräteeigentümer bereits vorhanden.  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `Sid`  
 Die [CSid](../../atl/reference/csid-class.md) Objekt für den neuen primären Besitzer der Sicherheitsbeschreibung. Dieser Parameter darf nicht NULL sein.  
  
 `bDefaulted`  
 Gibt an, ob eine Standardmechanismus für die Informationen zum Besitzer abgeleitet ist. Wenn dieser Wert auf "true" festgelegt ist, ist es Standardinformationen an. Die Methode speichert diesen Wert als das SE_OWNER_DEFAULTED-Flag in der **SECURITY_DESCRIPTOR_CONTROL** Struktur. Wenn dieser Parameter auf 0 (null) ist, wird das Flag SE_OWNER_DEFAULTED gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="setsacl"></a>CSecurityDesc:: Setsacl  
 Legt die Informationen in eine System Access Control List (SACL) fest. Wenn eine SACL bereits in der Sicherheitsbeschreibung vorhanden ist, wird es ersetzt.  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *SACL*  
 Zeiger auf ein `CSacl` Objekt, das die SACL für die Sicherheitsbeschreibung angibt. Dieser Parameter darf nicht NULL sein und muss ein CSacl-Objekt. Im Gegensatz zu DACLs zu speichern besteht kein Unterschied zwischen NULL und einer leeren SACL wie SACL Objekte nicht Zugriffsrechte, die nur die Überwachungsinformationen angeben.  
  
 `bDefaulted`  
 Gibt ein Flag, der die Quelle der SACL angibt. Wenn dieses Flag auf "true" festgelegt ist, wurde die SACL über einen Standardmechanismus abgerufen. Wenn "false", wurde die SACL explizit von einem Benutzer angegeben. Die Methode speichert diesen Wert in das Flag SE_SACL_DEFAULTED des der **SECURITY_DESCRIPTOR_CONTROL** Struktur. Wenn dieser Parameter nicht angegeben ist, wird das Flag SE_SACL_DEFAULTED gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="tostring"></a>CSecurityDesc::ToString  
 Eine Sicherheitsbeschreibung konvertiert in ein Zeichenfolgenformat.  
  
```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pstr`  
 Zeiger auf eine Null-terminierte Zeichenfolge, die erhält die [Zeichenfolgenformat Sicherheitsbeschreibung](http://msdn.microsoft.com/library/windows/desktop/aa379570).  
  
 `si`  
 Gibt eine Kombination von Bitflags an, dass die Komponenten der Sicherheitsbeschreibung einschließt, die Ausgabezeichenfolge SECURITY_INFORMATION an.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Sobald die Sicherheitsbeschreibung im Zeichenfolgenformat ist, kann es einfacher gespeichert oder übertragen werden. Verwenden der `CSecurityDesc::FromString` Methode die Zeichenfolge in eine Sicherheitsbeschreibung umzuwandeln.  
  
 Die `si` Parameter kann die folgenden SECURITY_INFORMATION Flags enthalten:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|Schließen Sie den Besitzer.|  
|GROUP_SECURITY_INFORMATION|Die primäre Gruppe einschließen|  
|DACL_SECURITY_INFORMATION|Die DACL einschließen|  
|SACL_SECURITY_INFORMATION|Schließen Sie die SACL.|  
  
 Wenn die DACL NULL ist, und die SE_DACL_PRESENT Steuerbit in die eingabesicherheitsbeschreibung festgelegt ist, schlägt die Methode fehl.  
  
 Wenn die DACL NULL ist, und die SE_DACL_PRESENT Steuerbit nicht, in dem die eingabesicherheitsbeschreibung festgelegt ist, resultierende sicherheitsbeschreibungs-Zeichenfolge eine Komponente D: keinen. Finden Sie unter [Sicherheitsbeschreibungsformat Zeichenfolge](http://msdn.microsoft.com/library/windows/desktop/aa379570) Weitere Details.  
  
 Diese Methode ist nur verfügbar mit Windows 2000 und höher, wie er ruft [ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für nachrichtensicherheit](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
