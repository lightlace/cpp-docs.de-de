---
title: "__declspec"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__declspec_cpp"
  - "__declspec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++]"
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# __declspec
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Die erweiterte Attributsyntax für die Angabe von Speicherklasseninformationen verwendet das `__declspec`\-Schlüsselwort, das angibt, dass eine Instanz eines angegebenen Typs mit einem der unten aufgelisteten Microsoft\-spezifischen Speicherklassenattribute gespeichert werden muss.  Andere Speicherklassenmodifizierer sind beispielsweise die Schlüsselwörter `static` und `extern`.  Allerdings sind diese Schlüsselwörter Teil der ANSI\-Spezifikation der Programmiersprachen C\- und C\+\+ und werden als solche nicht von der erweiterten Attributsyntax abgedeckt.  Die erweiterte Attributsyntax vereinfacht und standardisiert Microsoft\-spezifische Erweiterungen der Programmiersprachen C und C\+\+.  
  
## Grammatik  
 *decl\-specifier*:  
 `__declspec (`  *extended\-decl\-modifier\-seq*  `)`  
  
 *extended\-decl\-modifier\-seq*:  
 *extended\-decl\-modifier* opt  
  
 *extended\-decl\-modifier extended\-decl\-modifier\-seq*  
  
 *extended\-decl\-modifier*:  
 `align(` *\#* `)`  
  
 `allocate("` *segname* `")`  
  
 `appdomain`  
  
 `code_seg("` *segname* `")`  
  
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
  
 `property(`{`get=`*get\_func\_name*&#124;`,put=`*put\_func\_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("` *ComObjectGUID* `")`  
  
 Die Deklarationsmodifizierersequenz ist durch Leerzeichen getrennt.  Beispiele finden Sie in späteren Abschnitten.  
  
 Die erweiterte Attributgrammatik unterstützt die folgenden Microsoft\-spezifischen Speicherklassenattribute: [align](../cpp/align-cpp.md), [allocate](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code\_seg](../cpp/code-seg-declspec.md), [deprecated](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md), [process](../cpp/process.md), [restrict](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md) und [thread](../cpp/thread.md).  Sie unterstützt auch diese COM\-Objektattribute: [property](../cpp/property-cpp.md) und [uuid](../cpp/uuid-cpp.md).  
  
 Die Speicherklassenattribute `code_seg`, `dllexport`, `dllimport`, `naked`, `noalias`, `nothrow`, `property`, `restrict`, `selectany`, `thread` und `uuid` sind Eigenschaften nur der Deklaration des Objekts oder der Funktion, auf das bzw. die sie angewendet werden.  Das `thread`\-Attribut wirkt sich nur auf Daten und Objekte aus.  Das `naked`\-Attribut wirkt sich nur auf Funktionen aus.  Die Attribute `dllimport` und `dllexport` haben Auswirkung auf Funktionen, Daten und Objekte.  Die Attribute `property`, `selectany` und `uuid` beeinflussen COM\-Objekte.  
  
 Die `__declspec` Schlüsselwörter sollten am Anfang einer einfachen Deklaration platziert werden.  Der Compiler ignoriert ohne Warnung alle `__declspec`\-Schlüsselwörter, die nach \* oder & und vor dem Variablenbezeichner in einer Deklaration auftreten.  
  
 Ein `__declspec`\-Attribut, das am Anfang einer benutzerdefinierten Typdeklaration angegeben wird, wird auf die Variable dieses Typs angewendet.  Beispiel:  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 In diesem Fall wird das Attribut auf `varX` angewendet.  Ein `__declspec`\-Attribut, das nach dem `class`\- oder `struct`\-Schlüsselwort platziert wird, wird auf den benutzerdefinierten Typ angewendet.  Beispiel:  
  
```  
class __declspec(dllimport) X {};  
```  
  
 In diesem Fall wird das Attribut auf `X` angewendet.  
  
 Die allgemeine Richtlinie für die Verwendung des `__declspec`\-Attributs für einfache Deklarationen lautet wie folgt:  
  
```  
  
decl-specifier-seq declarator-list;  
```  
  
 *decl\-specifier\-seq* sollte unter anderem einen Basistyp enthalten \(z. B.  `int`, `float`, `typedef` oder einen Klassennamen\), eine Speicherklasse \(z. B.  `static`, `extern`\) oder die `__declspec`\-Erweiterung.  *init\-declarator\-list* sollte unter anderem den Zeigerteil von Deklarationen enthalten.  Beispiel:  
  
```  
__declspec(selectany) int * pi1 = 0;   //OK, selectany & int both part of decl-specifier  
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier  
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator  
```  
  
 Mit folgendem Code wird z. B. eine Ganzzahl\-TLS\-Variable deklariert und mit einem Wert initialisiert:  
  
```  
// Example of the __declspec keyword  
__declspec( thread ) int tls_i = 1;  
```  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [C\-Speicherklassenattribute \(erweitert\)](../c-language/c-extended-storage-class-attributes.md)