---
title: "Gewusst wie: Verwenden von regul&#228;ren Ausdr&#252;cken zur &#220;berpr&#252;fung der Datenformatierung (C++/CLI)"
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
  - "Daten [C++], Formatierung"
  - "Reguläre Ausdrücke [C++], Validieren der Datenformatierung"
  - "Zeichenfolgen [C++], Formatierung"
ms.assetid: 225775c3-3efc-4734-bde2-1fdf73e3d397
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von regul&#228;ren Ausdr&#252;cken zur &#220;berpr&#252;fung der Datenformatierung (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird die Verwendung regulärer Ausdrücke veranschaulicht, um die Formatierung einer Zeichenfolge zu überprüfen.  In diesem Beispiel sollte die Zeichenfolge eine gültige Telefonnummer enthalten.  Die Zeichenfolge "\\d{3}\-\\d{3}\-\\d{4}" wird verwendet, um anzuzeigen, dass jedes Feld für eine gültige Telefonnummer steht.  Das "d" in der Zeichenfolge weist auf eine Ziffer hin. Das Argument hinter jedem "d" zeigt die Anzahl der Ziffern an, die vorhanden sein muss.  In diesem Fall muss die Zahl durch Bindestriche getrennt werden.  
  
## Beispiel  
  
```  
// regex_validate.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ number =   
   {  
      "123-456-7890",   
      "444-234-22450",   
      "690-203-6578",   
      "146-893-232",  
      "146-839-2322",  
      "4007-295-1111",   
      "407-295-1111",   
      "407-2-5555",   
   };  
  
   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";  
  
   for ( int i = 0; i < number->Length; i++ )  
   {  
      Console::Write( "{0,14}", number[i] );  
  
      if ( Regex::IsMatch( number[i], regStr ) )  
         Console::WriteLine(" - valid");  
      else  
         Console::WriteLine(" - invalid");  
   }  
   return 0;  
}  
```  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)