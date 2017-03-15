---
title: "Gewusst wie: Analysieren von Zeichenfolgen mithilfe von regul&#228;ren Ausdr&#252;cken (C++/CLI)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Beispiele [C++], Zeichenfolgen"
  - "Analysieren von Zeichenfolgen [C++]"
  - "Reguläre Ausdrücke [C++], Analysieren von Zeichenfolgen"
  - "Zeichenfolgen [C++], Analysieren"
ms.assetid: 5b0c7ca3-9bba-4389-a45c-6d373cff91b0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Analysieren von Zeichenfolgen mithilfe von regul&#228;ren Ausdr&#252;cken (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird die einfache Zeichenfolgenanalyse mithilfe der <xref:System.Text.RegularExpressions.Regex>\-Klasse im <xref:System.Text.RegularExpressions?displayProperty=fullName>\-Namespace veranschaulicht.  Eine Zeichenfolge mit mehreren Arten von Wortdelineatoren wird erstellt.  Die Zeichenfolge wird dann mit der <xref:System.Text.RegularExpressions.Regex>\-Klasse in Verbindung mit der <xref:System.Text.RegularExpressions.Match>\-Klasse analysiert.  Anschließend werden alle Wörter des Satzes getrennt angezeigt.  
  
## Beispiel  
  
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
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)