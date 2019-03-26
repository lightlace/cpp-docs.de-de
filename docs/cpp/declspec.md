---
title: __declspec
ms.date: 03/21/2019
f1_keywords:
- __declspec_cpp
- __declspec
- _declspec
helpviewer_keywords:
- __declspec keyword [C++]
ms.openlocfilehash: e924f3e4a038f900e084dbf84d85430d815c8e8f
ms.sourcegitcommit: 0064d37467f958dd6a5111f20d7660eaccd53ee9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58416948"
---
# <a name="declspec"></a>__declspec

**Microsoft-spezifisch**

Die erweiterte Attributsyntax für die Angabe von Storage speicherklasseninformationen verwendet das **__declspec** Schlüsselwort, das angibt, dass eine Instanz eines angegebenen Typs mit einem Microsoft-spezifische Speicherklassen-Attribut, die unten aufgeführten gespeichert werden. Beispiele anderer Speicherklassenmodifizierer umfassen die **statische** und **"extern"** Schlüsselwörter. Allerdings sind diese Schlüsselwörter Teil der ANSI-Spezifikation der Programmiersprachen C- und C++ und werden als solche nicht von der erweiterten Attributsyntax abgedeckt. Die erweiterte Attributsyntax vereinfacht und standardisiert Microsoft-spezifische Erweiterungen der Programmiersprachen C und C++.

## <a name="grammar"></a>Grammatik

*decl-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (**  *extended-decl-modifier-seq*  **)**

*extended-decl-modifier-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier* *extended-decl-modifier-seq*

*extended-decl-modifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**align(** *#* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**allocate("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**allocator**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**appdomain**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Als veraltet markiert**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Prozess**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**property(** { **get=**_get_func_name_ &#124; **,put=**_put_func_name_ } **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**restrict**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**spectre(nomitigation)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uuid("** *ComObjectGUID* **")**

Die Deklarationsmodifizierersequenz ist durch Leerzeichen getrennt. Beispiele finden Sie in späteren Abschnitten.

Erweitertes Attribut-Grammatik unterstützt diese Microsoft-spezifische Speicherklassen-Attribute: [ausrichten](../cpp/align-cpp.md), [zuordnen](../cpp/allocate.md), [Allocator](../cpp/allocator.md), [Appdomain](../cpp/appdomain.md), [Code_seg](../cpp/code-seg-declspec.md), [veraltet](../cpp/deprecated-cpp.md), [Dllexport](../cpp/dllexport-dllimport.md), [Dllimport](../cpp/dllexport-dllimport.md), [Jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [Noalias](../cpp/noalias.md), [Noinline](../cpp/noinline.md), [Noreturn](../cpp/noreturn.md), [Nothrow](../cpp/nothrow-cpp.md), [Novtable](../cpp/novtable.md), [Prozess](../cpp/process.md), [einschränken](../cpp/restrict.md), [Safebuffers](../cpp/safebuffers.md), [Selectany](../cpp/selectany.md), [Spectre](../cpp/spectre.md), und [Thread](../cpp/thread.md). Sie unterstützt auch diese COM-Objektattribute: [Eigenschaft](../cpp/property-cpp.md) und [Uuid](../cpp/uuid-cpp.md).

Die **Code_seg**, **Dllexport**, **Dllimport**, **naked**, **Noalias**, **Nothrow** , **Eigenschaft**, **einschränken**, **Selectany**, **Thread**, und **Uuid**Speicherklassen-Attribute sind Eigenschaften nur der Deklaration des Objekts oder der Funktion, die sie angewendet werden. Die **Thread** Attribut wirkt sich auf Daten und nur für die Objekte. Die **naked** und **Spectre** Attribute beeinflussen nur Funktionen. Die **Dllimport** und **Dllexport** Attribute beeinflussen, Funktionen, Daten und Objekte. Die **Eigenschaft**, **Selectany**, und **Uuid** Attribute beeinflussen COM-Objekte.

Für die Kompatibilität mit früheren Versionen **_declspec** ist ein Synonym für **__declspec** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) ist angegeben.

Die **__declspec** Schlüsselwörter sollten am Anfang einer einfachen Deklaration platziert werden. Der Compiler ignoriert ohne Warnung alle **__declspec** Schlüsselwörter platziert nach * oder & und vor dem Variablenbezeichner in einer Deklaration.

Ein **__declspec** Attribut am Anfang einer benutzerdefinierten Typdeklaration angegeben, die auf die Variable dieses Typs angewendet wird. Zum Beispiel:

```cpp
__declspec(dllimport) class X {} varX;
```

In diesem Fall wird das Attribut auf `varX` angewendet. Ein **__declspec** Attribut platziert werden, nachdem die **Klasse** oder **Struktur** -Schlüsselwort gilt für den benutzerdefinierten Typ. Zum Beispiel:

```cpp
class __declspec(dllimport) X {};
```

In diesem Fall wird das Attribut auf `X` angewendet.

Die allgemeine Richtlinie für die Verwendung der **__declspec** -Attributs für einfache Deklarationen lautet wie folgt:

*decl-specifier-seq* *init-declarator-list*;

Die *Decl-Specifier-Seq* enthalten soll, unter anderem einen Basistyp (z. B. **Int**, **"float"**, **Typedef**, oder einen Klassennamen), Speicherklasse (z. B. **statische**, **"extern"**), oder die **__declspec** Erweiterung. Die *Init-Declarator-List* enthalten soll, unter anderem den zeigerteil von Deklarationen. Zum Beispiel:

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

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[C-Speicherklassenattribute (erweitert)](../c-language/c-extended-storage-class-attributes.md)