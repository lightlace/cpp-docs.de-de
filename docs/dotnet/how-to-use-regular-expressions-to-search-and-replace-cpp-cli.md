---
title: "Gewusst wie: Verwenden von regul&#228;ren Ausdr&#252;cken zum Suchen und Ersetzen (C++/CLI)"
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
  - "Reguläre Ausdrücke [C++], Suchen und Ersetzen"
  - "Replace-Methode"
  - "Suchen und Ersetzen"
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von regul&#228;ren Ausdr&#252;cken zum Suchen und Ersetzen (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird dargestellt, wie mit der <xref:System.Text.RegularExpressions.Regex>\-Klasse als regulärer Ausdruck ein "Suchen und Ersetzen"\-Vorgang durchgeführt werden kann.  Hierzu wird die <xref:System.Text.RegularExpressions.Regex.Replace*>\-Methode verwendet.  In dieser Version werden für die Eingabe zwei Zeichenfolgen akzeptiert: Die zu ändernde Zeichenfolge und die Zeichenfolge, die anstelle der Abschnitte eingefügt wird, die dem an das <xref:System.Text.RegularExpressions.Regex>\-Objekt weitergegebene Muster entsprechen.  
  
 Durch diesen Code werden alle Ziffern in einer Zeichenfolge gelöscht, indem diese durch einen Unterstrich \(\_\) und anschließend durch eine leere Zeichenfolge ersetzt werden.  Zur Verdeutlichung der Vorgehensweise werden an dieser Stelle zwei Schritte verwendet. Dasselbe Ergebnis kann auch in einem einzelnen Schritt erzielt werden.  
  
## Beispiel  
  
```  
// regex_replace.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System::Text::RegularExpressions;  
using namespace System;  
  
int main()  
{  
   String^ before = "The q43uick bro254wn f0ox ju4mped";  
   Console::WriteLine("original  : {0}", before);  
  
   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");  
   String^ after = digitRegex->Replace(before, "_");  
   Console::WriteLine("1st regex : {0}", after);  
  
   Regex^ underbarRegex = gcnew Regex("_");  
   String^ after2 = underbarRegex->Replace(after, "");  
   Console::WriteLine("2nd regex : {0}", after2);  
  
   return 0;  
}  
```  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)