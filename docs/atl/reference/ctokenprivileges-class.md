---
title: CTokenPrivileges Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CTokenPrivileges
- CTokenPrivileges
- ATL.CTokenPrivileges
dev_langs:
- C++
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
caps.latest.revision: 23
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
ms.openlocfilehash: 4d732dbf27c2155ffb98ca59b140d01ea92458e0
ms.lasthandoff: 02/24/2017

---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges-Klasse
Diese Klasse ist ein Wrapper für die **TOKEN_PRIVILEGES** Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CTokenPrivileges
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|Ruft den Anzeigenamen für die Berechtigungen, die Bestandteil der `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetLength](#getlength)|Gibt die Größe des Puffers in Bytes, die zum Speichern der **TOKEN_PRIVILEGES** Struktur dargestellt werden, indem die `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Ruft die lokal eindeutige Bezeichner (LUIDs) und Attributflags aus der `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Ruft den Namen der Berechtigung und Attributflags aus ab dem `CTokenPrivileges` Objekt.|  
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Gibt einen Zeiger auf die **TOKEN_PRIVILEGES** Struktur.|  
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Das Attribut, das eine Berechtigungsnamen zugeordnete abgerufen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Const TOKEN_PRIVILEGES CTokenPrivileges::operator *](#operator_const_token_privileges__star)|Wandelt einen Wert in einen Zeiger auf die **TOKEN_PRIVILEGES** Struktur.|  
|[CTokenPrivileges::operator =](#operator_eq)|Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 Ein [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ist ein Objekt, das beschreibt den Sicherheitskontext für einen Prozess oder Thread, und jeder Benutzer ein Windows NT oder Windows 2000-System angemeldet zugeordnet ist.  
  
 Das Zugriffstoken wird zur Beschreibung der verschiedenen Sicherheitsprivilegien gewährt jedem Benutzer verwendet. Ein Recht besteht aus einer 64-Bit-Zahl, die bezeichnet einer lokal eindeutigen Kennung ( [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)) und eine Deskriptorzeichenfolge.  
  
 Die `CTokenPrivileges` ist ein Wrapper für die [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur und enthält 0 oder mehr Berechtigungen. Berechtigungen können gelöscht oder abgefragte mithilfe der angegebenen Klassenmethoden hinzugefügt werden.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="a-nameadda--ctokenprivilegesadd"></a><a name="add"></a>CTokenPrivileges::Add  
 Fügt eine oder mehrere Berechtigungen, um die `CTokenPrivileges` Access token-Objekt.  
  
```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);  
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pszPrivilege`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Berechtigung, gibt an, wie in der WINNT definiert. H-Headerdatei.  
  
 `bEnable`  
 Wenn true, ist die Berechtigung aktiviert. Bei false wird die Berechtigung deaktiviert.  
  
 `rPrivileges`  
 Ein Verweis auf eine [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur. Die Berechtigungen und Attribute von dieser Struktur kopiert und hinzugefügt, die `CTokenPrivileges` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Form dieser Methode zurückgibt true, wenn die Berechtigungen erfolgreich hinzugefügt werden, False andernfalls.  
  
##  <a name="a-namectokenprivilegesa--ctokenprivilegesctokenprivileges"></a><a name="ctokenprivileges"></a>CTokenPrivileges::CTokenPrivileges  
 Der Konstruktor.  
  
```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );  
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rhs`  
 Das `CTokenPrivileges` Objekt, das das neue Objekt zugewiesen.  
  
 `rPrivileges`  
 Die [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur, die dem neuen Server `CTokenPrivileges` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CTokenPrivileges` -Objekt kann optional mit erstellt werden ein **TOKEN_PRIVILEGES** Struktur oder eine zuvor definierte `CTokenPrivileges` Objekt.  
  
##  <a name="a-namedtora--ctokenprivilegesctokenprivileges"></a><a name="dtor"></a>CTokenPrivileges:: ~ CTokenPrivileges  
 Der Destruktor.  
  
```
virtual ~CTokenPrivileges() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="a-namedeletea--ctokenprivilegesdelete"></a><a name="delete"></a>CTokenPrivileges::Delete  
 Löscht eine Berechtigung aus der `CTokenPrivileges` Access token-Objekt.  
  
```
bool Delete(LPCTSTR pszPrivilege) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszPrivilege`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Berechtigung, gibt an, wie in der WINNT definiert. H-Headerdatei. Beispielsweise kann dieser Parameter der SE_SECURITY_NAME-Konstante oder die entsprechende Zeichenfolge, die "Berechtigung" SeSecurityPrivilege "." angeben  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Berechtigung wurde erfolgreich gelöscht, andernfalls false wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode eignet sich als Tool zum Erstellen von eingeschränkter Tokens unter Windows 2000.  
  
##  <a name="a-namedeletealla--ctokenprivilegesdeleteall"></a><a name="deleteall"></a>CTokenPrivileges::DeleteAll  
 Löscht alle Berechtigungen für die `CTokenPrivileges` Zugriff-token-Objekts.  
  
```
void DeleteAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Löscht alle Berechtigungen, die Bestandteil der `CTokenPrivileges` Zugriff-token-Objekts.  
  
##  <a name="a-namegetdisplaynamesa--ctokenprivilegesgetdisplaynames"></a><a name="getdisplaynames"></a>CTokenPrivileges::GetDisplayNames  
 Ruft den Anzeigenamen für die Berechtigungen, die Bestandteil der `CTokenPrivileges` Zugriff-token-Objekts.  
  
```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisplayNames`  
 Ein Zeiger auf ein Array von `CString`-Objekten. **CNames** wird definiert, wie eine Typedef: **CTokenPrivileges::CAtlArray\<CString >**.  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter `pDisplayNames` ist ein Zeiger auf ein Array von `CString` Objekte, die die Anzeigenamen für den in enthaltenen Berechtigungen erhält das `CTokenPrivileges` Objekt. Diese Methode ruft nur die Berechtigungen im Abschnitt definiert Berechtigungen von WINNT angegebenen Anzeigenamen ab. H.  
  
 Diese Methode ruft einen angezeigten Namen: z. B. der Attributnamen SE_REMOTE_SHUTDOWN_NAME angezeigten Namen ist, "Erzwingen des Herunterfahrens von einem Remotesystem aus." Verwenden Sie zum Abrufen der Systemname [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes).  
  
##  <a name="a-namegetcounta--ctokenprivilegesgetcount"></a><a name="getcount"></a>CTokenPrivileges::GetCount  
 Gibt die Anzahl der Berechtigung Einträge in der `CTokenPrivileges` Objekt.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Berechtigungen, die Bestandteil der `CTokenPrivileges` Objekt.  
  
##  <a name="a-namegetlengtha--ctokenprivilegesgetlength"></a><a name="getlength"></a>CTokenPrivileges::GetLength  
 Gibt die Länge der `CTokenPrivileges` Objekt.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Bytes, die zum Speichern einer **TOKEN_PRIVILEGES** Struktur dargestellt werden, indem die `CTokenPrivileges` -Objekts, einschließlich aller enthaltenen Recht Einträge.  
  
##  <a name="a-namegetluidsandattributesa--ctokenprivilegesgetluidsandattributes"></a><a name="getluidsandattributes"></a>CTokenPrivileges::GetLuidsAndAttributes  
 Ruft die lokal eindeutige Bezeichner (LUIDs) und Attributflags aus der `CTokenPrivileges` Objekt.  
  
```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pPrivileges`  
 Zeiger auf ein Array von [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) Objekte. **CLUIDArray** ist eine Typedef, die als definiert **CAtlArray\<LUID > CLUIDArray**.  
  
 `pAttributes`  
 Ein Zeiger auf ein Array von DWORD-Objekten. Wenn dieser Parameter nicht angegeben oder NULL ist, werden die Attribute nicht abgerufen werden. **CAttributes** ist eine Typedef definiert als **CAtlArray \<DWORD > CAttributes**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode werden alle Berechtigungen, die in enthaltenen Aufzählen der `CTokenPrivileges` -token-Objekts zugreifen, und platzieren Sie die einzelnen LUIDs und (optional) die Attributflags in Arrayobjekte.  
  
##  <a name="a-namegetnamesandattributesa--ctokenprivilegesgetnamesandattributes"></a><a name="getnamesandattributes"></a>CTokenPrivileges::GetNamesAndAttributes  
 Ruft den Namen und Flags aus der `CTokenPrivileges` Objekt.  
  
```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *pNames*  
 Zeiger auf ein Array von `CString` Objekte. **CNames** ist eine Typedef, die als definiert **CAtlArray \<CString > CNames**.  
  
 `pAttributes`  
 Ein Zeiger auf ein Array von DWORD-Objekten. Wenn dieser Parameter nicht angegeben oder NULL ist, werden die Attribute nicht abgerufen werden. **CAttributes** ist eine Typedef definiert als **CAtlArray \<DWORD > CAttributes**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode werden alle Berechtigungen, die in enthaltenen Aufzählen der `CTokenPrivileges` -Objekt, platzieren den Namen und (optional) die Attributflags in Arrayobjekte.  
  
 Diese Methode ruft den angezeigten Namen, anstatt den Attributnamen ab: z. B. der Attributnamen SE_REMOTE_SHUTDOWN_NAME, der Namen des ist "SeRemoteShutdownPrivilege." Um den angezeigten Namen zu erhalten, verwenden Sie die Methode [CTokenPrivileges::GetDisplayNames](#getdisplaynames).  
  
##  <a name="a-namegetptokenprivilegesa--ctokenprivilegesgetptokenprivileges"></a><a name="getptoken_privileges"></a>CTokenPrivileges::GetPTOKEN_PRIVILEGES  
 Gibt einen Zeiger auf die **TOKEN_PRIVILEGES** Struktur.  
  
```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur.  
  
##  <a name="a-namelookupprivilegea--ctokenprivilegeslookupprivilege"></a><a name="lookupprivilege"></a>CTokenPrivileges::LookupPrivilege  
 Das Attribut, das eine Berechtigungsnamen zugeordnete abgerufen.  
  
```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pszPrivilege`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Berechtigung, gibt an, wie in der WINNT definiert. H-Headerdatei. Beispielsweise kann dieser Parameter der SE_SECURITY_NAME-Konstante oder die entsprechende Zeichenfolge, die "Berechtigung" SeSecurityPrivilege "." angeben  
  
 `pdwAttributes`  
 Ein Zeiger auf eine Variable, die Attribute empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn das Attribut wurde erfolgreich abgerufen, andernfalls false ist.  
  
##  <a name="a-nameoperatoreqa--ctokenprivilegesoperator-"></a><a name="operator_eq"></a>CTokenPrivileges::operator =  
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
 Gibt den aktualisierten `CTokenPrivileges` Objekt.  
  
##  <a name="a-nameoperatorconsttokenprivilegesstara--ctokenprivilegesoperator-const-tokenprivileges-"></a><a name="operator_const_token_privileges__star"></a>Const TOKEN_PRIVILEGES CTokenPrivileges::operator *  
 Wandelt einen Wert in einen Zeiger auf die **TOKEN_PRIVILEGES** Struktur.  
  
```  
operator const TOKEN_PRIVILEGES *() const throw(...);
```  
  
### <a name="remarks"></a>Hinweise  
 Wandelt einen Wert in einen Zeiger auf die [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für die Sicherheit](../../visual-cpp-samples.md)   
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 ["LUID_AND_ATTRIBUTES"](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Globale Funktionen für Sicherheit](../../atl/reference/security-global-functions.md)

