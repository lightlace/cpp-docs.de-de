---
title: C++-Typsystem
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
# <a name="c-type-system"></a>C++-Typsystem

Das Konzept des *Typs* ist in C++sehr wichtig. Jede Variable, jedes Funktionsargument und jeder Rückgabewert muss über einen Typ verfügen, um kompiliert werden zu können. Außerdem wird jedem Ausdruck (einschließlich Literalwerten) vom Compiler implizit ein Typ angegeben, bevor der Ausdruck ausgewertet wird. Einige Beispiele für Typen sind z. a. **int** zum Speichern ganzzahliger Werte, **Double** zum Speichern von Gleit Komma Werten (auch als *skalare* Datentypen bezeichnet) oder die Standard Bibliotheks Klasse [Std:: basic_string](../standard-library/basic-string-class.md) zum Speichern von Text. Sie können einen eigenen Typ erstellen, indem Sie eine **Klasse** oder **Struktur**definieren. Der Typ gibt den Speicher an, der für die Variable (oder das Ausdrucksergebnis) zugeordnet ist, die Wertarten, die in dieser Variablen gespeichert werden können, wie diese Werte (als Bitmuster) interpretiert werden, und die Vorgänge, die darauf ausgeführt werden können. In diesem Artikel ist eine informelle Übersicht der Hauptfunktionen des C++-Typsystems enthalten.

## <a name="terminology"></a>Terminologie

**Variable**: der symbolische Name einer Datenmenge, sodass der Name für den Zugriff auf die Daten verwendet werden kann, auf die er im gesamten Code Bereich verweist, in dem er definiert ist. In C++wird im Allgemeinen eine *Variable* verwendet, um auf Instanzen von skalaren Datentypen zu verweisen, wohingegen Instanzen anderer Typen normalerweise als *Objekte*bezeichnet werden.

**Objekt**: aus Gründen der Einfachheit und Konsistenz wird in diesem Artikel der Begriff *Objekt* verwendet, um auf eine beliebige Instanz einer Klasse oder Struktur zu verweisen. wenn diese im allgemeinen Sinn verwendet wird, sind alle Typen, sogar skalare Variablen, enthalten.

**POD-Typ** (Plain Old Data): diese informelle Kategorie von Datentypen C++ in bezieht sich auf skalare Typen (siehe Abschnitt "grundlegende Typen") oder " *Pod-Klassen*". Eine POD-Klasse verfügt über keine statischen Datenmember, die nicht auch PODs sind. Sie verfügt über keine benutzerdefinierten Konstruktoren, keine benutzerdefinierten Destruktoren oder keine benutzerdefinierten Zuweisungsoperatoren. Darüber hinaus verfügt eine POD-Klasse über keine virtuellen Funktionen, keine Basisklasse und keine privaten oder geschützten nicht statischen Datenmember. POD-Typen werden häufig für externen Datenaustausch verwendet, z. B. mit einem in der Programmiersprache C (die nur über POD-Typen verfügt) geschriebenen Modul.

## <a name="specifying-variable-and-function-types"></a>Angeben von Variablen und Funktionstypen

C++ist eine Sprache mit *starker Typisierung* und auch *statisch typisiert*. jedes Objekt weist einen Typ auf, und dieser Typ ändert sich nie (nicht mit statischen Datenobjekten verwechselt).
**Wenn Sie im Code eine Variable deklarieren** , müssen Sie entweder den Typ explizit angeben oder das Schlüsselwort " **Auto** " verwenden, um den Compiler anzuweisen, den Typ aus dem Initialisierer abzuleiten.
**Wenn Sie eine Funktion im Code deklarieren** , müssen Sie den Typ jedes Arguments und dessen Rückgabewerts angeben oder **void** , wenn kein Wert von der Funktion zurückgegeben wird. Die Verwendung von Funktionsvorlagen, die Argumente beliebiger Typen ermöglichen stellen eine Ausnahme dar.

Nachdem Sie eine Variable deklariert haben, können Sie den Typ zu einem späteren Zeitpunkt nicht ändern. Sie können allerdings den Wert der Variablen oder den Rückgabewert einer Funktion in eine andere Variable eines anderen Typs kopieren. Solche Vorgänge werden als *Typkonvertierungen*bezeichnet, die manchmal erforderlich sind, aber auch potenzielle Quellen für Datenverlust oder Unrichtigkeit sind.

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

Im Gegensatz zu einigen Sprachen gibt es bei C++ keinen universellen Basistyp, von dem alle anderen Typen abgeleitet werden. Die Sprache umfasst viele *grundlegende Typen*, die auch als *integrierte Typen*bezeichnet werden. Dazu zählen numerische Typen wie **int**, **Double**, **Long**, **bool**sowie die **char** -und **wchar_t** -Typen für ASCII-und Unicode-Zeichen. Die meisten grundlegenden Typen (außer " **bool**", " **Double**", " **wchar_t** " und verwandte Typen) haben alle nicht signierte Versionen, die den Wertebereich ändern, den die Variable speichern kann. Ein **int**-Wert, der eine 32-Bit-Ganzzahl mit Vorzeichen speichert, kann z. b. einen Wert zwischen-2.147.483.648 und 2.147.483.647 darstellen. Ein **int**-Wert ohne Vorzeichen, der auch als 32-Bits gespeichert wird, kann einen Wert zwischen 0 und 4.294.967.295 speichern. Die Gesamtzahl der möglichen Werte ist in beiden Fällen gleich, nur der Bereich ist anders.

Die grundlegenden Typen werden vom Compiler erkannt, der über interne Regeln verfügt, die bestimmen, welche Vorgänge auf den Typen ausgeführt werden können und wie sie in andere grundlegenden Typen konvertiert werden können. Eine umfassende Liste der integrierten Typen und ihrer Größe und numerischen Grenzwerte finden Sie unter [grundlegende Typen](../cpp/fundamental-types-cpp.md).

In der folgende Abbildung wird die relative Größe der integrierten Datentypen dargestellt:

![Größe von integrierten&#45;Typen in Byte](../cpp/media/built-intypesizes.png "Größe von integrierten&#45;Typen in Byte")

In der folgenden Tabelle werden die am häufigsten verwendeten grundlegenden Typen aufgelistet:

|Typ|Größe|Anmerkungen|
|----------|----------|-------------|
|int|4 Bytes|Die Standardauswahl für ganzzahlige Werte.|
|double|8 Bytes|Die Standardauswahl für Gleitkommawerte.|
|bool|1 Byte|Stellt Werte dar, die entweder wahr oder falsch sein können.|
|char|1 Byte|Verwenden Sie sie für ASCII-Zeichen in Zeichenfolgen im älteren C-Format oder in std::string Objekten, die nie in den UNICODE konvertiert werden müssen.|
|wchar_t|2 Bytes|Stellt "breite" Zeichenwerte dar, die in den UNICODE-Format codiert werden (UTF-16 bei Windows, andere Betriebssysteme können abweichen). Dies ist der Zeichentyp, der in Zeichenfolgen des Typs `std::wstring` verwendet wird.|
|nicht signiertes&nbsp;Char|1 Byte|C++ verfügt über keine integrierten `byte`-Typen.  Verwenden Sie "char" ohne Vorzeichen, um einen Bytewert darzustellen.|
|unsigned int|4 Bytes|Die Standardauswahl für Bitflags.|
|long long|8 Bytes|Stellt sehr große ganzzahlige Werte dar.|

## <a name="the-void-type"></a>Der void-Typ

Der **void** -Typ ist ein spezieller Typ. Sie können eine Variable vom Typ " **void**" nicht deklarieren, aber Sie können eine Variable vom Typ " __void \*__ (Zeiger auf" **void**") deklarieren, was manchmal notwendig ist, wenn Sie unformatierten (nicht typisierten) Arbeitsspeicher zuordnen Zeiger auf " **void** " sind jedoch nicht typsicher, und in der Regel wird in der modernen C++Verwendung dringend davon abgeraten. In einer Funktionsdeklaration bedeutet der Rückgabewert **void** , dass die Funktion keinen Wert zurückgibt. Dies ist eine gängige und akzeptable Verwendung von **void**. Obwohl in der Programmiersprache C Funktionen erforderlich sind, die NULL-Parameter aufweisen, um **void** in der Parameterliste zu deklarieren (z. b C++ . `fou(void)`), wird diese Vorgehensweise in modernen und sollte als `fou()`deklariert werden. Weitere Informationen finden Sie unter [Typkonvertierungen und Typsicherheit](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="const-type-qualifier"></a>const-Typqualifizierer

Alle integrierten oder benutzerdefinierten Typen werden vom const-Schlüsselwort qualifiziert. Darüber hinaus können Element Funktionen **konstant**qualifiziert und sogar **konstant**überlastet werden. Der Wert eines **Konstanten** Typs kann nicht geändert werden, nachdem er initialisiert wurde.

```cpp

const double PI = 3.1415;
PI = .75 //Error. Cannot modify const variable.
```

Der **Konstante** Qualifizierer wird in Funktions-und Variablen Deklarationen ausführlich verwendet, und "Konstante Richtigkeit" ist ein C++wichtiges Konzept in; im Grunde bedeutet **dies, dass** bei der Kompilierung sichergestellt wird, dass die Werte nicht unbeabsichtigt geändert werden. Weitere Informationen finden Sie unter [konstant](../cpp/const-cpp.md).

Ein **Konst** -Typ unterscheidet sich von seiner nicht konstanten Version. Beispielsweise ist " **Konstanten int** " ein eindeutiger Typ von " **int**". Sie können den C++ **const_cast** -Operator in seltenen Fällen verwenden, wenn Sie die *Konstante aus einer* Variablen entfernen müssen. Weitere Informationen finden Sie unter [Typkonvertierungen und Typsicherheit](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="string-types"></a>String-Typen

Streng genommen hat die C++ Sprache keinen integrierten Zeichen foldetyp. Zeichen für **char** und **wchar_t** Store: Sie müssen ein Array dieser Typen deklarieren, um eine Zeichenfolge zu finden, und dem Array Element einen NULL-Beendigungs Wert (z. b. ASCII `'\0'`) hinzufügen, der hinter dem letzten gültigen Zeichen (auch als Zeichenfolge im *C-Stil*bezeichnet) liegt. Für Zeichenfolgen im C-Stil ist das Schreiben von viel mehr Code oder die Verwendung externer Hilfsprogrammbibliotheken für Zeichenfolgefunktionen erforderlich. In modernen C++haben wir jedoch die Standard Bibliothekstypen `std::string` (für Zeichen folgen mit 8 **-Bit-** Zeichen folgen) oder `std::wstring` (bei 16-Bit-Zeichen folgen vom Typ " **wchar_t**"). Diese C++ Standard Bibliotheks Container können als systemeigene Zeichen folgen Typen betrachtet werden, da Sie Teil der Standardbibliotheken sind, die in einer beliebigen C++ kompatiblen Buildumgebung enthalten sind. Verwenden Sie einfach die `#include <string>`-Anweisung, um diese Typen im Programm bereitzustellen. (Wenn Sie MFC oder ATL verwenden, ist die CString-Klasse ebenfalls verfügbar, aber nicht Teil des C++ Standards.) Die Verwendung von auf NULL endenden Zeichen Arrays (die zuvor erwähnten Zeichen folgen im C-Format) wird in C++modernen nicht dringend empfohlen.

## <a name="user-defined-types"></a>Benutzerdefinierte Typen

Wenn Sie eine **Klasse**, **Struktur**, **Union**oder Enumeration definieren **, wird dieses**Konstrukt im restlichen Code verwendet, als ob es sich um einen grundlegenden Typ handelt. Es verfügt über eine bekannte Größe im Arbeitsspeicher und bestimmte Regeln zur Verwendung gelten zur Kompilierzeitüberprüfung und zur Laufzeit für die Lebensdauer des Programms. Die wichtigsten Unterschiede zwischen den grundlegenden integrierten Typen und den benutzerdefinierten Typen sind wie folgt:

- Der Compiler verfügt über kein integriertes Wissen zu einem benutzerdefinierten Typ. Es erfährt den Typ, wenn er während des Kompilierungsprozesses zum ersten Mal auf die Definition trifft.

- Sie geben an, welche Vorgänge auf dem Typ ausgeführt werden können und wie er in andere Typen konvertiert werden kann, indem Sie (durch Überladen) die entsprechenden Operatoren entweder als Klassenmember oder als Funktionen definieren. Weitere Informationen finden Sie unter [Funktions Überladung](function-overloading.md) .

## <a name="pointer-types"></a>Zeigertypen

Zurückgehend zur frühesten Versionen der Programmiersprache C, können Sie in C++ weiterhin eine Variable eines Zeigertyps deklarieren, indem Sie den speziellen Deklarator `*` (Sternchen) verwenden. Ein Zeigertyp speichert die Adresse des Speicherorts im Arbeitsspeicher, in dem der tatsächliche Datenwert gespeichert wird. In modernen C++werden diese als unformatierte *Zeiger*bezeichnet, und der Zugriff erfolgt in Ihrem Code über spezielle Operatoren `*` (Sternchen) oder `->` (Dash mit größer als). Dies wird als *Dereferenzierung*bezeichnet, und welches Element Sie verwenden, hängt davon ab, ob Sie einen Zeiger auf einen Skalar oder einen Zeiger auf einen Member in einem Objekt dereferenzieren. Das Arbeiten mit Zeigertypen ist seit Langem einer der schwierigsten und verwirrendsten Aspekte bei der Programmentwicklung mit C- und C++. In diesem Abschnitt werden einige Fakten und Verfahren beschrieben, die Ihnen bei der Verwendung von unformatierten Zeigern helfen, wenn Sie möchten, aber in modernen C++ Daten ist es nicht mehr erforderlich (oder empfohlen), unformatierte Zeiger für den Besitz von Objekten zu verwenden, da der [intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md) (am Ende dieses Abschnitts ausführlicher erläutert wird). Es ist dennoch hilfreich und sicher, unformatierte Zeiger für das Beobachten von Objekten zu verwenden. Wenn Sie sie aber für Objektbesitz verwenden müssen, sollten Sie dies mit Vorsicht tun und sich genau überlegen, wie die Objekte in deren Besitz erstellt und zerstört werden.

Als Erstes sollten Sie wissen, dass bei der Deklaration einer unformatierter Zeigervariable nur Speicher zugeordnet wird, der zum Speichern der Adresse des Speicherorts belegt wird, auf den der Zeiger verweist, wenn er dereferenziert wird. Die Speicher Belegung für den Daten Wert selbst (auch als *Sicherungs Speicher*bezeichnet) wurde noch nicht zugeordnet. Das heißt, indem Sie eine unformatierte Zeigervariable deklarieren, erstellen Sie eine Speicheradressenvariable, keine tatsächliche Datenvariable. Das Dereferenzieren einer Zeigervariable vor der Sicherstellung, dass sie eine gültige Adresse auf einen Sicherungsspeicher enthält, verursacht nicht definiertes Verhalten (normalerweise ein schwerwiegender Fehler) im Programm. Im folgenden Beispiel wird die Verwendung dieses Fehlertyps veranschaulicht.

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

Im korrigierten Codebeispiel wird lokaler Stapelarbeitsspeicher zum Erstellen von Sicherungsspeicher, auf den `pNumber` verweist, verwendet. Wir verwenden der Einfachheit halber einen grundlegenden Typ. In der Praxis handelt es sich bei dem Sicherungs Speicher für Zeiger meistens um benutzerdefinierte Typen, die mithilfe eines **neuen** Schlüsselwort Ausdrucks (bei der c-Programmierung, der älteren `malloc()` c-Lauf Zeit Bibliotheksfunktion) dynamisch in einem Speicherbereich mit dem Namen *Heap* (oder *freiem*Speicher) zugeordnet werden. Nach der Zuordnung werden diese Variablen normalerweise als Objekte bezeichnet, insbesondere, wenn Sie auf einer Klassendefinition basieren. Arbeitsspeicher, der mit **New** zugewiesen wird, muss durch eine entsprechende **Delete** -Anweisung gelöscht werden (oder, wenn Sie die `malloc()`-Funktion verwendet haben, um diese zuzuweisen, die C-Lauf Zeitfunktion `free()`).

Es ist jedoch leicht zu vergessen, ein dynamisch zugeordneter Objekt zu löschen, insbesondere in komplexem Code, der einen Ressourcen Fehler auslöst, der als *Speicher*Fehler bezeichnet wird. Aus diesem Grund wird vor der Verwendung unformatierter Zeigern in modernem C++ abgesehen. Es ist fast immer besser, einen rohzeiger in einen [intelligenten Zeiger](../cpp/smart-pointers-modern-cpp.md)zu umschließen, der den Speicher automatisch freigibt, wenn der Dekonstruktor aufgerufen wird (wenn der Code den Gültigkeitsbereich des intelligenten Zeigers verlässt). mithilfe von intelligenten Zeigern eliminieren Sie praktisch eine ganze Klasse von Fehlern in C++ ihren Programmen. Im folgenden Beispiel wird angenommen, dass `MyClass` ein benutzerdefinierter Typ ist, der eine öffentliche Methode `DoSomeWork();` umfasst.

```cpp
void someFunction() {
    unique_ptr<MyClass> pMc(new MyClass);
    pMc->DoSomeWork();
}
  // No memory leak. Out-of-scope automatically calls the destructor
  // for the unique_ptr, freeing the resource.
```

Weitere Informationen zu intelligenten Zeigern finden Sie unter [intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md).

Weitere Informationen zu Zeiger Konvertierungen finden Sie unter [Typkonvertierungen und Typsicherheit](../cpp/type-conversions-and-type-safety-modern-cpp.md).

Weitere Informationen zu Zeigern im Allgemeinen finden Sie unter [Zeiger](../cpp/pointers-cpp.md).

## <a name="windows-data-types"></a>Windows-Datentypen

In der klassischen Win32-Programmierung für C und C++ verwenden die meisten Funktionen Windows-spezifische Typdefinitionen und #define-Makros (die in `windef.h` definiert sind), um die Typen von Parametern und Rückgabewerten anzugeben. Diese Windows-Datentypen sind größtenteils nur spezielle Namen (Aliase), die inC++ C/integrierten Typen angegeben sind. Eine umfassende Liste dieser Typedefs-und Präprozessordefinitionen finden Sie unter [Windows-Datentypen](/windows/win32/WinProg/windows-data-types). Einige dieser Typdefinitionen, wie HRESULT und LCID, sind nützlich und beschreibend. Andere, wie INT, haben keine besondere Bedeutung und sind nur Alias für grundlegende C++-Typen. Weitere Windows-Datentypen haben Namen, die seit den Tagen der C-Programmierung und der 16-Bit-Prozessoren beibehalten werden. Sie haben keinen Zweck oder keine Bedeutung mehr bei moderner Hardware oder Betriebssystemen. Der Windows-Runtime-Bibliothek sind auch besondere Datentypen zugeordnet, die als [Windows-Runtime Basis Datentypen](/windows/win32/WinRT/base-data-types)aufgeführt sind. Für modernes C++ gilt die allgemeine Richtlinie, die grundlegenden C++-Typen vorzuziehen, es sei denn, mit dem Windows-Typ wird zusätzliche Bedeutung über die Interpretationsweise des Werts kommuniziert.

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen zum Typsystem von C++ finden Sie in den folgenden Themen.

|||
|-|-|
|[Werttypen](../cpp/value-types-modern-cpp.md)|Beschreibt *Werttypen* sowie Probleme im Zusammenhang mit deren Verwendung.|
|[Typkonvertierungen und Typsicherheit](../cpp/type-conversions-and-type-safety-modern-cpp.md)|Beschreibt allgemeine Typkonvertierungsprobleme und zeigt, wie sie vermieden werden.|

## <a name="see-also"></a>Siehe auch

[Willkommen zurück beiC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
