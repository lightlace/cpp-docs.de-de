---
title: "Gewusst wie: Schreiben einer Textdatei (C++/CLI)"
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
  - "Dateien [C++], Text"
  - "Textdateien, Schreiben in C++"
ms.assetid: 39ecdba6-84e0-485c-a202-84cf6d7b8d4a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Schreiben einer Textdatei (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird veranschaulicht, wie eine Textdatei erstellt und in diese mithilfe der im <xref:System.IO>\-Namespace definierten <xref:System.IO.StreamWriter>\-Klasse geschrieben wird.  Der Name der zu erstellenden Datei wird vom <xref:System.IO.StreamWriter>\-Konstruktor übernommen.  Wenn die Datei existiert, wird sie überschrieben \(außer wenn Sie True als zweites <xref:System.IO.StringWriter>\-Konstruktorargument übergeben\).  
  
 Die Datei wird dann mithilfe der Funktionen <xref:System.IO.StreamWriter.Write*> und <xref:System.IO.TextWriter.WriteLine*> abgelegt.  
  
## Beispiel  
  
```  
// text_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "textfile.txt";  
  
   StreamWriter^ sw = gcnew StreamWriter(fileName);  
   sw->WriteLine("A text file is born!");  
   sw->Write("You can use WriteLine");  
   sw->WriteLine("...or just Write");  
   sw->WriteLine("and do {0} output too.", "formatted");  
   sw->WriteLine("You can also send non-text objects:");  
   sw->WriteLine(DateTime::Now);  
   sw->Close();  
   Console::WriteLine("a new file ('{0}') has been written", fileName);  
  
   return 0;  
}  
```  
  
## Siehe auch  
 [Datei\- und Stream\-E\/A](../Topic/File%20and%20Stream%20I-O.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)