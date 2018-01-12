---
title: Static_assert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: static_assert_cpp
dev_langs: C++
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 660b91f4902e42d393509aa190172e53839b2621
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="staticassert"></a>static_assert
Überprüft eine Softwareassertion zur Kompilierzeit. Wenn der angegebene Konstante Ausdruck wird `false`, zeigt der Compiler die angegebene Nachricht aus, sofern vorhanden, und die Kompilierung schlägt fehl mit Fehler c2338 auf; andernfalls hat die Deklaration keine Auswirkungen.  
  
## <a name="syntax"></a>Syntax  
  
```   
static_assert( constant-expression, string-literal );  

**Visual Studio 2017 and later:**
static_assert( constant-expression ); 
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`constant-expression`|Ein ganzzahliger konstanter Ausdruck, der in einen booleschen Wert konvertiert werden kann.<br /><br /> Wenn der ausgewertete Ausdruck 0 (false) ist, wird der `string-literal`-Parameter angezeigt, und bei der Kompilierung tritt ein Fehler auf. Wenn der Ausdruck nicht 0 (true) ist, hat die `static_assert`-Deklaration keine Auswirkungen.|  
|`string-literal`|Eine Meldung, die angezeigt wird, wenn der `constant-expression`-Parameter 0 (null) ist. Die Nachricht ist eine Zeichenfolge von Zeichen in der [basieren Zeichensatz](../c-language/ascii-character-set.md) des Compilers; die, nicht [Multibyte-oder Breitzeichen](../c-language/multibyte-and-wide-characters.md).|  
  
## <a name="remarks"></a>Hinweise  
 Die `constant-expression` Parameter von einem `static_assert` Deklaration stellt eine *Softwareassertion*. Eine Softwareassertion gibt eine Bedingung an, die an einer bestimmten Stelle im Programm "true" sein muss. Wenn die Bedingung "true" ist, hat die `static_assert`-Deklaration keine Auswirkungen. Wenn die Bedingung "false" ist, tritt bei der Assertion ein Fehler auf, der Compiler zeigt die Nachricht im `string-literal`-Parameter an, und bei der Kompilierung tritt ein Fehler auf. In Visual Studio 2017 und höher ist der Zeichenfolgenliteral Parameter optional. 
  
 Die `static_assert`-Deklaration testet eine Softwareassertion zur Kompilierzeit. Im Gegensatz dazu die [assert-Makro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) Makro testet eine Softwareassertion zur Laufzeit und fallen Kosten an, zur Laufzeit Bereich bzw. die Zeit. Die `static_assert`-Deklaration ist zum Debuggen von Vorlagen besonders nützlich, da Vorlagenargumente im `constant-expression`-Parameter aufgenommen werden können.  
  
 Der Compiler überprüft die `static_assert`-Deklaration auf Syntaxfehler, wenn die Deklaration gefunden wird. Der Compiler wertet den `constant-expression`-Parameter sofort aus, wenn er nicht von einem Vorlagenparameter abhängt. Andernfalls wertet der Compiler den `constant-expression`-Parameter aus, wenn die Vorlage instanziiert wird. Daher gibt der Compiler möglicherweise eine Diagnosemeldung aus: einmal, wenn die Deklaration gefunden wird, und noch einmal, wenn die Vorlage instanziiert wird.  
  
 Sie können das `static_assert`-Schlüsselwort im Namespace-, Klassen- oder Blockbereich verwenden. (Das `static_assert`-Schlüsselwort ist technisch gesehen eine Deklaration, obwohl es keine neuen Namen in das Programm einführt, da es im Namespacebereich verwendet werden kann.)  
  
## <a name="description"></a>Beschreibung  
 Im folgenden Beispiel verfügt die `static_assert`-Deklaration über einen Namespacebereich. Da der Compiler die Größe des Typs `void *` kennt, wird der Ausdruck sofort ausgewertet.  
  
## <a name="example"></a>Beispiel  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## <a name="description"></a>Beschreibung  
 Im folgenden Beispiel verfügt die `static_assert`-Deklaration über einen Klassenbereich. Die `static_assert` überprüft, ob ein Template-Parameter ist ein *rein alte Daten* (POD)-Typ. Der Compiler überprüft die `static_assert`-Deklaration, wenn sie deklariert wird, wertet den `constant-expression`-Parameter jedoch nicht aus, bis die `basic_string`-Klassenvorlage in `main()` instanziiert wird.  
  
## <a name="example"></a>Beispiel  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(std::is_pod<CharT>::value,  
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
  
## <a name="description"></a>Beschreibung  
 Im folgenden Beispiel verfügt die `static_assert`-Deklaration über einen Blockbereich. `static_assert` überprüft, ob die Größe der VMPage-Struktur der Seitengröße des virtuellen Arbeitsspeichers des Systems entspricht.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Assertion und vom Benutzer bereitgestellte Meldungen (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [#error-Direktive (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Vorlagen](../cpp/templates-cpp.md)   
 [ASCII-Zeichensatz](../c-language/ascii-character-set.md)   
 [Deklarationen und Definitionen](declarations-and-definitions-cpp.md)