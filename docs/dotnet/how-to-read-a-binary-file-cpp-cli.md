---
title: 'Vorgehensweise: Lesen einer Binärdatei (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- files [C++], binary
- binary files, reading in C++
ms.assetid: 41ad9ad1-5cac-489c-874e-4bb3a649073a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8411971c8bca79d9cb1809481b5a6be61b052262
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-a-binary-file-ccli"></a>Gewusst wie: Lesen einer Binärdatei (C++/CLI)
Im folgenden Codebeispiel wird das Lesen von Binärdaten aus einer Datei, mithilfe von zwei Klassen aus dem <xref:System.IO?displayProperty=fullName>-Namespace: <xref:System.IO.FileStream> und <xref:System.IO.BinaryReader> verdeutlicht. <xref:System.IO.FileStream> repräsentiert die eigentliche Datei. <xref:System.IO.BinaryReader> stellt eine Schnittstelle zum Stream für den Binärzugriff bereit.  
  
 Im Codebeispiel wird eine Datei namens "data.bin" gelesen, in der ganze Zahlen im Binärformat enthalten sind. Informationen über diese Art von Datei finden Sie unter [wie: Schreiben einer Binärdatei (C + c++ / CLI)](../dotnet/how-to-write-a-binary-file-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Datei- und Datenstrom-E/A](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)