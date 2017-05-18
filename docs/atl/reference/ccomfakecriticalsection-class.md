---
title: Klasse CComFakeCriticalSection | Microsoft-Dokumentation
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
ms.openlocfilehash: 2c1269288e03a8ac9f359dad9acf1a81ddbc84c2
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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
|[CComFakeCriticalSection::Init](#init)|Hat keine Auswirkung, da keine kritischen Abschnitt vorhanden ist.|  
|[CComFakeCriticalSection::Lock](#lock)|Hat keine Auswirkung, da keine kritischen Abschnitt vorhanden ist.|  
|[CComFakeCriticalSection::Term](#term)|Hat keine Auswirkung, da keine kritischen Abschnitt vorhanden ist.|  
|[CComFakeCriticalSection::Unlock](#unlock)|Hat keine Auswirkung, da keine kritischen Abschnitt vorhanden ist.|  
  
## <a name="remarks"></a>Hinweise  
 `CComFakeCriticalSection`spiegelt die Methoden in ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md). Allerdings `CComFakeCriticalSection` bietet kein kritischen Abschnitts; daher seine Methoden werden keine Aktionen ausgeführt.  
  
 Normalerweise verwenden Sie `CComFakeCriticalSection` über eine `typedef` name entweder `AutoCriticalSection` oder `CriticalSection`. Bei Verwendung [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), beide `typedef` Namen Verweis `CComFakeCriticalSection`. Bei Verwendung [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), sie verweisen auf [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) und `CComCriticalSection`bzw..  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="init"></a>CComFakeCriticalSection::Init  
 Hat keine Auswirkung, da keine kritischen Abschnitt vorhanden ist.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
##  <a name="lock"></a>CComFakeCriticalSection::Lock  
 Hat keine Auswirkung, da keine kritischen Abschnitt vorhanden ist.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
##  <a name="term"></a>CComFakeCriticalSection::Term  
 Hat keine Auswirkung, da keine kritischen Abschnitt vorhanden ist.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
##  <a name="unlock"></a>CComFakeCriticalSection::Unlock  
 Hat keine Auswirkung, da keine kritischen Abschnitt vorhanden ist.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

