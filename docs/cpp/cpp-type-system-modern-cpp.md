---
title: C++ type system
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
ms.openlocfilehash: 1f12f7505438dc995aaf8a045fd903488e9ff092
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246600"
---
# <a name="c-type-system"></a>C++ type system

The concept of *type* is very important in C++. Jede Variable, jedes Funktionsargument und jeder Rückgabewert muss über einen Typ verfügen, um kompiliert werden zu können. Außerdem wird jedem Ausdruck (einschließlich Literalwerten) vom Compiler implizit ein Typ angegeben, bevor der Ausdruck ausgewertet wird. Some examples of types include **int** to store integral values, **double** to store floating-point values (also known as *scalar* data types), or the Standard Library class [std::basic_string](../standard-library/basic-string-class.md) to store text. You can create your own type by defining a **class** or **struct**. Der Typ gibt den Speicher an, der für die Variable (oder das Ausdrucksergebnis) zugeordnet ist, die Wertarten, die in dieser Variablen gespeichert werden können, wie diese Werte (als Bitmuster) interpretiert werden, und die Vorgänge, die darauf ausgeführt werden können. In diesem Artikel ist eine informelle Übersicht der Hauptfunktionen des C++-Typsystems enthalten.

## <a name="terminology"></a>Terminologie

**Variable**: The symbolic name of a quantity of data so that the name can be used to access the data it refers to throughout the scope of the code where it is defined. In C++, *variable* is generally used to refer to instances of scalar data types, whereas instances of other types are usually called *objects*.

**Object**: For simplicity and consistency, this article uses the term *object* to refer to any instance of a class or structure, and when it is used in the general sense includes all types, even scalar variables.

**POD type** (plain old data): This informal category of data types in C++ refers to types that are scalar (see the Fundamental types section) or are *POD classes*. Eine POD-Klasse verfügt über keine statischen Datenmember, die nicht auch PODs sind. Sie verfügt über keine benutzerdefinierten Konstruktoren, keine benutzerdefinierten Destruktoren oder keine benutzerdefinierten Zuweisungsoperatoren. Darüber hinaus verfügt eine POD-Klasse über keine virtuellen Funktionen, keine Basisklasse und keine privaten oder geschützten nicht statischen Datenmember. POD-Typen werden häufig für externen Datenaustausch verwendet, z. B. mit einem in der Programmiersprache C (die nur über POD-Typen verfügt) geschriebenen Modul.

## <a name="specifying-variable-and-function-types"></a>Angeben von Variablen und Funktionstypen

C++ is a *strongly typed* language and it is also *statically-typed*; every object has a type and that type never changes (not to be confused with static data objects).
**When you declare a variable** in your code, you must either specify its type explicitly, or use the **auto** keyword to instruct the compiler to deduce the type from the initializer.
**When you declare a function** in your code, you must specify the type of each argument and its return value, or **void** if no value is returned by the function. Die Verwendung von Funktionsvorlagen, die Argumente beliebiger Typen ermöglichen stellen eine Ausnahme dar.

Nachdem Sie eine Variable deklariert haben, können Sie den Typ zu einem späteren Zeitpunkt nicht ändern. Sie können allerdings den Wert der Variablen oder den Rückgabewert einer Funktion in eine andere Variable eines anderen Typs kopieren. Such operations are called *type conversions*, which are sometimes necessary but are also potential sources of data loss or incorrectness.

Wenn Sie eine Variable des POD-Typs deklarieren, empfehlen wir dringend, sie zu initialisieren, ihr also einen Anfangswert zu geben. Wenn Sie eine Variable initialisieren, verfügt sie über einen "Garbage"-Wert, der aus allen Bits dessen besteht, das sich grade zuvor an diesem Speicherort befand. Sich an diesen Aspekt von C++ zu erinnern ist, insbesondere dann wichtig, wenn Sie vorher in einer anderen Sprache geschrieben haben, bei der die Initialisierung für Sie bearbeitet wurde. Wenn Sie eine Variable eines Typs deklarieren, der keine POD-Klasse ist, wird die Initialisierung vom Konstruktor behandelt.

Im folgenden Beispiel werden einige einfache Variablendeklarationen dargestellt, jeweils mit einigen Beschreibungen. In dem Beispiel wird auch die Verwendung der Typinformationen durch den Compiler dargestellt, um bestimmte nachfolgende Vorgänge in den Variablen zuzulassen oder zu verweigern.

```cpp
int result = 0;              // Declare and initialize an integer.
double coefficient = 10.8;   // Declare and initialize a floating
                             // point value.
auto name = "Lady G.";       // Declare a variable and let compiler
                             // deduce the type.
auto address;                // error. Compiler cannot deduce a type
                             // without an intializing value.
age = 12;                    // error. Variable declaration must
                             // specify a type or use auto!
result = "Kenny G.";         // error. Can’t assign text to an int.
string result = "zero";      // error. Can’t redefine a variable with
                             // new type.
int maxValue;                // Not recommended! maxValue contains
                             // garbage bits until it is initialized.
```

## <a name="fundamental-built-in-types"></a>Grundlegende (integrierte) Typen

Im Gegensatz zu einigen Sprachen gibt es bei C++ keinen universellen Basistyp, von dem alle anderen Typen abgeleitet werden. The language includes many *fundamental types*, also known as *built-in types*. This includes numeric types such as **int**, **double**, **long**, **bool**, plus the **char** and **wchar_t** types for ASCII and UNICODE characters, respectively. Most fundamental types (except **bool**, **double**, **wchar_t** and related types) all have unsigned versions, which modify the range of values that the variable can store. For example, an **int**, which stores a 32-bit signed integer, can represent a value from -2,147,483,648 to 2,147,483,647. An **unsigned int**, which is also stored as 32-bits, can store a value from 0 to 4,294,967,295. Die Gesamtzahl der möglichen Werte ist in beiden Fällen gleich, nur der Bereich ist anders.

Die grundlegenden Typen werden vom Compiler erkannt, der über interne Regeln verfügt, die bestimmen, welche Vorgänge auf den Typen ausgeführt werden können und wie sie in andere grundlegenden Typen konvertiert werden können. For a complete list of built-in types and their size and numeric limits, see [Fundamental Types](../cpp/fundamental-types-cpp.md).

In der folgende Abbildung wird die relative Größe der integrierten Datentypen dargestellt:

![Size in bytes of built&#45;in types](../cpp/media/built-intypesizes.png "Size in bytes of built&#45;in types")

In der folgenden Tabelle werden die am häufigsten verwendeten grundlegenden Typen aufgelistet:

|Geben Sie Folgendes ein:|Größe|Kommentar|
|----------|----------|-------------|
|int|4 Bytes|Die Standardauswahl für ganzzahlige Werte.|
|Doppelt|8 Bytes|Die Standardauswahl für Gleitkommawerte.|
|bool|1 Byte|Stellt Werte dar, die entweder wahr oder falsch sein können.|
|char|1 Byte|Verwenden Sie sie für ASCII-Zeichen in Zeichenfolgen im älteren C-Format oder in std::string Objekten, die nie in den UNICODE konvertiert werden müssen.|
|wchar_t|2 Bytes|Stellt "breite" Zeichenwerte dar, die in den UNICODE-Format codiert werden (UTF-16 bei Windows, andere Betriebssysteme können abweichen). Dies ist der Zeichentyp, der in Zeichenfolgen des Typs `std::wstring` verwendet wird.|
|unsigned&nbsp;char|1 Byte|C++ verfügt über keine integrierten `byte`-Typen.  Verwenden Sie "char" ohne Vorzeichen, um einen Bytewert darzustellen.|
|unsigned int|4 Bytes|Die Standardauswahl für Bitflags.|
|long long|8 Bytes|Stellt sehr große ganzzahlige Werte dar.|

## <a name="the-void-type"></a>Der void-Typ

The **void** type is a special type; you cannot declare a variable of type **void**, but you can declare a variable of type __void \*__ (pointer to **void**), which is sometimes necessary when allocating raw (un-typed) memory. However, pointers to **void** are not type-safe and generally their use is strongly discouraged in modern C++. In a function declaration, a **void** return value means that the function does not return a value; this is a common and acceptable use of **void**. While the C language required functions that have zero parameters to declare **void** in the parameter list, for example, `fou(void)`, this practice is discouraged in modern C++ and should be declared `fou()`. For more information, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="const-type-qualifier"></a>const-Typqualifizierer

Alle integrierten oder benutzerdefinierten Typen werden vom const-Schlüsselwort qualifiziert. Additionally, member functions may be **const**-qualified and even **const**-overloaded. The value of a **const** type cannot be modified after it is initialized.

```cpp

const double PI = 3.1415;
PI = .75 //Error. Cannot modify const variable.
```

The **const** qualifier is used extensively in function and variable declarations and "const correctness" is an important concept in C++; essentially it means to use **const** to guarantee, at compile time, that values are not modified unintentionally. For more information, see [const](../cpp/const-cpp.md).

A **const** type is distinct from its non-const version; for example, **const int** is a distinct type from **int**. You can use the C++ **const_cast** operator on those rare occasions when you must remove *const-ness* from a variable. For more information, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="string-types"></a>String-Typen

Strictly speaking, the C++ language has no built-in string type; **char** and **wchar_t** store single characters - you must declare an array of these types to approximate a string, adding a terminating null value (for example, ASCII `'\0'`) to the array element one past the last valid character (also called a *C-style string*). Für Zeichenfolgen im C-Stil ist das Schreiben von viel mehr Code oder die Verwendung externer Hilfsprogrammbibliotheken für Zeichenfolgefunktionen erforderlich. But in modern C++, we have the Standard Library types `std::string` (for 8-bit **char**-type character strings) or `std::wstring` (for 16-bit **wchar_t**-type character strings). These C++ Standard Library containers can be thought of as native string types because they are part of the standard libraries that are included in any compliant C++ build environment. Verwenden Sie einfach die `#include <string>`-Anweisung, um diese Typen im Programm bereitzustellen. (If you are using MFC or ATL, the CString class is also available, but is not part of the C++ standard.) The use of null-terminated character arrays (the C-style strings previously mentioned) is strongly discouraged in modern C++.

## <a name="user-defined-types"></a>Benutzerdefinierte Typen

When you define a **class**, **struct**, **union**, or **enum**, that construct is used in the rest of your code as if it were a fundamental type. Es verfügt über eine bekannte Größe im Arbeitsspeicher und bestimmte Regeln zur Verwendung gelten zur Kompilierzeitüberprüfung und zur Laufzeit für die Lebensdauer des Programms. Die wichtigsten Unterschiede zwischen den grundlegenden integrierten Typen und den benutzerdefinierten Typen sind wie folgt:

- Der Compiler verfügt über kein integriertes Wissen zu einem benutzerdefinierten Typ. It learns of the type when it first encounters the definition during the compilation process.

- Sie geben an, welche Vorgänge auf dem Typ ausgeführt werden können und wie er in andere Typen konvertiert werden kann, indem Sie (durch Überladen) die entsprechenden Operatoren entweder als Klassenmember oder als Funktionen definieren. For more information, see [Function Overloading](function-overloading.md)

## <a name="pointer-types"></a>Zeigertypen

Zurückgehend zur frühesten Versionen der Programmiersprache C, können Sie in C++ weiterhin eine Variable eines Zeigertyps deklarieren, indem Sie den speziellen Deklarator `*` (Sternchen) verwenden. Ein Zeigertyp speichert die Adresse des Speicherorts im Arbeitsspeicher, in dem der tatsächliche Datenwert gespeichert wird. In modern C++, these are referred to as *raw pointers*, and are accessed in your code through special operators `*` (asterisk) or `->` (dash with greater-than). This is called *dereferencing*, and which one that you use depends on whether you are dereferencing a pointer to a scalar or a pointer to a member in an object. Das Arbeiten mit Zeigertypen ist seit Langem einer der schwierigsten und verwirrendsten Aspekte bei der Programmentwicklung mit C- und C++. This section outlines some facts and practices to help use raw pointers if you want to, but in modern C++ it’s no longer required (or recommended) to use raw pointers for object ownership at all, due to the evolution of the [smart pointer](../cpp/smart-pointers-modern-cpp.md) (discussed more at the end of this section). Es ist dennoch hilfreich und sicher, unformatierte Zeiger für das Beobachten von Objekten zu verwenden. Wenn Sie sie aber für Objektbesitz verwenden müssen, sollten Sie dies mit Vorsicht tun und sich genau überlegen, wie die Objekte in deren Besitz erstellt und zerstört werden.

Als Erstes sollten Sie wissen, dass bei der Deklaration einer unformatierter Zeigervariable nur Speicher zugeordnet wird, der zum Speichern der Adresse des Speicherorts belegt wird, auf den der Zeiger verweist, wenn er dereferenziert wird. Allocation of the memory for the data value itself (also called *backing store*) is not yet allocated. Das heißt, indem Sie eine unformatierte Zeigervariable deklarieren, erstellen Sie eine Speicheradressenvariable, keine tatsächliche Datenvariable. Das Dereferenzieren einer Zeigervariable vor der Sicherstellung, dass sie eine gültige Adresse auf einen Sicherungsspeicher enthält, verursacht nicht definiertes Verhalten (normalerweise ein schwerwiegender Fehler) im Programm. Im folgenden Beispiel wird die Verwendung dieses Fehlertyps veranschaulicht.

```cpp
int* pNumber;       // Declare a pointer-to-int variable.
*pNumber = 10;      // error. Although this may compile, it is
                    // a serious error. We are dereferencing an
                    // uninitialized pointer variable with no
                    // allocated memory to point to.
```

Das Beispiel dereferenziert einen Zeigertyp, ohne dass Arbeitsspeicher zum Speichern der tatsächlichen Ganzzahldaten belegt ist oder dass ein gültiger Speicherort zu zugewiesen wurde. Der folgende Code korrigiert diese Fehler:

```cpp
    int number = 10;          // Declare and initialize a local integer
                              // variable for data backing store.
    int* pNumber = &number;   // Declare and initialize a local integer
                              // pointer variable to a valid memory
                              // address to that backing store.
...
    *pNumber = 41;            // Dereference and store a new value in
                              // the memory pointed to by
                              // pNumber, the integer variable called
                              // "number". Note "number" was changed, not
                              // "pNumber".
```

Im korrigierten Codebeispiel wird lokaler Stapelarbeitsspeicher zum Erstellen von Sicherungsspeicher, auf den `pNumber` verweist, verwendet. Wir verwenden der Einfachheit halber einen grundlegenden Typ. In practice, the backing store for pointers are most often user-defined types that are dynamically-allocated in an area of memory called the *heap* (or *free store*) by using a **new** keyword expression (in C-style programming, the older `malloc()` C runtime library function was used). Once allocated, these variables are usually referred to as objects, especially if they are based on a class definition. Memory that is allocated with **new** must be deleted by a corresponding **delete** statement (or, if you used the `malloc()` function to allocate it, the C runtime function `free()`).

However, it is easy to forget to delete a dynamically-allocated object- especially in complex code, which causes a resource bug called a *memory leak*. Aus diesem Grund wird vor der Verwendung unformatierter Zeigern in modernem C++ abgesehen. It is almost always better to wrap a raw pointer in a [smart pointer](../cpp/smart-pointers-modern-cpp.md), which will automatically release the memory when its destructor is invoked (when the code goes out of scope for the smart pointer); by using smart pointers you virtually eliminate a whole class of bugs in your C++ programs. Im folgenden Beispiel wird angenommen, dass `MyClass` ein benutzerdefinierter Typ ist, der eine öffentliche Methode `DoSomeWork();` umfasst.

```cpp
void someFunction() {
    unique_ptr<MyClass> pMc(new MyClass);
    pMc->DoSomeWork();
}
  // No memory leak. Out-of-scope automatically calls the destructor
  // for the unique_ptr, freeing the resource.
```

For more information about smart pointers, see [Smart Pointers](../cpp/smart-pointers-modern-cpp.md).

For more information about pointer conversions, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

For more information about pointers in general, see [Pointers](../cpp/pointers-cpp.md).

## <a name="windows-data-types"></a>Windows-Datentypen

In der klassischen Win32-Programmierung für C und C++ verwenden die meisten Funktionen Windows-spezifische Typdefinitionen und #define-Makros (die in `windef.h` definiert sind), um die Typen von Parametern und Rückgabewerten anzugeben. These Windows data types are mostly just special names (aliases) given to C/C++ built-in types. For a complete list of these typedefs and preprocessor definitions, see [Windows Data Types](/windows/win32/WinProg/windows-data-types). Einige dieser Typdefinitionen, wie HRESULT und LCID, sind nützlich und beschreibend. Andere, wie INT, haben keine besondere Bedeutung und sind nur Alias für grundlegende C++-Typen. Weitere Windows-Datentypen haben Namen, die seit den Tagen der C-Programmierung und der 16-Bit-Prozessoren beibehalten werden. Sie haben keinen Zweck oder keine Bedeutung mehr bei moderner Hardware oder Betriebssystemen. There are also special data types associated with the Windows Runtime Library, listed as [Windows Runtime base data types](/windows/win32/WinRT/base-data-types). Für modernes C++ gilt die allgemeine Richtlinie, die grundlegenden C++-Typen vorzuziehen, es sei denn, mit dem Windows-Typ wird zusätzliche Bedeutung über die Interpretationsweise des Werts kommuniziert.

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen zum Typsystem von C++ finden Sie in den folgenden Themen.

|||
|-|-|
|[Werttypen](../cpp/value-types-modern-cpp.md)|Describes *value types* along with issues relating to their use.|
|[Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md)|Beschreibt allgemeine Typkonvertierungsprobleme und zeigt, wie sie vermieden werden.|

## <a name="see-also"></a>Siehe auch

[Welcome back to C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
