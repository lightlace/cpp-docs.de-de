---
title: "Gewusst wie: Schreiben einer Bin&#228;rdatei (C++/CLI)"
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
  - "Binärdateien, Schreiben in C++"
  - "Dateien [C++], Binär"
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Schreiben einer Bin&#228;rdatei (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird das Schreiben von Binärdaten in eine Datei veranschaulicht.  Zwei Klassen des <xref:System.IO>\-Namespace werden verwendet: <xref:System.IO.FileStream> und <xref:System.IO.BinaryWriter>.  <xref:System.IO.FileStream> repräsentiert die eigentliche Datei, während <xref:System.IO.BinaryWriter> eine Schnittstelle zum Stream für den Binärzugriff bereitstellt.  
  
 Im folgenden Codebeispiel wird eine Datei erzeugt, die ganze Zahlen im Binärformat enthält.  Diese Datei kann mit dem Code in [Gewusst wie: Lesen einer Binärdatei](../dotnet/how-to-read-a-binary-file-cpp-cli.md) gelesen werden.  
  
## Beispiel  
  
```  
// binary_write.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   array<Int32>^ data = {1, 2, 3, 10000};  
  
   FileStream^ fs = gcnew FileStream("data.bin", FileMode::Create);  
   BinaryWriter^ w = gcnew BinaryWriter(fs);  
  
   try   
   {  
      Console::WriteLine("writing data to file:");  
      for (int i=0; i<data->Length; i++)  
      {  
         Console::WriteLine(data[i]);  
         w->Write(data[i]);  
      }  
   }  
   catch (Exception^)   
   {  
     Console::WriteLine("data could not be written");  
     fs->Close();  
     return -1;  
   }  
  
   fs->Close();  
   return 0;  
}  
```  
  
## Siehe auch  
 [Datei\- und Stream\-E\/A](../Topic/File%20and%20Stream%20I-O.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)