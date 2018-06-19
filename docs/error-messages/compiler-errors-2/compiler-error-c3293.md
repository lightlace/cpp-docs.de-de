---
title: Compilerfehler C3293 | Microsoft Docs
ms.custom: ''
ms.date: 07/21/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3293
dev_langs:
- C++
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b195a91825b0f20445b29e330f67810329584db7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257727"
---
# <a name="compiler-error-c3293"></a>Compilerfehler C3293
'Accessor': Verwenden Sie 'default', um auf die Standardeigenschaft (Indexer) der 'Typ'-Klasse zuzugreifen.  
  
 Auf eine indizierte Eigenschaft wurde nicht ordnungsgemäß zugegriffen.  Finden Sie unter [wie: Verwenden von Eigenschaften in C + c++ / CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md) für Weitere Informationen.  

 **Visual Studio 2017 und höher**: In Visual Studio 2015 und frühere Versionen der Compiler in einigen Fällen eine Standardeigenschaft als einen Standardindexer falsch kategorisiert. Es war möglich das Problem zu umzugehen, indem mithilfe des „default“-Bezeichners auf die Eigenschaft zugegriffen wurde. Die Lösung selbst wurde problematisch, nachdem default als Schlüsselwort in C++11 eingeführt wurde. Aus diesem Grund wurden in Visual Studio 2017 Fehler behoben, die die Problemumgehung erforderten, und der Compiler löst jetzt einen Fehler aus, wenn „default“ verwendet wird, um auf die Standardeigenschaft für eine Klasse zuzugreifen.
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3293 in Visual Studio 2015 und früher.  
  
```  
// C3293.cpp  
// compile with: /clr /c  
using namespace System;  
ref class IndexerClass {  
public:  
   // default indexer  
   property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
  
int main() {  
   IndexerClass ^ ic = gcnew IndexerClass;  
   ic->Item[0] = 21;   // C3293 in VS2015 OK in VS2017
   ic->default[0] = 21;   // OK in VS2015 and earlier
  
   String ^s = "Hello";  
   wchar_t wc = s->Chars[0];   // C3293 in VS2015 OK in VS2017
   wchar_t wc2 = s->default[0];   // OK in VS2015 and earlier  
   Console::WriteLine(wc2);  
}  
```