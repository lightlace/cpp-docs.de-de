---
title: CComSafeDeleteCriticalSection Klasse | Microsoft Docs
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
ms.openlocfilehash: cff637f9e307f2714cd351f3c6bcaf1e4b78342e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363858"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection-Klasse
Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt bereit.  
  
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
|[CComSafeDeleteCriticalSection::Init](#init)|Erstellt und initialisiert ein kritisches Abschnittsobjekt.|  
|[CComSafeDeleteCriticalSection::Lock](#lock)|Ruft den Besitz des Objekts kritischen Abschnitt ab.|  
|[CComSafeDeleteCriticalSection::Term](#term)|Gibt die Systemressourcen geschont, indem Sie die kritischen Abschnittsobjekt frei.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_bInitialized](#m_binitialized)|Flags, ob die interne **CRITICAL_SECTION** Objekt initialisiert wurde.|  
  
## <a name="remarks"></a>Hinweise  
 `CComSafeDeleteCriticalSection` leitet sich von der Klasse ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md). Allerdings `CComSafeDeleteCriticalSection` bietet zusätzliche Sicherheit Mechanismen gegenüber ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md).  
  
 Wenn eine Instanz von `CComSafeDeleteCriticalSection` den Gültigkeitsbereich verlässt oder wird explizit aus dem Arbeitsspeicher gelöscht, die zugrunde liegenden kritischen Abschnittsobjekt werden automatisch bereinigt, wenn es noch gültig ist. Darüber hinaus die [CComSafeDeleteCriticalSection::Term](#term) Methode ordnungsgemäß beendet, wenn die zugrunde liegenden kritischen Abschnittsobjekt noch nicht belegt wurde oder bereits aus dem Arbeitsspeicher freigegeben wurde.  
  
 Finden Sie unter ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md) für Weitere Informationen zu kritischen Abschnitt Hilfsklassen.  
  
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
 Legt die [M_bInitialized](#m_binitialized) Datenmember **"false"**.  
  
##  <a name="dtor"></a>  CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection  
 Der Destruktor.  
  
```
~CComSafeDeleteCriticalSection() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt das interne **CRITICAL_SECTION** Objekt aus dem Arbeitsspeicher, wenn die [M_bInitialized](#m_binitialized) -Datenmember festgelegt ist, um **"true"**.  
  
##  <a name="init"></a>  CComSafeDeleteCriticalSection::Init  
 Ruft die basisklassenimplementierung der [Init](/visualstudio/debugger/init) und legt [M_bInitialized](#m_binitialized) auf **"true"** bei Erfolg.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init).  
  
##  <a name="lock"></a>  CComSafeDeleteCriticalSection::Lock  
Ruft die basisklassenimplementierung der [Sperre](ccomcriticalsection-class.md#lock).  

  
```
HRESULT Lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode geht davon aus den [M_bInitialized](#m_binitialized) -Datenmember festgelegt ist, um **"true"** beim eintritt. Eine Assertion wird in Debugbuilds generiert, wenn diese Condidtion nicht erfüllt wird.  
  
 Weitere Informationen zum Verhalten der Funktion finden Sie unter [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
##  <a name="m_binitialized"></a>  CComSafeDeleteCriticalSection::m_bInitialized  
 Flags, ob die interne **CRITICAL_SECTION** Objekt initialisiert wurde.  
  
```
bool m_bInitialized;
```  
  
### <a name="remarks"></a>Hinweise  
 Die **M_bInitialized** Datenmember wird verwendet, um die Gültigkeit des zugrunde liegenden nachverfolgen **CRITICAL_SECTION** zugeordnete Objekt der [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) Klasse. Die zugrunde liegende **CRITICAL_SECTION** Objekt wird nicht ausgeführt werden, um aus dem Arbeitsspeicher freigegeben werden, wenn dieses Flag nicht, um festgelegt ist **"true"**.  
  
##  <a name="term"></a>  CComSafeDeleteCriticalSection::Term  
 Ruft die basisklassenimplementierung der [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) Wenn das interne **CRITICAL_SECTION** -Objekt gültig ist.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), oder **S_OK** Wenn [M_bInitialized](#m_binitialized) wurde **"false"** beim eintritt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode auch wenn das interne aufrufen ruhig **CRITICAL_SECTION** -Objekt ist ungültig. Der Destruktor für diese Klasse ruft diese Methode auf, wenn die [M_bInitialized](#m_binitialized) -Datenmember festgelegt ist, um **"true"**.  
  
## <a name="see-also"></a>Siehe auch  
 ["CComCriticalSection"-Klasse](../../atl/reference/ccomcriticalsection-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
