---
title: 'Sichere Bibliotheken: C++-Standardbibliothek | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
dev_langs:
- C++
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: f1698faaf860ab5b1e2e8579d2077c09c2a46114
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="safe-libraries-c-standard-library"></a>Sichere Bibliotheken: C++-Standardbibliothek
An den mit Visual C++ ausgelieferten Bibliotheken wurden verschiedene Verbesserungen vorgenommen, einschließlich der C++-Standardbibliothek, um die Sicherheit zu erhöhen.  
  
 Einige Methoden in der C++-Standardbibliothek wurden als möglicherweise unsicher identifiziert, da sie zu einem Pufferüberlauf oder anderen Codefehlern führen könnten. Von der Verwendung dieser Methoden wird abgeraten, und es wurden neue, sicherere Methoden erstellt, um diese zu ersetzen. Diese neuen Methoden enden alle mit `_s`.  
  
 Zudem wurden verschiedene Verbesserungen vorgenommen, um Iteratoren und Algorithmen sicherer zu gestalten. Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md), [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md) und [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle sind die Methoden der C++-Standardbibliothek enthalten, die als potenziell unsicher gelten, sowie deren sicherere Entsprechung:  
  
|Potenziell unsichere Methode|Sicherere Entsprechung|  
|-------------------------------|----------------------|  
|[copy](../standard-library/basic-string-class.md#copy)|[basic_string::_Copy_s](../standard-library/basic-string-class.md#copy_s)|  
|[copy](../standard-library/char-traits-struct.md#copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#copy_s)|  
  
 Wenn Sie eine der oben genannten potenziell unsicheren Methoden aufrufen oder die Iteratoren unsachgemäß verwenden, generiert der Compiler eine [Compilerwarnung (Level 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Informationen zum Deaktivieren dieser Warnungen finden Sie unter [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [Checked Iterators](../standard-library/checked-iterators.md)  
  
 [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)


