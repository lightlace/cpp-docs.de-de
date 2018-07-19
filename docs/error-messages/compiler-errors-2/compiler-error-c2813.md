---
title: Compilerfehler C2813 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 253f0d54b603c2b859f806053a906378025a39ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237249"
---
# <a name="compiler-error-c2813"></a>Compilerfehler C2813
\#Import wird mit/MP nicht unterstützt.  
  
 C2813 wird ausgegeben, wenn Sie in einem Compilerbefehl die **/MP** -Compileroption und zwei oder mehr zu kompilierende Dateien angeben, von denen mindestens eine Datei die[#import](../../preprocessor/hash-import-directive-cpp.md) -Präprozessordirektive enthält. Die [#import](../../preprocessor/hash-import-directive-cpp.md) -Direktive generiert C++-Klassen aus den Typen in der angegebenen Typbibliothek und schreibt diese Klassen dann in zwei Headerdateien. Die [#import](../../preprocessor/hash-import-directive-cpp.md) -Direktive wird nicht unterstützt. Wenn mehrere Kompilierungseinheiten dieselbe Typbibliothek importieren, tritt zwischen diesen Einheiten ein Konflikt auf, wenn sie versuchen, die gleichen Headerdateien zur gleichen Zeit zu schreiben.  
  
 Dieser Compilerfehler und die **/MP** -Compileroption sind neu in Visual Studio 2008.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2813 generiert. Die Befehlszeile im "compile with:"-Kommentar weist den Compiler an, die Compileroptionen **/MP** und **/c** zum Kompilieren mehrerer Dateien zu verwenden. Mindestens eine der Dateien enthält die [#import](../../preprocessor/hash-import-directive-cpp.md) -Direktive. Zum Testen dieses Beispiels wird die gleiche Datei zweimal verwendet.  
  
```  
// C2813.cpp  
// compile with: /MP /c C2813.cpp C2813.cpp  
#import "C:\windows\system32\stdole2.tlb"   // C2813  
int main()   
{  
}  
```