---
title: "Gewusst wie: Verwenden von regul&#228;ren Ausdr&#252;cken zum Extrahieren von Datenfeldern (C++/CLI)"
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
  - "Daten [C++], Extrahieren aus Zeichenfolgen"
  - "Formatierte Zeichenfolgen [C++]"
  - "Reguläre Ausdrücke [C++], Extrahieren von Datenfeldern"
  - "Zeichenfolgen [C++], Extrahieren von Daten aus"
ms.assetid: b581d9b6-630e-48fa-94fe-20b0f7b89b06
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von regul&#228;ren Ausdr&#252;cken zum Extrahieren von Datenfeldern (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird die Verwendung von regulären Ausdrücken zum Extrahieren von Daten aus einer formatierten Zeichenfolge dargestellt.  Das folgende Codebeispiel verwendet die <xref:System.Text.RegularExpressions.Regex>\-Klasse, um ein Schema festzulegen, das einer E\-Mail\-Adresse entspricht.  Zu diesem Schema gehören Feldbezeichner, mit denen der Benutzerbereich und der Hostbereich jeder E\-Mail\-Adresse abgerufen werden können.  Die <xref:System.Text.RegularExpressions.Match>\-Klasse wird verwendet, um den eigentlichen Mustervergleich auszuführen.  Wenn die E\-Mail\-Adresse gültig ist, werden der Benutzername und der Host extrahiert und angezeigt.  
  
## Beispiel  
  
```  
// Regex_extract.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
    array<String^>^ address=  
    {  
        "jay@southridgevideo.com",  
        "barry@adatum.com",  
        "treyresearch.net",  
        "karen@proseware.com"  
    };  
  
    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");  
  
    for (int i=0; i<address->Length; i++)  
    {  
        Match^ m = emailregex->Match( address[i] );  
        Console::Write("\n{0,25}", address[i]);  
  
        if ( m->Success )   
        {  
            Console::Write("   User='{0}'",   
            m->Groups["user"]->Value);  
            Console::Write("   Host='{0}'",   
            m->Groups["host"]->Value);  
        }  
        else   
            Console::Write("   (invalid email address)");  
        }  
  
    Console::WriteLine("");  
    return 0;  
}  
```  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)