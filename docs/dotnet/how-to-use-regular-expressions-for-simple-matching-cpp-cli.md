---
title: "Gewusst wie: Verwenden regul&#228;rer Ausdr&#252;cke f&#252;r einfache Gleichheitspr&#252;fung (C++/CLI)"
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
  - "IsMatch-Methode"
  - "Reguläre Ausdrücke [C++], Einfache Übereinstimmung"
  - "Suchen, Genaue Übereinstimmung von untergeordneten Zeichenfolgen"
  - "Zeichenfolgen [C++], Genaue Übereinstimmung von untergeordneten Zeichenfolgen"
  - "Teilzeichenfolgen, Einfache Übereinstimmung"
ms.assetid: 4661f6f3-0f6d-48f2-abe4-cb4770bf9bd5
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden regul&#228;rer Ausdr&#252;cke f&#252;r einfache Gleichheitspr&#252;fung (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel werden reguläre Ausdrücke verwendet, um nach genauen Übereinstimmungen in Teilzeichenfolgen zu suchen.  Die Suche wird von der statischen <xref:System.Text.RegularExpressions.Regex.IsMatch*>\-Methode ausgeführt, in die zwei Zeichenfolgen eingegeben werden.  Bei der ersten Zeichenfolge handelt es sich um die zu durchsuchende, bei der zweiten um das Muster, nach dem gesucht werden soll.  
  
## Beispiel  
  
```  
// regex_simple.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ sentence =   
   {  
      "cow over the moon",  
      "Betsy the Cow",  
      "cowering in the corner",  
      "no match here"  
   };  
  
   String^ matchStr = "cow";  
   for (int i=0; i<sentence->Length; i++)  
   {  
      Console::Write( "{0,24}", sentence[i] );  
      if ( Regex::IsMatch( sentence[i], matchStr,  
                     RegexOptions::IgnoreCase ) )  
         Console::WriteLine("  (match for '{0}' found)", matchStr);  
      else  
         Console::WriteLine("");  
   }  
   return 0;  
}  
```  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)