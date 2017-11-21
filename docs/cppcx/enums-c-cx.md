---
title: Enumerationen (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: d21a887c29b792b2857d0ee546dbc9722b60a264
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="enums-ccx"></a>Enumerationen (C++/CX)
C + c++ / CX unterstützt die `public enum class` Schlüsselwort, das entspricht einem standardmäßigen C++ `scoped  enum`. Wenn Sie einen Enumerator verwenden, der durch das Schlüsselwort `public enum class` deklariert ist, müssen Sie den Enumerationsbezeichner dazu benutzen, den Umfang jedes Enumeratorwerts festzulegen.  
  
### <a name="remarks"></a>Hinweise  
 Eine `public enum class` , die keinen Zugriffsspezifizierer hat, z. B. `public`, wird als standardmäßige [Enumeration mit C++-Bereichseinschränkung](../cpp/enumerations-cpp.md)behandelt.  
  
 Ein `public enum class` oder `public enum struct` Deklaration kann einen zugrunde liegenden Typ jedes beliebigen ganzzahligen Typs haben, obwohl die Windows-Runtime selbst erfordert, dass der Typ int32- oder uint32 für eine Flags-Enumeration sein. Die folgende Syntax beschreibt die Teile einer `public enum class` oder `public enum struct`.  
  
 Dieses Beispiel zeigt, wie eine öffentliche Enumerationsklasse definiert wird:  
  
 [!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]  
  
 In diesem folgenden Beispiel wird zeigt, wie sie verwendet wird:  
  
 [!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]  
  
### <a name="examples"></a>Beispiele  
 In den folgenden Beispielen wird veranschaulicht, wie eine Enumeration deklariert wird.  
  
 [!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]  
  
 Im nächsten Beispiel wird gezeigt, wie Sie eine Enumeration in numerische Werte umwandeln und Vergleiche durchführen. Beachten Sie, dass die Verwendung des Enumerators `One` vom Enumerationsbezeichner `Enum1` beschränkt wird, und der Enumerator `First` wird durch `Enum2`beschränkt.  
  
 [!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Visual C++-Sprachreferenz](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)