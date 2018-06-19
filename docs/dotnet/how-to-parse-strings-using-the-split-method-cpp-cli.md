---
title: 'Vorgehensweise: Analysieren von Zeichenfolgen mithilfe der Split-Methode (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- Split method, parsing strings
- strings [C++], parsing
ms.assetid: d52d2539-5ebb-4716-86b3-07314dd7e4bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48c5f26cae67dbfa9feb412917ed3a1d3dc7abbf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132020"
---
# <a name="how-to-parse-strings-using-the-split-method-ccli"></a>Gewusst wie: Analysieren von Zeichenfolgen mithilfe der split-Methode (C++/CLI)
Im folgenden Codebeispiel wird die Verwendung der <xref:System.String.Split%2A?displayProperty=fullName>-Methode veranschaulicht, um alle Wörter einer Zeichenfolge zu extrahieren. Eine Zeichenfolge mit mehreren Arten von Wortdelineatoren wird generiert und dann durch Aufrufen von <xref:System.String.Split%2A> mit einer Liste der Delineatoren analysiert. Anschließend werden alle Wörter des Satzes getrennt angezeigt.  
  
## <a name="example"></a>Beispiel  
  
```  
// regex_split.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String^ delimStr = " ,.:\t";  
   Console::WriteLine( "delimiter : '{0}'", delimStr );  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ words;  
   String^ line = "one\ttwo three:four,five six seven";  
  
   Console::WriteLine( "text : '{0}'", line );  
   words = line->Split( delimiter );  
   Console::WriteLine( "Number of Words : {0}", words->Length );  
   for (int word=0; word<words->Length; word++)  
      Console::WriteLine( "{0}", words[word] );  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](/dotnet/standard/base-types/regular-expressions)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)