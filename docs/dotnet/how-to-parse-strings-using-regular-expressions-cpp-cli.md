---
title: 'Vorgehensweise: Analysieren von Zeichenfolgen mithilfe von regulären Ausdrücken (C + c++ / CLI) | Microsoft Docs'
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
- strings [C++], parsing
ms.assetid: 5b0c7ca3-9bba-4389-a45c-6d373cff91b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5940a59d7e9b4e68f289848523710594621e73d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-parse-strings-using-regular-expressions-ccli"></a>Gewusst wie: Analysieren von Zeichenfolgen mithilfe von regulären Ausdrücken (C++/CLI)
Im folgenden Codebeispiel wird die einfache Zeichenfolgenanalyse mithilfe der <xref:System.Text.RegularExpressions.Regex>-Klasse im <xref:System.Text.RegularExpressions?displayProperty=fullName>-Namespace veranschaulicht. Eine Zeichenfolge mit mehreren Arten von Wortdelineatoren wird erstellt. Die Zeichenfolge wird dann mit der <xref:System.Text.RegularExpressions.Regex>-Klasse in Verbindung mit der <xref:System.Text.RegularExpressions.Match>-Klasse analysiert. Anschließend werden alle Wörter des Satzes getrennt angezeigt.  
  
## <a name="example"></a>Beispiel  
  
```  
// regex_parse.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main( )  
{  
   int words = 0;  
   String^ pattern = "[a-zA-Z]*";  
   Console::WriteLine( "pattern : '{0}'", pattern );  
   Regex^ regex = gcnew Regex( pattern );  
  
   String^ line = "one\ttwo three:four,five six  seven";     
   Console::WriteLine( "text : '{0}'", line );  
   for( Match^ match = regex->Match( line );   
        match->Success; match = match->NextMatch( ) )   
   {  
      if( match->Value->Length > 0 )  
      {  
         words++;  
         Console::WriteLine( "{0}", match->Value );  
      }  
   }  
   Console::WriteLine( "Number of Words : {0}", words );  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](/dotnet/standard/base-types/regular-expressions)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)