---
title: Klasse CComSafeDeleteCriticalSection | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
dev_langs:
- C++
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 511627de9d4f6411c508dd78a237cf546e2493de
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection-Klasse
Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|Der Konstruktor.|  
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::Init](#init)|Erstellt und initialisiert ein kritisches Abschnittsobjekt.|  
|[CComSafeDeleteCriticalSection::Lock](#lock)|Ruft den Besitz des Objekt des kritischen Abschnitts.|  
|[CComSafeDeleteCriticalSection::Term](#term)|Gibt die vom Objekt kritischen Abschnitts verwendete Systemressourcen frei.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_bInitialized](#m_binitialized)|Flags, ob die interne **CRITICAL_SECTION** Objekt initialisiert wurde.|  
  
## <a name="remarks"></a>Hinweise  
 `CComSafeDeleteCriticalSection`leitet sich von der Klasse ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md). Allerdings `CComSafeDeleteCriticalSection` bietet zusätzliche Sicherheit Mechanismen über ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md).  
  
 Wenn eine Instanz von `CComSafeDeleteCriticalSection` den Gültigkeitsbereich verlässt oder explizit aus dem Speicher gelöscht, das zugrunde liegende Objekt des kritischen Abschnitts werden automatisch bereinigt, wenn es noch gültig ist. Darüber hinaus die [CComSafeDeleteCriticalSection::Term](#term) Methode ordnungsgemäß beendet, wenn das zugrunde liegende Objekt des kritischen Abschnitts noch nicht zugewiesen wurde oder bereits aus dem Speicher freigegeben wurde.  
  
 Finden Sie unter ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md) Weitere Informationen zu kritischen Abschnitt Hilfsklassen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="ccomsafedeletecriticalsection"></a>CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection  
 Der Konstruktor.  
  
```
CComSafeDeleteCriticalSection();
```  
  
### <a name="remarks"></a>Hinweise  
 Legt die [M_bInitialized](#m_binitialized) -Datenmember auf **false**.  
  
##  <a name="dtor"></a>CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection  
 Der Destruktor.  
  
```
~CComSafeDeleteCriticalSection() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die interne **CRITICAL_SECTION** Objekt aus dem Speicher, wenn der [M_bInitialized](#m_binitialized) -Datenmember festgelegt ist, um **true**.  
  
##  <a name="init"></a>CComSafeDeleteCriticalSection::Init  
 Ruft die Implementierung der Basisklasse der [Init](/visualstudio/debugger/init) und [M_bInitialized](#m_binitialized) auf **true** bei Erfolg.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init).  
  
##  <a name="lock"></a>CComSafeDeleteCriticalSection::Lock  
Ruft die Implementierung der Basisklasse der [Sperren](ccomcriticalsection-class.md#lock).  

  
```
HRESULT Lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode geht die [M_bInitialized](#m_binitialized) -Datenmember auf festgelegt ist **true** bei der Eingabe. Eine Assertion in Debugbuilds generiert, wenn diese Condidtion nicht erfüllt wird.  
  
 Weitere Informationen zum Verhalten der Funktion finden Sie unter [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
##  <a name="m_binitialized"></a>CComSafeDeleteCriticalSection::m_bInitialized  
 Flags, ob die interne **CRITICAL_SECTION** Objekt initialisiert wurde.  
  
```
bool m_bInitialized;
```  
  
### <a name="remarks"></a>Hinweise  
 Die **M_bInitialized** -Datenmember wird verwendet, um die Gültigkeit des zugrunde liegenden nachverfolgen **CRITICAL_SECTION** zugeordnete Objekt der [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) Klasse. Die zugrunde liegende **CRITICAL_SECTION** Objekt wird nicht aus dem Speicher freigegeben werden, wenn dieses Flag nicht festgelegt ist versucht **true**.  
  
##  <a name="term"></a>CComSafeDeleteCriticalSection::Term  
 Ruft die Implementierung der Basisklasse der [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) Wenn das interne **CRITICAL_SECTION** -Objekt gültig ist.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), oder **S_OK** Wenn [M_bInitialized](#m_binitialized) wurde **false** bei der Eingabe.  
  
### <a name="remarks"></a>Hinweise  
 Es ist sicher, rufen Sie diese Methode auch wenn die interne **CRITICAL_SECTION** Objekt ist ungültig. Der Destruktor dieser Klasse ruft diese Methode auf, wenn die [M_bInitialized](#m_binitialized) -Datenmember festgelegt ist, um **true**.  
  
## <a name="see-also"></a>Siehe auch  
 ["CComCriticalSection"-Klasse](../../atl/reference/ccomcriticalsection-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

