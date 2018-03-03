---
title: result_of-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 256f24ad40234db2bbc191a50b0d7e05de39c073
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resultof-class"></a>result_of-Klasse
Bestimmt den Rückgabetyp des aufrufbaren Typs, der die angegebenen Argumenttypen akzeptiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class>  
struct result_of; // Causes a static assert  
  
template <class Fn, class... ArgTypes>  
struct result_of<Fn(ArgTypes...)>;

// Helper type  
template<class T>
   using result_of_t = typename result_of<T>::type;
```  
  
#### <a name="parameters"></a>Parameter  
 `Fn`  
 Der abzufragende, aufgerufene Typ.  
  
 `ArgTypes`  
 Die Typen der Argumentliste für den aufrufbaren, abzufragenden Typ.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Vorlage zum Zeitpunkt der Kompilierung zur Bestimmung des Ergebnistyps des `Fn`(`ArgTypes`), wobei `Fn` ein aufrufbarer Typ ist, ein Verweis auf eine Funktion oder der Verweis auf einen aufrufbaren Typ, der mit einer Argumentliste der Typen in `ArgTypes` bereitgestellt werden kann. Der `type`-Member der Vorlagenklasse benennt den Ergebnistyp von `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, wenn der ausgewertete Ausdruck `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` wohlgeformt ist. Andernfalls hat die Vorlagenklasse keinen `type`-Member. Der `Fn`-Typ und alle Typen im Parameterpaket `ArgTypes` müssen vollständige Typen, `void` oder Arrays mit unbekannter Grenze sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)



