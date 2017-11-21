---
title: 'Vorgehensweise: Abrufen von Text aus der Zwischenablage (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- text, retrieving from Clipboard
- Clipboard, retrieving text
ms.assetid: 99e77ba0-8573-4030-92d8-de8aa7623ee4
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6517b367e8c3d59538a4e36839ccc7f93d8b1817
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-retrieve-text-from-the-clipboard-ccli"></a>Gewusst wie: Abrufen von Text aus der Zwischenablage (C++/CLI)
Im folgenden Codebeispiel wird mit der <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> Memberfunktion zurückzugebenden einen Zeiger auf die <xref:System.Windows.Forms.IDataObject> Schnittstelle. Diese Schnittstelle kann dann für das Format der Daten abgefragt und verwendet, um die eigentlichen Daten abzurufen.  
  
## <a name="example"></a>Beispiel  
  
```  
// read_clipboard.cpp  
// compile with: /clr  
#using <system.dll>  
#using <system.Drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main( )  
{  
   IDataObject^ data = Clipboard::GetDataObject( );  
  
   if (data)  
   {  
      if (data->GetDataPresent(DataFormats::Text))   
      {  
         String^ text = static_cast<String^>  
           (data->GetData(DataFormats::Text));  
         Console::WriteLine(text);   
      }  
      else  
         Console::WriteLine("Nontext data is in the Clipboard.");  
   }  
   else   
   {  
      Console::WriteLine("No data was found in the Clipboard.");  
   }  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Vorgänge (C + c++ / CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)