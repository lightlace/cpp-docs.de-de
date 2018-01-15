---
title: atomic_flag-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs: C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d45d1cd6b0b0e4d12ee9a5567ee172cb7e772c3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="atomicflag-structure"></a>atomic_flag-Struktur
Beschreibt ein Objekt, das ein Flag `bool`-Flag atomisch festlegt und löscht. Vorgänge auf atomischen Flags sind immer sperrenfrei.  
  
## <a name="syntax"></a>Syntax  
  
```
struct atomic_flag;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[clear](#clear)|Legt das gespeicherte Flag auf `false` fest.|  
|[test_and_set](#test_and_set)|Legt das gespeicherte Flag auf `true` fest und gibt den ursprünglichen Flagwert zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `atomic_flag`-Objekte können den Nicht-Member-Funktionen [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set) und [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit) übergeben werden. Sie können mithilfe des `ATOMIC_FLAG_INIT`-Werts initialisiert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<atomic >  
  
 **Namespace:** std  
  
##  <a name="clear"></a>atomic_flag:: Clear
 Legt das in `*this` gespeicherte `bool`-Flag innerhalb der angegebenen [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkungen auf `false` fest.  
  
```
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="test_and_set"></a>atomic_flag:: test_and_set
 Legt das in `*this` gespeicherte `bool`-Flag innerhalb der angegebenen [memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Einschränkungen auf `true` fest.  
  
```
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Order`  
 Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Anfangswert des im `*this` gespeicherten Flags.  
  
## <a name="see-also"></a>Siehe auch  
 [\<atomic>](../standard-library/atomic.md)



