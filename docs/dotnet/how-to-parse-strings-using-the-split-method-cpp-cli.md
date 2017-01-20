---
title: "Gewusst wie: Analysieren von Zeichenfolgen mithilfe der split-Methode (C++/CLI)"
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
  - "Split-Methode, Analysieren von Zeichenfolgen"
  - "Zeichenfolgen [C++], Analysieren"
ms.assetid: d52d2539-5ebb-4716-86b3-07314dd7e4bd
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Analysieren von Zeichenfolgen mithilfe der split-Methode (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird die Verwendung der <xref:System.String.Split*?displayProperty=fullName>\-Methode veranschaulicht, um alle Wörter einer Zeichenfolge zu extrahieren.  Eine Zeichenfolge mit mehreren Arten von Wortdelineatoren wird generiert und dann durch Aufrufen von <xref:System.String.Split*> mit einer Liste der Delineatoren analysiert.  Anschließend werden alle Wörter des Satzes getrennt angezeigt.  
  
## Beispiel  
  
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
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)