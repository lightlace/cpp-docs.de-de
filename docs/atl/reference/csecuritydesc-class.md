---
title: CSecurityDesc Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSecurityDesc
- ATL.CSecurityDesc
- CSecurityDesc
dev_langs:
- C++
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6dbd586ee3ee07d3c567fa0aae46446397dfb62b
ms.lasthandoff: 02/24/2017

---
# <a name="csecuritydesc-class"></a>CSecurityDesc-Klasse
Diese Klasse ist ein Wrapper für die **SECURITY_DESCRIPTOR** Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
|[CSecurityDesc::FromString](#fromstring)|Konvertiert einen Sicherheitsdeskriptor Zeichenfolge-Format in eine gültige, funktionale Sicherheitsbeschreibung.|  
|[CSecurityDesc::GetControl](#getcontrol)|Ruft steuern, Informationen aus den Sicherheitsdeskriptor.|  
|[CSecurityDesc::GetDacl](#getdacl)|Ruft discretionary Access Control List (DACL) Informationen aus den Sicherheitsdeskriptor.|  
|[CSecurityDesc::GetGroup](#getgroup)|Ruft die primäre Gruppeninformationen aus den Sicherheitsdeskriptor.|  
|[CSecurityDesc::GetOwner](#getowner)|Besitzer-Informationen aus der Sicherheitsdeskriptor abgerufen.|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Gibt einen Zeiger auf die **SECURITY_DESCRIPTOR** Struktur.|  
|[CSecurityDesc::GetSacl](#getsacl)|Ruft Informationen zu System Access Control List (SACL) aus den Sicherheitsdeskriptor ab.|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|Bestimmt, ob die DACL für die automatische Übertragung unterstützen konfiguriert ist.|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Bestimmt, ob die Sicherheits-ID mit einer Standard-DACL konfiguriert ist.|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Bestimmt, ob die Sicherheitsbeschreibung eine DACL enthält.|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|Bestimmt, ob die DACL konfiguriert ist, um die Änderungen zu verhindern.|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Bestimmt, ob die Sicherheits-ID-Gruppe Sicherheits-ID (SID) in der Standardeinstellung festgelegt wurde.|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Bestimmt, ob der Besitzer die Sicherheits-ID-SID in der Standardeinstellung festgelegt wurde.|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|Bestimmt, ob die SACL konfiguriert ist, um automatische Weitergabe zu unterstützen.|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Bestimmt, ob die Sicherheits-ID mit einer Standard-SACL konfiguriert ist.|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Bestimmt, ob die Sicherheits-ID eine SACL enthält.|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|Bestimmt, ob die SACL konfiguriert ist, um die Änderungen zu verhindern.|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Bestimmt, ob die Sicherheitsbeschreibung im selbstbezogenen Format ist.|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Rufen Sie diese Methode, um die Sicherheits-ID in das absolute Format zu konvertieren.|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Rufen Sie diese Methode, um den Sicherheitsdeskriptor in relativen Format zu konvertieren.|  
|[CSecurityDesc::SetControl](#setcontrol)|Legt die Steuerungsbits einer Sicherheitsbeschreibung fest.|  
|[CSecurityDesc::SetDacl](#setdacl)|Legt die Informationen in einer DACL fest. Wenn eine DACL bereits in die Sicherheits-ID vorhanden ist, wird es ersetzt.|  
|[CSecurityDesc::SetGroup](#setgroup)|Legt die primären Informationen ein absolutes Format Sicherheitsbeschreibung, Austauschen von Informationen primäre Gruppe bereits vorhanden.|  
|[CSecurityDesc::SetOwner](#setowner)|Legt die Informationen zum Besitzer der ein absolutes Format Sicherheitsdeskriptor, ersetzen alle bereits vorhandenen Besitzerinformationen fest.|  
|[CSecurityDesc::SetSacl](#setsacl)|Legt die Informationen in einer SACL fest. Wenn eine SACL bereits in die Sicherheits-ID vorhanden ist, wird es ersetzt.|  
|[CSecurityDesc::ToString](#tostring)|Konvertiert einen Sicherheitsdeskriptor in einer Zeichenfolge.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Const SECURITY_DESCRIPTOR CSecurityDesc::operator *](#operator_const_security_descriptor__star)|Gibt einen Zeiger auf die **SECURITY_DESCRIPTOR** Struktur.|  
|[CSecurityDesc::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Die **SECURITY_DESCRIPTOR** Struktur enthält die Sicherheitsinformationen, die einem Objekt zugeordnet. Anwendungen mit dieser Struktur können festzulegen und den Status eines Objekts Sicherheit abzufragen. Siehe auch [AtlGetSecurityDescriptor](http://msdn.microsoft.com/library/233578b8-dcc5-4f51-8e62-7cdcc2ff6b11).  
  
 Clientanwendungen sollten nicht ändern, die **SECURITY_DESCRIPTOR** Struktur direkt aus, und stattdessen sollte die bereitgestellten Klassenmethoden verwenden.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="a-namecsecuritydesca--csecuritydesccsecuritydesc"></a><a name="csecuritydesc"></a>CSecurityDesc::CSecurityDesc  
 Der Konstruktor.  
  
```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );  
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CSecurityDesc` Objekt oder **SECURITY_DESCRIPTOR** Struktur, die dem neuen Server `CSecurityDesc` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CSecurityDesc` -Objekt kann optional mit erstellt werden ein **SECURITY_DESCRIPTOR** Struktur oder eine zuvor definierte `CSecurityDesc` Objekt.  
  
##  <a name="a-namedtora--csecuritydesccsecuritydesc"></a><a name="dtor"></a>CSecurityDesc:: ~ CSecurityDesc  
 Der Destruktor.  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="a-namefromstringa--csecuritydescfromstring"></a><a name="fromstring"></a>CSecurityDesc::FromString  
 Konvertiert einen Sicherheitsdeskriptor Zeichenfolge-Format in eine gültige, funktionale Sicherheitsbeschreibung.  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pstr`  
 Zeiger auf eine Null-terminierte Zeichenfolge mit der [Zeichenfolgenformat Sicherheitsdeskriptor](http://msdn.microsoft.com/library/windows/desktop/aa379570) konvertiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg True zurück. Löst eine Ausnahme bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeichenfolge kann erstellt werden, mithilfe von [CSecurityDesc::ToString](#tostring). Die Sicherheits-ID in eine Zeichenfolge konvertieren erleichtert das Speichern und übertragen.  
  
 Diese Methode ist nur verfügbar in Windows 2000 und höher da aufgerufen [wurde von ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
##  <a name="a-namegetcontrola--csecuritydescgetcontrol"></a><a name="getcontrol"></a>CSecurityDesc::GetControl  
 Ruft steuern, Informationen aus den Sicherheitsdeskriptor.  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *psdc*  
 Zeiger auf eine **SECURITY_DESCRIPTOR_CONTROL** -Struktur, die den Sicherheitsdeskriptor Steuerelement Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist nur sinnvoll, wenn unter Windows 2000 oder höher, wie er ruft [GetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa446647).  
  
##  <a name="a-namegetdacla--csecuritydescgetdacl"></a><a name="getdacl"></a>CSecurityDesc::GetDacl  
 Ruft discretionary Access Control List (DACL) Informationen aus den Sicherheitsdeskriptor.  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pDacl`  
 Zeiger auf eine `CDacl` Struktur, in der zum Speichern einer Kopie der Sicherheitsdeskriptor-DACL. Wenn eine freigegebene **ACL** vorhanden ist, handelt es sich bei der Methode wird `pDacl` die Adresse des Deskriptors des discretionary **ACL**. Wenn eine freigegebene **ACL** vorhanden ist, kein Wert gespeichert ist.  
  
 `pbPresent`  
 Zeiger auf einen Wert an das Vorhandensein einer discretionary **ACL** in der angegebenen Sicherheitsbeschreibung. Enthält der Sicherheitsdeskriptor keine freigegebene **ACL**, dieser Parameter den Wert "true". Enthält der Sicherheitsdeskriptor keine keine freigegebene **ACL**, diesen Parameter auf False festgelegt ist.  
  
 `pbDefaulted`  
 Zeiger auf ein Flag festgelegt, auf den Wert des SE_DACL_DEFAULTED-Flags in der **SECURITY_DESCRIPTOR_CONTROL** Struktur, wenn eine freigegebene **ACL** für die Sicherheits-ID vorhanden ist. Wenn dieses Flag auf true festgelegt ist die discretionary **ACL** wurde abgerufen, indem ein Standardmechanismus; false, die freigegebene **ACL** explizit vom Benutzer angegeben wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
##  <a name="a-namegetgroupa--csecuritydescgetgroup"></a><a name="getgroup"></a>CSecurityDesc::GetGroup  
 Ruft die primäre Gruppeninformationen aus den Sicherheitsdeskriptor.  
  
```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSid`  
 Zeiger auf eine [CSid](../../atl/reference/csid-class.md) (Security Identifier), empfängt eine Kopie der Gruppe in der CDacl gespeichert.  
  
 `pbDefaulted`  
 Zeiger auf ein Flag festgelegt, auf den Wert des SE_GROUP_DEFAULTED-Flags in der **SECURITY_DESCRIPTOR_CONTROL** Struktur, wenn die Methode zurückgibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
##  <a name="a-namegetownera--csecuritydescgetowner"></a><a name="getowner"></a>CSecurityDesc::GetOwner  
 Besitzer-Informationen aus der Sicherheitsdeskriptor abgerufen.  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSid`  
 Zeiger auf eine [CSid](../../atl/reference/csid-class.md) (Security Identifier), empfängt eine Kopie der Gruppe in der CDacl gespeichert.  
  
 `pbDefaulted`  
 Zeiger auf ein Flag festgelegt, auf den Wert des SE_OWNER_DEFAULTED-Flags in der **SECURITY_DESCRIPTOR_CONTROL** Struktur, wenn die Methode zurückgibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
##  <a name="a-namegetpsecuritydescriptora--csecuritydescgetpsecuritydescriptor"></a><a name="getpsecurity_descriptor"></a>CSecurityDesc::GetPSECURITY_DESCRIPTOR  
 Gibt einen Zeiger auf die **SECURITY_DESCRIPTOR** Struktur.  
  
```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) Struktur.  
  
##  <a name="a-namegetsacla--csecuritydescgetsacl"></a><a name="getsacl"></a>CSecurityDesc::GetSacl  
 Ruft Informationen zu System Access Control List (SACL) aus den Sicherheitsdeskriptor ab.  
  
```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSacl`  
 Zeiger auf eine `CSacl` Struktur, in der eine Kopie der Sicherheitsdeskriptor SACL speichern. Wenn ein System **ACL** vorhanden ist, handelt es sich bei der Methode wird `pSacl` an die Adresse des Systems den Sicherheitsdeskriptor **ACL**. Wenn ein System **ACL** vorhanden ist, kein Wert gespeichert ist.  
  
 `pbPresent`  
 Zeiger auf ein Flag, das die Methode legt fest, das Vorhandensein eines Systems **ACL** in der angegebenen Sicherheitsbeschreibung. Wenn die Sicherheits-ID ein Systems enthält **ACL**, dieser Parameter den Wert auf "true". Enthält der Sicherheitsdeskriptor kein System **ACL**, diesen Parameter auf False festgelegt ist.  
  
 `pbDefaulted`  
 Zeiger auf ein Flag festgelegt, auf den Wert des SE_SACL_DEFAULTED-Flags in der **SECURITY_DESCRIPTOR_CONTROL** Struktur, wenn ein System **ACL** für die Sicherheits-ID vorhanden ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Methode erfolgreich ist, False, wenn ein Fehler auftritt.  
  
##  <a name="a-nameisdaclautoinheriteda--csecuritydescisdaclautoinherited"></a><a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoInherited  
 Bestimmt, ob die DACL (discretionary Access Control List) konfiguriert ist, um automatische Weitergabe zu unterstützen.  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Sicherheits-ID eine DACL enthält die automatische Übertragung von vererbbare Access-Zugriffssteuerungseinträge (ACEs) für vorhandene untergeordnete Objekte unterstützen festgelegt ist. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn sie die automatische Vererbung Algorithmus für das Objekt und seine untergeordneten Objekte ausführt, setzt das System dieses Bit.  
  
##  <a name="a-nameisdacldefaulteda--csecuritydescisdacldefaulted"></a><a name="isdacldefaulted"></a>CSecurityDesc::IsDaclDefaulted  
 Bestimmt, ob die Sicherheits-ID mit einer Standardliste Zugriffssteuerungsliste (DACL) konfiguriert ist.  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Sicherheits-ID eine Standard-DACL, enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag kann beeinflussen, wie das System die DACL, in Bezug auf Vererbung von Access Control Entry (ACE) behandelt. Wenn der Ersteller des Objekts eine DACL nicht angegeben wird, empfängt das Objekt z. B. die Standard-DACL von Zugriffstoken für den Ersteller. Das System ignoriert dieses Flag an, wenn das SE_DACL_PRESENT-Flag nicht festgelegt ist.  
  
 Dieses Flag wird verwendet, um zu bestimmen, wie die endgültigen DACL für das Objekt ist, berechnet werden soll und nicht physisch im Security Descriptor-Steuerelement des sicherungsfähigen Objekts gespeichert.  
  
 Verwenden Sie zum Festlegen dieses Flags der [CSecurityDesc::SetDacl](#setdacl) Methode.  
  
##  <a name="a-nameisdaclpresenta--csecuritydescisdaclpresent"></a><a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent  
 Bestimmt, ob die Sicherheitsbeschreibung eine DACL (discretionary Access Control List) enthält.  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Sicherheitsbeschreibung eine DACL enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Flag nicht festgelegt ist, oder wenn dieses Flag festgelegt ist und die DACL NULL ist, kann der Sicherheitsdeskriptor Vollzugriff auf alle Benutzer.  
  
 Dieses Flag wird verwendet, enthält die Sicherheitsinformationen, die von einem Aufrufer angegeben werden, bis die Sicherheits-ID einem sicherungsfähigen Objekt zugeordnet ist. Sobald die Sicherheits-ID einem sicherungsfähigen Objekt zugeordnet ist, wird das Flag SE_DACL_PRESENT immer im Security Descriptor-Steuerelement festgelegt.  
  
 Verwenden Sie zum Festlegen dieses Flags der [CSecurityDesc::SetDacl](#setdacl) Methode.  
  
##  <a name="a-nameisdaclprotecteda--csecuritydescisdaclprotected"></a><a name="isdaclprotected"></a>CSecurityDesc::IsDaclProtected  
 Bestimmt, ob die DACL (discretionary Access Control List) konfiguriert ist, um die Änderungen zu verhindern.  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die DACL konfiguriert ist, um zu verhindern, dass die Sicherheits-ID durch vererbbare Access-Zugriffssteuerungseinträge (ACEs) geändert wird. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flags der [CSecurityDesc::SetDacl](#setdacl) Methode.  
  
 Diese Methode ist nur sinnvoll, für Windows 2000 oder höher, als nur Windows 2000 unterstützt die automatische Übertragung von vererbbare ACEs.  
  
##  <a name="a-nameisgroupdefaulteda--csecuritydescisgroupdefaulted"></a><a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted  
 Bestimmt, ob die Sicherheits-ID-Gruppe Sicherheits-ID (SID) in der Standardeinstellung festgelegt wurde.  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, sofern ein Standardmechanismus statt der ursprünglichen Anbieter des Sicherheitsdeskriptors, des Sicherheitsdeskriptors SID gruppieren. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flags der [CSecurityDesc::SetGroup](#setgroup) Methode.  
  
##  <a name="a-nameisownerdefaulteda--csecuritydescisownerdefaulted"></a><a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted  
 Bestimmt, ob der Sicherheitsdeskriptor Besitzer-Sicherheits-ID (SID) in der Standardeinstellung festgelegt wurde.  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn ein Standardmechanismus statt der ursprünglichen Anbieter des Sicherheitsdeskriptors, den Sicherheitsdeskriptor Besitzer-SID bereitgestellt. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flags der [CSecurityDesc::SetOwner](#setowner) Methode.  
  
##  <a name="a-nameissaclautoinheriteda--csecuritydescissaclautoinherited"></a><a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoInherited  
 Bestimmt, ob die System Access Control List (SACL) konfiguriert ist, um automatische Weitergabe zu unterstützen.  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Sicherheits-ID eine SACL enthält die automatische Übertragung von vererbbare Access-Zugriffssteuerungseinträge (ACEs) für vorhandene untergeordnete Objekte unterstützen festgelegt ist. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn sie die automatische Vererbung Algorithmus für das Objekt und seine untergeordneten Objekte ausführt, setzt das System dieses Bit.  
  
##  <a name="a-nameissacldefaulteda--csecuritydescissacldefaulted"></a><a name="issacldefaulted"></a>CSecurityDesc::IsSaclDefaulted  
 Bestimmt, ob die Sicherheits-ID mit einer Standard-System Access Control List (SACL) konfiguriert ist.  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Sicherheits-ID eine Standard-SACL, enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Flag kann beeinflussen, wie das System die SACL in Bezug auf Vererbung von Access Control Entry (ACE) behandelt. Das System ignoriert dieses Flag an, wenn das SE_SACL_PRESENT-Flag nicht festgelegt ist.  
  
 Verwenden Sie zum Festlegen dieses Flags der [CSecurityDesc::SetSacl](#setsacl) Methode.  
  
##  <a name="a-nameissaclpresenta--csecuritydescissaclpresent"></a><a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent  
 Bestimmt, ob die Sicherheits-ID eine System Access Control List (SACL) enthält.  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Sicherheits-ID eine SACL enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flags der [CSecurityDesc::SetSacl](#setsacl) Methode.  
  
##  <a name="a-nameissaclprotecteda--csecuritydescissaclprotected"></a><a name="issaclprotected"></a>CSecurityDesc::IsSaclProtected  
 Bestimmt, ob die System Access Control List (SACL) konfiguriert ist, um die Änderungen zu verhindern.  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die SACL konfiguriert ist, um zu verhindern, dass die Sicherheits-ID durch vererbbare Access-Zugriffssteuerungseinträge (ACEs) geändert wird. Andernfalls wird False zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Festlegen dieses Flags der [CSecurityDesc::SetSacl](#setsacl) Methode.  
  
 Diese Methode ist nur sinnvoll, für Windows 2000 oder höher, als nur Windows 2000 unterstützt die automatische Übertragung von vererbbare ACEs.  
  
##  <a name="a-nameisselfrelativea--csecuritydescisselfrelative"></a><a name="isselfrelative"></a>CSecurityDesc::IsSelfRelative  
 Bestimmt, ob die Sicherheitsbeschreibung im selbstbezogenen Format ist.  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Sicherheitsbeschreibung im selbstbezogenen Format mit alle Sicherheitsinformationen in einem zusammenhängenden Speicherblock. Gibt False zurück, wenn die Sicherheitsbeschreibung im absoluten Format ist. Weitere Informationen finden Sie unter [Absolute und Sicherheitsdeskriptoren Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="a-namemakeabsolutea--csecuritydescmakeabsolute"></a><a name="makeabsolute"></a>CSecurityDesc::MakeAbsolute  
 Rufen Sie diese Methode, um die Sicherheits-ID in das absolute Format zu konvertieren.  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Methode erfolgreich ist, False andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Eine Sicherheitsbeschreibung im absoluten Format enthält Zeiger auf die darin enthaltenen Informationen, die anstatt die Informationen selbst. Eine Sicherheitsbeschreibung im selbstbezogenen Format enthält die Informationen in einem zusammenhängenden Speicherblock. In einer selbstbezogenen Sicherheitsbeschreibung eine **SECURITY_DESCRIPTOR** Struktur beginnt immer die Informationen, aber der Sicherheitsdeskriptor zu den anderen Komponenten die Struktur in einer beliebigen Reihenfolge folgen können. Statt Speicheradressen zu verwenden, werden die Komponenten des Sicherheitsdeskriptors selbstbezogenen durch Offsets vom Anfang des Sicherheitsdeskriptors identifiziert. Dieses Format ist nützlich, wenn ein Sicherheitsdeskriptor muss auf einem Datenträger gespeichert oder über ein Kommunikationsprotokoll übertragen. Weitere Informationen finden Sie unter [Absolute und Sicherheitsdeskriptoren Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="a-namemakeselfrelativea--csecuritydescmakeselfrelative"></a><a name="makeselfrelative"></a>CSecurityDesc::MakeSelfRelative  
 Rufen Sie diese Methode, um den Sicherheitsdeskriptor in relativen Format zu konvertieren.  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Methode erfolgreich ist, False andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Eine Sicherheitsbeschreibung im absoluten Format enthält Zeiger auf die darin enthaltenen Informationen, sondern mit den Daten selbst. Eine Sicherheitsbeschreibung im selbstbezogenen Format enthält die Informationen in einem zusammenhängenden Speicherblock. In einer selbstbezogenen Sicherheitsbeschreibung eine **SECURITY_DESCRIPTOR** Struktur beginnt immer die Informationen, aber der Sicherheitsdeskriptor zu den anderen Komponenten die Struktur in einer beliebigen Reihenfolge folgen können. Statt Speicheradressen zu verwenden, werden die Komponenten des Sicherheitsdeskriptors durch Offsets vom Anfang des Sicherheitsdeskriptors identifiziert. Dieses Format ist nützlich, wenn ein Sicherheitsdeskriptor muss auf einem Datenträger gespeichert oder über ein Kommunikationsprotokoll übertragen. Weitere Informationen finden Sie unter [Absolute und Sicherheitsdeskriptoren Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="a-nameoperatoreqa--csecuritydescoperator-"></a><a name="operator_eq"></a>CSecurityDesc::operator =  
 Zuweisungsoperator.  
  
```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);  
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die **SECURITY_DESCRIPTOR** Struktur oder `CSecurityDesc` Objekt zuweisen der `CSecurityDesc` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten `CSecurityDesc` Objekt.  
  
##  <a name="a-nameoperatorconstsecuritydescriptorstara--csecuritydescoperator-const-securitydescriptor-"></a><a name="operator_const_security_descriptor__star"></a>Const SECURITY_DESCRIPTOR CSecurityDesc::operator *  
 Wandelt einen Wert in einen Zeiger auf die **SECURITY_DESCRIPTOR** Struktur.  
  
```  
operator const SECURITY_DESCRIPTOR *() const throw();
```  
  
##  <a name="a-namesetcontrola--csecuritydescsetcontrol"></a><a name="setcontrol"></a>CSecurityDesc::SetControl  
 Legt die Steuerungsbits einer Sicherheitsbeschreibung fest.  
  
```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest, 
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ControlBitsOfInterest`  
 Ein **SECURITY_DESCRIPTOR_CONTROL** Maske, die die festzulegenden Steuerungsbits angibt. Eine Liste mit Flags, die festgelegt werden können, finden Sie unter [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
 `ControlBitsToSe`t  
 Eine `SECURITY_DESCRIPTOR_CONTROL`-Maske, die die neuen Werten für die Steuerbits angibt, die durch die `ControlBitsOfInterest`-Maske angegeben werden. Dieser Parameter kann eine Kombination der Flags sein, die für den Parameter `ControlBitsOfInterest` aufgeführt sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist verfügbar nur unter Windows 2000 und höher, wie er ruft [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
##  <a name="a-namesetdacla--csecuritydescsetdacl"></a><a name="setdacl"></a>CSecurityDesc::SetDacl  
 Legt die Informationen in eine DACL (discretionary Access Control List) fest. Wenn eine DACL bereits in die Sicherheits-ID vorhanden ist, wird es ersetzt.  
  
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
 Ein Verweis auf ein `CDacl` -Objekt, das die DACL für die Sicherheits-ID angibt. Dieser Parameter darf nicht NULL sein. Um eine NULL-DACL in den Sicherheitsdeskriptor festzulegen, sollte mit die erste Form der Methode verwendet werden `bPresent` auf False festgelegt.  
  
 `bPresent`  
 Gibt ein Flag, das Vorhandensein einer DACL in die Sicherheits-ID angibt. Wenn dieser Parameter auf true festgelegt ist, legt die Methode das SE_DACL_PRESENT-Flag in der **SECURITY_DESCRIPTOR_CONTROL** Struktur und verwendet die Werte in der *Dacl* und `bDefaulted` Parameter. Wenn sie falsch ist, wird die Methode löscht das Flag SE_DACL_PRESENT und `bDefaulted` wird ignoriert.  
  
 `bDefaulted`  
 Gibt ein Flag an, der die Quelle der DACL. Wenn dieses Flag auf true festgelegt ist, wurde die DACL durch einen Standardmechanismus abgerufen. Wenn false, wurde die DACL explizit von einem Benutzer angegeben. Die Methode speichert diesen Wert in das SE_DACL_DEFAULTED-Flag von der **SECURITY_DESCRIPTOR_CONTROL** Struktur. Wenn dieser Parameter nicht angegeben wird, wird das Flag SE_DACL_DEFAULTED deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Es ist ein wichtiger Unterschied zwischen einer leeren und einer nicht vorhandenen DACL. Wenn eine DACL leer ist, wird keine Access-Control-Einträge enthält, und keine Zugriffsrechte explizit erteilt wurde. Daher ist der Zugriff auf das Objekt implizit verweigert. Wenn ein Objekt keine DACL besitzt, auf der anderen Seite ist kein Schutz auf das Objekt zugewiesen, und jede zugriffsanforderung gewährt wird.  
  
##  <a name="a-namesetgroupa--csecuritydescsetgroup"></a><a name="setgroup"></a>CSecurityDesc::SetGroup  
 Legt die primären Informationen ein absolutes Format Sicherheitsbeschreibung, Austauschen von Informationen primäre Gruppe bereits vorhanden.  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `Sid`  
 Ein Verweis auf eine [CSid](../../atl/reference/csid-class.md) Objekt für den Sicherheitsdeskriptor neue primäre Gruppe. Dieser Parameter darf nicht NULL sein. Ein Sicherheitsdeskriptor kann gekennzeichnet werden, ohne eine DACL oder eine SACL, jedoch müssen sie diese auch eine Gruppe und einen Besitzer werden die NULL-SID (die eine integrierte SID mit einer speziellen Bedeutung ist).  
  
 `bDefaulted`  
 Gibt an, ob ein Standardmechanismus für die primäre Gruppeninformationen abgeleitet wurde. Wenn dieser Wert true ist, Standardinformationen ist und die-Methode diesen Wert als das SE_GROUP_DEFAULTED-Flag in speichert der **SECURITY_DESCRIPTOR_CONTROL** Struktur. Wenn dieser Parameter NULL ist, wird das Flag SE_GROUP_DEFAULTED deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="a-namesetownera--csecuritydescsetowner"></a><a name="setowner"></a>CSecurityDesc::SetOwner  
 Die Besitzerinformationen von einem Sicherheitsdeskriptor absolute Format fest. Alle bereits vorhandenen Besitzerinformationen ersetzt.  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `Sid`  
 Die [CSid](../../atl/reference/csid-class.md) -Objekt für den neuen primären Besitzer die Sicherheits-ID. Dieser Parameter darf nicht NULL sein.  
  
 `bDefaulted`  
 Gibt an, ob ein Standardmechanismus für die Informationen zum Besitzer abgeleitet wird. Wenn dieser Wert auf true festgelegt ist, ist es standardmäßig Informationen. Die Methode speichert diesen Wert als das SE_OWNER_DEFAULTED-Flag in der **SECURITY_DESCRIPTOR_CONTROL** Struktur. Wenn dieser Parameter NULL ist, wird das Flag SE_OWNER_DEFAULTED deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="a-namesetsacla--csecuritydescsetsacl"></a><a name="setsacl"></a>CSecurityDesc::SetSacl  
 Legt die Informationen in einem System Access Control List (SACL) fest. Wenn eine SACL bereits in die Sicherheits-ID vorhanden ist, wird es ersetzt.  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *SACL*  
 Zeiger auf ein `CSacl` -Objekt, das die SACL für die Sicherheits-ID angibt. Dieser Parameter darf nicht NULL sein und muss ein CSacl sein. Im Gegensatz zu DACLs besteht kein Unterschied zwischen NULL und eine leere SACL, wie die SACL-Objekte nicht Zugriffsrechte nur Überwachungsinformationen angeben.  
  
 `bDefaulted`  
 Gibt ein Flag, das die Quelle der SACL angibt. Wenn dieses Flag auf true festgelegt ist, wurde die SACL durch einen Standardmechanismus abgerufen. Wenn false, wurde die SACL explizit von einem Benutzer angegeben. Die Methode speichert diesen Wert in das SE_SACL_DEFAULTED-Flag von der **SECURITY_DESCRIPTOR_CONTROL** Struktur. Wenn dieser Parameter nicht angegeben wird, wird das Flag SE_SACL_DEFAULTED deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="a-nametostringa--csecuritydesctostring"></a><a name="tostring"></a>CSecurityDesc::ToString  
 Konvertiert einen Sicherheitsdeskriptor in einer Zeichenfolge.  
  
```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pstr`  
 Zeiger auf eine auf Null endende Zeichenfolge, die erhalten, wird die [Sicherheitsdeskriptor Zeichenfolgenformat](http://msdn.microsoft.com/library/windows/desktop/aa379570).  
  
 `si`  
 Gibt eine Kombination von Bitflags an, dass die Komponenten des Sicherheitsdeskriptors hinzufügen in der Ausgabezeichenfolge SECURITY_INFORMATION.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Sobald die Sicherheits-ID im Zeichenfolgenformat ist, kann es einfacher gespeichert oder übertragen werden. Verwenden der `CSecurityDesc::FromString` Methode, um die Zeichenfolge wieder in einen Sicherheitsdeskriptor zu konvertieren.  
  
 Die `si` Parameter kann die folgenden SECURITY_INFORMATION Flags enthalten:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|Sind Sie des Besitzers.|  
|GROUP_SECURITY_INFORMATION|Enthalten Sie die primäre Gruppe.|  
|DACL_SECURITY_INFORMATION|Enthalten Sie die DACL.|  
|SACL_SECURITY_INFORMATION|Enthalten Sie die SACL.|  
  
 Wenn die DACL NULL ist, und das Bit SE_DACL_PRESENT-Steuerelement in der Eingabe Sicherheitsdeskriptor festgelegt ist, schlägt die Methode fehl.  
  
 Wenn die DACL NULL ist, und das Bit SE_DACL_PRESENT-Steuerelement ist nicht in der Eingabe Sicherheitsdeskriptor festgelegt, muss die resultierende sicherheitsbeschreibungs-Zeichenfolge D: Komponente nicht. Finden Sie unter [Security Descriptor Zeichenfolgenformat](http://msdn.microsoft.com/library/windows/desktop/aa379570) für weitere Details.  
  
 Diese Methode ist nur verfügbar in Windows 2000 und höher wie ruft [wurde von ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für die Sicherheit](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Globale Funktionen für Sicherheit](../../atl/reference/security-global-functions.md)

