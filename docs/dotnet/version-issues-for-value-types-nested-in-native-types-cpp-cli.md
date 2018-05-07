---
title: Versionsprobleme bei Werttypen in systemeigenen Typen geschachtelten (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __nogc type declarations
- __value keyword, issues when nesting
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4c4f2598594930f49c1217c937c9142b3f84a47e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="version-issues-for-value-types-nested-in-native-types-ccli"></a>Versionsprobleme bei in systemeigenen Typen geschachtelten Werttypen (C++/CLI)
Beispiel: eine mit Vorzeichen (starker Name)-Assembly-Komponente verwendet, um eine Clientassembly zu erstellen. Die Komponente enthält einen Werttyp, der auf dem Client als Typ für ein Mitglied einer systemeigenen Union, eine Klasse oder ein Array verwendet wird. Wenn die Größe oder das Layout des Werttyps eine zukünftige Version der Komponente geändert wird, muss der Client neu kompiliert werden.  
  
 Erstellen Sie eine Schlüsseldatei mit [sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) (`sn -k mykey.snk`).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel ist die Komponente.  
  
```  
// nested_value_types.cpp  
// compile with: /clr /LD  
using namespace System::Reflection;  
[assembly:AssemblyVersion("1.0.0.*"),   
assembly:AssemblyKeyFile("mykey.snk")];  
  
public value struct S {  
   int i;  
   void Test() {  
      System::Console::WriteLine("S.i = {0}", i);  
   }  
};  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Client:  
  
```  
// nested_value_types_2.cpp  
// compile with: /clr  
#using <nested_value_types.dll>  
  
struct S2 {  
   S MyS1, MyS2;  
};  
  
int main() {  
   S2 MyS2a, MyS2b;  
   MyS2a.MyS1.i = 5;  
   MyS2a.MyS2.i = 6;  
   MyS2b.MyS1.i = 10;  
   MyS2b.MyS2.i = 11;  
  
   MyS2a.MyS1.Test();  
   MyS2a.MyS2.Test();  
   MyS2b.MyS1.Test();  
   MyS2b.MyS2.Test();  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### <a name="comments"></a>Kommentare  
 Jedoch, wenn Sie einen anderen Member hinzufügen `struct S` in nested_value_types.cpp, (z. B. `double d;`) und kompilieren Sie die Komponente ohne erneute Kompilierung des Clients, das Ergebnis ist eine nicht behandelte Ausnahme (vom Typ <xref:System.IO.FileLoadException?displayProperty=fullName>).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwaltete Typen (C++/CLI)](../dotnet/managed-types-cpp-cli.md)