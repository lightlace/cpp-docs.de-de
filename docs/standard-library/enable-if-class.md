---
title: enable_if-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::enable_if
dev_langs: C++
helpviewer_keywords:
- enable_if class
- enable_if
ms.assetid: c6b8d41c-a18f-4e30-a39e-b3aa0e8fd926
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7753c840fe1b4c9850408b53fa0adf09ed1bc121
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="enableif-class"></a>enable_if-Klasse
Wandelt einen Typ für die SFINAE-Überladungsauflösung bedingt in eine Instanz um. Der geschachtelte typedef-`enable_if<Condition,Type>::type` existiert und ist ein Synonym für `Type` – wenn und nur dann, wenn `Condition` gleich `true` ist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <bool B, class T = void>
struct enable_if;
```  
  
#### <a name="parameters"></a>Parameter  
 `B`  
 Der Wert, der das Vorhandensein des Ergebnistyps bestimmt.  
  
 `T`  
 Der Typ, der instanziert werden soll, wenn `B` "true" ist.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `B` "true" ist, weist `enable_if<B, T>` eine geschachtelte Typdefinition namens "type" auf, die ein Synonym für `T` ist.  
  
 Wenn `B` "false" ist, weist `enable_if<B, T>` keine geschachtelte Typdefinition namens "type" auf.  
  
 Die folgende Alias-Vorlage steht zur Verfügung:  
  
```cpp  
template <bool B, class T = void>
using enable_if_t = typename enable_if<B,T>::type;
```  
  
 In C++ ist eine fehlgeschlagene Substitution von Vorlagenparametern kein eigentlicher Fehler – dies wird als *SFINAE* (Substitution Failure Is Not An Error) bezeichnet. Normalerweise wird `enable_if` verwendet, um Kandidaten aus einer Überladungsauflösung zu entfernen – also aus dem Überladungssatz auszusortieren, sodass eine Definition zugunsten einer anderen zurückgewiesen werden kann. Dies entspricht dem SFINAE-Verhalten. Weitere Informationen zu SFINAE finden Sie unter [Substitution failure is not an error](http://go.microsoft.com/fwlink/LinkId=394798) auf Wikipedia.  
  
 Im Folgenden finden Sie vier Beispielszenarien:  
  
-   Szenario 1: Umschließen des Rückgabetyps einer Funktion:  
  
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
  
-   Szenario 2: Hinzufügen eines Funktionsparameters mit einem Standardargument:  
  
 ```cpp  
    template <your_stuff>  
your_return_type_if_present
    yourfunction(args, enable_if_t<your condition, FOO> = BAR) {// ...
 }
```  
  
-   Szenario 3: Hinzufügen eines Vorlagenparameters mit einem Standardargument:  
  
 ```cpp  
    template <your_stuff, typename Dummy = enable_if_t<your_condition>>  
rest_of_function_declaration_goes_here
```  
  
-   Szenario 4: Wenn Ihre Funktion über ein Argument ohne Vorlage verfügt, können Sie ihren Typ umschließen:  
  
 ```cpp  
    template <typename T>  
void your_function(const T& t,
    enable_if_t<is_something<T>::value, const string&>  
s) {// ...
 }
```  
  
 Szenario 1 funktioniert nicht mit Konstruktoren und Konvertierungsoperatoren, da diese keine Rückgabetypen haben.  
  
 In Szenario 2 bleibt der Parameter unbenannt. Sie können ihn `::type Dummy = BAR` nennen, aber der Namens-`Dummy` ist irrelevant, und eine Benennung löst wahrscheinlich eine Warnung über einen nicht referenzierten Parameter aus. Sie müssen einen `FOO` Funktionsparameter typ und ein `BAR`-Standardargument auswählen.  Sie können diese `int` und `0` nennen, aber in diesem Falle könnten Benutzer Ihres Codes zufällig eine zusätzliche Ganzzahl an diese Funktion übergeben, die ignoriert würde. Wir empfehlen stattdessen, `void **` und entweder `0` oder `nullptr` zu verwenden, da fast nichts in `void **` umwandelbar ist:  
  
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
  
-   Verwenden Sie `enable_if` nicht, um zur Kompilierungszeit zwischen Implementierungen auszuwählen. Schreiben Sie niemals ein `enable_if` für `CONDITION` und ein anderes für `!CONDITION`.  Verwenden Sie stattdessen ein *tag dispatch*-Muster – z.B. einen Algorithmus, der Implementierungen abhängig von den Stärken der Iteratoren auswählt, die sie erhalten.  
  
-   Verwenden Sie nicht `enable_if`, um Anforderungen zu erzwingen.  Wenn Sie Vorlagenparameter überprüfen möchten und die Validierung fehlschlägt und statt der Auswahl einer anderen Implementierung zu einem Fehler führt, verwenden Sie [static_assert](../cpp/static-assert.md).  
  
-   Verwenden Sie `enable_if`, wenn Sie einen Überladungssatz haben, der einen ansonsten guten Code mehrdeutig macht.  Dies tritt sehr häufig bei der impliziten Konvertierung von Konstruktoren auf.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird erläutert, wie die Vorlagenfunktion [std::make_pair()](../standard-library/utility-functions.md#make_pair) von der C++-Standardbibliothek `enable_if` genutzt wird.  
  
```cpp  
void func(const pair<int, int>&);

void func(const pair<string, string>&);

func(make_pair("foo", "bar"));
```  
  
  In diesem Beispiel gibt `make_pair("foo", "bar")` `pair<const char *, const char *>` zurück. Überladungsauslösung, die bestimmen muss, welche `func()` Sie möchten. `pair<A, B>` hat einen impliziten Konvertierungskonstruktor aus `pair<X, Y>`.  Dies ist nicht neu, sondern war schon in C++98 vorhanden. In C++98/03 ist allerdings die Signatur des impliziten Konvertierungskonstruktors immer vorhanden, selbst wenn es `pair<int, int>(const pair<const char *, const char *>&)` ist.  Für die Überladungsauslösung ist es egal, wenn ein Versuch, diesen Konstruktor zu instanzieren, fehlschlägt, da `const char *` nicht implizit in `int` konvertierbar ist; sie schaut nur auf Signaturen, bevor Funktionsdefinitionen instanziert werden.  Deshalb ist der Beispielcode mehrdeutig, da Signaturen zur Konvertierung von `pair<const char *, const char *>` in `pair<int, int>` und in `pair<string, string>` vorhanden sind.  
  
 In C++11 wurde diese Mehrdeutigkeit durch Verwendung von `enable_if` aufgelöst, um sicherzustellen, dass `pair<A, B>(const pair<X, Y>&)` **nur dann** vorhanden ist, wenn `const X&` implizit in `A` konvertierbar ist und `const Y&` implizit in `B` konvertierbar ist.  Dadurch kann die Überladungsauflösung festlegen, dass `pair<const char *, const char *>` nicht in `pair<int, int>` konvertierbar ist und dass die Überladung, die `pair<string, string>` aufnimmt, realisierbar ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)



