---
title: "Gewusst wie: Speichern von Text in der Zwischenablage (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Zwischenablage, Speichern von Text"
  - "Text, Speichern in Zwischenablage"
ms.assetid: 9996023f-b700-47ad-8ad9-1ba201eaa5a6
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Speichern von Text in der Zwischenablage (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird das im <xref:System.Windows.Forms>\-Namespace definierte <xref:System.Windows.Forms.Clipboard>\-Objekt verwendet, um eine Zeichenfolge zu speichern.  Dieses Objekt stellt zwei Memberfunktionen bereit: <xref:System.Windows.Forms.Clipboard.SetDataObject*> und <xref:System.Windows.Forms.Clipboard.GetDataObject*>.  Daten werden in der Zwischenablage gespeichert, indem jedes von <xref:System.Object> abgeleitete Objekt an <xref:System.Windows.Forms.Clipboard.SetDataObject*> gesendet wird.  
  
## Beispiel  
  
```  
// store_clipboard.cpp  
// compile with: /clr  
#using <System.dll>  
#using <System.Drawing.dll>  
#using <System.Windows.Forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main()  
{  
   String^ str = "This text is copied into the Clipboard.";  
  
   // Use 'true' as the second argument if  
   // the data is to remain in the clipboard  
   // after the program terminates.  
   Clipboard::SetDataObject(str, true);  
  
   Console::WriteLine("Added text to the Clipboard.");  
  
   return 0;  
}  
```  
  
## Siehe auch  
 [Gewusst wie: Abrufen von Text aus der Zwischenablage](../dotnet/how-to-retrieve-text-from-the-clipboard-cpp-cli.md)   
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)