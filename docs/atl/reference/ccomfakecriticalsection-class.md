---
title: CComFakeCriticalSection Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 6232a3e8b6c392361a1e57681e9ba4dff66d6aa4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection-Klasse
Diese Klasse bietet dieselben Methoden wie ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md) jedoch kein kritischen Abschnitts.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComFakeCriticalSection
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](#init)|Wird keine Aktion ausgeführt, da keine kritischen Abschnitt vorhanden ist.|  
|[CComFakeCriticalSection::Lock](#lock)|Wird keine Aktion ausgeführt, da keine kritischen Abschnitt vorhanden ist.|  
|[CComFakeCriticalSection::Term](#term)|Wird keine Aktion ausgeführt, da keine kritischen Abschnitt vorhanden ist.|  
|[CComFakeCriticalSection::Unlock](#unlock)|Wird keine Aktion ausgeführt, da keine kritischen Abschnitt vorhanden ist.|  
  
## <a name="remarks"></a>Hinweise  
 `CComFakeCriticalSection`spiegelt die Methoden in ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md). Allerdings `CComFakeCriticalSection` bietet kein kritischen Abschnitts; daher ihre Methoden werden keine Aktionen ausgeführt.  
  
 Verwenden Sie in der Regel `CComFakeCriticalSection` über eine `typedef` nennen, entweder `AutoCriticalSection` oder `CriticalSection`. Bei Verwendung [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), beide `typedef` benennt Verweis `CComFakeCriticalSection`. Bei Verwendung [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), verweisen auf [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) und `CComCriticalSection`zugeordnet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="init"></a>CComFakeCriticalSection::Init  
 Wird keine Aktion ausgeführt, da keine kritischen Abschnitt vorhanden ist.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
##  <a name="lock"></a>CComFakeCriticalSection::Lock  
 Wird keine Aktion ausgeführt, da keine kritischen Abschnitt vorhanden ist.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
##  <a name="term"></a>CComFakeCriticalSection::Term  
 Wird keine Aktion ausgeführt, da keine kritischen Abschnitt vorhanden ist.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
##  <a name="unlock"></a>CComFakeCriticalSection::Unlock  
 Wird keine Aktion ausgeführt, da keine kritischen Abschnitt vorhanden ist.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)

