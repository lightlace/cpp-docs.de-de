---
title: 'Vorgehensweise: Schreiben einer Textdatei (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- files [C++], text
- text files, writing in C++
ms.assetid: 39ecdba6-84e0-485c-a202-84cf6d7b8d4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e0ce3839a5d0a0668d921a2d64cb0cf7bd1c775
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-a-text-file-ccli"></a>Gewusst wie: Schreiben einer Textdatei (C++/CLI)
Im folgenden Codebeispiel wird veranschaulicht, wie eine Textdatei erstellt und in diese mithilfe der im <xref:System.IO.StreamWriter>-Namespace definierten <xref:System.IO>-Klasse geschrieben wird. Der Name der zu erstellenden Datei wird vom <xref:System.IO.StreamWriter>-Konstruktor übernommen. Wenn die Datei existiert, wird sie überschrieben (außer wenn Sie True als zweites <xref:System.IO.StringWriter>-Konstruktorargument übergeben).  
  
 Die Datei wird dann mithilfe der Funktionen <xref:System.IO.StreamWriter.Write%2A> und <xref:System.IO.TextWriter.WriteLine%2A> abgelegt.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Datei- und Datenstrom-E/A](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)