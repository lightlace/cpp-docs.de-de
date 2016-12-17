---
title: "Gewusst wie: Auflisten von Dateien in einem Verzeichnis (C++/CLI)"
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
  - "Verzeichnisse [C++], Auflisten von Dateien"
  - "Dateien [C++], Auflisten von Dateien"
ms.assetid: ebfc2666-229f-4b94-a9a1-e8f1b5d946d6
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Auflisten von Dateien in einem Verzeichnis (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird veranschaulicht, wie eine Liste von Dateien in einem Verzeichnis abgerufen wird.  Zusätzlich werden die Unterverzeichnisse aufgelistet.  Im folgenden Beispiel werden die <xref:System.IO.Directory.GetFiles*> <xref:System.IO.Directory.GetFiles*>\-Methode und <xref:System.IO.Directory.GetDirectories*>\-Methode verwendet, um den Inhalt des Verzeichnisses C:\\Windows anzuzeigen.  
  
## Beispiel  
  
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
  
## Siehe auch  
 [Datei\- und Stream\-E\/A](../Topic/File%20and%20Stream%20I-O.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)