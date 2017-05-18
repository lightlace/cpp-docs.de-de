---
title: Klasse CHeapPtrBase | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8084104489f6f1e2358ce0cbb573f4e20a0c4fce
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptrbase-class"></a>CHeapPtrBase-Klasse
Diese Klasse bildet die Grundlage für mehrere smart Heap zeigerklassen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class Allocator = CCRTAllocator>  
class CHeapPtrBase
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Objekttyp, auf dem Heap gespeichert werden.  
  
 `Allocator`  
 Die Speicher-Allocation-Klasse verwenden. Standardmäßig werden CRT-Routinen zum Belegen und Freigeben von Arbeitsspeicher.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Rufen Sie diese Methode, um Speicher zu belegen.|  
|[CHeapPtrBase::Attach](#attach)|Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz.|  
|[CHeapPtrBase::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.|  
|[CHeapPtrBase::Free](#free)|Rufen Sie diese Methode zum Löschen eines Objekts, auf das ein `CHeapPtrBase`.|  
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|Rufen Sie diese Methode, um Arbeitsspeicher neu zuzuordnen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrBase::operator T *](#operator_t_star)|Der Cast-Operator.|  
|[CHeapPtrBase::operator &](#operator_amp)|Die & -Operator.|  
|[CHeapPtrBase::operator->](#operator_ptr)|Der Zeiger-auf-Member-Operator.|  

  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrBase::m_pData](#m_pdata)|Die Zeiger-Membervariable.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bildet die Grundlage für mehrere smart Heap zeigerklassen. Die abgeleiteten Klassen, z. B. [CHeapPtr](../../atl/reference/cheapptr-class.md) und [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), ihre eigenen Konstruktoren und Operatoren hinzufügen. Finden Sie unter diesen Klassen Beispiele für die Implementierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="allocatebytes"></a>CHeapPtrBase::AllocateBytes  
 Rufen Sie diese Methode, um Speicher zu belegen.  
  
```
bool AllocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die Anzahl der Bytes, belegt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn der Speicher erfolgreich belegt, False andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CHeapPtrBase::m_pData](#m_pdata) Membervariable zeigt derzeit zu einem vorhandenen Wert; es ist also nicht gleich NULL.  
  
##  <a name="attach"></a>CHeapPtrBase::Attach  
 Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz.  
  
```
void Attach(T* pData) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pData`  
 Das `CHeapPtrBase` Objekt wird die Besitzrechte des this-Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CHeapPtrBase` Objekt übernimmt den Besitz eines Zeigers, wird es automatisch löschen den Zeiger und alle zugeordneten Daten, wenn sie den Gültigkeitsbereich verlässt.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CHeapPtrBase::m_pData](#m_pdata) Membervariable zeigt derzeit zu einem vorhandenen Wert; es ist also nicht gleich NULL.  
  
##  <a name="dtor"></a>CHeapPtrBase:: ~ CHeapPtrBase  
 Der Destruktor.  
  
```
~CHeapPtrBase() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="detach"></a>CHeapPtrBase::Detach  
 Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Kopie des Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz eines Zeigers frei wird, wird die [CHeapPtrBase::m_pData](#m_pdata) Membervariable den Wert NULL hat, und gibt eine Kopie des Zeigers zurück.  
  
##  <a name="free"></a>CHeapPtrBase::Free  
 Rufen Sie diese Methode zum Löschen eines Objekts, auf das ein `CHeapPtrBase`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt verweist die `CHeapPtrBase` wird freigegeben, und die [CHeapPtrBase::m_pData](#m_pdata) Member-Variable auf NULL festgelegt ist.  
  
##  <a name="m_pdata"></a>CHeapPtrBase::m_pData  
 Die Zeiger-Membervariable.  
  
```
T* m_pData;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Membervariable enthält Zeigerinformationen.  
  
##  <a name="operator_amp"></a>CHeapPtrBase::operator&amp;  
 Die & -Operator.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Adresse des Objekts, auf das das `CHeapPtrBase` Objekt.  
  

##  <a name="operator_ptr"></a>CHeapPtrBase::operator-&gt;  

 Der Zeiger-auf-Member-Operator.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der [CHeapPtrBase::m_pData](#m_pdata) Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Operator zum Aufrufen einer Methode in einer Klasse verweist, auf die `CHeapPtrBase` Objekt. Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CHeapPtrBase` verweist auf NULL.  
  
##  <a name="operator_t_star"></a>CHeapPtrBase::operator T *  
 Der Cast-Operator.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt [CHeapPtrBase::m_pData](#m_pdata).  
  
##  <a name="reallocatebytes"></a>CHeapPtrBase::ReallocateBytes  
 Rufen Sie diese Methode, um Arbeitsspeicher neu zuzuordnen.  
  
```
bool ReallocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die neue Speichergröße in Bytes zu reservieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn der Speicher erfolgreich belegt, False andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr-Klasse](../../atl/reference/ccomheapptr-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

