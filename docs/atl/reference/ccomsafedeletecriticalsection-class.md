---
title: CComSafeDeleteCriticalSection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b822a76cf98acb38cd5b785a868b989a96b96a12
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879438"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection-Klasse
Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts-Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|Der Konstruktor.|  
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::Init](#init)|Erstellt und initialisiert ein Objekt des kritischen Abschnitts.|  
|[CComSafeDeleteCriticalSection::Lock](#lock)|Ruft den Besitz von Objekt des kritischen Abschnitts ab.|  
|[CComSafeDeleteCriticalSection::Term](#term)|Gibt ein Objekt des kritischen Abschnitts, die Systemressourcen frei.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_bInitialized](#m_binitialized)|Flags, ob die interne `CRITICAL_SECTION` Objekt initialisiert wurde.|  
  
## <a name="remarks"></a>Hinweise  
 `CComSafeDeleteCriticalSection` leitet sich von der Klasse [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Allerdings `CComSafeDeleteCriticalSection` bietet zusätzliche Sicherheit Mechanismen gegenüber [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  
  
 Wenn eine Instanz des `CComSafeDeleteCriticalSection` den Gültigkeitsbereich verlässt oder wird explizit aus dem Arbeitsspeicher gelöscht, das zugrunde liegende Objekt des kritischen Abschnitts werden automatisch bereinigt, wenn es noch gültig ist. Darüber hinaus die [CComSafeDeleteCriticalSection::Term](#term) Methode wird ordnungsgemäß beendet, wenn das zugrunde liegende Objekt für den kritischen Abschnitt noch nicht zugewiesen wurde oder bereits aus dem Arbeitsspeicher freigegeben wurde.  
  
 Finden Sie unter [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) für Weitere Informationen zu den kritischen Abschnitt-Hilfsklassen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="ccomsafedeletecriticalsection"></a>  CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection  
 Der Konstruktor.  
  
```
CComSafeDeleteCriticalSection();
```  
  
### <a name="remarks"></a>Hinweise  
 Legt die [M_bInitialized](#m_binitialized) -Datenmember auf "false".  
  
##  <a name="dtor"></a>  CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection  
 Der Destruktor.  
  
```
~CComSafeDeleteCriticalSection() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt das interne `CRITICAL_SECTION` Objekt vom Arbeitsspeicher, wenn die [M_bInitialized](#m_binitialized) -Datenmember auf "true" festgelegt ist.  
  
##  <a name="init"></a>  CComSafeDeleteCriticalSection::Init  
 Ruft die basisklassenimplementierung von [Init](/visualstudio/debugger/init) und [M_bInitialized](#m_binitialized) auf "true" bei Erfolg.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis des [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init).  
  
##  <a name="lock"></a>  CComSafeDeleteCriticalSection::Lock  
Ruft die basisklassenimplementierung von [Sperre](ccomcriticalsection-class.md#lock).  

  
```
HRESULT Lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis des [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode geht davon aus den [M_bInitialized](#m_binitialized) Datenmember beim Eintritt auf "true" festgelegt ist. Eine Assertion in Debugbuilds generiert, wenn diese Condidtion nicht erfüllt wird.  
  
 Weitere Informationen zum Verhalten der Funktion finden Sie unter [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
##  <a name="m_binitialized"></a>  CComSafeDeleteCriticalSection::m_bInitialized  
 Flags, ob die interne `CRITICAL_SECTION` Objekt initialisiert wurde.  
  
```
bool m_bInitialized;
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_bInitialized` Datenmember wird verwendet, um die Gültigkeit des zugrunde liegenden nachverfolgen `CRITICAL_SECTION` zugeordnete Objekt der [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) Klasse. Die zugrunde liegende `CRITICAL_SECTION` Objekt wird nicht ausgeführt werden, um aus dem Speicher freigegeben werden, wenn dieses Flag nicht auf "true" festgelegt ist.  
  
##  <a name="term"></a>  CComSafeDeleteCriticalSection::Term  
 Ruft die basisklassenimplementierung von [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) Wenn die interne `CRITICAL_SECTION` Objekt gültig ist.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis des [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), oder S_OK Wenn [M_bInitialized](#m_binitialized) beim Eintritt auf "false" festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Es ist sicherer, rufen Sie diese Methode auch, wenn die interne `CRITICAL_SECTION` -Objekt ist ungültig. Der Destruktor dieser Klasse ruft diese Methode auf, wenn die [M_bInitialized](#m_binitialized) -Datenmember auf "true" festgelegt ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CComCriticalSection-Klasse](../../atl/reference/ccomcriticalsection-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
