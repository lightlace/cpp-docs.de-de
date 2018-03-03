---
title: "Literal (Komponentenerweiterungen für C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- literal
- literal_cpp
dev_langs:
- C++
helpviewer_keywords:
- literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f858e94bf916c2d441cee607739bb9e08da09b85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="literal-c-component-extensions"></a>literal (Komponentenerweiterungen für C++)
Eine Variable (Datenmember) gekennzeichnet, als `literal` in einer **"/ CLR"** Kompilierung ist das systemeigene Äquivalent der eine `static const` Variable.  
  
## <a name="all-platforms"></a>Alle Plattformen  
 **Hinweise**  
  
 (Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.)  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 **Hinweise**  
  
 (Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows-Runtime gelten.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
  
## <a name="remarks"></a>Hinweise  
 Ein Datenmember als gekennzeichnet `literal` muss initialisiert werden, wenn Sie deklariert und der Wert muss eine Konstante integrale, Enumerations- oder Zeichenfolgentyp sein. Eine benutzerdefinierte Konvertierung erforderlich Konvertierung vom Typ des Initialisierungsausdrucks in den Typ des static const-Datenmembers nicht.  
  
 Keine "Erinnerung" wird für das literal Feld zur Laufzeit reserviert. der Compiler fügt den Wert nur in den Metadaten für die Klasse.  
  
 Markiert eine Variable `static const` ist nicht in den Metadaten auf andere Compiler verfügbar.  
  
 Weitere Informationen finden Sie unter [statische](../cpp/storage-classes-cpp.md) und [const](../cpp/const-cpp.md).  
  
 `literal` ist ein kontextbezogenes Schlüsselwort. Finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, dass eine `literal` Variable impliziert `static`.  
  
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
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Auswirkungen der literal in den Metadaten:  
  
```  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 Beachten Sie den Unterschied in den Metadaten für `sc` und `lit`: die `modopt` Richtlinie wird angewendet, um `sc`, d. h. sie kann von anderen Compilern ignoriert werden.  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird in c# erstellte verweist auf die Metadaten, die im vorherigen Beispiel erstellt und zeigt die Auswirkungen der `literal` und `static const` Variablen:  
  
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
  
## <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)