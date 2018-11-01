---
title: enable_if-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::enable_if
helpviewer_keywords:
- enable_if class
- enable_if
ms.assetid: c6b8d41c-a18f-4e30-a39e-b3aa0e8fd926
ms.openlocfilehash: b6990dba20643b35dde36a492d40c3e3e76ae0b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591879"
---
# <a name="enableif-class"></a>enable_if-Klasse

Wandelt einen Typ für die SFINAE-Überladungsauflösung bedingt in eine Instanz um. Die geschachtelte Typedef `enable_if<Condition,Type>::type` vorhanden ist, und ist ein Synonym für `Type`– nur, wenn `Condition` ist **"true"**.

## <a name="syntax"></a>Syntax

```cpp
template <bool B, class T = void>
struct enable_if;
```

### <a name="parameters"></a>Parameter

*B*<br/>
Der Wert, der das Vorhandensein des Ergebnistyps bestimmt.

*T*<br/>
Der Typ, wenn instanziieren *B* ist "true".

## <a name="remarks"></a>Hinweise

Wenn *B* ist "true" `enable_if<B, T>` verfügt über eine geschachtelte Typdefinition namens "type", das ein Synonym für *T*.

Wenn *B* ist "false" `enable_if<B, T>` verfügt nicht über eine geschachtelte Typdefinition namens "Type".

Die folgende Alias-Vorlage steht zur Verfügung:

```cpp
template <bool B, class T = void>
using enable_if_t = typename enable_if<B,T>::type;
```

In C++ ist eine fehlgeschlagene Substitution von Vorlagenparametern kein eigentlicher Fehler – dies wird als *SFINAE* (Substitution Failure Is Not An Error) bezeichnet. Normalerweise wird `enable_if` verwendet, um Kandidaten aus einer Überladungsauflösung zu entfernen – also aus dem Überladungssatz auszusortieren, sodass eine Definition zugunsten einer anderen zurückgewiesen werden kann. Dies entspricht dem SFINAE-Verhalten. Weitere Informationen zu SFINAE finden Sie unter [Substitution failure is not an error](http://go.microsoft.com/fwlink/p/?linkid=394798) auf Wikipedia.

Im Folgenden finden Sie vier Beispielszenarien:

- Szenario 1: Umschließen des Rückgabetyps einer Funktion:

```cpp
    template <your_stuff>
typename enable_if<your_condition, your_return_type>::type
    yourfunction(args) {// ...
}
// The alias template makes it more concise:
    template <your_stuff>
enable_if_t<your_condition, your_return_type>
yourfunction(args) {// ...
}
```

- Szenario 2: Hinzufügen eines Funktionsparameters mit einem Standardargument:

```cpp
    template <your_stuff>
your_return_type_if_present
    yourfunction(args, enable_if_t<your condition, FOO> = BAR) {// ...
}
```

- Szenario 3: Hinzufügen eines Vorlagenparameters mit einem Standardargument:

```cpp
    template <your_stuff, typename Dummy = enable_if_t<your_condition>>
rest_of_function_declaration_goes_here
```

- Szenario 4: Wenn Ihre Funktion über ein Argument ohne Vorlage verfügt, können Sie ihren Typ umschließen:

```cpp
    template <typename T>
void your_function(const T& t,
    enable_if_t<is_something<T>::value, const string&>
s) {// ...
}
```

Szenario 1 funktioniert nicht mit Konstruktoren und Konvertierungsoperatoren, da diese keine Rückgabetypen haben.

In Szenario 2 bleibt der Parameter unbenannt. Sie können ihn `::type Dummy = BAR` nennen, aber der Namens-`Dummy` ist irrelevant, und eine Benennung löst wahrscheinlich eine Warnung über einen nicht referenzierten Parameter aus. Sie müssen einen `FOO` Funktionsparameter typ und ein `BAR`-Standardargument auswählen.  Sie können z. B. **Int** und `0`, aber dann Benutzer Ihres Codes könnte versehentlich an die Funktion übergeben eine zusätzliche Ganzzahl, die ignoriert würde. Stattdessen empfehlen wir die Verwendung von `void **` und entweder `0` oder **"nullptr"** da fast nichts konvertierbar ist `void **`:

```cpp
template <your_stuff>
your_return_type_if_present
yourfunction(args, typename enable_if<your_condition, void **>::type = nullptr) {// ...
}
```

Szenario 2 funktioniert auch mit normalen Konstruktoren.  Allerdings funktioniert es nicht mit Konvertierungsoperatoren, da diese keine zusätzlichen Parameter aufnehmen können.  Es funktioniert ebenfalls nicht mit [variadic](../cpp/ellipses-and-variadic-templates.md)-Konstruktoren, da die Hinzufügung zusätzlicher Parameter dazu führt, dass der Funktionsparameter einen nicht abgeleiteten Kontext verpackt und dadurch den Zweck von `enable_if` verfehlt.

Szenario 3 verwendet den Namen `Dummy`, aber dieser ist optional. Nur „`typename = typename`“ wäre geeignet, aber wenn Ihnen dies seltsam vorkommt, können Sie einen „Dummy“-Namen wählen. Wählen Sie jedoch keinen Namen, der auch in der Funktionsdefinition verwendet werden könnte. Wenn Sie keinen Typ für das `enable_if` angeben, bleibt es standardmäßig leer, was verständlich ist, da es Sie nicht kümmern muss, was `Dummy` ist. Dies funktioniert für alle Elemente einschließlich Konvertierungsoperatoren und [variadic](../cpp/ellipses-and-variadic-templates.md)-Konstruktoren.

Szenario 4 funktioniert mit Konstruktoren, die keine Rückgabetypen haben, und löst dadurch die Umschließungseinschränkung von Szenario 1 auf.  Szenario 4 ist allerdings auf Funktionsargumente ohne Vorlage beschränkt, die nicht immer zur Verfügung stehen.  (Die Verwendung von Szenario 4 mit einem Funktionsargument mit Vorlage verhindert, dass die Ableitung eines Vorlagenarguments in diesem Szenario funktioniert.)

`enable_if` ist leistungsstark, aber bei falscher Verwendung auch gefährlich.  Da es sein Zweck ist, Kandidaten vor einer Überladungsauflösung verschwinden zu lassen, wenn es fehlerhaft verwendet wird, können seine Wirkungen sehr verwirrend sein.  Hier einige Empfehlungen:

- Verwenden Sie `enable_if` nicht, um zur Kompilierungszeit zwischen Implementierungen auszuwählen. Schreiben Sie niemals ein `enable_if` für `CONDITION` und ein anderes für `!CONDITION`.  Verwenden Sie stattdessen ein *tag dispatch*-Muster – z.B. einen Algorithmus, der Implementierungen abhängig von den Stärken der Iteratoren auswählt, die sie erhalten.

- Verwenden Sie nicht `enable_if`, um Anforderungen zu erzwingen.  Wenn Sie Vorlagenparameter überprüfen möchten und die Validierung fehlschlägt und statt der Auswahl einer anderen Implementierung zu einem Fehler führt, verwenden Sie [static_assert](../cpp/static-assert.md).

- Verwenden Sie `enable_if`, wenn Sie einen Überladungssatz haben, der einen ansonsten guten Code mehrdeutig macht.  Dies tritt sehr häufig bei der impliziten Konvertierung von Konstruktoren auf.

## <a name="example"></a>Beispiel

In diesem Beispiel wird erläutert, wie die Vorlagenfunktion [std::make_pair()](../standard-library/utility-functions.md#make_pair) von der C++-Standardbibliothek `enable_if` genutzt wird.

```cpp
void func(const pair<int, int>&);

void func(const pair<string, string>&);

func(make_pair("foo", "bar"));
```

In diesem Beispiel gibt `make_pair("foo", "bar")` `pair<const char *, const char *>` zurück. Überladungsauslösung, die bestimmen muss, welche `func()` Sie möchten. `pair<A, B>` hat einen impliziten Konvertierungskonstruktor aus `pair<X, Y>`.  Dies ist nicht neu, sondern war schon in C++98 vorhanden. In C++98/03 ist allerdings die Signatur des impliziten Konvertierungskonstruktors immer vorhanden, selbst wenn es `pair<int, int>(const pair<const char *, const char *>&)` ist.  Überladungsauflösung ist unerheblich, dass der Versuch, diesen Konstruktor zu instanzieren furchtbar da überladungsauslösung `const char *` wird nicht implizit in **Int**; nur auf Signaturen gesucht wird, vor der Funktion sind instanziiert.  Deshalb ist der Beispielcode mehrdeutig, da Signaturen zur Konvertierung von `pair<const char *, const char *>` in `pair<int, int>` und in `pair<string, string>` vorhanden sind.

In C++11 wurde diese Mehrdeutigkeit durch Verwendung von `enable_if` aufgelöst, um sicherzustellen, dass `pair<A, B>(const pair<X, Y>&)` **nur dann** vorhanden ist, wenn `const X&` implizit in `A` konvertierbar ist und `const Y&` implizit in `B` konvertierbar ist.  Dadurch kann die Überladungsauflösung festlegen, dass `pair<const char *, const char *>` nicht in `pair<int, int>` konvertierbar ist und dass die Überladung, die `pair<string, string>` aufnimmt, realisierbar ist.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
