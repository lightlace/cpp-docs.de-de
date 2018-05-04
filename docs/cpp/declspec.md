---
title: __declspec | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c610da3545e7269c307542930140616dc6af9dce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="declspec"></a>__declspec

**Microsoft-spezifisch**

Die erweiterte Attributsyntax für die Angabe von Speicher speicherklasseninformationen verwendet das **__declspec** Schlüsselwort, das angibt, dass eine Instanz eines angegebenen Typs mit einem Microsoft-spezifischen Speicherklassenattribut unten aufgeführten gespeichert werden. Beispiele anderer Speicherklassenmodifizierer umfassen die **statische** und **"extern"** Schlüsselwörter. Allerdings sind diese Schlüsselwörter Teil der ANSI-Spezifikation der Programmiersprachen C- und C++ und werden als solche nicht von der erweiterten Attributsyntax abgedeckt. Die erweiterte Attributsyntax vereinfacht und standardisiert Microsoft-spezifische Erweiterungen der Programmiersprachen C und C++.

## <a name="grammar"></a>Grammatik

*Decl-Specifiers*:  
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (***extended-Decl-Modifier-Seq***)** 

*extended-decl-modifier-seq*:  
&nbsp;&nbsp;&nbsp;&nbsp;*Extended-Decl-Modifier*<sub>abonnieren</sub>  
&nbsp;&nbsp;&nbsp;&nbsp;*Extended-Decl-Modifier* *extended-Decl-Modifier-Seq*

*extended-decl-modifier*:  
&nbsp;&nbsp;&nbsp;&nbsp;**align (** *#* **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**zuordnen ("** *Segname* **")**  
&nbsp;&nbsp;&nbsp;&nbsp;**appdomain**  
&nbsp;&nbsp;&nbsp;&nbsp;**Code_seg ("** *Segname* **")**  
&nbsp;&nbsp;&nbsp;&nbsp;**Als veraltet markiert**  
&nbsp;&nbsp;&nbsp;&nbsp;**DllImport**  
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**  
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**  
&nbsp;&nbsp;&nbsp;&nbsp;**naked**  
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**  
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**  
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**  
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**  
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**  
&nbsp;&nbsp;&nbsp;&nbsp;**Prozess**  
&nbsp;&nbsp;&nbsp;&nbsp;**Eigenschaft (** { **get =**_Get_func_name_ &#124; **, put =**_Put_func_name_ } **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**Einschränken**  
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**  
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**  
&nbsp;&nbsp;&nbsp;&nbsp;**spectre(nomitigation)**  
&nbsp;&nbsp;&nbsp;&nbsp;**Thread**  
&nbsp;&nbsp;&nbsp;&nbsp;**UUID ("** *ComObjectGUID* **")**  

Die Deklarationsmodifizierersequenz ist durch Leerzeichen getrennt. Beispiele finden Sie in späteren Abschnitten.

Erweitertes Attribut-Grammatik unterstützt diese Microsoft-spezifische Speicherklassen-Attribute: [ausrichten](../cpp/align-cpp.md), [zuordnen](../cpp/allocate.md), [Appdomain](../cpp/appdomain.md), [Code_seg](../cpp/code-seg-declspec.md), [veraltet](../cpp/deprecated-cpp.md), [Dllexport](../cpp/dllexport-dllimport.md), [Dllimport](../cpp/dllexport-dllimport.md), [Jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [Noalias](../cpp/noalias.md), [Noinline](../cpp/noinline.md), [Noreturn](../cpp/noreturn.md), [Nothrow](../cpp/nothrow-cpp.md), [Novtable](../cpp/novtable.md) , [Prozess](../cpp/process.md), [beschränken](../cpp/restrict.md), [Safebuffers](../cpp/safebuffers.md), [Selectany](../cpp/selectany.md), [Absorptionsspektrum](../cpp/spectre.md), und [Thread](../cpp/thread.md). Sie unterstützt auch diese COM-Objektattribute: [Eigenschaft](../cpp/property-cpp.md) und [Uuid](../cpp/uuid-cpp.md).

Die **Code_seg**, **Dllexport**, **Dllimport**, **naked**, **Noalias**, **Nothrow** , **Eigenschaft**, **beschränken**, **Selectany**, **Thread**, und **Uuid**Speicherklassen-Attribute sind Eigenschaften nur der Deklaration des Objekts oder der Funktion, die auf die sie angewendet werden. Die **Thread** Attribut wirkt sich auf Daten und nur Objekte. Die **naked** und **Absorptionsspektrum** Attribute beeinflussen nur Funktionen. Die **Dllimport** und **Dllexport** Attribute beeinflussen, Funktionen, Daten und Objekte. Die **Eigenschaft**, **Selectany**, und **Uuid** Attribute beeinflussen COM-Objekte.

Die **__declspec** Schlüsselwörter sollten am Anfang einer einfachen Deklaration platziert werden. Der Compiler ignoriert ohne Warnung alle **__declspec** Schlüsselwörter platziert nach * oder & und vor dem Variablenbezeichner in einer Deklaration.

Ein **__declspec** am Anfang einer benutzerdefinierten Typdeklaration angegebene Attribut gilt, für die Variable dieses Typs. Zum Beispiel:

```cpp
__declspec(dllimport) class X {} varX;
```

In diesem Fall wird das Attribut auf `varX` angewendet. Ein **__declspec** Attribut platziert werden, nachdem die **Klasse** oder **Struktur** -Schlüsselwort gilt für den benutzerdefinierten Typ. Zum Beispiel:

```cpp
class __declspec(dllimport) X {};
```

In diesem Fall wird das Attribut auf `X` angewendet.

Die allgemeine Richtlinie für die Verwendung der **__declspec** -Attributs für einfache Deklarationen lautet wie folgt:

*Decl-Specifier-Seq* *Init-Declarator-List*;

Die *Decl-Specifier-Seq* enthalten soll, unter anderem einen Basistyp (z. B. **Int**, **"float"**, eine **Typedef**, oder einen Klassennamen), Speicherklasse (z. B. **statische**, **"extern"**), oder die **__declspec** Erweiterung. Die *Init-Declarator-List* enthalten soll, unter anderem den Zeiger Teil Deklarationen. Zum Beispiel:

```cpp
__declspec(selectany) int * pi1 = 0;   //Recommended, selectany & int both part of decl-specifier
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator
```

Mit folgendem Code wird z. B. eine ganzzahlige threadlokale Variable deklariert und mit einem Wert initialisiert:

```cpp
// Example of the __declspec keyword
__declspec( thread ) int tls_i = 1;
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)  
[C-Speicherklassenattribute (erweitert)](../c-language/c-extended-storage-class-attributes.md)  
