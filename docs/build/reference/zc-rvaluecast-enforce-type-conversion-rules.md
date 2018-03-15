---
title: '/ Zc: rvaluecast (typkonvertierungsregeln erzwingen) | Microsoft Docs'
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9e2223176082a2252dd410af4012ace31c14267
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (Typkonvertierungsregeln erzwingen)

Wenn die **/Zc: rvaluecast** angegeben wird, identifiziert der Compiler ordnungsgemäß einen Rvalue-Verweistyp als Ergebnis eines Umwandlungsvorgangs entsprechend dem standard C ++ 11. Wenn diese Option nicht angegeben ist, entspricht das Compilerverhalten dem von Visual Studio 2012.

## <a name="syntax"></a>Syntax

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>Hinweise

Wenn **/Zc: rvaluecast** angegeben wird, folgt der Compiler Abschnitt 5.4 des standard C ++ 11 und behandelt nur Umwandlungsausdrücke, die in Typen ohne Verweis führen sowie Umwandlungsausdrücke, die zu Rvalue-verweisen zu nichtfunktionstypen führen als Rvalue-Typen. Standardmäßig oder wenn **/Zc:rvalueCast-** angegeben wird, der Compiler nicht konform und behandelt alle Umwandlungsausdrücke, die zu Rvalue-Verweise als Rvalues führen. Für Konformität und um Fehler bei der Verwendung von Umwandlungen zu vermeiden, empfehlen wir die Verwendung **/Zc: rvaluecast**.

Standardmäßig **/Zc: rvaluecast** ist deaktiviert (**/Zc:rvalueCast-**). Die [/ liberalen-](permissive-standards-conformance.md) Compileroption legt implizit diese Option, jedoch können sie mithilfe von außer Kraft gesetzt werden **/Zc:rvalueCast-**.

Verwendung **/Zc: rvaluecast** , wenn Sie einen Umwandlungsausdruck als Argument an eine Funktion übergeben, die einen Rvalue-Verweistyp akzeptiert. Das Standardverhalten verursacht Compilerfehler [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) Wenn der Compiler fälschlicherweise den Typ des Umwandlungsausdrucks bestimmt. In diesem Beispiel demonstriert einen Compilerfehler im korrekten code beim **/Zc: rvaluecast** nicht angegeben wird:

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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc: rvaluecast** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
