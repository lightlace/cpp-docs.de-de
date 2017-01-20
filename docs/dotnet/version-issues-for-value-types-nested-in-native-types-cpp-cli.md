---
title: "Versionsprobleme bei in systemeigenen Typen geschachtelten Werttypen (C++/CLI)"
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
  - "__nogc-Typdeklarationen"
  - "__value-Schlüsselwort, Probleme bei Schachtelung"
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Versionsprobleme bei in systemeigenen Typen geschachtelten Werttypen (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellen Sie sich eine signierte Assemblykomponente vor \(mit starkem Namen\), die zum Erstellen einer Clientassembly verwendet wird.  Die Komponente enthält einen Werttyp, der auf dem Client als Typ für einen Member einer systemeigenen Union, einer Klasse oder eines Arrays verwendet wird.  Wenn in einer zukünftigen Version der Komponente die Größe oder das Layout des Werttyps geändert wird, muss der Client neu kompiliert werden.  
  
 Erstellen Sie mithilfe von [sn.exe](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) eine Schlüsseldatei \(`sn -k mykey.snk`\).  
  
## Beispiel  
 Das folgende Beispiel stellt die Komponente dar.  
  
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
  
## Beispiel  
 Dieses Beispiel stellt den Client dar:  
  
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
  
## Ausgabe  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### Kommentare  
 Wenn Sie jedoch in nested\_value\_types.cpp einen weiteren Member zu `struct S` hinzufügen \(zum Beispiel `double d;`\) und die Komponente ohne Neukompilierung des Clients neu kompilieren, erhalten Sie als Ergebnis eine unbehandelte Ausnahme \(vom Typ <xref:System.IO.FileLoadException?displayProperty=fullName>\).  
  
## Siehe auch  
 [Verwaltete Typen](../dotnet/managed-types-cpp-cli.md)