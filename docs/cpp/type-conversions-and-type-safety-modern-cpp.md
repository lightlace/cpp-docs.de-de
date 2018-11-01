---
title: Typumwandlungen und Typsicherheit (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 629b361a-2ce1-4700-8b5d-ab4f57b245d5
ms.openlocfilehash: ae3b2d89c06d0e7b17b648907fa3d7734b51205c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471343"
---
# <a name="type-conversions-and-type-safety-modern-c"></a>Typumwandlungen und Typsicherheit (Modern C++)

In diesem Dokument werden allgemeine Typkonvertierungsprobleme behandelt, und es wird beschrieben, wie Sie diese im C++-Code vermeiden können.

Beim Schreiben eines C++-Programms müssen Sie sicherzustellen, dass es typsicher ist. Das bedeutet, dass alle Variablen, Funktionsargumente und Rückgabewerte von Funktionen akzeptable Daten speichern und dass Vorgänge, bei denen Werte verschiedener Typen verwendet werden, einen „Sinn“ ergeben und nicht zu Datenverlust, falschen Interpretationen von Bitmustern oder Speicherschäden führen. Ein Programm, das nie explizit oder implizit Werte von einem Typ in einen anderen konvertiert, ist definitionsgemäß typsicher. Manchmal sind jedoch Typkonvertierungen oder sogar unsichere Konvertierungen erforderlich. Angenommen, Sie müssen möglicherweise zum Speichern des Ergebnisses eines auf Gleitkommazahlen anzuwendenden point-Vorgang in eine Variable vom Typ **Int**, oder Sie müssen möglicherweise den Wert in einen nicht signierten übergeben **Int** an eine Funktion, die eine signierte akzeptiert  **Int**. Beide Beispiele stehen für unsichere Konvertierungen, da sie zu Datenverlust oder einer Neuinterpretation eines Werts führen können.

Wenn der Compiler eine unsichere Konvertierung erkennt, wird entweder ein Fehler oder eine Warnung ausgegeben. Ein Fehler beendet die Kompilierung. Bei einer Warnung kann die Kompilierung fortgesetzt werden, es wird jedoch ein möglicher Fehler im Code angegeben. Auch wenn Ihr Programm ohne Warnungen kompiliert wird, kann es trotzdem noch Code enthalten, der zu impliziten Typkonvertierungen führt, welche falsche Ergebnisse erzeugen. Typfehler können auch durch explizite Konvertierungen oder Umwandlungen im Code verursacht werden.

## <a name="implicit-type-conversions"></a>Implizite Typkonvertierungen

Wenn ein Ausdruck Operanden unterschiedlicher integrierter Typen enthält und keine explizite Umwandlungen vorhanden sind, verwendet der Compiler integrierte *standardkonvertierungen* einer der Operanden konvertiert, damit die Typen übereinstimmen. Der Compiler testet die Konvertierungen in einer klar definierte Abfolge, bis eine erfolgreich ist. Wenn es sich bei der ausgewählten Konvertierung um eine Heraufstufung handelt, gibt der Compiler keine Warnung aus. Wenn es sich bei der Konvertierung um eine Einschränkung handelt, gibt der Compiler eine Warnung zu möglichem Datenverlust aus. Ob wirklich ein Datenverlust auftritt, hängt von den verwendeten tatsächlichen Werten ab. Es wird jedoch empfohlen, diese Warnung als Fehler zu behandeln. Bei einem benutzerdefinierten Typ versucht der Compiler, die Konvertierungen zu verwenden, die Sie in der Klassendefinition angegeben haben. Wenn er keine zulässige Konvertierung finden kann, gibt der Compiler einen Fehler aus und kompiliert das Programm nicht. Weitere Informationen zu den Regeln, die die standardkonvertierungen steuern, finden Sie unter [Standardkonvertierungen](../cpp/standard-conversions.md). Weitere Informationen über benutzerdefinierte Konvertierungen finden Sie unter [User-Defined Conversions (C++ / CLI)](../dotnet/user-defined-conversions-cpp-cli.md).

### <a name="widening-conversions-promotion"></a>Erweiternde Konvertierungen (Heraufstufung)

Bei einer erweiternden Konvertierung wird ein Wert in einer kleineren Variable einer größeren Variable zugewiesen, ohne dass es zu einem Datenverlust kommt. Da erweiternde Konvertierungen immer sicher sind, führt der Compiler sie automatisch aus und gibt keine Warnungen aus. Die folgenden Konvertierungen sind erweiternde Konvertierungen.

|Von|Beschreibung|
|----------|--------|
|Alle signiert oder unsigniert ganzzahligen Typ außer **long long** oder **__int64**|**double**|
|**"bool"** oder **Char**|Ein beliebiger anderer integrierter Typ|
|**kurze** oder **"wchar_t"**|**Int**, **lange**, **long long**|
|**Int**, **lange**|**langes long**|
|**float**|**double**|

### <a name="narrowing-conversions-coercion"></a>Einschränkende Konvertierungen (Koersion)

Der Compiler führt einschränkende Konvertierungen implizit aus, warnt jedoch vor möglichem Datenverlust. Nehmen Sie diese Warnungen ernst. Wenn Sie sicher sind, dass kein Datenverlust auftritt, da die Werte in der größeren Variable immer in die kleinere Variable passen, fügen Sie eine explizite Umwandlung hinzu, damit der Compiler keine Warnung mehr ausgibt. Wenn Sie nicht genau wissen, ob die Konvertierung sicher ist, fügen Sie dem Code eine Laufzeitüberprüfung zur Handhabung des möglichen Datenverlusts hinzu, damit Ihr Programm keine falschen Ergebnisse erzeugt.

Jede Konvertierung von einem Gleitkommatyp zu einem ganzzahligen Typ ist eine einschränkende Konvertierung, da der Bruchteil des Gleitkommawerts verworfen wird und verloren geht.

Das folgende Codebeispiel zeigt einige implizite einschränkende Konvertierungen sowie die Warnungen, die der Compiler dafür ausgibt.

```cpp
int i = INT_MAX + 1; //warning C4307:'+':integral constant overflow
wchar_t wch = 'A'; //OK
char c = wch; // warning C4244:'initializing':conversion from 'wchar_t'
              // to 'char', possible loss of data
unsigned char c2 = 0xfffe; //warning C4305:'initializing':truncation from
                           // 'int' to 'unsigned char'
int j = 1.9f; // warning C4244:'initializing':conversion from 'float' to
              // 'int', possible loss of data
int k = 7.7; // warning C4244:'initializing':conversion from 'double' to
             // 'int', possible loss of data
```

### <a name="signed---unsigned-conversions"></a>Konvertierungen zwischen Typen mit und ohne Vorzeichen

Ein ganzzahliger Typ mit Vorzeichen und seine Entsprechung ohne Vorzeichen haben immer die gleiche Größe, sie unterscheiden sich jedoch in der Interpretation des Bitmusters für die Werttransformation. Das folgende Codebeispiel zeigt, was geschieht, wenn das gleiche Bitmuster als Wert mit Vorzeichen und als Wert ohne Vorzeichen interpretiert wird. Das sowohl in `num` als auch in `num2` gespeicherte Bitmuster weicht nie von dem in der Abbildung oben Gezeigten ab.

```cpp
using namespace std;
unsigned short num = numeric_limits<unsigned short>::max(); // #include <limits>
short num2 = num;
cout << "unsigned val = " << num << " signed val = " << num2 << endl;
// Prints: unsigned val = 65535 signed val = -1

// Go the other way.
num2 = -1;
num = num2;
cout << "unsigned val = " << num << " signed val = " << num2 << endl;
// Prints: unsigned val = 65535 signed val = -1
```

Beachten Sie, dass die Werte in beide Richtungen neu interpretiert werden. Wenn Ihr Programm seltsame Ergebnisse erzeugt, in denen das Vorzeichen des Werts anders als erwartet umgekehrt erscheint, suchen Sie nach impliziten Konvertierungen zwischen ganzzahligen Typen mit und ohne Vorzeichen. Im folgenden Beispiel, das Ergebnis des Ausdrucks (0 - 1) wird vom implizit konvertiert **Int** zu **ganze Zahl ohne Vorzeichen** ist bei im gespeichert `num`. Dies führt zu einer Neuinterpretation des Bitmusters.

```cpp
unsigned int u3 = 0 - 1;
cout << u3 << endl; // prints 4294967295
```

Der Compiler warnt nicht vor impliziten Konvertierungen zwischen ganzzahligen Typen mit und ohne Vorzeichen. Daher wird empfohlen, Konvertierungen zwischen Typen mit und ohne Vorzeichen grundsätzlich zu vermeiden. Wenn sie sich nicht vermeiden lassen, fügen Sie Ihrem Code eine Laufzeitüberprüfung hinzu, um festzustellen, ob der konvertierte Wert größer oder gleich Null und kleiner oder gleich dem maximalen Wert des Typs mit Vorzeichen ist. Werte in diesem Bereich werden von Typen mit Vorzeichen in Typen ohne Vorzeichen oder Typen ohne Vorzeichen in Typen mit Vorzeichen übertragen, ohne neu interpretiert zu werden.

### <a name="pointer-conversions"></a>Zeigerkonvertierungen

In vielen Ausdrücken wird ein Array im C-Format implizit in einen Zeiger auf das erste Element im Array konvertiert, und konstante Konvertierungen können automatisch ausgeführt werden. Dieser Prozess ist zwar sinnvoll, kann aber auch fehleranfällig sein. Das folgende fehlerhafte Codebeispiel erscheint z. B. unsinnig, wird aber dennoch in Visual C++ kompiliert und erzeugt das Ergebnis "p". Zuerst wird die literale Zeichenfolgenkonstante "Help" in einen `char*` konvertiert, der auf das erste Element des Arrays zeigt. Dieser Zeiger wird dann um drei Elemente erhöht, damit er auf das letzte Element "p" zeigt.

```cpp
char* s = "Help" + 3;
```

## <a name="explicit-conversions-casts"></a>Explizite Konvertierungen (Umwandlungen)

Mithilfe eines Umwandlungsvorgangs können Sie den Compiler anweisen, einen Wert eines bestimmten Typs in einen anderen Typ zu konvertieren. In einigen Fällen löst der Compiler einen Fehler aus, wenn die beiden Typen in keiner Beziehung zueinander stehen. In anderen Fällen wird jedoch kein Fehler ausgelöst, selbst wenn der Vorgang nicht typsicher ist. Verwenden Sie Umwandlungen möglichst selten, da Konvertierungen von einem Typ in einen anderen eine potenzielle Quelle für Programmfehler darstellen. Manchmal sind Umwandlungen jedoch erforderlich, und nicht alle Umwandlungen sind gleichermaßen gefährlich. Die Verwendung einer Umwandlung ist effektiv, wenn Ihr Code eine einschränkende Konvertierung ausführt und Sie wissen, dass die Konvertierung nicht dazu führt, dass Ihr Programm falsche Ergebnisse erzeugt. Dadurch erfährt der Compiler, dass Sie wissen, was Sie tun, und wird angewiesen, keine weiteren Warnungen mehr dazu auszugeben. Eine weitere Verwendungsmöglichkeit ist die Umwandlung von Zeigern auf eine abgeleitete Klasse in Zeiger auf eine Basisklasse. Eine weitere Verwendungsmöglichkeit besteht im Umwandeln der **const**- Ness einer Variablen an eine Funktion übergeben, die einen nicht erforderlich sind –**const** Argument. Die meisten dieser Umwandlungsvorgänge gehen mit gewissen Risiken einher.

Bei der Programmierung im C-Format wird der gleiche Umwandlungsoperator im C-Format für alle Arten von Umwandlungen verwendet.

```cpp
(int) x; // old-style cast, old-style syntax
int(x); // old-style cast, functional syntax
```

Der Umwandlungsoperator im C-Format ist mit dem Aufrufoperator () identisch und daher unauffällig im Code und leicht zu übersehen. Beide sind fehlerhaft, da sind schwer zu erkennen, auf einen Blick oder suchen Sie nach, und sie jedoch ausreichend unterschiedlich sind, um eine beliebige Kombination von Aufrufen **statische**, **const**, und **"reinterpret_cast"**. Zu ermitteln, was bei einer Umwandlung im alten Stil tatsächlich geschieht, kann kompliziert und fehleranfällig sein. Wenn eine Umwandlung erforderlich ist, empfiehlt es sich aus diesen Gründen, einen der folgenden C++-Umwandlungsoperatoren zu verwenden, die manchmal deutlich typsicherer sind und die Programmierabsicht genauer zum Ausdruck bringen:

- **"static_cast"**, Umwandlungen, die beim Kompilieren überprüft werden nur eine Uhrzeit. **"static_cast"** gibt einen Fehler zurück, wenn der Compiler erkennt, dass Sie versuchen, die Umwandlung zwischen Typen, die nicht vollständig kompatibel sind. Eine Verwendung für Umwandlungen zwischen Zeigern auf eine Basisklasse und Zeigern auf eine abgeleitete Klasse ist ebenfalls möglich. Für den Compiler ist jedoch nicht immer erkennbar, ob solche Konvertierungen zur Laufzeit sicher sind.

    ```cpp
    double d = 1.58947;
    int i = d;  // warning C4244 possible loss of data
    int j = static_cast<int>(d);       // No warning.
    string s = static_cast<string>(d); // Error C2440:cannot convert from
                                       // double to std:string

    // No error but not necessarily safe.
    Base* b = new Base();
    Derived* d2 = static_cast<Derived*>(b);
    ```

   Weitere Informationen finden Sie unter ["static_cast"](../cpp/static-cast-operator.md).

- **Dynamic_cast**, für die sichere, zur Laufzeit geprüfte Umwandlungen von Zeiger-auf eine Basisklasse in Zeiger auf eine abgeleitete. Ein **Dynamic_cast** ist sicherer als ein **"static_cast"** Typumwandlungen, aber die Runtime Kontrollkästchen verursacht zusätzlichen Aufwand.

    ```cpp
    Base* b = new Base();

    // Run-time check to determine whether b is actually a Derived*
    Derived* d3 = dynamic_cast<Derived*>(b);

    // If b was originally a Derived*, then d3 is a valid pointer.
    if(d3)
    {
       // Safe to call Derived method.
       cout << d3->DoSomethingMore() << endl;
    }
    else
    {
       // Run-time check failed.
       cout << "d3 is null" << endl;
    }

    //Output: d3 is null;
    ```

   Weitere Informationen finden Sie unter [Dynamic_cast](../cpp/dynamic-cast-operator.md).

- **const_cast-Operator**für entfernt Umwandeln der **const**- Ness einer Variablen oder Konvertieren einer nicht--**const** Variable **const**. Umwandeln **const**-Ness mithilfe dieses Operators ist nur als fehleranfällig wie eine C-Format umgewandelt werden, außer dass mit **Const Cast** Sie weniger wahrscheinlich, dass Sie die Umwandlung versehentlich ausgeführt werden. Manchmal müssen Sie das Umwandeln der **const**-Ness einer Variablen, z. B. zum Übergeben einer **const** -Variablen an eine Funktion, die nicht akzeptiert**const** Parameter. Das folgende Beispiel zeigt die dazu erforderliche Vorgehensweise.

    ```cpp
    void Func(double& d) { ... }
    void ConstCast()
    {
       const double pi = 3.14;
       Func(const_cast<double&>(pi)); //No error.
    }
    ```

   Weitere Informationen finden Sie unter ["const_cast"](../cpp/const-cast-operator.md).

- **"reinterpret_cast"** für Umwandlungen zwischen unzusammenhängenden Typen wie **Zeiger** zu **Int**.

    > [!NOTE]
    >  Dieser Umwandlungsoperator wird so oft verwendet wie die übrigen Operatoren, und er ist u. U. nicht auf andere Compiler übertragbar.

   Im folgende Beispiel wird veranschaulicht, wie **"reinterpret_cast"** unterscheidet sich von **"static_cast"**.

    ```cpp
    const char* str = "hello";
    int i = static_cast<int>(str);//error C2440: 'static_cast' : cannot
                                  // convert from 'const char *' to 'int'
    int j = (int)str; // C-style cast. Did the programmer really intend
                      // to do this?
    int k = reinterpret_cast<int>(str);// Programming intent is clear.
                                       // However, it is not 64-bit safe.
    ```

   Weitere Informationen finden Sie unter [Reinterpret_cast-Operator](../cpp/reinterpret-cast-operator.md).

## <a name="see-also"></a>Siehe auch

[C++-Typsystem](../cpp/cpp-type-system-modern-cpp.md)<br/>
[Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)