---
title: __declspec | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __declspec_cpp
dev_langs: C++
helpviewer_keywords: __declspec keyword [C++]
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0351b5ba8469918dfe52462485ebf36255db56fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="declspec"></a>__declspec
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Die erweiterte Attributsyntax für die Angabe von Speicherklasseninformationen verwendet das `__declspec`-Schlüsselwort, das angibt, dass eine Instanz eines angegebenen Typs mit einem der unten aufgelisteten Microsoft-spezifischen Speicherklassenattribute gespeichert werden muss. Andere Speicherklassenmodifizierer sind beispielsweise die Schlüsselwörter `static` und `extern`. Allerdings sind diese Schlüsselwörter Teil der ANSI-Spezifikation der Programmiersprachen C- und C++ und werden als solche nicht von der erweiterten Attributsyntax abgedeckt. Die erweiterte Attributsyntax vereinfacht und standardisiert Microsoft-spezifische Erweiterungen der Programmiersprachen C und C++.  
  
## <a name="grammar"></a>Grammatik  
 *Decl-Specifiers*:  
 `__declspec (`  *Extended-Decl-Modifier-seq*  `)`  
  
 *extended-decl-modifier-seq*:  
 *extended-decl-modifier*opt  
  
 *Extended-Decl-Modifier extended-Decl-Modifier-seq*  
  
 *extended-decl-modifier*:  
 `align(` *#* `)`  
  
 `allocate("`*Segname*`")`  
  
 `appdomain`  
  
 `code_seg("`*Segname*`")`  
  
 `deprecated`  
  
 `dllimport`  
  
 `dllexport`  
  
 `jitintrinsic`  
  
 `naked`  
  
 `noalias`  
  
 `noinline`  
  
 `noreturn`  
  
 `nothrow`  
  
 `novtable`  
  
 `process`  
  
 `property(`{`get=`*Get_func_name*&#124;`,put=` *Put_func_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("`*ComObjectGUID*`")`  
  
 Die Deklarationsmodifizierersequenz ist durch Leerzeichen getrennt. Beispiele finden Sie in späteren Abschnitten.  
  
 Erweitertes Attribut-Grammatik unterstützt diese Microsoft-spezifische Speicherklassen-Attribute: [ausrichten](../cpp/align-cpp.md), [zuordnen](../cpp/allocate.md), [Appdomain](../cpp/appdomain.md), [Code_seg](../cpp/code-seg-declspec.md), [veraltet](../cpp/deprecated-cpp.md), [Dllexport](../cpp/dllexport-dllimport.md), [Dllimport](../cpp/dllexport-dllimport.md), [Jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [Noalias](../cpp/noalias.md), [Noinline](../cpp/noinline.md), [Noreturn](../cpp/noreturn.md), [Nothrow](../cpp/nothrow-cpp.md), [Novtable](../cpp/novtable.md) , [Prozess](../cpp/process.md), [beschränken](../cpp/restrict.md), [Safebuffers](../cpp/safebuffers.md), [Selectany](../cpp/selectany.md), und [Thread](../cpp/thread.md). Sie unterstützt auch diese COM-Objektattribute: [Eigenschaft](../cpp/property-cpp.md) und [Uuid](../cpp/uuid-cpp.md).  
  
 Die Speicherklassenattribute `code_seg`, `dllexport`, `dllimport`, `naked`, `noalias`, `nothrow`, `property`, `restrict`, `selectany`, `thread` und `uuid` sind Eigenschaften nur der Deklaration des Objekts oder der Funktion, auf das bzw. die sie angewendet werden. Das `thread`-Attribut wirkt sich nur auf Daten und Objekte aus. Das `naked`-Attribut wirkt sich nur auf Funktionen aus. Die Attribute `dllimport` und `dllexport` haben Auswirkung auf Funktionen, Daten und Objekte. Die Attribute `property`, `selectany` und `uuid` beeinflussen COM-Objekte.  
  
 Die `__declspec` Schlüsselwörter sollten am Anfang einer einfachen Deklaration platziert werden. Der Compiler ignoriert ohne Warnung alle `__declspec`-Schlüsselwörter, die nach * oder & und vor dem Variablenbezeichner in einer Deklaration auftreten.  
  
 Ein `__declspec`-Attribut, das am Anfang einer benutzerdefinierten Typdeklaration angegeben wird, wird auf die Variable dieses Typs angewendet. Zum Beispiel:  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 In diesem Fall wird das Attribut auf `varX` angewendet. Ein `__declspec`-Attribut, das nach dem `class`- oder `struct`-Schlüsselwort platziert wird, wird auf den benutzerdefinierten Typ angewendet. Zum Beispiel:  
  
```  
class __declspec(dllimport) X {};  
```  
  
 In diesem Fall wird das Attribut auf `X` angewendet.  
  
 Die allgemeine Richtlinie für die Verwendung des `__declspec`-Attributs für einfache Deklarationen lautet wie folgt:  
  
```  
  
decl-specifier-seq  
declarator-list;  
```  
  
 Die *Decl-Specifier-Seq* enthalten soll, unter anderem einen Basistyp (z. B. `int`, `float`, `typedef`, oder einen Klassennamen), eine Speicherklasse (z. B. `static`, `extern`), oder die `__declspec`Erweiterung. Die *Init-Declarator-List* enthalten soll, unter anderem den Zeiger Teil Deklarationen. Zum Beispiel:  
  
```  
__declspec(selectany) int * pi1 = 0;   //OK, selectany & int both part of decl-specifier  
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier  
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator  
```  
  
 Mit folgendem Code wird z. B. eine ganzzahlige threadlokale Variable deklariert und mit einem Wert initialisiert:  
  
```  
// Example of the __declspec keyword  
__declspec( thread ) int tls_i = 1;  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [C-Speicherklassenattribute (erweitert)](../c-language/c-extended-storage-class-attributes.md)