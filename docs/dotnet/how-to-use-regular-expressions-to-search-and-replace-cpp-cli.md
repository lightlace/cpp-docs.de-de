---
title: "Vorgehensweise: Verwenden von regulären Ausdrücken zum Suchen und Ersetzen (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- search and replace
- Replace method
- regular expressions [C++], search and replace
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f66df471d66a82a565fc5c072757664567d1f25c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-regular-expressions-to-search-and-replace-ccli"></a>Gewusst wie: Verwenden von regulären Ausdrücken zum Suchen und Ersetzen (C++/CLI)
Im folgenden Codebeispiel wird veranschaulicht, wie die Klasse regulärer Ausdrücke <xref:System.Text.RegularExpressions.Regex> verwendet werden können, suchen und Ersetzen durchgeführt. Dies erfolgt mit der <xref:System.Text.RegularExpressions.Regex.Replace%2A> Methode. Verwendete Version, die zwei Zeichenfolgen als Eingabe akzeptiert: die Zeichenfolge, die geändert werden, und die Zeichenfolge, die anstelle der Abschnitte (sofern vorhanden) eingefügt werden, die dem Muster entsprechen erhält der <xref:System.Text.RegularExpressions.Regex> Objekt.  
  
 Dieser Code ersetzt alle Ziffern in einer Zeichenfolge durch Unterstriche (_) und ersetzt diese mit einer leeren Zeichenfolge, die effektiv zu entfernen. Die gleiche Auswirkungen kann in einem einzigen Schritt erfolgen, aber zwei Schritte werden hier zur Veranschaulichung verwendet.  
  
## <a name="example"></a>Beispiel  
  
```  
// regex_replace.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System::Text::RegularExpressions;  
using namespace System;  
  
int main()  
{  
   String^ before = "The q43uick bro254wn f0ox ju4mped";  
   Console::WriteLine("original  : {0}", before);  
  
   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");  
   String^ after = digitRegex->Replace(before, "_");  
   Console::WriteLine("1st regex : {0}", after);  
  
   Regex^ underbarRegex = gcnew Regex("_");  
   String^ after2 = underbarRegex->Replace(after, "");  
   Console::WriteLine("2nd regex : {0}", after2);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](/dotnet/standard/base-types/regular-expressions)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)