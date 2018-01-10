---
title: allocator_traits-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::allocator_traits
- memory/std::allocator_traits::propagate_on_container_move_assignment
- memory/std::allocator_traits::const_pointer
- memory/std::allocator_traits::propagate_on_container_swap
- memory/std::allocator_traits::propagate_on_container_copy_assignment
- memory/std::allocator_traits::difference_type
- memory/std::allocator_traits::allocator_type
- memory/std::allocator_traits::value_type
- memory/std::allocator_traits::pointer
- memory/std::allocator_traits::size_type
- memory/std::allocator_traits::const_void_pointer
- memory/std::allocator_traits::void_pointer
- memory/std::allocator_traits::allocate
- memory/std::allocator_traits::construct
- memory/std::allocator_traits::deallocate
- memory/std::allocator_traits::destroy
- memory/std::allocator_traits::max_size
- memory/std::allocator_traits::select_on_container_copy_construction
dev_langs: C++
ms.assetid: 612974b8-b5d4-4668-82fb-824bff6821d6
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::allocator_traits [C++]
- std::allocator_traits [C++], propagate_on_container_move_assignment
- std::allocator_traits [C++], const_pointer
- std::allocator_traits [C++], propagate_on_container_swap
- std::allocator_traits [C++], propagate_on_container_copy_assignment
- std::allocator_traits [C++], difference_type
- std::allocator_traits [C++], allocator_type
- std::allocator_traits [C++], value_type
- std::allocator_traits [C++], pointer
- std::allocator_traits [C++], size_type
- std::allocator_traits [C++], const_void_pointer
- std::allocator_traits [C++], void_pointer
- std::allocator_traits [C++], allocate
- std::allocator_traits [C++], construct
- std::allocator_traits [C++], deallocate
- std::allocator_traits [C++], destroy
- std::allocator_traits [C++], max_size
- std::allocator_traits [C++], select_on_container_copy_construction
ms.workload: cplusplus
ms.openlocfilehash: 7d96b4a03085a2a6486fa2f2fe0d7050323682c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="allocatortraits-class"></a>allocator_traits-Klasse
Die Vorlagenklasse beschreibt ein Objekt, das einen *Allocatortyp* ergänzt. Ein Allocatortyp ist jeder Typ, der ein Zuweisungsobjekt beschreibt, das zum Verwalten von zugewiesenem Speicherplatz verwendet wird. Sie können insbesondere für jeden Allocator des Typs `Alloc` `allocator_traits<Alloc>` verwenden, um alle Informationen zu erhalten, die für einen zuweisungsfähigen Container erforderlich sind. Weitere Informationen finden Sie unter der Standard-[Allocator-Klasse](../standard-library/allocator-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <class Alloc>
class allocator_traits;
```  
  
### <a name="typedefs"></a>Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`allocator_traits::allocator_type`|Dieser Typ stellt ein Synonym für den Vorlagenparameter `Alloc`dar.|  
|`allocator_traits::const_pointer`|Dieser Typ ist `Alloc::const_pointer`, wenn dieser Typ wohlgeformt ist; andernfalls ist dieser Typ `pointer_traits<pointer>::rebind<const value_type>`.|  
|`allocator_traits::const_void_pointer`|Dieser Typ ist `Alloc::const_void_pointer`, wenn dieser Typ wohlgeformt ist; andernfalls ist dieser Typ `pointer_traits<pointer>::rebind<const void>`.|  
|`allocator_traits::difference_type`|Dieser Typ ist `Alloc::difference_type`, wenn dieser Typ wohlgeformt ist; andernfalls ist dieser Typ `pointer_traits<pointer>::difference_type`.|  
|`allocator_traits::pointer`|Dieser Typ ist `Alloc::pointer`, wenn dieser Typ wohlgeformt ist; andernfalls ist dieser Typ `value_type *`.|  
|`allocator_traits::propagate_on_container_copy_assignment`|Dieser Typ ist `Alloc::propagate_on_container_copy_assignment`, wenn dieser Typ wohlgeformt ist; andernfalls ist dieser Typ `false_type`.|  
|`allocator_traits::propagate_on_container_move_assignment`|Dieser Typ ist `Alloc::propagate_on_container_move_assignment`, wenn dieser Typ wohlgeformt ist; andernfalls ist dieser Typ `false_type`. Wenn der Typ weiter gilt, kopiert ein zuweisungsfähiger Container seinen gespeicherten Allocator auf eine Bewegungszuweisung.|  
|`allocator_traits::propagate_on_container_swap`|Dieser Typ ist `Alloc::propagate_on_container_swap`, wenn dieser Typ wohlgeformt ist; andernfalls ist dieser Typ `false_type`. Wenn der Typ weiter gilt, tauscht ein zuweisungsfähiger Container seinen gespeicherten Allocator auf einem Swap aus.|  
|`allocator_traits::size_type`|Dieser Typ ist `Alloc::size_type`, wenn dieser Typ wohlgeformt ist; andernfalls ist dieser Typ `make_unsigned<difference_type>::type`.|  
|`allocator_traits::value_type`|Dieser Typ ist ein Synonym für `Alloc::value_type`.|  
|`allocator_traits::void_pointer`|Dieser Typ ist `Alloc::void_pointer`, wenn dieser Typ wohlgeformt ist; andernfalls ist dieser Typ `pointer_traits<pointer>::rebind<void>`.|  
  
### <a name="static-methods"></a>Statische Methoden  
 Folgende statische Methoden rufen die entsprechenden Methoden auf einem vorhandenen Allocator-Parameter auf.  
  
|name|Beschreibung|  
|----------|-----------------|  
|[allocate](#allocate)|Eine statische Methode, die mithilfe des vorhandenen Allocator-Parameters Arbeitsspeicher zuweist.|  
|[construct](#construct)|Eine statische Methode, die mithilfe eines angegebenen Allocators ein Objekt erstellt.|  
|[deallocate](#deallocate)|Eine statische Methode, die mithilfe eines angegebenen Allocators eine angegebene Anzahl von Objekten freigibt.|  
|[destroy](#destroy)|Eine statische Methode, die mithilfe eines angegebenen Allocators den Destruktor in einem Objekt aufruft, ohne dass dessen Arbeitsspeicher freigegeben wird.|  
|[max_size](#max_size)|Eine statische Methode, die mithilfe eines angegebenen Allocators die maximale Anzahl von zuweisbaren Objekten ermittelt.|  
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Eine statische Methode, die `select_on_container_copy_construction` in einem angegebenen Allocator aufruft.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<memory>  
  
 **Namespace:** std  
  
##  <a name="allocate"></a>allocator_traits:: Allocate
 Eine statische Methode, die mithilfe des vorhandenen Allocator-Parameters Arbeitsspeicher zuweist.  
  
```cpp  
static pointer allocate(Alloc& al, size_type count);

static pointer allocate(Alloc& al, size_type count,
    typename allocator_traits<void>::const_pointer* hint);
```  
  
### <a name="parameters"></a>Parameter  
 `al`  
 Ein Zuweisungsobjekt.  
  
 `count`  
 Die Anzahl der zuzuweisenden Elemente.  
  
 `hint`  
 Ein `const_pointer`, der dem Zuweisungsobjekt möglicherweise dabei hilft, die Anforderung von Speicherplatz zu erfüllen. Dazu sucht er die Adresse eines vor der Anforderung zugewiesenen Objekts. Ein NULL-Zeiger wird nicht als Hinweis behandelt.  
  
### <a name="return-value"></a>Rückgabewert  
 Jede Methode gibt einen Zeiger auf das zugewiesene Objekt zurück.  
  
 Die erste statische Methode gibt `al.allocate(count)` zurück.  
  
 Die zweite Methode gibt dann `al.allocate(count, hint)` zurück, wenn der Ausdruck wohlgeformt ist; andernfalls `al.allocate(count)`.  
  
##  <a name="construct"></a>allocator_traits:: Construct
 Eine statische Methode, die mithilfe eines angegebenen Allocators ein Objekt erstellt.  
  
```cpp  
template <class Uty, class Types>
static void construct(Alloc& al, Uty* ptr, Types&&... args);
```  
  
### <a name="parameters"></a>Parameter  
 `al`  
 Ein Zuweisungsobjekt.  
  
 `ptr`  
 Ein Zeiger auf den Speicherort, in dem das Objekt erstellt werden soll.  
  
 `args`  
 Eine Liste von Argumenten, die an den Objektkonstruktor übergeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Die statische Memberfunktion ruft `al.construct(ptr, args...)` auf, wenn der Ausdruck wohlgeformt ist; andernfalls wertet es `::new (static_cast<void *>(ptr)) Uty(std::forward<Types>(args)...)` aus.  
  
##  <a name="deallocate"></a>allocator_traits:: DEALLOCATE
 Eine statische Methode, die mithilfe eines angegebenen Allocators eine angegebene Anzahl von Objekten freigibt.  
  
```cpp  
static void deallocate(Alloc al,
    pointer ptr,
    size_type count);
```  
  
### <a name="parameters"></a>Parameter  
 `al`  
 Ein Zuweisungsobjekt.  
  
 `ptr`  
 Ein Zeiger auf den Anfangsort der freizugebenden Objekte.  
  
 `count`  
 Die Anzahl der freizugebenden Objekte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft `al.deallocate(ptr, count)` auf.  
  
 Diese Methode löst keine Aktion aus.  
  
##  <a name="destroy"></a>allocator_traits:: Destroy
 Eine statische Methode, die mithilfe eines angegebenen Allocators den Destruktor in einem Objekt aufruft, ohne dass dessen Arbeitsspeicher freigegeben wird.  
  
```cpp  
template <class Uty>
static void destroy(Alloc& al, Uty* ptr);
```  
  
### <a name="parameters"></a>Parameter  
 `al`  
 Ein Zuweisungsobjekt.  
  
 `ptr`  
 Ein Zeiger auf den Speicherort des Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft `al.destroy(ptr)` auf, wenn der Ausdruck wohlgeformt ist; andernfalls wertet es `ptr->~Uty()` aus.  
  
##  <a name="max_size"></a>allocator_traits:: max_size
 Eine statische Methode, die mithilfe eines angegebenen Allocators die maximale Anzahl von zuweisbaren Objekten ermittelt.  
  
```cpp  
static size_type max_size(const Alloc& al);
```  
  
### <a name="parameters"></a>Parameter  
 `al`  
 Ein Zuweisungsobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt dann `al.max_size()` zurück, wenn der Ausdruck wohlgeformt ist; andernfalls `numeric_limits<size_type>::max()`.  
  
##  <a name="select_on_container_copy_construction"></a>allocator_traits:: select_on_container_copy_construction
 Eine statische Methode, die `select_on_container_copy_construction` in einem angegebenen Allocator aufruft.  
  
```cpp  
static Alloc select_on_container_copy_construction(const Alloc& al);
```  
  
### <a name="parameters"></a>Parameter  
 `al`  
 Ein Zuweisungsobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt dann `al.select_on_container_copy_construction()` zurück, wenn der Typ wohlgeformt ist; andernfalls `al`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird verwendet, um einen Allocator anzugeben, wenn der zugeordnete Container durch eine Kopie erstellt wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [\<memory>](../standard-library/memory.md)   
 [pointer_traits-Struktur](../standard-library/pointer-traits-struct.md)   
 [scoped_allocator_adaptor-Klasse](../standard-library/scoped-allocator-adaptor-class.md)
