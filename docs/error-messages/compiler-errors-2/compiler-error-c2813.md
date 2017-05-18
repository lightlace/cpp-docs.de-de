---
title: Compilerfehler C2813 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 9
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: fc5f5437751abf6bcb11299e8484a199275db970
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2813"></a>Compilerfehler C2813
\#Import wird mit/MP nicht unterstützt.  
  
 C2813 wird ausgegeben, wenn in einem Compilerbefehl Sie geben die **/MP** -Compileroption und zwei oder mehr Dateien zu kompilieren, und mindestens eine der Dateien enthält die[#import](../../preprocessor/hash-import-directive-cpp.md) Präprozessordirektive angegeben. Die [#import](../../preprocessor/hash-import-directive-cpp.md) -Direktive generiert C++-Klassen aus den Typen in der angegebenen Typbibliothek und schreibt diese Klassen dann in zwei Headerdateien. Die [#import](../../preprocessor/hash-import-directive-cpp.md) Richtlinie wird nicht unterstützt, da Wenn mehrere Kompilierungseinheiten dieselbe Typbibliothek importieren, diesen Einheiten ein Konflikt auftreten, wenn sie versuchen, die gleichen Headerdateien zur gleichen Zeit zu schreiben.  
  
 Dieser Compilerfehler und die **/MP** -Compileroption sind neu in [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)].  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2813 generiert. Die Befehlszeile im "compile with:"-Kommentar weist den Compiler an, die Compileroptionen **/MP** und **/c** zum Kompilieren mehrerer Dateien zu verwenden. Mindestens eine der Dateien enthält die [#import](../../preprocessor/hash-import-directive-cpp.md) Richtlinie. Zum Testen dieses Beispiels wird die gleiche Datei zweimal verwendet.  
  
```  
// C2813.cpp  
// compile with: /MP /c C2813.cpp C2813.cpp  
#import "C:\windows\system32\stdole2.tlb"   // C2813  
int main()   
{  
}  
```
