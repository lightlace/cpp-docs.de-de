---
title: "&lt; funktionale &gt;"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "<functional>"
  - "functional/std::<functional>"
  - "std.<functional>"
  - "std::<functional>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionselemente"
  - "functional-Header"
ms.assetid: 7dd463e8-a29f-49bc-aedd-8fa53b54bfbc
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "corob"
manager: "ghogen"
---
# &lt; funktionale &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert Standardbibliotheksfunktionen, mit deren Hilfe erstellen *Funktion Objekte*– auch als Funktionselemente bekannt – und die Sammelmappe. Ein Funktionsobjekt ist ein Objekt eines Typs, der `operator()` definiert. Ein Funktionsobjekt kann ein Funktionszeiger sein, aber in der Regel, wird das Objekt zum Speichern zusätzlicher Informationen verwendet, auf die während eines Funktionsaufrufs zugegriffen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <functional>  
```  
  
## <a name="remarks"></a>Hinweise  
 Algorithmen erfordern zwei Typen von Funktionsobjekten: unär und binär. Für unäre Funktionsobjekte ist ein Argument und für binäre Funktionsobjekte sind zwei Argumente erforderlich. Ein Funktionsobjekt und Funktionszeiger können einem Algorithmus als Prädikat übergeben werden, Funktionsobjekte sind allerdings auch anwendbar und erhöhen den Bereich, die Flexibilität und die Effizienz des STL. Wenn beispielsweise ein Wert, der benötigt wurde, an eine Funktion gebunden, bevor an einem Algorithmus, dann ein Funktionszeiger übergeben wurde, nicht verwendet werden kann. Funktionsadapter konvertieren Funktionszeiger in anwendbare Funktionsobjekte, die an einen Wert gebunden werden können. Der Header \< funktionale> enthält auch memberfunktionsadapter, die Member-Funktionen als anwendbare Funktionsobjekte aufgerufen werden können. Funktionen sind anwendbar, wenn sie über geschachtelte Typdeklarationen verfügen, die die Argument- und Rückgabetypen angeben. Der C++-Standard erfordert, dass diese Anwendbarkeit implementiert wird, indem alle Standardobjektklassen von den "unary_function"- oder "binary_function"-Basisklassen erben. Funktionsobjekte und Adapter ermöglichen STL bestehende Anwendungen zu aktualisieren und helfen bei der Integration von STL in die C++-Programmierumgebung.  
  
 Die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] -Implementierung der Funktionsobjekte in \< funktionale> enthält *transparente operatorfunktionselemente*, die spezialisierungen von standardfunktionsobjekten sind keine Vorlagenparameter akzeptieren, und für eine perfekte Weiterleitung der Funktionsargumente und perfekte Rückgabe des Ergebnisses. Diese Funktion ist Teil der Spezifikation des Normenentwurfs C++14. Für diese Vorlagenspezialisierungen müssen keine Argumenttypen angeben werden, wenn arithmetische, bitweise sowie Vergleichs- und Logikoperatorfunktionselemente aufgerufen werden. Sie können arithmetische, bitweise sowie Vergleichs- und Logikoperatoren für eigene Typen überladen oder für heterogene Typkombinationen und die transparenten Operatorfunktionselemente dann als Funktionsargumente verwenden. Z. B. Wenn Ihr Typ *MyType* implementiert `operator<`, können Sie aufrufen `sort(my_collection.begin(), my_collection.end(), less<>())` den Typ explizit angeben, statt `sort(my_collection.begin(), my_collection.end(), less<MyType>())`.  
  
## <a name="c11c14-implementation"></a>C++11/C++14-Implementierung  
 Die folgenden Funktionen werden in der Visual C++-Implementierung von C++11/C++14 hinzugefügt:  
  
-   Ein *Aufrufsignatur* ist der Name eines Rückgabetyps, gefolgt von einer durch Trennzeichen getrennte Liste mit in Klammern von NULL oder mehr Argumenttypen.  
  
-   Ein *aufrufbaren Typs* ist ein Zeiger auf die Funktion, ein Zeiger auf eine Memberfunktion, ein Zeiger auf Memberdaten oder ein Klassentyp, deren Objekte können direkt auf der linken Seite des einen Funktionsaufrufoperator angezeigt.  
  
-   Ein *aufrufbaren Objekts* ist ein Objekt eines aufrufbaren Typs.  
  
-   Ein *aufrufwrappertyp* ist ein Typ, der ein aufrufbares Objekt enthält und einen Aufrufvorgang, die auf dieses Objekt weiterleitet unterstützt.  
  
-   Ein *Aufrufwrapper* ist ein Objekt eines aufrufwrappertyps.  
  
-   Ein *Zielobjekt* das aufrufbare Objekt ein Aufruf Wrapperobjekt reserviert ist.  
  
 Die Pseudofunktion `INVOKE(f, t1, t2, ..., tN)` bedeutet eine der folgenden Aktionen:  
  
- `(t1.*f)(t2, ..., tN)`, wenn `f` ein Zeiger auf eine Memberfunktion der Klasse `T` und `t1` ist, ist ein Objekt vom Typ `T` oder ein Verweis auf ein Objekt vom Typ `T` oder ein Verweis auf ein Objekt eines Typs, der von `T` abgeleitet wird.  
  
- `((*t1).*f)(t2, ..., tN)`, wenn `f` ein Zeiger auf eine Memberfunktion der Klasse `T` ist, und `t1` keinem der Typen entspricht, die im vorherigen Element beschrieben werden.  
  
- `t1.*f`, wenn N == 1 und `f` ein Zeiger auf Memberdaten einer Klasse `T` und `t1` ist, ist ein Objekt vom Typ `T` oder ein Verweis auf ein Objekt vom Typ `T` oder ein Verweis auf ein Objekt eines Typs, der von `T` abgeleitet wird.  
  
- `(*t1).*f`, wenn N == 1 und `f` ein Zeiger auf Memberdaten einer Klasse `T` ist, und `t1` keinem der Typen entspricht, die im vorherigen Element beschrieben werden.  
  
- In allen anderen Fällen `f(t1, t2, ..., tN)`.  
  
 Die Pseudofunktion `INVOKE(f, t1, t2, ..., tN, R)` bedeutet, dass `INVOKE(f, t1, t2, ..., tN)` implizit in `R` konvertiert wird.  
  
 Wenn ein Aufrufwrapper weist einen *schwache Ergebnistyp*, den Typ des Membertyps `result_type` basiert auf den Typ `T` des Zielobjekts des Wrappers, wie folgt:  
  
-   Wenn `T` ein Zeiger auf eine Funktion ist, ist `result_type` ein Synonym für den Rückgabetyp von `T`.  
  
-   Wenn `T` ein Zeiger auf eine Memberfunktion ist, ist `result_type` ein Synonym für den Rückgabetyp von `T`.  
  
-   Wenn `T` ein Klassentyp ist, der einen Membertyp `result_type` aufweist, dann ist `result_type` ein Synonym für `T::result_type`.  
  
-   Andernfalls gibt es kein Member `result_type`.  
  
 Jeder Aufrufwrapper weist einen Verschiebekonstruktor und einen Kopierkonstruktor auf. Ein *einfachen Aufrufwrapper* ist ein Aufrufwrapper, der einen Zuweisungsoperator verfügt Operator und, deren Kopierkonstruktor, verschiebekonstruktor und Zuweisungsoperator keine Ausnahmen auslösen. Ein *weiterleitungsaufrufwrapper* ist ein Aufrufwrapper, der mit einer beliebigen Argumentliste aufgerufen werden kann und die Argumente den umschlossenen aufrufbaren Objekt als Verweise liefert. Alle rvalue-Argumente werden als rvalue-Verweise geliefert, und lvalue-Argumente werden als lvalue-Verweise geliefert.  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[bad_function_call](../standard-library/bad-function-call-class.md)|Eine Klasse, die einer Ausnahme ausgelöst werden, um anzugeben, dass einen Aufruf von beschreibt `operator()` auf eine [Funktion](../standard-library/function-class.md) Objekt ist fehlgeschlagen, da das Objekt leer war.|  
|[binary_negate](../standard-library/binary-negate-class.md)|Eine Klasse, mit der eine Memberfunktion bereitgestellt wird, die den Rückgabewert einer angegebenen binären Funktion negiert.|  
|[binder1st](../standard-library/binder1st-class.md)|Eine Vorlagenklasse, mit der ein Konstruktor bereitgestellt wird, der ein binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert, indem das erste Argument der binären Funktion an einen angegebenen Wert gebunden wird.|  
|[binder2nd](../standard-library/binder2nd-class.md)|Eine Vorlagenklasse, mit der ein Konstruktor bereitgestellt wird, der ein binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert, indem das zweite Argument der binären Funktion an einen angegebenen Wert gebunden wird.|  
|[const_mem_fun_ref_t](../standard-library/const-mem-fun-ref-t-class.md)|Eine Adapterklasse, die einer const-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird.|  
|[const_mem_fun_t](../standard-library/const-mem-fun-t-class.md)|Eine Adapterklasse, die einer const-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Zeigerargument initialisiert wird.|  
|[const_mem_fun1_ref_t](../standard-library/const-mem-fun1-ref-t-class.md)|Eine Adapterklasse, die einer const-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird.|  
|[const_mem_fun1_t](../standard-library/const-mem-fun1-t-class.md)|Eine Adapterklasse, die einer const-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Zeigerargument initialisiert wird.|  
|[Funktion](../standard-library/function-class.md)|Eine Klasse, die ein aufrufbares Objekt umschließt.|  
|[Hash](hash%20Class.md)|Eine Klasse, die einen Hashcode für einen Wert berechnet.|  
|[is_bind_expression](../standard-library/is-bind-expression-class.md)|Eine Klasse, die überprüft, ob ein bestimmter Typ generiert wird, indem `bind` aufgerufen wird.|  
|[is_placeholder](../standard-library/is-placeholder-class.md)|Eine Klasse, die überprüft, ob ein bestimmter Typ ein Platzhalter ist.|  
|[mem_fun_ref_t](../standard-library/mem-fun-ref-t-class.md)|Eine Adapterklasse, die ermöglicht eine **Non_const** Memberfunktion, die keine Argumente als wenn Sie mit einem Verweisargument Initialisiert ein unäres Funktionsobjekt aufgerufen zu werden.|  
|[mem_fun_t](../standard-library/mem-fun-t-class.md)|Eine Adapterklasse, die ermöglicht eine **Non_const** Memberfunktion, die keine Argumente als wenn Sie mit einem Zeigerargument Initialisiert ein unäres Funktionsobjekt aufgerufen zu werden.|  
|[mem_fun1_ref_t](../standard-library/mem-fun1-ref-t-class.md)|Eine Adapterklasse, die ermöglicht eine **Non_const** Memberfunktion, die ein einzelnes Argument als wenn Sie mit einem Verweisargument initialisiert in ein binäres Funktionsobjekt aufgerufen zu werden.|  
|[mem_fun1_t](../standard-library/mem-fun1-t-class.md)|Eine Adapterklasse, die ermöglicht eine **Non_const** Memberfunktion, die ein einzelnes Argument als wenn Sie mit einem Zeigerargument initialisiert in ein binäres Funktionsobjekt aufgerufen zu werden.|  
|[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md)|Konvertiert einen binären Funktionszeiger in eine anwendbare binäre Funktion.|  
|[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)|Konvertiert einen unären Funktionszeiger in eine anwendbare unäre Funktion.|  
|[reference_wrapper](../standard-library/reference-wrapper-class.md)|Eine Klasse, die einen Verweis umschließt.|  
|[result_of](../standard-library/result-of-class2.md)|Eine Struktur, die den Rückgabetyp eines umschlossenen aufrufbaren Objekts enthält.|  
|[unary_negate](../standard-library/unary-negate-class.md)|Eine Klasse, mit der eine Memberfunktion bereitgestellt wird, die den Rückgabewert einer angegebenen unären Funktion negiert.|  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[Binden](../Topic/%3Cfunctional%3E%20functions.md#bind_function)|Bindet Argumente an ein aufrufbares Objekt.|  
|[bind1st](../Topic/%3Cfunctional%3E%20functions.md#bind1st_function)|Eine Hilfevorlagenfunktion, mit der ein Adapter erstellt wird, um ein binäres Funktionsobjekt in ein unäres Funktionsobjekt zu konvertieren, indem das erste Argument der binären Funktion an einen angegebenen Wert gebunden wird.|  
|[bind2nd](../Topic/%3Cfunctional%3E%20functions.md#bind2nd_function)|Eine Hilfevorlagenfunktion, mit der ein Adapter erstellt wird, um ein binäres Funktionsobjekt in ein unäres Funktionsobjekt zu konvertieren, indem das zweite Argument der binären Funktion an einen angegebenen Wert gebunden wird.|  
|[BIT_AND](../Topic/%3Cfunctional%3E%20functions.md#bit_and_function)|Gibt das bitweise logische UND (binärer Operator&) der zwei Parameter zurück.|  
|[bit_not](../Topic/%3Cfunctional%3E%20functions.md#bit_not_function)|Gibt das bitweise logische Komplement (operator~) des Parameters zurück.|  
|[BIT_OR](../Topic/%3Cfunctional%3E%20functions.md#bit_or_function)|Gibt das bitweise logische OR (Operator &#124;) der zwei Parameter.|  
|[BIT_XOR](../Topic/%3Cfunctional%3E%20functions.md#bit_xor_function)|Gibt das bitweise logische XOR (Operator^) der zwei Parameter zurück.|  
|[cref](../Topic/%3Cfunctional%3E%20functions.md#cref_function)|Erstellt ein konstantes `reference_wrapper`-Element aus einem Argument.|  
|[mem_fn](../Topic/%3Cfunctional%3E%20functions.md#mem_fn_function)|Generiert einen einfachen Aufrufwrapper.|  
|[mem_fun](../Topic/%3Cfunctional%3E%20functions.md#mem_fun_function)|Hilfevorlagenfunktionen, die verwendet werden, um Funktionsobjektadapter für Memberfunktionen zu konstruieren, wenn Sie mit Zeigerargumenten initialisiert werden.|  
|[mem_fun_ref](../Topic/%3Cfunctional%3E%20functions.md#mem_fun_ref_function)|Eine Hilfevorlagenfunktion, die verwendet wird, um Funktionsobjektadapter für Memberfunktionen zu konstruieren, wenn Sie mit Verweisargumenten initialisiert wird.|  
|[not1](../Topic/%3Cfunctional%3E%20functions.md#not1_function)|Gibt das Komplement eines unären Prädikats zurück.|  
|[not2](../Topic/%3Cfunctional%3E%20functions.md#not2_function)|Gibt das Komplement eines binären Prädikats zurück.|  
|[ptr_fun](../Topic/%3Cfunctional%3E%20functions.md#ptr_fun_function)|Eine Hilfevorlagenfunktion, die verwendet wird, um die jeweiligen unären und binären Funktionszeiger in die unären und binären anwendbaren Funktionen zu konvertieren.|  
|[ref](../Topic/%3Cfunctional%3E%20functions.md#ref_function)|Konstruiert ein `reference_wrapper` aus einem Argument.|  
|[Swap](../Topic/%3Cfunctional%3E%20functions.md#swap_function)|Tauscht zwei `function`-Objekte.|  
  
### <a name="structs"></a>Strukturen  
  
|||  
|-|-|  
|[binary_function](../standard-library/binary-function-struct.md)|Eine leere Basisklasse, mit der Typen definiert werden, die möglicherweise von einer abgeleiteten Klasse geerbt wird, die ein binäres Funktionsobjekt bereitstellt.|  
|[dividiert](../standard-library/divides-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation der Unterteilung für Elemente eines angegebenen Werttyps ausführt.|  
|[equal_to](../standard-library/equal-to-struct.md)|Ein binäres Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs gleich einem anderen Wert dieses Typs ist.|  
|[größer](../standard-library/greater-struct.md)|Ein binärer Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs größer als ein anderer Wert dieses Typs ist.|  
|[greater_equal](../standard-library/greater-equal-struct.md)|Ein binärer Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs größer oder gleich einem anderen Wert dieses Typs ist.|  
|[weniger](../standard-library/less-struct.md)|Ein binäres Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs kleiner oder gleich einem anderen Wert dieses Typs ist.|  
|[less_equal](../standard-library/less-equal-struct.md)|Ein binäres Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs kleiner als ein anderer Wert dieses Typs ist.|  
|[logical_and](../standard-library/logical-and-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, mit dem die logische Operation der Konjunktion für Elemente eines angegebenen Werttyps ausgeführt und die Wahrheit oder Falschheit des Ergebnisses getestet wird.|  
|[logical_not](../standard-library/logical-not-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, mit dem die logische Operation der Negation für Elemente eines angegebenen Werttyps ausgeführt und die Wahrheit oder Falschheit des Ergebnisses getestet wird.|  
|[logical_or](../standard-library/logical-or-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, mit dem die logische Operation der Disjunktion für Elemente eines angegebenen Werttyps ausgeführt und die Wahrheit oder Falschheit des Ergebnisses getestet wird.|  
|[minus](../standard-library/minus-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation der Subtraktion für Elemente eines angegebenen Werttyps ausführt.|  
|[Modulo](../standard-library/modulus-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation des Modulus für Elemente eines angegebenen Werttyps ausführt.|  
|[multipliziert](../standard-library/multiplies-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation der Multiplikation für Elemente eines angegebenen Werttyps ausführt.|  
|[Negate-](../standard-library/negate-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, mit dem der negative Bereich eines Elementwerts zurückgegeben wird.|  
|[Not_Equal_To](../standard-library/not-equal-to-struct.md)|Ein binäres Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs ungleich einem anderen Wert dieses Typs ist.|  
|[Plus](../standard-library/plus-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation der Addition für Elemente eines angegebenen Werttyps ausführt.|  
|[unary_function](../standard-library/unary-function-struct.md)|Eine leere Basisklasse, mit der Typen definiert werden, die möglicherweise von einer abgeleiteten Klasse geerbt wird, die ein unäres Funktionsobjekt bereitstellt.|  
  
### <a name="objects"></a>erzwingen  
  
|||  
|-|-|  
|[_1.._M](../standard-library/1-object.md)|Platzhalter für austauschbare Argumente.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator ==](../Topic/%3Cfunctional%3E%20operators.md#operator_eq_eq)|Lässt den Gleichheitsvergleich von aufrufbaren Objekten nicht zu.|  
|[Operator! =](../Topic/%3Cfunctional%3E%20operators.md#operator_neq)|Lässt den Ungleichheitsvergleich von aufrufbaren Objekten nicht zu.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

