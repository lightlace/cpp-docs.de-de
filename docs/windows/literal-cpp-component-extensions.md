---
title: "literal (C++ Component Extensions)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "literal"
  - "literal_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "literal keyword [C++]"
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# literal (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Variable \(Datenmember\) hat, da `literal` in einer **\/clr** \- Kompilierung die systemeigene Entsprechung einer `static const`\-Variable ist.  
  
## Alle Plattformen  
 **Hinweise**  
  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.\)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Hinweise**  
  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows\-Runtime gelten.\)  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## Common Language Runtime  
  
## Hinweise  
 Ein Datenmember, der als `literal` gekennzeichnet ist, muss initialisiert werden, wenn er und Wert deklariert, ein konstantes ganzzahlig, Enumeration oder ein Zeichenfolgentyp sein muss.  Konvertierung vom Typ des Initialisierungsausdrucks in den Typ des statischen Datenmembers const darf eine benutzerdefinierte Konvertierung nicht benötigen.  
  
 wird kein Speicher für das literale Feld zur Laufzeit zugeordnet; der Compiler fügt nur den Wert in den Metadaten für die Klasse ein.  
  
 Variable als `static const` gekennzeichnet ist in den Metadaten mit anderen Compilern verfügbar.  
  
 Weitere Informationen finden Sie unter [Statisch](../misc/static-cpp.md) und [const](../cpp/const-cpp.md).  
  
 `literal` ist ein kontextbezogenes Schlüsselwort.  Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## Beispiel  
 Dieses Beispiel zeigt, dass eine `literal`\-Variable `static` bedeutet.  
  
```  
// mcppv2_literal.cpp  
// compile with: /clr  
ref struct X {  
   literal int i = 4;  
};  
  
int main() {  
   int value = X::i;  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird die Auswirkung des Literals in den Metadaten angezeigt:  
  
```  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 Beachten Sie den Unterschied in den Metadaten für `sc` und `lit`: Direktive werden die `modopt` auf `sc` angewendet heißt, dass sie von anderen Compilern ignoriert werden kann.  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## Beispiel  
 Im folgenden Beispiel, in C\# erstellt, verweist die Metadaten, die im vorherigen Beispiel erstellt wird und der Einfluss von `literal` und `static const` an Variablen:  
  
```  
// mcppv2_literal3.cs  
// compile with: /reference:mcppv2_literal2.dll  
// A C# program  
class B {  
   public static void Main() {  
      // OK  
      System.Console.WriteLine(A.lit);  
      System.Console.WriteLine(A.sc);  
  
      // C# does not enforce C++ const  
      A.sc = 9;  
      System.Console.WriteLine(A.sc);  
  
      // C# enforces const for a literal  
      A.lit = 9;   // CS0131  
  
      // you can assign a C++ literal variable to a C# const variable  
      const int i = A.lit;  
      System.Console.WriteLine(i);  
  
      // but you cannot assign a C++ static const variable  
      // to a C# const variable  
      const int j = A.sc;   // CS0133  
      System.Console.WriteLine(j);  
   }  
}  
```  
  
## Voraussetzungen  
 Compileroption: **\/clr**  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)