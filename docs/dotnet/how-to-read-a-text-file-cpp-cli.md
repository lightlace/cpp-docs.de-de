---
title: 'Vorgehensweise: Lesen einer Textdatei (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- reading text files
- text files, reading
ms.assetid: 80551c01-d769-4b6d-8db7-fd53bde21b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c350ea9cd8b71378d059a93ac80ca808d4f48790
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130197"
---
# <a name="how-to-read-a-text-file-ccli"></a>Gewusst wie: Lesen einer Textdatei (C++/CLI)
Im folgenden Codebeispiel wird veranschaulicht, wie eine Textdatei geöffnet und dann zeilenweise mithilfe der <xref:System.IO.StreamReader>-Klasse gelesen wird, die im <xref:System.IO?displayProperty=fullName>-Namespace definiert ist. Mit einer Instanz dieser Klasse wird eine Textdatei geöffnet und anschließend jede Zeile mithilfe der <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>-Methode abgerufen.  
  
 In diesem Codebeispiel wird eine Datei mit dem Namen textfile.txt gelesen, die Text enthält. Informationen über diese Art von Datei finden Sie unter [wie: Schreiben einer Textdatei (C + c++ / CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Datei- und Datenstrom-E/A](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)