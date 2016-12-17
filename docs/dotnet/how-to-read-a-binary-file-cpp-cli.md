---
title: "Gewusst wie: Lesen einer Bin&#228;rdatei (C++/CLI)"
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
  - "Binärdateien, Lesen in C++"
  - "Dateien [C++], Binär"
ms.assetid: 41ad9ad1-5cac-489c-874e-4bb3a649073a
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Lesen einer Bin&#228;rdatei (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird das Lesen von Binärdaten aus einer Datei, mithilfe von zwei Klassen aus dem <xref:System.IO?displayProperty=fullName>\-Namespace: <xref:System.IO.FileStream> und <xref:System.IO.BinaryReader> verdeutlicht.  <xref:System.IO.FileStream> repräsentiert die eigentliche Datei.  <xref:System.IO.BinaryReader> stellt eine Schnittstelle zum Stream für den Binärzugriff bereit.  
  
 Im Codebeispiel wird eine Datei namens "data.bin" gelesen, in der ganze Zahlen im Binärformat enthalten sind.  Weitere Informationen über diese Art von Datei finden Sie unter [Gewusst wie: Schreiben einer Binärdatei](../dotnet/how-to-write-a-binary-file-cpp-cli.md).  
  
## Beispiel  
  
```  
// binary_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "data.bin";  
   try  
   {  
      FileStream^ fs = gcnew FileStream(fileName, FileMode::Open);  
      BinaryReader^ br = gcnew BinaryReader(fs);  
  
      Console::WriteLine("contents of {0}:", fileName);  
      while (br->BaseStream->Position < br->BaseStream->Length)  
         Console::WriteLine(br->ReadInt32().ToString());  
  
      fs->Close( );  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("File '{0}' not found", fileName);  
      else  
         Console::WriteLine("Exception: ({0})", e);  
      return -1;  
   }  
   return 0;  
}  
```  
  
## Siehe auch  
 [Datei\- und Stream\-E\/A](../Topic/File%20and%20Stream%20I-O.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)