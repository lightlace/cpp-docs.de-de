---
title: Vorlagen (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- template_cpp
dev_langs:
- C++
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 935bee8447ad0d49ae965fb92538d2e260ec68ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="templates-c"></a>Vorlagen (C++)
Vorlagen sind die Grundlage für die generische Programmierung in C++. Als stark typisierte Sprache erfordert C++ alle Variablen, die einen bestimmten Typ, entweder explizit durch den Programmierer deklariert oder vom Compiler abgeleitet wurden. Allerdings sehen viele Datenstrukturen und Algorithmen identisch, unabhängig davon, welche Art, die sie für ausgeführt werden. Vorlagen ermöglichen Ihnen die Vorgänge einer Klasse oder Funktion zu definieren, und ermöglichen das Angeben von welche konkret diese Vorgänge Typen sollten am arbeiten.  
  
## <a name="defining-and-using-templates"></a>Definieren und Verwenden von Vorlagen  
 Eine Vorlage ist ein Konstrukt, das generiert einen normalen Typ oder eine Funktion zum Zeitpunkt der Kompilierung anhand der Argumente, die der Benutzer für die Vorlagenparameter bereitstellt. Sie können z. B. eine Funktionsvorlage wie folgt definieren:  
  
```cpp  
template <typename T>  
T minimum(const T& lhs, const T& rhs)  
{  
    return lhs < rhs ? lhs : rhs;  
}  
```  
  
 Der Code oben wird beschrieben, eine Vorlage für eine generische Funktion einen einzelnen Typparameter `T`, deren Rückgabewert, und rufen Sie Parameter (Lhs und Rhs) sind "all" dieses Typs. Sie können einen Typparameter einen beliebigen Namen geben Sie z. B., sondern auch von einzelnen Großbuchstaben Konvention am häufigsten verwendet werden. `T`ist ein Template-Parameter. die `typename` Schlüsselwort besagt, dass dieser Parameter als Platzhalter für einen Typ ist. Wenn die Funktion aufgerufen wird, ersetzt der Compiler jede Instanz des `T` mit dem konkreten Typ-Argument, das vom Benutzer angegebenen oder vom Compiler abgeleitet ist. Der Prozess, in denen der Compiler generiert eine Klasse oder Funktion aus einer Vorlage wird als bezeichnet *Vorlageninstanziierung*;   `minimum<int>` ist eine Instanziierung der Vorlage `minimum<T>`.  
  
 Benutzer kann in anderen Kontexten eine Instanz der Vorlage deklarieren, die für "int". spezialisiert ist Angenommen Sie, get_a() und get_b() Funktionen handelt, die einen "Int" zurück:  
  
```  
int a = get_a();  
int b = get_b();  
int i = minimum<int>(a, b);  
```  
  
 Jedoch, da dies ist eine Funktionsvorlage und der Compiler können hergeleitet werden den Typ des `T` aus den Argumenten `a` und `b`, können Sie ihn genau wie einer gewöhnlichen Funktion aufrufen:  
  
```cpp  
int i = minimum(a, b);  
```  
  
 Wenn der Compiler, letzte Anweisung trifft, wird eine neue Funktion in der jedes Vorkommen von generiert *T* in der Vorlage wird ersetzt durch `int`:  
  
```  
  
      int minimum(const int& lhs, const int& rhs)  
{  
    return lhs < rhs ? lhs : rhs;  
}  
```  
  
 Die Regeln für wie führt der Compiler die typableitung in den Funktionsvorlagen basieren auf den Regeln für normale Funktionen. Weitere Informationen finden Sie unter [überladen Auflösung von Funktionsvorlagenaufrufen](../cpp/overload-resolution-of-function-template-calls.md).  
  
## <a id="type_parameters"></a>Typparameter  
 In der `minimum` Vorlage oben, beachten Sie, dass der Typparameter `T` sind nicht in keiner Weise gekennzeichnet, bis er in die Funktionsparameter Aufruf verwendet wird, wo die Const und Qualifizierer Verweis hinzugefügt.  
  
 Es gibt keine praktische Begrenzung für die Anzahl von Typparametern. Trennen Sie mehrere Parameter, durch Trennzeichen getrennt:  
  
```cpp  
template <typename T, typename U, typename V> class Foo{};  
  
```  
  
 Das Schlüsselwort `class` entspricht `typename` in diesem Kontext. Sie können das vorherige Beispiel als Ausdrücken:  
  
```  
template <class T, class U, class V> class Foo{};   
```  
  
 Den Operator Auslassungspunkte (...) können Sie eine Vorlage definieren, die eine beliebige Anzahl von 0 (null) oder mehrere Typparameter akzeptiert:  
  
```cpp  
template<typename... Arguments> class vtclass;  
  
vtclass< > vtinstance1;  
vtclass<int> vtinstance2;  
vtclass<float, bool> vtinstance3;  
```  
  
 Alle integrierten oder benutzerdefinierten Typ kann als Typargument verwendet werden. Sie können z. B. Std:: Vector in der Standardbibliothek verwenden, zum Speichern von Ganzzahlen, Double-Werte, Zeichenfolgen, MyClass, const MyClass *, MyClass &. Die primäre Einschränkung bei Verwendung von Vorlagen ist, dass ein Typargument beliebige Vorgänge unterstützen muss, die die Typparameter angewendet werden. Angenommen, wir rufen Sie minimale MyClass wie in diesem Beispiel verwenden:  
  
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
  
 Ein Compilerfehler generiert werden, weil MyClass keine Überladung für bietet der < Operator.  
  
 Es gibt keine inhärente erforderlich, dass die Typargumente für eine bestimmte Vorlage, die alle zur selben Objekthierarchie gehören, obwohl Sie eine Vorlage definieren können, die eine solche Einschränkung erzwingt. Sie können mit dem objektorientierten Techniken mit Vorlagen kombinieren; Beispielsweise können Sie eine abgeleitete * in speichern einen Vektor\<Base\*>.    Beachten Sie, dass die Argumente müssen einen Zeiger aufweisen  
  
```  
vector<MyClass*> vec;  
   MyDerived d(3, L"back again", time(0));  
   vec.push_back(&d);  
  
   // or more realistically:  
   vector<shared_ptr<MyClass>> vec2;  
   vec2.push_back(make_shared<MyDerived>());  
```  
  
 Die grundlegenden Anforderungen, die für Elemente eines Vektor- und andere standardbibliothekscontainer vorgeben `T` , die `T` Kopie zugewiesen werden und die Kopie erstellt werden.  
  
## <a name="non-type-parameters"></a>Nichttyp-Parameter  
 Im Gegensatz zu generische Typen in anderen Sprachen wie c# und Java unterstützt C++-Vorlagen Nichttyp-Parameter, die auch als Wertparametern bezeichnet. Beispielsweise können Sie einen Konstanten ganzzahligen Wert um die Länge eines Arrays angeben, wie in diesem Beispiel bereitstellen, die auf die Std:: Array-Klasse in der Standardbibliothek ähnlich ist:  
  
```  
template<typename T, size_t L>  
class MyArray  
{  
    T arr[L];  
public:  
    MyArray() { ... }  
};  
  
```  
  
 Beachten Sie die Syntax in der Vorlagendeklaration. Der Size_t-Wert wird als ein Vorlagenargument zum Zeitpunkt der Kompilierung übergeben und -Konstante oder eine Constexpr-Ausdruck sein muss. Sie können Sie wie folgt verwenden:  
  
```cpp  
MyArray<MyClass*, 10> arr;  
```  
  
 Andere Arten von einschließlich Zeiger und Verweise auf Werte können als Nichttyp-Parameter übergeben werden. Sie können z. B. in einen Zeiger an eine Funktion oder ein Funktionsobjekt, das Sie zum Anpassen eines Vorgangs innerhalb der Vorlagencode übergeben.  
  
## <a id="template_parameters"></a>Vorlagen als Vorlagenparameter  
 Eine Vorlage kann es sich um eine Template-Parameter sein. In diesem Beispiel MyClass2 zwei Vorlagenparameter hat: eine Typnamenparameter `T` und einem Vorlagenparameter `Arr`:  
  
```cpp  
template<typename T, template<typename U, int I> class Arr>  
class MyClass2  
{  
    T t; //OK  
    Arr<T, 10> a;  
    U u; //Error. U not in scope  
};  
```  
  
 Da die `Arr` Parameter selbst hat keine Text, dessen Parameternamen sind nicht erforderlich. Es ist tatsächlich ein Fehler zum Verweisen auf `Arr`des Typename oder Klasse Parameternamen aus dem Funktionstext `MyClass2`. Aus diesem Grund `Arr`des Typparameternamen können ausgelassen werden, wie im folgenden Beispiel gezeigt:  
  
```cpp  
template<typename T, template<typename, int> class Arr>  
class MyClass2  
{  
    T t; //OK  
    Arr<T, 10> a;  
};  
```  
  
## <a name="default-template-arguments"></a>Standardvorlagenargumente  
 Klassen- und Funktionsvorlagen können Standardargumente haben. Wenn eine Vorlage einem Standardargument, Sie lassen, nicht bei der Verwendung angegeben. Beispielsweise weist die Std:: Vector-Vorlage ein Standardargument für die Zuweisung:  
  
```cpp  
template <class T, class Allocator = allocator<T>> class vector;  
```  
  
 In den meisten Fällen ist die Standardklasse Std:: allocator akzeptabel, damit Sie einen Vektor wie folgt verwenden:  
  
```cpp  
vector<int> myInts;  
```  
  
 Jedoch bei Bedarf eine benutzerdefinierte Zuweisung Angabe kann wie folgt:  
  
```cpp  
vector<int, MyAllocator> ints;  
```  
  
 Bei mehrfachen Vorlagenargumenten müssen alle Argumente nach dem ersten Standardargument Standardargumente haben.  
  
 Wenn Sie eine Vorlage verwenden, deren Parameter alle übernommen werden, verwenden Sie die leeren spitzen Klammern:  
  
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
  
## <a name="template-specialization"></a>Spezialisierung einer Klassenvorlage  
 In einigen Fällen ist es nicht möglich oder wünschenswert ist für eine Vorlage aus, um genau den gleichen Code für einen beliebigen Typ zu definieren. Sie möchten z. B. einen Codepfad ausgeführt werden, nur, wenn das Typargument ein Zeiger ist oder ein Std:: wstring ist oder einen von einer bestimmten Basisklasse Typ abgeleiteten zu definieren.  In solchen Fällen können Sie definieren eine *Spezialisierung* der Vorlage für dieses bestimmten Typs. Wenn ein Benutzer die Vorlage mit diesem Typ instanziiert, der Compiler die Spezialisierung verwendet, um die Klasse zu generieren, und für alle anderen Datentypen wählt des Compilers die allgemeinere Vorlage. Spezialisierungen, in dem alle Parameter sind spezialisiert, sind *abgeschlossen spezialisierungen*. Wenn nur einige der Parameter angegeben wurden, heißt es eine *teilweise Spezialisierung*.  
  
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
  
 Eine Vorlage kann eine beliebige Anzahl von spezialisierungen sein, solange jede spezielle Typparameter eindeutig ist.   Nur Klassenvorlagen können teilweise spezialisiert werden. Alle vollständige und partielle spezialisierungen einer Vorlage müssen im selben Namespace wie die ursprüngliche Vorlage deklariert werden.  
  
 Weitere Informationen finden Sie unter [Spezialisierung einer Klassenvorlage](../cpp/template-specialization-cpp.md).