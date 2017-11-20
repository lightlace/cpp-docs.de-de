---
title: '-Zc: RvalueCast (typkonvertierungsregeln erzwingen) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 068d1e0e9061645729728c4d0a3c956e521948cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (Typkonvertierungsregeln erzwingen)
Wenn die **/Zc: rvaluecast** angegeben wird, identifiziert der Compiler ordnungsgemäß einen Rvalue-Verweistyp als Ergebnis eines Umwandlungsvorgangs entsprechend dem standard C ++ 11. Wenn diese Option nicht angegeben ist, entspricht das Compilerverhalten dem von Visual Studio 2012. Standardmäßig **/Zc: rvaluecast** ist deaktiviert. Für Konformität und um Fehler bei der Verwendung von Umwandlungen zu vermeiden, empfehlen wir die Verwendung **/Zc: rvaluecast**.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Zc:rvalueCast[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn **/Zc: rvaluecast** angegeben wird, folgt der Compiler Abschnitt 5.4 des standard C ++ 11 und behandelt nur Umwandlungsausdrücke, die in Typen ohne Verweis führen sowie Umwandlungsausdrücke, die zu Rvalue-verweisen zu nichtfunktionstypen führen als Rvalue-Typen. Standardmäßig oder wenn **/Zc:rvalueCast-** angegeben wird, der Compiler nicht konform und behandelt alle Umwandlungsausdrücke, die zu Rvalue-Verweise als Rvalues führen.  
  
 Verwendung **/Zc: rvaluecast** , wenn Sie einen Umwandlungsausdruck als Argument an eine Funktion übergeben, die einen Rvalue-Verweistyp akzeptiert. Das Standardverhalten verursacht Compilerfehler [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) Wenn der Compiler fälschlicherweise den Typ des Umwandlungsausdrucks bestimmt. Dieses Beispiel demonstriert einen Compilerfehler im korrekten Code, wenn "/Zc:rvalueCast" nicht angegeben ist:  
  
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
  
 Das standardmäßige Compilerverhalten meldet möglicherweise keinen Fehler C2102, wenn dies angemessen ist. In diesem Beispiel wird der Compiler meldet keine Fehler ab, wenn die Adresse des durch eine Identität umgewandelt identitätsumwandlung erstellten Rvalue verwendet wird **/Zc: rvaluecast** nicht angegeben wird:  
  
```cpp  
int main() {  
   int a = 1;  
   int *p = &a;   // Okay, take address of lvalue   
                  // Identity cast creates rvalue from lvalue;    
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value  
}  
```  
  
 Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc: rvaluecast** und wählen Sie dann **OK**.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)