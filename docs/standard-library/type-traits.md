---
title: '&lt;type_traits&gt;'
ms.date: 02/21/2019
f1_keywords:
- <type_traits>
helpviewer_keywords:
- typetrait header
- type_traits
ms.assetid: 2260b51f-8160-4c66-a82f-00b534cb60d4
ms.openlocfilehash: c80629fd8771206d193b53aa7c32073de0ba45dd
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006724"
---
# <a name="lttypetraitsgt"></a>&lt;type_traits&gt;

Definiert Vorlagen, die für Konstanten zur Kompilierzeit, die Informationen zu den Eigenschaften ihrer Typargumente geben oder transformierte Typen erstellen.

## <a name="syntax"></a>Syntax

```cpp
#include <type_traits>
```

## <a name="remarks"></a>Hinweise

Die Klassen und Vorlagen in \<Type_traits > werden verwendet, um den Typrückschluss, Klassifizierung und Transformation zum Zeitpunkt der Kompilierung zu unterstützen. Sie dienen auch um typbezogene Fehler zu erkennen und Ihnen helfen, den generischen Code zu optimieren. Unäre typmerkmale Beschreiben einer Eigenschaft eines Typs, binäre typmerkmale beschreiben eine Beziehung zwischen Typen und transformationsmerkmale Ändern einer Eigenschaft eines Typs.

Die Hilfsklasse `integral_constant` und die vorlagenspezialisierungen `true_type` und `false_type` die Basisklassen für typprädikate bilden. Ein *Typprädikat* ist eine Vorlage, die ein oder mehrere Typargumente entgegennimmt. Wenn ein typprädikat *gilt*, öffentlich abgeleitet wurde, direkt oder indirekt von [True_type](../standard-library/type-traits-typedefs.md#true_type). Wenn ein typprädikat *ist Sie false*, öffentlich abgeleitet wurde, direkt oder indirekt von [False_type](../standard-library/type-traits-typedefs.md#false_type).

Ein *Typmodifizierer* oder *Transformationsmerkmal* ist eine Vorlage, die ein oder mehrere Vorlagenargumente entgegennimmt und über einen Member `type` verfügt, der ein Synonym für den geänderten Typ ist.

### <a name="alias-templates"></a>Alias-Vorlagen

Um die typmerkmalausdrücke zu vereinfachen [aliasvorlagen](../cpp/aliases-and-typedefs-cpp.md) für `typename some_trait<T>::type` zur Verfügung, wobei *Some_trait* der vorlagenklassenname ist. Zum Beispiel verfügt [add_const](../standard-library/add-const-class.md) über eine Aliasvorlage für seinen Typ `add_const_t`, definiert als:

```cpp
template <class T>
using add_const_t = typename add_const<T>::type;
```

Hierbei handelt es sich um die angegebenen Aliase für die `type` Mitglieder:

||||
|-|-|-|
| add_const_t | add_cv_t | add_lvalue_reference_t |
| add_pointer_t | add_rvalue_reference_t | add_volatile_t |
| aligned_storage_t | aligned_union_t | common_type_t |
| conditional_t | decay_t | enable_if_t |
| invoke_result_t | make_signed_t | make_unsigned_t |
| remove_all_extents_t | remove_const_t | remove_cv_t |
| remove_extent_t | remove_pointer_t | remove_reference_t |
| remove_volatile_t | result_of_t | underlying_type_t |

### <a name="classes"></a>Klassen

Hilfsprogrammklasse und Typedefs

|||
|-|-|
|[integral_constant](../standard-library/integral-constant-class-bool-constant-class.md)|Wandelt einen Typ und einen Wert in eine Ganzzahlkonstante um.|
|[true_type](../standard-library/type-traits-typedefs.md#true_type)|Enthält eine Ganzzahlkonstante mit einem wahren Wert.|
|[false_type](../standard-library/type-traits-typedefs.md#false_type)|Enthält eine Ganzzahlkonstante mit einem falschen Wert.|

Primäre Typkategorien

|||
|-|-|
|[is_void](../standard-library/is-void-class.md)|Testet, ob der Typ ist **"void"**.|
|[is_null_pointer](../standard-library/is-null-pointer-class.md)|Testet, ob der Typ `std::nullptr_t` ist.|
|[is_integral](../standard-library/is-integral-class.md)|Testet, ob der Typ eine Ganzzahl ist.|
|[is_floating_point](../standard-library/is-floating-point-class.md)|Testet, ob der Typ ein Gleitkomma ist.|
|[is_array](../standard-library/is-array-class.md)|Testet, ob der Typ ein Array ist.|
|[is_pointer](../standard-library/is-pointer-class.md)|Testet, ob der Typ ein Zeiger ist.|
|[is_lvalue_reference](../standard-library/is-lvalue-reference-class.md)|Testet, ob es sich beim Typ um einen lvalue-Verweis handelt.|
|[is_rvalue_reference](../standard-library/is-rvalue-reference-class.md)|Testet, ob es sich beim Typ um einen „rvalue“-Verweis handelt.|
|[is_member_object_pointer](../standard-library/is-member-object-pointer-class.md)|Testet, ob der Typ ein Zeiger auf ein Memberobjekt ist.|
|[is_member_function_pointer](../standard-library/is-member-function-pointer-class.md)|Testet, ob der Typ ein Zeiger auf eine Memberfunktion ist.|
|[is_enum](../standard-library/is-enum-class.md)|Testet, ob der Typ eine Aufzählung ist.|
|[is_union](../standard-library/is-union-class.md)|Testet, ob der Typ eine Union ist.|
|[is_class](../standard-library/is-class-class.md)|Testet, ob der Typ eine Klasse ist.|
|[is_function](../standard-library/is-function-class.md)|Testet, ob der Typ ein Funktionstyp ist.|

Zusammengesetzte Typkategorien

|||
|-|-|
|[is_reference](../standard-library/is-reference-class.md)|Testet, ob der Typ ein Verweis ist.|
|[is_arithmetic](../standard-library/is-arithmetic-class.md)|Testet, ob der Typ arithmetisch ist.|
|[is_fundamental](../standard-library/is-fundamental-class.md)|Testet, ob der Typ ist **"void"** oder arithmetische.|
|[is_object](../standard-library/is-object-class.md)|Testet, ob der Typ ein Objekttyp ist.|
|[is_scalar](../standard-library/is-scalar-class.md)|Testet, ob der Typ skalar ist.|
|[is_compound](../standard-library/is-compound-class.md)|Testet, ob der Typ nicht skalar ist.|
|[is_member_pointer](../standard-library/is-member-pointer-class.md)|Testet, ob der Typ ein Zeiger auf ein Member ist.|

Typeigenschaften

|||
|-|-|
|[is_const](../standard-library/is-const-class.md)|Testet, ob der Typ ist **const**.|
|[is_volatile](../standard-library/is-volatile-class.md)|Testet, ob der Typ ist **flüchtige**.|
|[is_trivial](../standard-library/is-trivial-class.md)|Testet, ob der Typ trivial ist.|
|[is_trivially_copyable](../standard-library/is-trivially-copyable-class.md)|Testet, ob der Typ trivial kopierbar ist.|
|[is_standard_layout](../standard-library/is-standard-layout-class.md)|Testet, ob der Typ ein Standardlayouttyp ist.|
|[is_pod](../standard-library/is-pod-class.md)|Testet, ob der Typ ein POD-Typ ist.|
|[is_literal_type](../standard-library/is-literal-type-class.md)|Testet, ob der Typ eine `constexpr`-Variable sein oder in einer `constexpr`-Funktion verwendet werden kann.|
|[is_empty](../standard-library/is-empty-class.md)|Testet, ob es sich bei dem Typ um eine leere Klasse handelt.|
|[is_polymorphic](../standard-library/is-polymorphic-class.md)|Testet, ob der Typ eine polymorphe Klasse ist.|
|[is_abstract](../standard-library/is-abstract-class.md)|Testet, ob es dich bei dem Typ um eine abstrakte Klasse handelt.|
|[is_final](../standard-library/is-final-class.md)|Testet, ob der Typ ein als `final` markierter Klassentyp ist.|
|[is_signed](../standard-library/is-signed-class.md)|Testet, ob der Typ eine Ganzzahl mit einem Vorzeichen ist.|
|[is_unsigned](../standard-library/is-unsigned-class.md)|Testet, ob der Typ eine Ganzzahl ohne Vorzeichen ist.|
|[is_constructible](../standard-library/is-constructible-class.md)|Testet, ob der Typ konstruiert werden kann, wenn die angegebenen Argumenttypen verwendet werden.|
|[is_default_constructible](../standard-library/type-traits-functions.md#is_default_constructible)|Testet, ob der Typ über einen Standardkonstruktor verfügt.|
|[is_copy_constructible](../standard-library/type-traits-functions.md#is_copy_constructible)|Testet, ob der Typ über einen Kopierkonstruktor verfügt.|
|[is_move_constructible](../standard-library/type-traits-functions.md#is_move_constructible)|Testet, ob der Typ über einen Bewegungskonstruktor verfügt.|
|[is_assignable](../standard-library/type-traits-functions.md#is_assignable)|Testet, ob dem ersten Typ ein Wert des zweiten Typs zugewiesen werden kann.|
|[is_copy_assignable](../standard-library/type-traits-functions.md#is_copy_assignable)|Testet, ob einem Typ ein konstanter Verweiswert des Typs zugewiesen werden kann.|
|[is_move_assignable](../standard-library/type-traits-functions.md#is_move_assignable)|Testet, ob einem Typ ein rvalue-Verweis des Typs zugewiesen werden kann.|
|[is_destructible](../standard-library/is-destructible-class.md)|Testet, ob der Typ „destructible“ ist.|
|[is_trivially_constructible](../standard-library/is-trivially-constructible-class.md)|Testet, ob der Typ keine nicht trivialen Vorgänge verwendet, wenn er mit den angegebenen Typen konstruiert wird.|
|[is_trivially_default_constructible](../standard-library/is-trivially-default-constructible-class.md)|Testet, ob der Typ keine nicht trivialen Vorgänge verwendet, wenn er standardmäßig konstruiert wird.|
|[is_trivially_copy_constructible](../standard-library/is-trivially-copy-constructible-class.md)|Testet, ob der Typ keine nicht trivialen Vorgänge verwendet, wenn er durch Kopie konstruiert wird.|
|[is_trivially_move_constructible](../standard-library/type-traits-functions.md#is_trivially_move_constructible)|Testet, ob der Typ keine nicht trivialen Vorgänge verwendet, wenn er durch Bewegung konstruiert wird.|
|[is_trivially_assignable](../standard-library/is-trivially-assignable-class.md)|Testet, ob die Typen zugewiesen werden können und bei der Zuweisung keine nicht trivialen Vorgänge verwendet werden.|
|[is_trivially_copy_assignable](../standard-library/type-traits-functions.md#is_trivially_copy_assignable)|Testet, ob der Typ durch Kopie zugewiesen werden kann und bei der Zuweisung keine nicht trivialen Vorgänge verwendet werden.|
|[is_trivially_move_assignable](../standard-library/type-traits-functions.md#is_trivially_move_assignable)|Prüft, ob dem Typ eine Verschiebung zugewiesen werden kann und bei der Zuweisung keine nicht trivialen Vorgänge verwendet werden.|
|[is_trivially_destructible](../standard-library/is-trivially-destructible-class.md)|Testet, ob der Typ zerstörbar ist und der Destruktor keine nicht trivialen Vorgänge verwendet.|
|[is_nothrow_constructible](../standard-library/is-nothrow-constructible-class.md)|Testet, ob der Typ konstruiert werden kann und keine Ausnahmefehler auslöst, wenn er mit den angegebenen Typen konstruiert wird.|
|[is_nothrow_default_constructible](../standard-library/is-nothrow-default-constructible-class.md)|Testet, ob der Typ standardmäßig konstruiert werden kann und keine Ausnahmefehler auslöst, wenn er standardmäßig konstruiert wird.|
|[is_nothrow_copy_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|Testet, ob der Typ durch Kopie konstruiert werden kann und der Kopierkonstruktor keine Ausnahmefehler auslöst.|
|[is_nothrow_move_constructible](../standard-library/is-nothrow-move-constructible-class.md)|Testet, ob der Typ durch Bewegung konstruiert werden kann und der Bewegungskonstruktor keine Ausnahmefehler auslöst.|
|[is_nothrow_assignable](../standard-library/is-nothrow-assignable-class.md)|Testet, ob der Typ mit dem angegebenen Typ zugewiesen werden kann und die Zuweisung keine Ausnahmefehler auslöst.|
|[is_nothrow_copy_assignable](../standard-library/is-nothrow-copy-assignable-class.md)|Testet, ob der Typ durch Kopie zugewiesen werden kann und die Zuweisung keine Ausnahmefehler auslöst.|
|[is_nothrow_move_assignable](../standard-library/type-traits-functions.md#is_nothrow_move_assignable)|Prüft, ob dem Typ eine Verschiebung zugewiesen werden kann und die Zuweisung keine Ausnahmefehler auslöst.|
|[is_nothrow_destructible](../standard-library/is-nothrow-destructible-class.md)|Testet, ob der Typ zerstörbar ist und der Destruktor keine Ausnahmefehler auslöst.|
|`has_virtual_destructor`|Testet, ob der Typ einen virtuellen Destruktor aufweist.|
| [is_invocable](is-invocable-classes.md) | Testet, ob ein aufrufbaren Typs mit den angegebenen Argumenttypen aufgerufen werden kann.<br/> In C ++ 17-hinzugefügt. |
| [is_invocable_r](is-invocable-classes.md) | Testet, ob ein aufrufbaren Typs mit den angegebenen Argumenttypen und das Ergebnis aufgerufen werden kann in den angegebenen Typ konvertiert werden kann.<br/> In C ++ 17-hinzugefügt. |
| [is_nothrow_invocable](is-invocable-classes.md) | Testet, ob ein aufrufbaren Typs aufgerufen werden kann, mit dem angegebenen Argument Typen und ist keine Ausnahmen auslösen.<br/> In C ++ 17-hinzugefügt. |
| [is_nothrow_invocable_r](is-invocable-classes.md) | Testet, ob ein aufrufbaren Typs mit den angegebenen Argumenttypen aufgerufen werden kann, und ist bekannt, nicht zum Auslösen von Ausnahmen, und das Ergebnis in den angegebenen Typ konvertiert wird.<br/> In C ++ 17-hinzugefügt. |

Typeigenschaftsabfragen

|||
|-|-|
|[alignment_of](../standard-library/alignment-of-class.md)|Ruft die Ausrichtung eines Typs ab.|
|[rank](../standard-library/rank-class.md)|Ruft die Anzahl von Arraydimensionen ab.|
|[extent](../standard-library/extent-class.md)|Ruft die Anzahl der Elemente in der angegebenen Arraydimension ab.|

Typbeziehungen

|||
|-|-|
|[is_same](../standard-library/is-same-class.md)|Stellt fest, ob zwei Typen identisch sind.|
|[is_base_of](../standard-library/is-base-of-class.md)|Testet, ob ein Typ die Basis eines anderen ist.|
|[is_convertible](../standard-library/is-convertible-class.md)|Testet, ob ein Typ in einen anderen konvertiert werden kann.|

Änderungen flüchtiger Konstanten

|||
|-|-|
|[add_const](../standard-library/add-const-class.md)|Erzeugt eine **const** Typ vom Typ.|
|[add_volatile](../standard-library/add-volatile-class.md)|Erzeugt eine **flüchtige** Typ vom Typ.|
|[add_cv](../standard-library/add-cv-class.md)|Erzeugt eine **const Volatile** Typ vom Typ.|
|[remove_const](../standard-library/remove-const-class.md)|Wandelt den Typ in einen nicht konstanten Typ um.|
|[remove_volatile](../standard-library/remove-volatile-class.md)|Wandelt den Typ in einen nicht flüchtigen Typ um.|
|[remove_cv](../standard-library/remove-cv-class.md)|Wandelt den Typ in einen nicht konstanten nicht flüchtigen Typ um.|

Verweisänderungen

|||
|-|-|
|[add_lvalue_reference](../standard-library/add-lvalue-reference-class.md)|Wandelt den Typ in einen Verweis auf den Typ um.|
|[add_rvalue_reference](../standard-library/add-rvalue-reference-class.md)|Wandelt den Typ in einen rvalue-Verweis auf den Typ um|
|[remove_reference](../standard-library/remove-reference-class.md)|Wandelt den Typ in einen Typ ohne Verweis um.|

Vorzeichenmanipulation

|||
|-|-|
|[make_signed](../standard-library/make-signed-class.md)|Erzeugt bei einem signierten Typ den Typ und andernfalls den kleinsten signierten Typ größer oder gleich dem Typ.|
|[make_unsigned](../standard-library/make-unsigned-class.md)|Erzeugt bei einem unsignierten Typ den Typ und andernfalls den kleinsten unsignierten Typ größer oder gleich dem Typ.|

Arrayänderungen

|||
|-|-|
|[remove_all_extents](../standard-library/remove-all-extents-class.md)|Wandelt einen Arraytyp in einen Nichtarraytyp um.|
|[remove_extent](../standard-library/remove-extent-class.md)|Wandelt einen Arraytyp in einen Elementtyp um.|

Zeigeränderungen

|||
|-|-|
|[add_pointer](../standard-library/add-pointer-class.md)|Wandelt den Typ in einen Zeiger auf den Typ um.|
|[remove_pointer](../standard-library/remove-pointer-class.md)|Wandelt einen Zeiger auf den Typ in einen Typ um.|

Weitere Transformationen

|||
|-|-|
|[aligned_storage](../standard-library/aligned-storage-class.md)|Weist nicht initialisierten Arbeitsspeicher für eine ausgerichteten Typ zu.|
|[aligned_union](../standard-library/aligned-union-class.md)|Weist den nicht initialisierten Arbeitsspeicher für eine ausgerichtete Union mit einem nicht trivialen Konstruktor oder Destruktor zu.|
|[common_type](../standard-library/common-type-class.md)|Wandelt alle Typen des Parameterpakets in einen gemeinsamen Typ um.|
|[conditional](../standard-library/conditional-class.md)|Wenn die Bedingung TRUE ist, wird der erste angegebene Typ erzeugt, andernfalls der zweite angegebene Typ.|
|[decay](../standard-library/decay-class.md)|Erzeugt den Typ bei der Übergabe durch einen Wert. Erstellt einen non-reference-, non-const- oder non-volatile-Typ oder erstellt einen Zeiger auf den Typ.|
|[enable_if](../standard-library/enable-if-class.md)|Wenn die Bedingung TRUE ist, wird der angegebene Typ erzeugt, andernfalls kein Typ.|
|[invoke_result](invoke-result-class.md)|Bestimmt den Rückgabetyp des aufrufbaren Typs, der die angegebenen Argumenttypen akzeptiert. <br/>In C ++ 17-hinzugefügt. |
|[result_of](../standard-library/result-of-class.md)|Bestimmt den Rückgabetyp des aufrufbaren Typs, der die angegebenen Argumenttypen akzeptiert. <br/>Hinzugefügt in C ++ 14, C ++ 17 veraltet. |
|[underlying_type](../standard-library/underlying-type-class.md)|Erzeugt für einen Enumerationstyp den zugrunde liegenden ganzzahligen Typ.|

## <a name="see-also"></a>Siehe auch

[\<functional>](../standard-library/functional.md)<br/>
