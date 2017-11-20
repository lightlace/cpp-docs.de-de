---
title: 'Vorgehensweise: Analysieren von Zeichenfolgen mithilfe der Split-Methode (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- Split method, parsing strings
- strings [C++], parsing
ms.assetid: d52d2539-5ebb-4716-86b3-07314dd7e4bd
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: be3443995966c5ce7b9c2fe4a156c8d6c79069d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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