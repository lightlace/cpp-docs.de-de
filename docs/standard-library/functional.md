---
title: '&lt;functional&gt;'
ms.date: 02/21/2019
f1_keywords:
- <functional>
- functional/std::<functional>
- std::<functional>
helpviewer_keywords:
- functors
- functional header
ms.assetid: 7dd463e8-a29f-49bc-aedd-8fa53b54bfbc
ms.openlocfilehash: 7a72941c7b8c351f7b4fb8fa0e40afb809ea7cbe
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243760"
---
# <a name="ltfunctionalgt"></a>&lt;functional&gt;

Definiert C++-Standardbibliothek-Funktionen, mit deren Hilfe erstellen *Funktionsobjekte*, auch bekannt als *Funktionselemente*, und ihre Binder. Ein Funktionsobjekt ist ein Objekt eines Typs, der `operator()` definiert. Ein Funktionsobjekt kann ein Funktionszeiger sein, aber in der Regel, wird das Objekt zum Speichern zusätzlicher Informationen verwendet, auf die während eines Funktionsaufrufs zugegriffen werden kann.

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="remarks"></a>Hinweise

Algorithmen erfordern zwei Typen von Funktionsobjekten: *unäre* und *binäre*. Für unäre Funktionsobjekte ist ein Argument und für binäre Funktionsobjekte sind zwei Argumente erforderlich. Ein Funktionsobjekt und Funktionszeiger können einem Algorithmus als Prädikat übergeben werden; Funktionsobjekte sind allerdings auch anwendbar und erweitern den Bereich, die Flexibilität und die Effizienz der C++-Standardbibliothek. Wenn beispielsweise ein Wert, der benötigt wurde, an eine Funktion gebunden, bevor an einem Algorithmus, dann ein Funktionszeiger übergeben wurde, nicht verwendet werden kann. Funktionsadapter konvertieren Funktionszeiger in anwendbare Funktionsobjekte, die an einen Wert gebunden werden können. Im Header \<functional> sind auch Memberfunktionsadapter enthalten, die es ermöglichen, dass Memberfunktionen als anwendbare Funktionsobjekte aufgerufen werden können. Funktionen sind anwendbar, wenn sie über geschachtelte Typdeklarationen verfügen, die die Argument- und Rückgabetypen angeben. Funktionsobjekte und Adapter ermöglichen es der C++-Standardbibliothek, bestehende Anwendungen zu aktualisieren, und helfen bei der Integration der Bibliothek in die C++-Programmierumgebung.

Die Implementierung der Funktionsobjekte in \<funktionale > enthält *transparente operatorfunktionselemente*. die spezialisierungen von standard Funktionsobjekte sind keine Vorlagenparameter akzeptieren und für eine perfekte Weiterleitung der Funktionsargumente und eine perfekte Rückgabe der Ergebnisse. Für diese Vorlagenspezialisierungen müssen keine Argumenttypen angeben werden, wenn arithmetische, bitweise sowie Vergleichs- und Logikoperatorfunktionselemente aufgerufen werden. Sie können arithmetische, bitweise sowie Vergleichs- und Logikoperatoren für eigene Typen überladen oder für heterogene Typkombinationen und die transparenten Operatorfunktionselemente dann als Funktionsargumente verwenden. Wenn Ihr Typ *MyType* z.B. `operator<` implementiert, können Sie `sort(my_collection.begin(), my_collection.end(), less<>())` aufrufen, anstatt explizit den Typ `sort(my_collection.begin(), my_collection.end(), less<MyType>())` anzugeben.

Die folgenden Features sind in C ++ 11, C ++ 14 und C ++ 17 hinzugefügt:

- Eine *Aufrufsignatur* ist der Name eines Rückgabetyps, gefolgt von einer durch Trennzeichen getrennten Liste in Klammern von keinem oder mehr Argumenttypen.

- Ein *aufrufbarer Typ* ist entweder ein Zeiger auf eine Funktion, ein Zeiger auf eine Memberfunktion, ein Zeiger auf Memberdaten oder ein class-Typ, dessen Objekte unmittelbar links neben einem Funktionsaufrufoperators angezeigt werden können.

- Ein *aufrufbares Objekt* ist das Objekt eines aufrufbaren Typs.

- Ein *Aufrufwrappertyp* ist ein Typ, der ein aufrufbares Objekt enthält und einen Aufrufvorgang unterstützt, der dieses Objekt weiterleitet.

- Ein *Aufrufwrapper* ist das Objekt eines Aufrufwrappertyps.

- Ein *Zielobjekt* ist das aufrufbare Objekt, das in einem Aufrufwrapperobjekt enthalten ist.

Die Pseudofunktion `INVOKE(f, t1, t2, ..., tN)` bedeutet eine der folgenden Aktionen:

- `(t1.*f)(t2, ..., tN)`, wenn `f` ein Zeiger auf eine Memberfunktion der Klasse `T` und `t1` ist, ist ein Objekt vom Typ `T` oder ein Verweis auf ein Objekt vom Typ `T` oder ein Verweis auf ein Objekt eines Typs, der von `T` abgeleitet wird.

- `((*t1).*f)(t2, ..., tN)`, wenn `f` ein Zeiger auf eine Memberfunktion der Klasse `T` ist, und `t1` keinem der Typen entspricht, die im vorherigen Element beschrieben werden.

- `t1.*f`, wenn N == 1 und `f` ein Zeiger auf Memberdaten einer Klasse `T` und `t1` ist, ist ein Objekt vom Typ `T` oder ein Verweis auf ein Objekt vom Typ `T` oder ein Verweis auf ein Objekt eines Typs, der von `T` abgeleitet wird.

- `(*t1).*f`, wenn N == 1 und `f` ein Zeiger auf Memberdaten einer Klasse `T` ist, und `t1` keinem der Typen entspricht, die im vorherigen Element beschrieben werden.

- In allen anderen Fällen `f(t1, t2, ..., tN)`.

Die Pseudofunktion `INVOKE(f, t1, t2, ..., tN, R)` bedeutet, dass `INVOKE(f, t1, t2, ..., tN)` implizit in `R` konvertiert wird.

Wenn ein Aufrufwrapper über einen *schwachen Ergebnistyp* verfügt, basiert der Typ des Membertyps `result_type` wie folgt auf dem Typ `T` des Zielobjekts des Wrappers:

- Wenn `T` ein Zeiger auf eine Funktion ist, ist `result_type` ein Synonym für den Rückgabetyp von `T`.

- Wenn `T` ein Zeiger auf eine Memberfunktion ist, ist `result_type` ein Synonym für den Rückgabetyp von `T`.

- Wenn `T` ein Klassentyp ist, der einen Membertyp `result_type` aufweist, dann ist `result_type` ein Synonym für `T::result_type`.

- Andernfalls gibt es kein Member `result_type`.

Jeder Aufrufwrapper weist einen Verschiebekonstruktor und einen Kopierkonstruktor auf. Ein *einfacher Aufrufwrapper* ist ein Aufrufwrapper, der über einen Zuweisungsoperator verfügt und dessen Kopierkonstruktor, Verschiebekonstruktor und Zuweisungsoperator keine Ausnahmen auslösen. Ein *Aufrufweiterleitungwrapper* ist ein Aufrufwrapper, der mithilfe einer beliebigen Argumentliste aufgerufen werden kann, und der die Argumente den umschlossenen aufrufbaren Objekt als Verweise liefert. Alle rvalue-Argumente werden als rvalue-Verweise geliefert, und lvalue-Argumente werden als lvalue-Verweise geliefert.

## <a name="members"></a>Member

### <a name="classes"></a>Klassen

|||
|-|-|
|[bad_function_call](../standard-library/bad-function-call-class.md)|Eine Klasse, mit der eine Ausnahme beschrieben wird, die ausgelöst wird, um anzugeben, dass ein Aufruf von `operator()` an ein [function](../standard-library/function-class.md)-Objekt einen Fehler verursacht hat, da das Objekt leer war.|
|[binary_negate](../standard-library/binary-negate-class.md)|Eine Klasse, mit der eine Memberfunktion bereitgestellt wird, die den Rückgabewert einer angegebenen binären Funktion negiert.<br/> (In C ++ 17 veraltet.) |
|[binder1st](../standard-library/binder1st-class.md)|Eine Vorlagenklasse, mit der ein Konstruktor bereitgestellt wird, der ein binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert, indem das erste Argument der binären Funktion an einen angegebenen Wert gebunden wird.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[binder2nd](../standard-library/binder2nd-class.md)|Eine Vorlagenklasse, mit der ein Konstruktor bereitgestellt wird, der ein binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert, indem das zweite Argument der binären Funktion an einen angegebenen Wert gebunden wird.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[boyer_moore_horspool_searcher](../standard-library/boyer-moore-horspool-searcher-class.md)||
|[boyer_moore_searcher](../standard-library/boyer-moore-searcher-class.md)||
|[const_mem_fun_ref_t](../standard-library/const-mem-fun-ref-t-class.md)|Eine Adapterklasse, die einer const-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[const_mem_fun_t](../standard-library/const-mem-fun-t-class.md)|Eine Adapterklasse, die einer const-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Zeigerargument initialisiert wird.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[const_mem_fun1_ref_t](../standard-library/const-mem-fun1-ref-t-class.md)|Eine Adapterklasse, die einer const-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[const_mem_fun1_t](../standard-library/const-mem-fun1-t-class.md)|Eine Adapterklasse, die einer const-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Zeigerargument initialisiert wird.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[default_searcher](../standard-library/default-searcher-class.md)||
|[function](../standard-library/function-class.md)|Eine Klasse, die ein aufrufbares Objekt umschließt.|
|[hash](../standard-library/hash-class.md)|Eine Klasse, die einen Hashcode für einen Wert berechnet.|
|[is_bind_expression](../standard-library/is-bind-expression-class.md)|Eine Klasse, die überprüft, ob ein bestimmter Typ generiert wird, indem `bind` aufgerufen wird.|
|[is_placeholder](../standard-library/is-placeholder-class.md)|Eine Klasse, die überprüft, ob ein bestimmter Typ ein Platzhalter ist.|
|[mem_fun_ref_t](../standard-library/mem-fun-ref-t-class.md)|Eine Adapterklasse, die ermöglicht eine `non_const` Memberfunktion, die keine Argumente als wenn Sie mit einem Verweisargument Initialisiert ein unäres Funktionsobjekt aufgerufen zu werden.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[mem_fun_t](../standard-library/mem-fun-t-class.md)|Eine Adapterklasse, die ermöglicht eine `non_const` Memberfunktion, die keine Argumente als wenn Sie mit einem Zeigerargument Initialisiert ein unäres Funktionsobjekt aufgerufen zu werden.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[mem_fun1_ref_t](../standard-library/mem-fun1-ref-t-class.md)|Eine Adapterklasse, die ermöglicht eine `non_const` Memberfunktion, die ein einzelnes Argument als ein binäres Funktionsobjekt, wenn Sie mit einem Verweisargument initialisiert aufgerufen werden.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[mem_fun1_t](../standard-library/mem-fun1-t-class.md)|Eine Adapterklasse, die ermöglicht eine `non_const` Memberfunktion, die ein einzelnes Argument als ein binäres Funktionsobjekt, wenn Sie mit einem Zeigerargument initialisiert aufgerufen werden.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md)|Konvertiert einen binären Funktionszeiger in eine anwendbare binäre Funktion.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)|Konvertiert einen unären Funktionszeiger in eine anwendbare unäre Funktion.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[reference_wrapper](../standard-library/reference-wrapper-class.md)|Eine Klasse, die einen Verweis umschließt.|
|[unary_negate](../standard-library/unary-negate-class.md)|Eine Klasse, mit der eine Memberfunktion bereitgestellt wird, die den Rückgabewert einer angegebenen unären Funktion negiert.<br/> (In C ++ 17 veraltet.)  |

### <a name="functions"></a>Funktionen

|||
|-|-|
|[bind](../standard-library/functional-functions.md#bind)|Bindet Argumente an ein aufrufbares Objekt.|
|[bind1st](../standard-library/functional-functions.md#bind1st)|Eine Hilfevorlagenfunktion, mit der ein Adapter erstellt wird, um ein binäres Funktionsobjekt in ein unäres Funktionsobjekt zu konvertieren, indem das erste Argument der binären Funktion an einen angegebenen Wert gebunden wird.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[bind2nd](../standard-library/functional-functions.md#bind2nd)|Eine Hilfevorlagenfunktion, mit der ein Adapter erstellt wird, um ein binäres Funktionsobjekt in ein unäres Funktionsobjekt zu konvertieren, indem das zweite Argument der binären Funktion an einen angegebenen Wert gebunden wird.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[bit_and](../standard-library/functional-functions.md#bit_and)|Gibt das bitweise logische UND (binärer Operator&) der zwei Parameter zurück.|
|[bit_not](../standard-library/functional-functions.md#bit_not)|Gibt das bitweise logische Komplement (operator~) des Parameters zurück.<br/> (In C ++ 14 hinzugefügt.) |
|[bit_or](../standard-library/functional-functions.md#bit_or)|Gibt das bitweise logische OR (operator&#124;) der zwei Parameter zurück.|
|[bit_xor](../standard-library/functional-functions.md#bit_xor)|Gibt das bitweise logische XOR (Operator^) der zwei Parameter zurück.|
|[cref](../standard-library/functional-functions.md#cref)|Erstellt ein konstantes `reference_wrapper`-Element aus einem Argument.|
|[invoke](../standard-library/functional-functions.md#invoke)||
|[mem_fn](../standard-library/functional-functions.md#mem_fn)|Generiert einen einfachen Aufrufwrapper.|
|[mem_fun](../standard-library/functional-functions.md#mem_fun)|Hilfevorlagenfunktionen, die verwendet werden, um Funktionsobjektadapter für Memberfunktionen zu konstruieren, wenn Sie mit Zeigerargumenten initialisiert werden.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)|Eine Hilfevorlagenfunktion, die verwendet wird, um Funktionsobjektadapter für Memberfunktionen zu konstruieren, wenn Sie mit Verweisargumenten initialisiert wird.|
|[not1](../standard-library/functional-functions.md#not1)|Gibt das Komplement eines unären Prädikats zurück.<br/> (In C ++ 17 veraltet.) |
|[not2](../standard-library/functional-functions.md#not2)|Gibt das Komplement eines binären Prädikats zurück.<br/> (In C ++ 17 veraltet.) |
|[not_fn](../standard-library/functional-functions.md#not_fn)|Gibt das Komplement des Ergebnisses der Function-Objekt zurück.<br/> (In C ++ 17-hinzugefügt.) |
|[ptr_fun](../standard-library/functional-functions.md#ptr_fun)|Eine Hilfevorlagenfunktion, die verwendet wird, um die jeweiligen unären und binären Funktionszeiger in die unären und binären anwendbaren Funktionen zu konvertieren.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[ref](../standard-library/functional-functions.md#ref)|Konstruiert ein `reference_wrapper` aus einem Argument.|
|[swap](../standard-library/functional-functions.md#swap)|Tauscht zwei `function`-Objekte.|

### <a name="structs"></a>Strukturen

|||
|-|-|
|[binary_function](../standard-library/binary-function-struct.md)|Eine leere Basisklasse, mit der Typen definiert werden, die möglicherweise von einer abgeleiteten Klasse geerbt wird, die ein binäres Funktionsobjekt bereitstellt.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |
|[divides](../standard-library/divides-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation der Unterteilung für Elemente eines angegebenen Werttyps ausführt.|
|[equal_to](../standard-library/equal-to-struct.md)|Ein binäres Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs gleich einem anderen Wert dieses Typs ist.|
|[greater](../standard-library/greater-struct.md)|Ein binärer Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs größer als ein anderer Wert dieses Typs ist.|
|[greater_equal](../standard-library/greater-equal-struct.md)|Ein binärer Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs größer oder gleich einem anderen Wert dieses Typs ist.|
|[less](../standard-library/less-struct.md)|Ein binäres Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs kleiner oder gleich einem anderen Wert dieses Typs ist.|
|[less_equal](../standard-library/less-equal-struct.md)|Ein binäres Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs kleiner als ein anderer Wert dieses Typs ist.|
|[logical_and](../standard-library/logical-and-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, mit dem die logische Operation der Konjunktion für Elemente eines angegebenen Werttyps ausgeführt und die Wahrheit oder Falschheit des Ergebnisses getestet wird.|
|[logical_not](../standard-library/logical-not-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, mit dem die logische Operation der Negation für Elemente eines angegebenen Werttyps ausgeführt und die Wahrheit oder Falschheit des Ergebnisses getestet wird.|
|[logical_or](../standard-library/logical-or-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, mit dem die logische Operation der Disjunktion für Elemente eines angegebenen Werttyps ausgeführt und die Wahrheit oder Falschheit des Ergebnisses getestet wird.|
|[minus](../standard-library/minus-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation der Subtraktion für Elemente eines angegebenen Werttyps ausführt.|
|[modulus](../standard-library/modulus-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation des Modulus für Elemente eines angegebenen Werttyps ausführt.|
|[multiplies](../standard-library/multiplies-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation der Multiplikation für Elemente eines angegebenen Werttyps ausführt.|
|[negate](../standard-library/negate-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, mit dem der negative Bereich eines Elementwerts zurückgegeben wird.|
|[not_equal_to](../standard-library/not-equal-to-struct.md)|Ein binäres Prädikat, mit dem überprüft wird, ob der Wert eines bestimmten Typs ungleich einem anderen Wert dieses Typs ist.|
|[plus](../standard-library/plus-struct.md)|Die Klasse stellt ein vordefiniertes Funktionsobjekt bereit, das die arithmetische Operation der Addition für Elemente eines angegebenen Werttyps ausführt.|
|[unary_function](../standard-library/unary-function-struct.md)|Eine leere Basisklasse, mit der Typen definiert werden, die möglicherweise von einer abgeleiteten Klasse geerbt wird, die ein unäres Funktionsobjekt bereitstellt.<br/> (Veraltet in C ++ 11, C ++ 17 entfernt). |

### <a name="objects"></a>erzwingen

|||
|-|-|
|[_1.._M](../standard-library/1-object.md)|Platzhalter für austauschbare Argumente.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator==](../standard-library/functional-operators.md#op_eq_eq)|Lässt den Gleichheitsvergleich von aufrufbaren Objekten nicht zu.|
|[Operator!=](../standard-library/functional-operators.md#op_neq)|Lässt den Ungleichheitsvergleich von aufrufbaren Objekten nicht zu.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
