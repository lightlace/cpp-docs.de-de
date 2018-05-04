---
title: CHeapPtrBase Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ca18054509ab069722e632308b4d8f57706e548
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase-Klasse
Diese Klasse bildet die Grundlage für mehrere Heap intelligenten Zeiger-Klassen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class Allocator = CCRTAllocator>  
class CHeapPtrBase
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Objekttyp, auf dem Heap gespeichert werden.  
  
 `Allocator`  
 Die Arbeitsspeicher-Allocation-Klasse, verwendet. Standardmäßig werden CRT-Routinen zum Belegen und Freigeben von Arbeitsspeicher.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Rufen Sie diese Methode, um Arbeitsspeicher belegt werden.|  
|[CHeapPtrBase::Attach](#attach)|Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz zu nehmen.|  
|[CHeapPtrBase::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.|  
|[CHeapPtrBase::Free](#free)|Rufen Sie diese Methode zum Löschen eines Objekts verweist, zu einem `CHeapPtrBase`.|  
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|Rufen Sie diese Methode, um Arbeitsspeicher neu zuzuordnen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrBase::operator T *](#operator_t_star)|Der Cast-Operator.|  
|[CHeapPtrBase::operator &](#operator_amp)|Der &-Operator.|  
|[CHeapPtrBase::operator ->](#operator_ptr)|Der Pointer-to-Member-Operator.|  

  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrBase::m_pData](#m_pdata)|Die Zeiger-Membervariable.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bildet die Grundlage für mehrere Heap intelligenten Zeiger-Klassen. Die abgeleiteten Klassen, z. B. [CHeapPtr](../../atl/reference/cheapptr-class.md) und [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), ihre eigenen Konstruktoren und Operatoren hinzufügen. Finden Sie diese Klassen für die Beispiele für die Implementierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="allocatebytes"></a>  CHeapPtrBase::AllocateBytes  
 Rufen Sie diese Methode, um Arbeitsspeicher belegt werden.  
  
```
bool AllocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die Anzahl der Bytes an Arbeitsspeicher zugewiesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn der Speicher erfolgreich belegt, "false" andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CHeapPtrBase::m_pData](#m_pdata) Membervariable wird derzeit auf einen vorhandenen Wert zeigt; es ist also nicht gleich NULL.  
  
##  <a name="attach"></a>  CHeapPtrBase::Attach  
 Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz zu nehmen.  
  
```
void Attach(T* pData) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pData`  
 Die `CHeapPtrBase` Objekt wird die Besitzrechte des this-Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CHeapPtrBase` Objekt übernimmt den Besitz eines Zeigers, wird es automatisch löschen den Zeiger und alle zugeordneten Daten, wenn sie den Gültigkeitsbereich verlässt.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CHeapPtrBase::m_pData](#m_pdata) Membervariable wird derzeit auf einen vorhandenen Wert zeigt; es ist also nicht gleich NULL.  
  
##  <a name="dtor"></a>  CHeapPtrBase:: ~ CHeapPtrBase  
 Der Destruktor.  
  
```
~CHeapPtrBase() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="detach"></a>  CHeapPtrBase::Detach  
 Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Kopie des Zeigers zurück.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz eines Zeigers frei wird, wird dadurch die [CHeapPtrBase::m_pData](#m_pdata) Membervariable auf NULL, und gibt eine Kopie des Zeigers zurück.  
  
##  <a name="free"></a>  CHeapPtrBase::Free  
 Rufen Sie diese Methode zum Löschen eines Objekts verweist, zu einem `CHeapPtrBase`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt verweist die `CHeapPtrBase` wird freigegeben, und die [CHeapPtrBase::m_pData](#m_pdata) Membervariable wird auf NULL festgelegt.  
  
##  <a name="m_pdata"></a>  CHeapPtrBase::m_pData  
 Die Zeiger-Membervariable.  
  
```
T* m_pData;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Membervariable enthält die Zeigerinformationen zur.  
  
##  <a name="operator_amp"></a>  CHeapPtrBase::operator &amp;  
 Der &-Operator.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Adresse des Objekts verweist, zu der `CHeapPtrBase` Objekt.  
  

##  <a name="operator_ptr"></a>  CHeapPtrBase::operator-&gt;  

 Der Pointer-to-Member-Operator.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der [CHeapPtrBase::m_pData](#m_pdata) Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Operator zum Aufrufen einer Methode in einer Klasse, die durch die `CHeapPtrBase` Objekt. Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CHeapPtrBase` verweist auf NULL.  
  
##  <a name="operator_t_star"></a>  CHeapPtrBase::operator T *  
 Der Cast-Operator.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt [CHeapPtrBase::m_pData](#m_pdata).  
  
##  <a name="reallocatebytes"></a>  CHeapPtrBase::ReallocateBytes  
 Rufen Sie diese Methode, um Arbeitsspeicher neu zuzuordnen.  
  
```
bool ReallocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die neue Arbeitsspeichermenge in Bytes zugewiesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn der Speicher erfolgreich belegt, "false" andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr-Klasse](../../atl/reference/ccomheapptr-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
