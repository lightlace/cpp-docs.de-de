---
title: "Vorgehensweise: Schreiben einer Binärdatei (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- binary files, writing in C++
- files [C++], binary
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4aada166d8843665c645fbac90e58ef31714ab13
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-write-a-binary-file-ccli"></a>Gewusst wie: Schreiben einer Binärdatei (C++/CLI)
Im folgenden Codebeispiel wird das Schreiben von Binärdaten in eine Datei veranschaulicht. Zwei Klassen des <xref:System.IO>-Namespace werden verwendet: <xref:System.IO.FileStream> und <xref:System.IO.BinaryWriter>. <xref:System.IO.FileStream> repräsentiert die eigentliche Datei, während <xref:System.IO.BinaryWriter> eine Schnittstelle zum Stream für den Binärzugriff bereitstellt.  
  
 Im folgenden Codebeispiel wird eine Datei erzeugt, die ganze Zahlen im Binärformat enthält. Diese Datei gelesen werden kann, durch den Code in [wie: Lesen einer Binärdatei (C + c++ / CLI)](../dotnet/how-to-read-a-binary-file-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Datei- und Datenstrom-E/A](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)