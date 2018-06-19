---
title: 'Vorgehensweise: Verwenden von regulären Ausdrücken zum Neuanordnen von Daten (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular expressions [C++], rearranging data
- data [C++], rearranging
ms.assetid: 5f91e777-9471-424e-ba75-dca3d1b49e42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 72c72721aa68417ff13905fdf96f8d2a48b310cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130863"
---
# <a name="how-to-use-regular-expressions-to-rearrange-data-ccli"></a>Gewusst wie: Verwenden von regulären Ausdrücken zum Ändern der Anordnung von Daten (C++/CLI)
Im folgenden Codebeispiel wird veranschaulicht, wie die reguläre .NET Framework-Unterstützung zum neu anzuordnen, oder Formatieren von Daten verwendet werden kann. Im folgenden Codebeispiel wird mit der <xref:System.Text.RegularExpressions.Regex> und <xref:System.Text.RegularExpressions.Match> Klassen, die vor-und Nachnamen aus einer Zeichenfolge zu extrahieren, und klicken Sie dann in umgekehrter Reihenfolge angezeigt.  
  
 Die <xref:System.Text.RegularExpressions.Regex> Klasse wird verwendet, um einen regulären Ausdruck zu erstellen, die das aktuelle Format der Daten beschreibt. Die beiden Namen können wird angenommen, dass durch ein Komma getrennt werden und beliebige Anzahl von Leerzeichen, um das Komma. Die <xref:System.Text.RegularExpressions.Match> Methode wird verwendet, um jede Zeichenfolge zu analysieren. Bei erfolgreicher Ausführung werden vor-und Nachnamen abgerufen, von der <xref:System.Text.RegularExpressions.Match> -Objekt und angezeigt.  
  
## <a name="example"></a>Beispiel  
  
```  
// regex_reorder.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ name =   
   {  
      "Abolrous, Sam",   
      "Berg,Matt",   
      "Berry , Jo",  
      "www.contoso.com"  
   };  
  
   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");  
  
   for ( int i=0; i < name->Length; i++ )  
   {  
      Console::Write( "{0,-20}", name[i] );  
      Match^ m = reg->Match( name[i] );  
      if ( m->Success )  
      {  
         String^ first = m->Groups["first"]->Value;  
         String^ last = m->Groups["last"]->Value;  
         Console::WriteLine("{0} {1}", first, last);  
      }  
      else  
         Console::WriteLine("(invalid)");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](/dotnet/standard/base-types/regular-expressions)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)