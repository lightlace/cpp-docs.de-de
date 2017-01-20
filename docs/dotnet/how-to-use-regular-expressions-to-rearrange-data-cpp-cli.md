---
title: "Gewusst wie: Verwenden von regul&#228;ren Ausdr&#252;cken zum &#196;ndern der Anordnung von Daten (C++/CLI)"
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
  - "Daten [C++], Neuanordnen"
  - "Reguläre Ausdrücke [C++], Neuanordnen von Daten"
ms.assetid: 5f91e777-9471-424e-ba75-dca3d1b49e42
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von regul&#228;ren Ausdr&#252;cken zum &#196;ndern der Anordnung von Daten (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird dargestellt, wie in .NET Framework mithilfe regulärer Ausdrücke Daten neu angeordnet und formatiert werden.  Im folgenden Codebeispiel werden mit der <xref:System.Text.RegularExpressions.Regex>\-Klasse und der <xref:System.Text.RegularExpressions.Match>\-Klasse der erste und der letzte Name in einer Zeichenfolge extrahiert und anschließend in umgekehrter Reihenfolge angezeigt.  
  
 Die <xref:System.Text.RegularExpressions.Regex>\-Klasse wird zum Konstruieren eines regulären Ausdrucks verwendet, durch den das aktuelle Format der Daten beschrieben wird.  Es wird angenommen, dass die zwei Namen durch ein Komma getrennt sind und eine beliebige Anzahl von Leerzeichen vor und\/oder nach dem Komma stehen.  Anschließend wird mit der <xref:System.Text.RegularExpressions.Match>\-Methode jede Zeichenfolge analysiert.  Wenn dieser Vorgang erfolgreich abgeschlossen wird, werden der erste und der letzte Name im <xref:System.Text.RegularExpressions.Match>\-Objekt abgerufen und angezeigt.  
  
## Beispiel  
  
```  
// regex_reorder.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ name =   
   {  
      "Abolrous, Sam",   
      "Berg,Matt",   
      "Berry , Jo",  
      "www.contoso.com"  
   };  
  
   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");  
  
   for ( int i=0; i < name->Length; i++ )  
   {  
      Console::Write( "{0,-20}", name[i] );  
      Match^ m = reg->Match( name[i] );  
      if ( m->Success )  
      {  
         String^ first = m->Groups["first"]->Value;  
         String^ last = m->Groups["last"]->Value;  
         Console::WriteLine("{0} {1}", first, last);  
      }  
      else  
         Console::WriteLine("(invalid)");  
   }  
   return 0;  
}  
```  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)