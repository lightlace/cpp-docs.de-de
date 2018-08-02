---
title: Vorlagen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- template_cpp
dev_langs:
- C++
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5a9aa15839169de846439c73af1df92d7342358
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463927"
---
# <a name="templates-c"></a>Vorlagen (C++)
Vorlagen sind die Grundlage für die generische Programmierung in C++. Als stark typisierte Sprache erfordert C++ alle Variablen, ein bestimmtes Typs, entweder explizit vom Programmierer deklariert oder vom Compiler abgeleitet haben. Allerdings aussehen viele Datenstrukturen und Algorithmen gleich unabhängig davon, welche Art sie arbeiten. Vorlagen ermöglichen Ihnen, definieren Sie die Vorgänge einer Klasse oder Funktion, und ermöglichen das Angeben von welchen konkreten Typen, dass diese Vorgänge sollten auf funktionieren.  
  
## <a name="defining-and-using-templates"></a>Definieren und Verwenden von Vorlagen  
 Eine Vorlage ist ein Konstrukt, das generiert einen normalen Typ oder die Funktion zum Zeitpunkt der Kompilierung anhand der Argumente, die der Benutzer für den Vorlagenparameter bereitstellt. Beispielsweise können Sie eine Funktionsvorlage wie folgt definieren:  
  
```cpp  
template <typename T>  
T minimum(const T& lhs, const T& rhs)  
{  
    return lhs < rhs ? lhs : rhs;  
}  
```  
  
 Der obige Code wird beschrieben, eine Vorlage für eine generische Funktion mit einem einzelnen Typparameter *T*, deren Wert zurück, und rufen Sie die Parameter (Lhs und Rhs) sind "all" dieses Typs. Sie können einen Typparameter beliebig benennen, die Sie wie bei, aber durch Konvention einzelnen Großbuchstaben am häufigsten verwendet werden. *T* ist ein Vorlagenparameter, der **Typename** Schlüsselwort besagt, dass dieser Parameter als Platzhalter für einen Typ ist. Wenn die Funktion aufgerufen wird, wird der Compiler ersetzt jede Instanz des `T` mit dem konkreten Typ-Argument, das vom Benutzer angegebenen oder vom Compiler abgeleitet ist. Der Prozess, in dem der Compiler generiert eine Klasse oder Funktion aus einer Vorlage wird als bezeichnet *Vorlageninstanziierung*; `minimum<int>` ist eine Instanziierung der Vorlage `minimum<T>`.  
  
 Benutzer kann an anderer Stelle eine Instanz der Vorlage deklarieren, die speziell für "int" verwendet wird Nehmen Sie an, dass get_a() und get_b() Funktionen, die einem "int" zurückgeben:  
  
```cpp 
int a = get_a();  
int b = get_b();  
int i = minimum<int>(a, b);  
```  
  
 Allerdings da dies eine Funktionsvorlage und der Compiler können hergeleitet werden. den Typ des `T` aus den Argumenten *eine* und *b*, können Sie ihn genau wie eine normale Funktion aufrufen:  
  
```cpp  
int i = minimum(a, b);  
```  
  
 Wenn der Compiler diese letzte Anweisung erkennt, generiert er eine neue Funktion, in der jedes Vorkommen des *T* in der Vorlage wird durch ersetzt **Int**:  
  
```cpp   
int minimum(const int& lhs, const int& rhs)  
{  
    return lhs < rhs ? lhs : rhs;  
}  
```  
  
 Die Regeln für die wie führt der Compiler die typableitung in Funktionsvorlagen basieren auf den Regeln für normale Funktionen. Weitere Informationen finden Sie unter [überladen Auflösung von Funktionsvorlagenaufrufen](../cpp/overload-resolution-of-function-template-calls.md).  
  
## <a id="type_parameters"></a> Typparameter  
 In der `minimum` Vorlage oben, beachten Sie, dass der Typparameter *T* sind nicht in irgendeiner Weise gekennzeichnet, bis er in die Funktionsparameter Aufruf verwendet wird, werden die Konstanten und verweisqualifizierern hinzugefügt.  
  
 Es gibt praktisch keine Begrenzung hinsichtlich der Anzahl von Typparametern. Trennen Sie mehrere Parameter durch Kommas an:  
  
```cpp  
template <typename T, typename U, typename V> class Foo{};  
```  
  
 Das Schlüsselwort **Klasse** entspricht **Typename** in diesem Kontext. Sie können das vorherige Beispiel als Ausdrücken:  
  
```cpp 
template <class T, class U, class V> class Foo{};   
```  
  
 Den Operator Auslassungspunkte (...) können Sie um eine Vorlage zu definieren, die eine beliebige Anzahl von NULL oder mehr Parameter vom Typ akzeptiert:  
  
```cpp  
template<typename... Arguments> class vtclass;  
  
vtclass< > vtinstance1;  
vtclass<int> vtinstance2;  
vtclass<float, bool> vtinstance3;  
```  
  
 Alle integrierten oder benutzerdefinierten Typ kann als Typargument verwendet werden. Sie können z. B. Std:: Vector in der Standardbibliothek verwenden, zum Speichern von int-Elementen, Double-Werte, Zeichenfolgen, MyClass, const MyClass *, MyClass &. Die primäre Einschränkung, wenn mithilfe von Vorlagen ist, dass ein Argument vom Typ alle Operationen unterstützen muss, die an die Typparameter angewendet werden. Angenommen, wir rufen Sie minimale MyClass wie in diesem Beispiel verwenden:  
  
```cpp  
class MyClass  
{  
public:  
    int num;  
    std::wstring description;  
};  
  
int main()  
{      
    MyClass mc1 {1, L"hello"};  
    MyClass mc2 {2, L"goodbye"};  
    auto result = minimum(mc1, mc2); // Error! C2678  
}  
```  
  
 Ein Compilerfehler generiert werden, weil MyClass keine Überladung für bietet die < Operator.  
  
 Es gibt keine inhärenten Anforderung, dass die Typargumente für alle bestimmte Vorlage, die alle mit der gleichen Objekthierarchie angehören, obwohl Sie eine Vorlage definieren können, die eine solche Einschränkung erzwingt. Sie können mit Vorlagen Objekt-orientierte Techniken kombinieren. Angenommen, Sie können speichern abgeleiteten * in einem Vektor\<Base\*>.    Beachten Sie, dass die Argumente müssen Verweise  
  
```cpp 
vector<MyClass*> vec;  
   MyDerived d(3, L"back again", time(0));  
   vec.push_back(&d);  
  
   // or more realistically:  
   vector<shared_ptr<MyClass>> vec2;  
   vec2.push_back(make_shared<MyDerived>());  
```  
  
 Die grundlegenden Anforderungen, die auf Elemente in der Vektor und andere standard-Bibliothek-Container zu erzwingen `T` ist, die `T` werden Kopie zugewiesen werden kann und die Kopie konstruiert werden kann.  
  
## <a name="non-type-parameters"></a>Nichttyp-Parameter  
 Im Gegensatz zu generischen Typen in anderen Sprachen wie c# und Java unterstützt C++-Vorlagen Nichttyp-Parameter, die auch als Parameter bezeichnet. Beispielsweise können Sie einen Konstanten ganzzahligen Wert um anzugeben, die Länge eines Arrays, wie in diesem Beispiel bereitstellen, die auf die Klasse "Std:: Array" in der Standardbibliothek ähnlich ist:  
  
```cpp 
template<typename T, size_t L>  
class MyArray  
{  
    T arr[L];  
public:  
    MyArray() { ... }  
};  
```  
  
 Beachten Sie die Syntax in der Vorlagendeklaration. Der Wert von "size_t" wird als ein Vorlagenargument zum Zeitpunkt der Kompilierung übergeben und muss Konstante oder einen Ausdruck für "constexpr" sein. Sie verwenden es folgendermaßen:  
  
```cpp  
MyArray<MyClass*, 10> arr;  
```  
  
 Andere Arten von einschließlich Zeiger und Verweise auf Werte können als Nichttyp-Parameter übergeben werden. Beispielsweise können Sie einen Zeiger an eine Funktion oder ein Funktionsobjekt, das Sie zum Anpassen eines Vorgangs in den Code der Vorlage übergeben.  
  
## <a id="template_parameters"></a> Vorlagen als Vorlagenparameter  
 Eine Vorlage kann es sich um einen Template-Parameter sein. In diesem Beispiel MyClass2 verfügt über zwei Vorlagenparameter: Typename-Parameter *T* und einem Vorlagenparameter *Arr*:  
  
```cpp  
template<typename T, template<typename U, int I> class Arr>  
class MyClass2  
{  
    T t; //OK  
    Arr<T, 10> a;  
    U u; //Error. U not in scope  
};  
```  
  
 Da die *Arr* Parameter selbst keinen Text enthält, die Parameternamen sind nicht erforderlich. Es ist ein Fehler zum Verweisen auf *Arr*des Typename oder Klasse Parameternamen von innerhalb des Texts der `MyClass2`. Aus diesem Grund *Arr*des Typparameternamen können weggelassen werden, wie im folgenden Beispiel gezeigt:  
  
```cpp  
template<typename T, template<typename, int> class Arr>  
class MyClass2  
{  
    T t; //OK  
    Arr<T, 10> a;  
};  
```  
  
## <a name="default-template-arguments"></a>Standardvorlagenargumente  
 Klassen- und Funktionsvorlagen können Standardargumente haben. Wenn Sie eine Vorlage einem Standardargument, Sie lassen, es nicht angegeben, bei der Verwendung. Beispielsweise weist die Std:: Vector-Vorlage ein Standardargument für die Zuweisung:  
  
```cpp  
template <class T, class Allocator = allocator<T>> class vector;  
```  
  
 In den meisten Fällen ist die standardmäßige Std:: allocator-Klasse akzeptabel, damit Sie einen Vektor wie folgt verwenden:  
  
```cpp  
vector<int> myInts;  
```  
  
 Aber wenn es sich bei Bedarf eine benutzerdefinierte Zuweisung können Sie angeben, wie folgt:  
  
```cpp  
vector<int, MyAllocator> ints;  
```  
  
 Bei mehrfachen Vorlagenargumenten müssen alle Argumente nach dem ersten Standardargument Standardargumente haben.  
  
 Wenn Sie eine Vorlage verwenden, deren Parameter alle Standardwerte verwendet werden, verwenden Sie die leeren spitzen Klammern:  
  
```cpp  
template<typename A = int, typename B = double>  
class Bar  
{  
    //...  
};  
...  
int main()  
{  
    Bar<> bar; // use all default type arguments  
}  
```  
  
## <a name="template-specialization"></a>Vorlagenspezialisierung  
 In einigen Fällen ist es nicht möglich oder wünschenswert ist für eine Vorlage aus, um genau den gleichen Code für jeden Typ zu definieren. Möglicherweise möchten Sie z. B. einen Codepfad ausgeführt werden, nur dann, wenn das Typargument ein Zeiger oder ein Std:: wstring ist oder ein von einer bestimmten Basisklasse Typ abgeleiteter definieren.  In solchen Fällen können Sie definieren eine *Spezialisierung* der Vorlage für den gewählten. Wenn ein Benutzer die Vorlage mit diesem Typ instanziiert, der Compiler verwendet die Spezialisierung, um die Klasse zu generieren, und für alle anderen Dateitypen, wählt des Compilers die allgemeine Vorlage. Spezialisierungen, die in dem alle Parameter sind spezialisiert sind *abgeschlossen spezialisierungen*. Wenn nur einige der Parameter angegeben wurden, heißt es eine *teilspezialisierung*.  
  
```cpp  
template <typename K, typename V>  
class MyMap{/*...*/};  
  
// partial specialization for string keys  
template<typename V>  
class MyMap<string, V> {/*...*/};  
...  
MyMap<int, MyClass> classes; // uses original template  
MyMap<string, MyClass> classes2; // uses the partial specialization  
```  
  
 Eine Vorlage kann eine beliebige Anzahl von spezialisierungen haben, solange jede spezielle Typparameter eindeutig ist. Nur Klassenvorlagen können teilweise spezialisiert werden. Alle vollständige oder partielle spezialisierungen einer Vorlage müssen im selben Namespace wie die ursprüngliche Vorlage deklariert werden.  
  
 Weitere Informationen finden Sie unter [Spezialisierung einer Klassenvorlage](../cpp/template-specialization-cpp.md).