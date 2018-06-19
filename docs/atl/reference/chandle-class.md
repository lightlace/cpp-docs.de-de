---
title: CHandle Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
dev_langs:
- C++
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b57aab927380f8801c3b9cab258a695c7d8a59d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363070"
---
# <a name="chandle-class"></a>CHandle-Klasse
Diese Klasse stellt Methoden zum Erstellen und verwenden ein Handleobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CHandle
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|Der Konstruktor.|  
|[CHandle:: ~ CHandle](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|Rufen Sie diese Methode zum Anfügen der `CHandle` Objekt für eine vorhandene Handle.|  
|[CHandle::Close](#close)|Rufen Sie diese Methode zum Schließen einer `CHandle` Objekt.|  
|[CHandle::Detach](#detach)|Rufen Sie diese Methode, um ein Handle von trennen eine `CHandle` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHandle::operator HANDLE](#operator_handle)|Gibt den Wert des gespeicherten Handles.|  
|[CHandle::operator =](#operator_eq)|Zuweisungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|Die Membervariable, die das Handle speichert.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CHandle` Objekt kann verwendet werden, wenn ein Handle erforderlich ist: Der Hauptunterschied besteht darin, die die `CHandle` Objekt automatisch gelöscht werden.  
  
> [!NOTE]
>  Einige API-Funktionen verwenden die NULL als ein Handle leer oder ungültig, während andere INVALID_HANDLE_VALUE verwenden. `CHandle` verwendet NULL und wird nur behandeln INVALID_HANDLE_VALUE als echte Handle. Wenn Sie eine API der INVALID_HANDLE_VALUE zurückgegeben werden können aufrufen, sollten Sie überprüfen, für diesen Wert vor dem Aufruf [CHandle::Attach](#attach) oder Übergabe an die `CHandle` -Konstruktor, und stattdessen übergeben Sie NULL.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="attach"></a>  CHandle::Attach  
 Rufen Sie diese Methode zum Anfügen der `CHandle` Objekt für eine vorhandene Handle.  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 `CHandle` wird das Handle Besitz `h`.  
  
### <a name="remarks"></a>Hinweise  
 Weist die `CHandle` -Objekt an die `h` behandeln. Bei Builds den Debugger, werden ein ATLASSERT ausgegeben, wenn `h` ist NULL. Es erfolgt keine weitere Überprüfung hinsichtlich der Gültigkeit des Handles.  
  
##  <a name="chandle"></a>  CHandle::CHandle  
 Der Konstruktor.  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 Eine vorhandene Handle oder `CHandle`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein neues `CHandle` -Objekt optional mithilfe eines vorhandenen Handles oder `CHandle` Objekt.  
  
##  <a name="dtor"></a>  CHandle:: ~ CHandle  
 Der Destruktor.  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die `CHandle` Objekt durch Aufrufen von [CHandle::Close](#close).  
  
##  <a name="close"></a>  CHandle::Close  
 Rufen Sie diese Methode zum Schließen einer `CHandle` Objekt.  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Schließt ein Objekthandle öffnen. Wenn das Handle NULL, ist dies der Fall, wenn **schließen** wurde bereits aufgerufen wird, eine ATLASSERT ausgelöst in Debugbuilds.  
  
##  <a name="detach"></a>  CHandle::Detach  
 Rufen Sie diese Methode, um ein Handle von trennen eine `CHandle` Objekt.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die zu trennende Handle zurück.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz des Handles frei.  
  
##  <a name="m_h"></a>  CHandle::m_h  
 Die Membervariable, die das Handle speichert.  
  
```
HANDLE m_h;
```  
  
##  <a name="operator_eq"></a>  CHandle::operator =  
 Der Zuweisungsoperator.  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 `CHandle` wird das Handle Besitz `h`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das neue `CHandle` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CHandle` Objekt zurzeit ein Handle enthält, wird geschlossen. Die `CHandle` -Objekt übergebene wird über dessen Handle-Verweis, der auf NULL festgelegt. Dadurch wird sichergestellt, dass zwei `CHandle` Objekte nie active dasselbe Handle enthält.  
  
##  <a name="operator_handle"></a>  CHandle::operator HANDLE  
 Gibt den Wert des gespeicherten Handles.  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Wert in gespeicherten [CHandle::m_h](#m_h).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
