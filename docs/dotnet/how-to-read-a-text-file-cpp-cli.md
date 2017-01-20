---
title: "Gewusst wie: Lesen einer Textdatei (C++/CLI)"
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
  - "Lesen von Textdateien"
  - "Textdateien, Lesen"
ms.assetid: 80551c01-d769-4b6d-8db7-fd53bde21b62
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Lesen einer Textdatei (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird veranschaulicht, wie eine Textdatei geöffnet und dann zeilenweise mithilfe der <xref:System.IO.StreamReader>\-Klasse gelesen wird, die im <xref:System.IO?displayProperty=fullName>\-Namespace definiert ist.  Mit einer Instanz dieser Klasse wird eine Textdatei geöffnet und anschließend jede Zeile mithilfe der <xref:System.IO.StreamReader.ReadLine*?displayProperty=fullName>\-Methode abgerufen.  
  
 In diesem Codebeispiel wird eine Datei mit dem Namen textfile.txt gelesen, die Text enthält.  Weitere Informationen über diese Art von Datei finden Sie unter [Gewusst wie: Schreiben einer Textdatei](../dotnet/how-to-write-a-text-file-cpp-cli.md).  
  
## Beispiel  
  
```  
// text_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ fileName = "textfile.txt";  
   try   
   {  
      Console::WriteLine("trying to open file {0}...", fileName);  
      StreamReader^ din = File::OpenText(fileName);  
  
      String^ str;  
      int count = 0;  
      while ((str = din->ReadLine()) != nullptr)   
      {  
         count++;  
         Console::WriteLine("line {0}: {1}", count, str );  
      }  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("file '{0}' not found", fileName);  
      else  
         Console::WriteLine("problem reading file '{0}'", fileName);  
   }  
  
   return 0;  
}  
```  
  
## Siehe auch  
 [Datei\- und Stream\-E\/A](../Topic/File%20and%20Stream%20I-O.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)