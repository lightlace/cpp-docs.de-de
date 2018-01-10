---
title: CTokenPrivileges Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
dev_langs: C++
helpviewer_keywords: CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0dc0fb58d1b92fac1462b355b9afb353554f3f23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges-Klasse
Diese Klasse ist ein Wrapper für die **TOKEN_PRIVILEGES** Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CTokenPrivileges
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|Der Konstruktor.|  
|[CTokenPrivileges:: ~ CTokenPrivileges](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTokenPrivileges::Add](#add)|Fügt eine oder mehrere Berechtigungen, um die `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::Delete](#delete)|Löscht eine Berechtigung aus der `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::DeleteAll](#deleteall)|Löscht alle Berechtigungen aus der `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetCount](#getcount)|Gibt die Anzahl der Berechtigung Einträge in der `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|Ruft den Anzeigenamen für die Berechtigungen innerhalb der `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetLength](#getlength)|Gibt die Größe des Puffers in Bytes erforderlich ist, enthält die **TOKEN_PRIVILEGES** Struktur dargestellt werden, indem die `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Ruft Attributflags aus und lokal eindeutige Bezeichner (LUIDs) ab dem `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Ruft ab, die Berechtigung-Namen und Attributflags aus der `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Gibt einen Zeiger auf die **TOKEN_PRIVILEGES** Struktur.|  
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Ruft das Attribut verknüpft sind mit einem Namen der Berechtigung ab.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Const TOKEN_PRIVILEGES CTokenPrivileges::operator *](#operator_const_token_privileges__star)|Wandelt einen Wert in einen Zeiger auf die **TOKEN_PRIVILEGES** Struktur.|  
|[CTokenPrivileges::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Ein [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ein Objekt, das den Sicherheitskontext für einen Prozess oder Thread beschreibt und erhält jeder Benutzer ein Windows NT oder Windows 2000-System angemeldet ist.  
  
 Das Zugriffstoken wird verwendet, um die verschiedenen Sicherheitsprivilegien gewährt jedem Benutzer zu beschreiben. Eine Berechtigung besteht aus einer 64-Bit-Zahl, die eine lokal eindeutige Kennung aufgerufen ( [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)) und eine sicherheitsbeschreibungs-Zeichenfolge.  
  
 Die `CTokenPrivileges` Klasse ist ein Wrapper für die [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur und enthält 0 oder mehr Berechtigungen. Berechtigungen können gelöschte oder abgefragte mithilfe der angegebenen Klassenmethoden hinzugefügt werden.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Access Control](http://msdn.microsoft.com/library/windows/desktop/aa374860) im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="add"></a>CTokenPrivileges::Add  
 Fügt eine oder mehrere Berechtigungen, um die `CTokenPrivileges` Access-token-Objekt.  
  
```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);  
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pszPrivilege`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Berechtigung, gibt an, wie in der WINNT definiert. H-Headerdatei.  
  
 `bEnable`  
 Bei "true", ist die Berechtigung aktiviert. Die Berechtigung ist deaktiviert, wenn "false".  
  
 `rPrivileges`  
 Ein Verweis auf eine [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur. Die Berechtigungen und die Attribute von dieser Struktur kopiert und hinzugefügt werden, um die `CTokenPrivileges` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Form dieser Methode gibt "true", die Berechtigungen sind erfolgreich hinzugefügt, "false" andernfalls zurück.  
  
##  <a name="ctokenprivileges"></a>CTokenPrivileges::CTokenPrivileges  
 Der Konstruktor.  
  
```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );  
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Die `CTokenPrivileges` -Objekt, mit dem neuen Objekt zugewiesen.  
  
 `rPrivileges`  
 Die [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Zuweisen der neuen Struktur `CTokenPrivileges` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CTokenPrivileges` Objekt kann optional mit erstellt werden ein **TOKEN_PRIVILEGES** Struktur oder eine zuvor definierte `CTokenPrivileges` Objekt.  
  
##  <a name="dtor"></a>CTokenPrivileges:: ~ CTokenPrivileges  
 Der Destruktor.  
  
```
virtual ~CTokenPrivileges() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="delete"></a>CTokenPrivileges::Delete  
 Löscht eine Berechtigung aus der `CTokenPrivileges` Access-token-Objekt.  
  
```
bool Delete(LPCTSTR pszPrivilege) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszPrivilege`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Berechtigung, gibt an, wie in der WINNT definiert. H-Headerdatei. Beispielsweise kann dieser Parameter die Konstante SE_SECURITY_NAME oder die entsprechende Zeichenfolge, die "Berechtigung" SeSecurityPrivilege "." angeben  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Berechtigung wurde erfolgreich gelöscht, andernfalls false wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode eignet sich als ein Tool zum Erstellen von eingeschränkten Token unter Windows 2000.  
  
##  <a name="deleteall"></a>CTokenPrivileges::DeleteAll  
 Löscht alle Berechtigungen aus der `CTokenPrivileges` Access-token-Objekt.  
  
```
void DeleteAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Löscht alle Berechtigungen enthalten, die der `CTokenPrivileges` Access-token-Objekt.  
  
##  <a name="getdisplaynames"></a>CTokenPrivileges::GetDisplayNames  
 Ruft den Anzeigenamen für die Berechtigungen innerhalb der `CTokenPrivileges` Access-token-Objekt.  
  
```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisplayNames`  
 Ein Zeiger auf ein Array von `CString`-Objekten. **CNames** ist definiert als Typedef: **CTokenPrivileges::CAtlArray\<CString >**.  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter `pDisplayNames` ist ein Zeiger auf ein Array von `CString` -Objekte, die die Anzeigenamen für die Berechtigungen, die in enthaltenen erhält die `CTokenPrivileges` Objekt. Diese Methode ruft nur für die Berechtigungen, die im Abschnitt definiert Berechtigungen von WINNT angegebenen Anzeigenamen ab. H.  
  
 Diese Methode ruft einen angezeigten Namen ab: beispielsweise der Attributnamen SE_REMOTE_SHUTDOWN_NAME anzeigbaren Name ist, "Erzwingen des Herunterfahrens von einem Remotesystem." Verwenden Sie zum Abrufen der Systemname [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes).  
  
##  <a name="getcount"></a>CTokenPrivileges::GetCount  
 Gibt die Anzahl der Berechtigung Einträge in der `CTokenPrivileges` Objekt.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl von Berechtigungen, die der `CTokenPrivileges` Objekt.  
  
##  <a name="getlength"></a>CTokenPrivileges::GetLength  
 Gibt die Länge der `CTokenPrivileges` Objekt.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Bytes, die zum Speichern erforderlichen eine **TOKEN_PRIVILEGES** Struktur dargestellt werden, indem die `CTokenPrivileges` Objekts, z. B. alle Berechtigungen-Einträge, die es enthält.  
  
##  <a name="getluidsandattributes"></a>CTokenPrivileges::GetLuidsAndAttributes  
 Ruft Attributflags aus und lokal eindeutige Bezeichner (LUIDs) ab dem `CTokenPrivileges` Objekt.  
  
```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pPrivileges`  
 Zeiger auf ein Array von [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) Objekte. **CLUIDArray** ist eine Typedef, die als definiert **CAtlArray\<LUID > CLUIDArray**.  
  
 `pAttributes`  
 Ein Zeiger auf ein Array von DWORD-Objekten. Wenn dieser Parameter nicht angegeben oder NULL ist, werden die Attribute nicht abgerufen werden. **CAttributes** ist eine Typedef, die als definiert **CAtlArray \<DWORD > CAttributes**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode listet alle Berechtigungen enthalten, die der `CTokenPrivileges` Tokenobjekt zugreifen und die einzelnen LUIDs und (optional) die Attributflags in Arrayobjekte platziert.  
  
##  <a name="getnamesandattributes"></a>CTokenPrivileges::GetNamesAndAttributes  
 Ruft den Namen und Attribut Flags aus der `CTokenPrivileges` Objekt.  
  
```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *pNames*  
 Zeiger auf ein Array von `CString` Objekte. **CNames** ist eine Typedef, die als definiert **CAtlArray \<CString > CNames**.  
  
 `pAttributes`  
 Ein Zeiger auf ein Array von DWORD-Objekten. Wenn dieser Parameter nicht angegeben oder NULL ist, werden die Attribute nicht abgerufen werden. **CAttributes** ist eine Typedef, die als definiert **CAtlArray \<DWORD > CAttributes**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode listet alle Berechtigungen enthalten, die der `CTokenPrivileges` -Objekt, wenn Sie den Namen und (optional) die Attributflags in Arrayobjekte einfügen.  
  
 Diese Methode ruft den Attributnamen, anstelle des darstellbaren Namens ab: beispielsweise der Attributnamen SE_REMOTE_SHUTDOWN_NAME ist, ist der Systemname "SeRemoteShutdownPrivilege." Verwenden Sie die Methode zum Abrufen der anzeigbaren namens [CTokenPrivileges::GetDisplayNames](#getdisplaynames).  
  
##  <a name="getptoken_privileges"></a>CTokenPrivileges::GetPTOKEN_PRIVILEGES  
 Gibt einen Zeiger auf die **TOKEN_PRIVILEGES** Struktur.  
  
```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur.  
  
##  <a name="lookupprivilege"></a>CTokenPrivileges::LookupPrivilege  
 Ruft das Attribut verknüpft sind mit einem Namen der Berechtigung ab.  
  
```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pszPrivilege`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Berechtigung, gibt an, wie in der WINNT definiert. H-Headerdatei. Beispielsweise kann dieser Parameter die Konstante SE_SECURITY_NAME oder die entsprechende Zeichenfolge, die "Berechtigung" SeSecurityPrivilege "." angeben  
  
 `pdwAttributes`  
 Ein Zeiger auf eine Variable, die Attribute empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn das Attribut erfolgreich abgerufen werden, "false" ist.  
  
##  <a name="operator_eq"></a>CTokenPrivileges::operator =  
 Zuweisungsoperator.  
  
```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);  
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rPrivileges`  
 Die [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur zuweisen der `CTokenPrivileges` Objekt.  
  
 `rhs`  
 Die `CTokenPrivileges` -Objekt, das dem Objekt zugewiesen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CTokenPrivileges` Objekt.  
  
##  <a name="operator_const_token_privileges__star"></a>Const TOKEN_PRIVILEGES CTokenPrivileges::operator *  
 Wandelt einen Wert in einen Zeiger auf die **TOKEN_PRIVILEGES** Struktur.  
  
```  
operator const TOKEN_PRIVILEGES *() const throw(...);
```  
  
### <a name="remarks"></a>Hinweise  
 Wandelt einen Wert in einen Zeiger auf die [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für nachrichtensicherheit](../../visual-cpp-samples.md)   
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 ["LUID_AND_ATTRIBUTES"](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
