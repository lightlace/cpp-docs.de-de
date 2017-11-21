---
title: 'Vorgehensweise: Auflisten von Dateien in einem Verzeichnis (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [C++], listing files
- directories [C++], listing files
ms.assetid: ebfc2666-229f-4b94-a9a1-e8f1b5d946d6
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 365f54435c92ff464a0906cd719bd33ce28d61b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-enumerate-files-in-a-directory-ccli"></a>Gewusst wie: Auflisten von Dateien in einem Verzeichnis (C++/CLI)
Im folgenden Codebeispiel wird veranschaulicht, wie eine Liste von Dateien in einem Verzeichnis abgerufen wird. Zusätzlich werden die Unterverzeichnisse aufgelistet. Im folgenden Beispiel werden die <xref:System.IO.Directory.GetFiles%2A><xref:System.IO.Directory.GetFiles%2A>-Methode und <xref:System.IO.Directory.GetDirectories%2A>-Methode verwendet, um den Inhalt des Verzeichnisses C:\Windows anzuzeigen.  
  
## <a name="example"></a>Beispiel  
  
```  
// enum_files.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ folder = "C:\\";  
   array<String^>^ dir = Directory::GetDirectories( folder );  
   Console::WriteLine("--== Directories inside '{0}' ==--", folder);  
   for (int i=0; i<dir->Length; i++)  
      Console::WriteLine(dir[i]);  
  
   array<String^>^ file = Directory::GetFiles( folder );  
   Console::WriteLine("--== Files inside '{0}' ==--", folder);  
   for (int i=0; i<file->Length; i++)  
      Console::WriteLine(file[i]);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datei- und Datenstrom-E/A](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)