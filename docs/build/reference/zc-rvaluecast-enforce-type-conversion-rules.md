---
title: "/Zc:rvalueCast (Typkonvertierungsregeln erzwingen)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "rvaluecast"
  - "/Zc:rvalueCast"
  - "VC.Project.VCCLCompilerTool.EnforceTypeConversionRules"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (Compileroptionen) [C++]"
  - "Typkonvertierungsregeln erzwingen"
  - "rvaluecast"
  - "Zc (Compileroptionen) [C++]"
  - "-Zc (Compileroptionen) [C++]"
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:rvalueCast (Typkonvertierungsregeln erzwingen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn die Option **\/Zc:rvalueCast** angegeben ist, identifiziert der Compiler ordnungsgemäß einen rvalue\-Verweistyp als Ergebnis eines Umwandlungsvorgangs entsprechend dem Standard C\+\+11.  Wenn diese Option nicht angegeben ist, entspricht das Compilerverhalten dem von Visual Studio 2012.  **\/Zc:rvalueCast** ist standardmäßig deaktiviert.  Zur Erhaltung der Konformität und um Fehler bei der Verwendung von Umwandlungen zu vermeiden, wird empfohlen, **\/Zc:rvalueCast** zu verwenden.  
  
## Syntax  
  
```  
/Zc:rvalueCast[-]  
```  
  
## Hinweise  
 Wenn **\/Zc:rvalueCast** angegeben wird, folgt der Compiler Abschnitt 5.4 des C\+\+11\-Standards und behandelt nur Umwandlungsausdrücke als rvalue\-Typen, die zu Typen ohne Verweis führen sowie Umwandlungsausdrücke, die zu rvalue\-Verweisen zu Nichtfunktionstypen führen.  Standardmäßig oder wenn **\/Zc:rvalueCast\-** angegeben wird, ist der Compiler nicht konform und behandelt alle Umwandlungsausdrücke, die zu rvalue\-Verweisen führen, als rvalues.  
  
 Verwenden Sie **\/Zc:rvalueCast**, wenn Sie einen Umwandlungsausdruck als Argument an eine Funktion übergeben, die einen rvalu\-Verweistyp akzeptiert.  Das Standardverhalten verursacht Compilerfehler [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md), wenn der Compiler fälschlicherweise den Typ des Umwandlungsausdrucks bestimmt.  Dieses Beispiel demonstriert einen Compilerfehler im korrekten Code, wenn "\/Zc:rvalueCast" nicht angegeben ist:  
  
```cpp  
// Test of /Zc:rvalueCast  
// compile by using:  
// cl /c /Zc:rvalueCast- make_thing.cpp  
// cl /c /Zc:rvalueCast make_thing.cpp  
  
#include <utility>  
  
template <typename T>   
struct Thing {  
   // Construct a Thing by using two rvalue reference parameters  
   Thing(T&& t1, T&& t2)  
      : thing1(t1), thing2(t2) {}  
  
   T& thing1;  
   T& thing2;  
};  
  
// Create a Thing, using move semantics if possible  
template <typename T>  
Thing<T> make_thing(T&& t1, T&& t2)  
{  
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));  
}  
  
struct Test1 {  
   long a;  
   long b;  
  
   Thing<long> test() {   
      // Use identity casts to create rvalues as arguments  
      return make_thing(static_cast<long>(a), static_cast<long>(b));   
   }  
};  
  
```  
  
 Das standardmäßige Compilerverhalten meldet möglicherweise keinen Fehler C2102, wenn dies angemessen ist.  In diesem Beispiel meldet der Compiler keinen Fehler, wenn die Adresse eines durch Identitätsumwandlung erstellten rvalue verwendet wird, wenn **\/Zc:rvalueCast** nicht angegeben ist:  
  
```cpp  
int main() {  
   int a = 1;  
   int *p = &a;   // Okay, take address of lvalue   
                  // Identity cast creates rvalue from lvalue;    
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value  
}  
```  
  
 Weitere Informationen über Konformitätsprobleme in Visual C\+\+ finden Sie unter [Nicht dem Standard entsprechendes Verhalten](../../cpp/nonstandard-behavior.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Ändern Sie die Eigenschaft **Zusätzliche Optionen**, damit sie **\/Zc:rvalueCast** einschließt, und wählen Sie dann **OK** aus.  
  
## Siehe auch  
 [\/Zc \(Übereinstimmung\)](../../build/reference/zc-conformance.md)