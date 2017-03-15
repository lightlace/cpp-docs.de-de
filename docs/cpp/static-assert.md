---
title: "static_assert | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "C2338"
  - "static_assert_cpp"
  - "static_assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assertionen [C++], static_assert"
  - "C++-Schlüsselwörter, static_assert"
  - "C2338"
  - "static_assert"
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# static_assert
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Überprüft eine Softwareassertion zur Kompilierzeit.  Wenn der angegebene konstante Ausdruck `false` ist, zeigt der Compiler die angegebene Meldung an, und bei der Kompilierung tritt der Fehler C2338 auf; andernfalls hat die Deklaration keine Auswirkungen.  
  
## Syntax  
  
```  
static_assert(   
    constant-expression,   
    string-literal   
);  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`constant-expression`|Ein ganzzahliger konstanter Ausdruck, der in einen booleschen Wert konvertiert werden kann.<br /><br /> Wenn der ausgewertete Ausdruck 0 \(false\) ist, wird der `string-literal`\-Parameter angezeigt, und bei der Kompilierung tritt ein Fehler auf.  Wenn der Ausdruck nicht 0 \(true\) ist, hat die `static_assert`\-Deklaration keine Auswirkungen.|  
|`string-literal`|Eine Meldung, die angezeigt wird, wenn der `constant-expression`\-Parameter 0 \(null\) ist.  Die Meldung ist eine Zeichenfolge mit Zeichen im [Basiszeichensatz](../c-language/ascii-character-set.md) des Compilers, d. h. es sind keine [Multibyte\- oder Breitzeichen](../c-language/multibyte-and-wide-characters.md).|  
  
## Hinweise  
 Der `constant-expression`\-Parameter einer `static_assert`\-Deklaration stellt eine *Softwareassertion* dar.  Eine Softwareassertion gibt eine Bedingung an, die an einer bestimmten Stelle im Programm "true" sein muss.  Wenn die Bedingung "true" ist, hat die `static_assert`\-Deklaration keine Auswirkungen.  Wenn die Bedingung "false" ist, tritt bei der Assertion ein Fehler auf, der Compiler zeigt die Nachricht im `string-literal`\-Parameter an, und bei der Kompilierung tritt ein Fehler auf.  
  
 Die `static_assert`\-Deklaration testet eine Softwareassertion zur Kompilierzeit.  Im Gegensatz dazu testet das [assert\-Makro, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\-Makro eine Softwareassertion zur Laufzeit und wirkt sich zur Laufzeit auf Speicherplatz und Zeit aus.  Die `static_assert`\-Deklaration ist zum Debuggen von Vorlagen besonders nützlich, da Vorlagenargumente im `constant-expression`\-Parameter aufgenommen werden können.  
  
 Der Compiler überprüft die `static_assert`\-Deklaration auf Syntaxfehler, wenn die Deklaration gefunden wird.  Der Compiler wertet den `constant-expression`\-Parameter sofort aus, wenn er nicht von einem Vorlagenparameter abhängt.  Andernfalls wertet der Compiler den `constant-expression`\-Parameter aus, wenn die Vorlage instanziiert wird.  Daher gibt der Compiler möglicherweise eine Diagnosemeldung aus: einmal, wenn die Deklaration gefunden wird, und noch einmal, wenn die Vorlage instanziiert wird.  
  
 Sie können das `static_assert`\-Schlüsselwort im Namespace\-, Klassen\- oder Blockbereich verwenden. \(Das `static_assert`\-Schlüsselwort ist technisch gesehen eine Deklaration, obwohl es keine neuen Namen in das Programm einführt, da es im Namespacebereich verwendet werden kann.\)  
  
## Beschreibung  
 Im folgenden Beispiel verfügt die `static_assert`\-Deklaration über einen Namespacebereich.  Da der Compiler die Größe des Typs `void *` kennt, wird der Ausdruck sofort ausgewertet.  
  
## Beispiel  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## Beschreibung  
 Im folgenden Beispiel verfügt die `static_assert`\-Deklaration über einen Klassenbereich.  `static_assert` überprüft, ob ein Vorlagenparameter ein *Plain Old Data* \(POD\)\-Typ ist.  Der Compiler überprüft die `static_assert`\-Deklaration, wenn sie deklariert wird, wertet den `constant-expression`\-Parameter jedoch nicht aus, bis die `basic_string`\-Klassenvorlage in `main()` instanziiert wird.  
  
## Beispiel  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(tr1::is_pod<CharT>::value,  
                  "Template argument CharT must be a POD type in class template basic_string");  
    // ...  
    };  
}  
struct NonPOD {  
    NonPOD(const NonPOD &) {}  
    virtual ~NonPOD() {}  
};  
int main()  
{  
    std::basic_string<char> bs;  
}  
```  
  
## Beschreibung  
 Im folgenden Beispiel verfügt die `static_assert`\-Deklaration über einen Blockbereich.  `static_assert` überprüft, ob die Größe der VMPage\-Struktur der Seitengröße des virtuellen Arbeitsspeichers des Systems entspricht.  
  
## Beispiel  
  
```  
#include <sys/param.h> // defines PAGESIZE  
class VMMClient {  
public:  
    struct VMPage { // ...   
           };  
    int check_pagesize() {  
    static_assert(sizeof(VMPage) == PAGESIZE,  
        "Struct VMPage must be the same size as a system virtual memory page.");  
    // ...  
    }  
// ...  
};  
```  
  
## Siehe auch  
 [Assertion und benutzerdefinierte Meldungen \(C\+\+\)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [\#error\-Direktive](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert\-Makro, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Vorlagen](../cpp/templates-cpp.md)   
 [ASCII\-Zeichensatz](../c-language/ascii-character-set.md)   
 [Deklarationen](../misc/declarations.md)