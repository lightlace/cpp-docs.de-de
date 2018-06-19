---
title: So überprüfen Sie die Formatierung verwenden von regulären Ausdrücken (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 225775c3-3efc-4734-bde2-1fdf73e3d397
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 59a553ac2d58f9304fce3961aa8212c33b26643a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129615"
---
# <a name="how-to-use-regular-expressions-to-validate-data-formatting-ccli"></a>Gewusst wie: Verwenden von regulären Ausdrücken zur Überprüfung der Datenformatierung (C++/CLI)
Das folgende Codebeispiel veranschaulicht die Verwendung von regulären Ausdrücken, um zu überprüfen, ob die Formatierung einer Zeichenfolge. Im folgenden Codebeispiel muss die Zeichenfolge eine gültige Telefonnummer enthalten. Im folgenden Codebeispiel wird die Zeichenfolge "\d{3}-\d{3}-\d{4}", um anzugeben, dass jedes Feld eine gültige Telefonnummer darstellt. In der Zeichenfolge "d" eine Ziffer angibt, und das Argument nach jedes "d" gibt die Anzahl der Ziffern, die vorhanden sein muss. In diesem Fall muss die Anzahl durch Bindestriche voneinander getrennt werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// regex_validate.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ number =   
   {  
      "123-456-7890",   
      "444-234-22450",   
      "690-203-6578",   
      "146-893-232",  
      "146-839-2322",  
      "4007-295-1111",   
      "407-295-1111",   
      "407-2-5555",   
   };  
  
   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";  
  
   for ( int i = 0; i < number->Length; i++ )  
   {  
      Console::Write( "{0,14}", number[i] );  
  
      if ( Regex::IsMatch( number[i], regStr ) )  
         Console::WriteLine(" - valid");  
      else  
         Console::WriteLine(" - invalid");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](/dotnet/standard/base-types/regular-expressions)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)