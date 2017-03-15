---
title: Klasse CHandle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CHandle
- ATL::CHandle
- CHandle
dev_langs:
- C++
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: bbc0703ae5eaab01c0819be7e378509c7dc579ef
ms.lasthandoff: 02/24/2017

---
# <a name="chandle-class"></a>CHandle-Klasse
Diese Klasse stellt Methoden zum Erstellen und verwenden ein Handleobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CHandle
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|Der Konstruktor.|  
|[CHandle:: ~ CHandle](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|Rufen Sie diese Methode zum Anfügen der `CHandle` Objekt für ein vorhandenes Handle.|  
|[CHandle::Close](#close)|Rufen Sie diese Methode zum Schließen einer `CHandle` Objekt.|  
|[CHandle::Detach](#detach)|Rufen Sie diese Methode, um ein Handle von Trennen einer `CHandle` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHandle::operator HANDLE](#operator_handle)|Gibt den Wert des gespeicherten Handles.|  
|[CHandle::operator =](#operator_eq)|Zuweisungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|Membervariable, die das Handle gespeichert.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CHandle` -Objekt kann verwendet werden, wenn ein Handle erforderlich ist: Der Hauptunterschied besteht darin, die die `CHandle` Objekt automatisch gelöscht.  
  
> [!NOTE]
>  Manche API-Funktionen verwenden die NULL als ein Handle leer oder ungültig, während andere INVALID_HANDLE_VALUE verwenden. `CHandle`verwendet NULL und wird nur behandeln INVALID_HANDLE_VALUE als ein echtes Handle. Wenn Sie eine API, die INVALID_HANDLE_VALUE zurückgeben kann aufrufen, sollten Sie überprüfen, für diesen Wert vor dem Aufruf von [CHandle::Attach](#attach) oder Übergabe an den `CHandle` -Konstruktor, und stattdessen übergeben Sie NULL.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-nameattacha--chandleattach"></a><a name="attach"></a>CHandle::Attach  
 Rufen Sie diese Methode zum Anfügen der `CHandle` Objekt für ein vorhandenes Handle.  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 `CHandle`wird das Handle Besitz `h`.  
  
### <a name="remarks"></a>Hinweise  
 Weist die `CHandle` -Objekt an die `h` zu behandeln. Debugger-Builds ein ATLASSERT wird ausgelöst, wenn `h` NULL ist. Keine anderen Hinblick auf die Gültigkeit des Handles wird überprüft.  
  
##  <a name="a-namechandlea--chandlechandle"></a><a name="chandle"></a>CHandle::CHandle  
 Der Konstruktor.  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 Ein vorhandenes Handle oder `CHandle`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein neues `CHandle` -Objekt optional mithilfe eines vorhandenen Handles oder `CHandle` Objekt.  
  
##  <a name="a-namedtora--chandlechandle"></a><a name="dtor"></a>CHandle:: ~ CHandle  
 Der Destruktor.  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Frei der `CHandle` -Objekt durch Aufrufen von [CHandle::Close](#close).  
  
##  <a name="a-nameclosea--chandleclose"></a><a name="close"></a>CHandle::Close  
 Rufen Sie diese Methode zum Schließen einer `CHandle` Objekt.  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Schließt ein offenes Objekthandle. Wenn das Handle NULL ist, ist der Fall, wenn sich **schließen** wurde bereits aufgerufen wird, eine ATLASSERT ausgelöst in Debug-Builds.  
  
##  <a name="a-namedetacha--chandledetach"></a><a name="detach"></a>CHandle::Detach  
 Rufen Sie diese Methode, um ein Handle von Trennen einer `CHandle` Objekt.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Handle abgetrennt werden.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz des Handles frei.  
  
##  <a name="a-namemha--chandlemh"></a><a name="m_h"></a>CHandle::m_h  
 Membervariable, die das Handle gespeichert.  
  
```
HANDLE m_h;
```  
  
##  <a name="a-nameoperatoreqa--chandleoperator-"></a><a name="operator_eq"></a>CHandle::operator =  
 Der Zuweisungsoperator.  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 `CHandle`wird das Handle Besitz `h`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die neue `CHandle` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CHandle` Objekt zurzeit ein Handle enthält, wird geschlossen. Das `CHandle` -Objekt übergebene müssen den Handle-Verweis auf NULL festgelegt. Dadurch wird sichergestellt, dass zwei `CHandle` Objekte nie active dasselbe Handle enthält.  
  
##  <a name="a-nameoperatorhandlea--chandleoperator-handle"></a><a name="operator_handle"></a>CHandle::operator HANDLE  
 Gibt den Wert des gespeicherten Handles.  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Wert in gespeicherten [CHandle::m_h](#m_h).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

