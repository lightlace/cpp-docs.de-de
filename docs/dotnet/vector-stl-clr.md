---
title: Vektor (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector
- cliext::operator!=
- cliext::operator<
- cliext::operator<=
- cliext::operator==
- cliext::operator>
- cliext::operator>=
- cliext::vector::assign
- cliext::vector::at
- cliext::vector::back
- cliext::vector::back_item
- cliext::vector::begin
- cliext::vector::capacity
- cliext::vector::clear
- cliext::vector::const_iterator
- cliext::vector::const_reference
- cliext::vector::const_reverse_iterator
- cliext::vector::difference_type
- cliext::vector::empty
- cliext::vector::end
- cliext::vector::erase
- cliext::vector::front
- cliext::vector::front_item
- cliext::vector::generic_container
- cliext::vector::generic_iterator
- cliext::vector::generic_reverse_iterator
- cliext::vector::generic_value
- cliext::vector::insert
- cliext::vector::iterator
- cliext::vector::operator=
- cliext::vector::operator
- cliext::vector::pop_back
- cliext::vector::push_back
- cliext::vector::rbegin
- cliext::vector::reference
- cliext::vector::rend
- cliext::vector::reserve
- cliext::vector::resize
- cliext::vector::reverse_iterator
- cliext::vector::size
- cliext::vector::size_type
- cliext::vector::swap
- cliext::vector::to_array
- cliext::vector::value_type
- cliext::vector::vector
dev_langs:
- C++
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> (vector) member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- capacity member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
- pop_back member [STL/CLR]
- push_back member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reserve member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- vector member [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d5b3e94b0b594174538aebe6542b04df7214f1b
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079811"
---
# <a name="vector-stlclr"></a>vector (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge steuert, die zufälligen Zugriff hat. Verwenden Sie den Container `vector` um eine Sequenz von Elementen als einen zusammenhängenden Block von Speicher zu verwalten. Der Block wird als Array implementiert, die bei Bedarf vergrößert wird.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit `Value` , wenn die zweite Datei einen Ref-Typ ist, in diesem Fall wird `Value^`.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
### <a name="parameters"></a>Parameter  
 Wert  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Vektor >  
  
 **Namespace:** Cliext  

## <a name="declarations"></a>Deklarationen  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[vector::const_iterator (STL/CLR)](#const_iterator)|Der Typ eines konstanten Iterators für die gesteuerte Sequenz.|  
|[vector::const_reference (STL/CLR)](#const_reference)|Der Typ eines konstanten Verweises auf ein Element.|  
|[vector::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.|  
|[vector::difference_type (STL/CLR)](#difference_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[vector::generic_container (STL/CLR)](#generic_container)|Der Typ der generischen Schnittstelle für den Container.|  
|[vector::generic_iterator (STL/CLR)](#generic_iterator)|Der Typ eines Iterators für die generische Schnittstelle für den Container.|  
|[vector::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Der Typ eines umgekehrten Iterators für die generische Schnittstelle für den Container.|  
|[vector::generic_value (STL/CLR)](#generic_value)|Der Typ eines Elements für die generische Schnittstelle für den Container.|  
|[vector::iterator (STL/CLR)](#iterator)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[vector::reference (STL/CLR)](#reference)|Der Typ eines Verweises auf ein Element.|  
|[vector::reverse_iterator (STL/CLR)](#reverse_iterator)|Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.|  
|[vector::size_type (STL/CLR)](#size_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[vector::value_type (STL/CLR)](#value_type)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[vector::assign (STL/CLR)](#assign)|Ersetzt alle Elemente.|  
|[vector::at (STL/CLR)](#at)|Greift auf ein Element an einer angegebenen Position zu.|  
|[vector::back (STL/CLR)](#back)|Greift auf das letzte Element zu.|  
|[vector::begin (STL/CLR)](#begin)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[vector::capacity (STL/CLR)](#capacity)|Gibt die Größe des belegten Speichers für den Container.|  
|[vector::clear (STL/CLR)](#clear)|Entfernt alle Elemente.|  
|[vector::empty (STL/CLR)](#empty)|Testet, ob keine Elemente vorhanden sind.|  
|[vector::end (STL/CLR)](#end)|Legt das Ende der kontrollierten Sequenz fest.|  
|[vector::erase (STL/CLR)](#erase)|Entfernt Elemente an den angegebenen Positionen.|  
|[vector::front (STL/CLR)](#front)|Greift auf das erste Element zu.|  
|[vector::insert (STL/CLR)](#insert)|Fügt Elemente an einer angegebenen Position hinzu.|  
|[vector::pop_back (STL/CLR)](#pop_back)|Entfernt das letzte Element.|  
|[vector::push_back (STL/CLR)](#push_back)|Fügt ein neues Letztes Element hinzu.|  
|[vector::rbegin (STL/CLR)](#rbegin)|Legt den Anfang der umgekehrten kontrollierten Sequenz fest.|  
|[vector::rend (STL/CLR)](#rend)|Legt das Ende der umgekehrten kontrollierten Sequenz fest.|  
|[vector::reserve (STL/CLR)](#reserve)|Es wird sichergestellt, dass eine Erweiterung der Mindestkapazität für den Container.|  
|[vector::resize (STL/CLR)](#resize)|Ändert die Anzahl der Elemente an.|  
|[vector::size (STL/CLR)](#size)|Ermittelt die Anzahl von Elementen.|  
|[vector::swap (STL/CLR)](#swap)|Vertauscht den Inhalt von zwei Containern.|  
|[vector::to_array (STL/CLR)](#to_array)|Kopiert die gesteuerte Sequenz in ein neues Array.|  
|[vector::vector (STL/CLR)](#vector)|Erstellt ein container-Objekt.|  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|[vector::back_item (STL/CLR)](#back_item)|Greift auf das letzte Element zu.|  
|[vector::front_item (STL/CLR)](#front_item)|Greift auf das erste Element zu.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[vector::operator= (STL/CLR)](#op_as)|Ersetzt die kontrollierte Sequenz.|  
|[vector::operator(STL/CLR)](#op)|Greift auf ein Element an einer angegebenen Position zu.|  
|[operator!= (vector) (STL/CLR)](#op_neq)|Bestimmt, ob eine `vector` Objekt ist nicht gleich einem anderen `vector` Objekt.|  
|[operator< (vector) (STL/CLR)](#op_lt)|Bestimmt, ob eine `vector` Objekt ist kleiner als ein anderes `vector` Objekt.|  
|[operator<= (vector) (STL/CLR)](#op_lteq)|Bestimmt, ob eine `vector` Objekt ist kleiner als oder gleich einem anderen `vector` Objekt.|  
|[operator== (vector) (STL/CLR)](#op_eq)|Bestimmt, ob eine `vector` -Objekt gleich einem anderen `vector` Objekt.|  
|[operator> (vector) (STL/CLR)](#op_gt)|Bestimmt, ob eine `vector` -Quellobjekt ist größer als ein anderes `vector` Objekt.|  
|[operator>= (vector) (STL/CLR)](#op_gteq)|Bestimmt, ob eine `vector` Objekt ist größer als oder gleich einem anderen `vector` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|<xref:System.Collections.IEnumerable>|Durch die Elemente der Sequenz.|  
|<xref:System.Collections.ICollection>|Behalten Sie die Gruppe von Elementen.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Durch die Elemente der typisierte Sequenz.|  
|<xref:System.Collections.Generic.ICollection%601>|Behalten Sie die Gruppe von typisierten Elementen.|  
|<xref:System.Collections.Generic.IList%601>|Verwalten Sie geordnete Gruppe von typisierten Elementen.|  
|IVector < Wert\>|Verwalten von generischen Container.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist und-Freigaben für die Sequenz, die durch eine gespeicherte Array von Steuersoftware `Value` -Elemente, die bei Bedarf vergrößert wird. Wachstum tritt auf, auf eine Weise, dass die Kosten für das Anhängen eines neuen Elements amortisierter konstanter Zeit ist. Das heißt, erhöht die Kosten für das Hinzufügen von Elementen am Ende nicht, im Durchschnitt als die Länge der gesteuerten Sequenz ruft größere. Ein Vektor ist daher ein guter Kandidat für die zugrunde liegenden Container für die Vorlagenklasse [Stapel (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 Ein `vector` unterstützt random-Access-Iteratoren, d. h., Sie verweisen auf ein Element direkt die numerische Position Zählung von 0 (null) für das erste (Vordergrund)-Element, auf `size() - 1` für das letzte Element der (zurück). Es bedeutet auch, dass Sie ein Vektor ein guter Kandidat für die zugrunde liegenden Container für die Vorlagenklasse ist [Priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Ein Iterator Vektor speichert einen Handle für seine zugeordneten Vector-Objekt, zusammen mit den Zeitunterschied des Elements, die er festlegt. Sie können nur mit ihrer zugeordneten Containerobjekte Iteratoren verwenden. Die Verschiebung eines Vektorelements ist identisch mit seiner Position.  
  
 Einfügen und Löschen von Elementen kann den Elementwert an einer bestimmten Position gespeichert werden, sodass von einem Iterator festgelegten auch ändern kann, ändern. (Der Container möglicherweise, kopieren Sie Elemente oben oder nach unten, um eine Lücke vor einer INSERT-Anweisung zu erstellen oder nach einer löschen eine Lücke zu füllen). Ein Iterator Vektor bleibt dennoch gültig, solange im Bereich der Bias ist `[0, size()]`. Darüber hinaus ein gültiger Iterator bleibt dereferencable – können sie Zugriff haben und den Elementwert, die er festlegt – ändern, solange die Verschiebung nicht gleich `size()`.  
  
 Löschen oder Entfernen eines Elements ruft der Destruktor für den gespeicherten Wert. Zerstören von dem Container löscht alle Elemente. Somit wird sichergestellt, dass ein Container, dessen Elementtyp eine Verweisklasse ist, dass keine Elemente den Container Überleben. Beachten Sie jedoch, dass ein Container von Handles, die nicht über die Elemente gelöscht.  
  
## <a name="members"></a>Member

## <a name="assign"></a> Vector:: Assign (STL/CLR)
Ersetzt alle Elemente.  
  
### <a name="syntax"></a>Syntax  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parameter  
 count  
 Die Anzahl einzufügender Elemente.  
  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 Rechts  
 Die Enumeration eingefügt.  
  
 Val  
 Der Wert des einzufügenden Elements.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion ersetzt die kontrollierte Sequenz durch eine Wiederholung von `count` -Elementen des Werts `val`. Sie verwenden sie den Container mit Elementen gefüllt alle mit dem gleichen Wert.  
  
 Wenn `InIt` ein Ganzzahltyp ist, wird die zweite Memberfunktion verhält sich wie `assign((size_type)first, (value_type)last)`. Andernfalls ersetzt die kontrollierte Sequenz durch die Sequenz [`first`, `last`). Sie verwenden es für die gesteuerte Sequenz eine Kopie einer anderen Sequenz.  
  
 Die dritte Memberfunktion ersetzt die kontrollierte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer Sequenz, die durch einen Enumerator beschrieben.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_assign.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::vector<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  

## <a name="at"></a> Vector:: AT (STL/CLR)
Greift auf ein Element an einer angegebenen Position zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
reference at(size_type pos);  
```  
  
#### <a name="parameters"></a>Parameter  
 pos  
 Position des Elements, auf das zugegriffen wird  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Verweis auf das Element der kontrollierten Sequenz an der Position `pos`. Verwenden sie zum Lesen oder schreiben ein Element, dessen Position Sie kennen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_at.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  

## <a name="back"></a> Vector:: Back (STL/CLR)
Greift auf das letzte Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
reference back();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Verweis auf das letzte Element der gesteuerten Sequenz, die nicht leer sein darf. Sie verwenden es, auf das letzte Element zuzugreifen, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back() = c  
 a b x  
```  

## <a name="back_item"></a> Vector:: back_item (STL/CLR)
Greift auf das letzte Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
property value_type back_item;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaft greift auf das letzte Element der gesteuerten Sequenz, die nicht leer sein darf. Sie verwenden ihn zum Lesen oder schreiben das letzte Element, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_back_item.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
back_item = c  
 a b x  
```  

## <a name="begin"></a> Vector:: begin (STL/CLR)
Legt den Anfang der kontrollierten Sequenz fest.  
  
### <a name="syntax"></a>Syntax  
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Iterator mit zufälligem Zugriff, der das erste Element der kontrollierten Sequenz oder direkt hinter das Ende einer leeren Sequenz bestimmt. Es mit der einen Iterator abrufen, bestimmt die `current` Anfang der kontrollierten Sequenz kann ändern, wenn die Länge der gesteuerten Sequenz geändert wird.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_begin.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
 x y c  
```  

## <a name="capacity"></a> Vector:: Capacity (STL/CLR)
Gibt die Größe des belegten Speichers für den Container.  
  
### <a name="syntax"></a>Syntax  
  
```  
size_type capacity();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt den Speicherplatz, um die kontrollierte Sequenz, ein Wert, der mindestens so groß wie derzeit zugewiesen [Vector:: Size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`()`. Sie verwenden es, um zu bestimmen, wie viel der Container vergrößert werden kann, bevor sie Speicher für die gesteuerte Sequenz neu zugeordnet werden muss.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_capacity.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
capacity() = 4, ok = True  
capacity() = 9, ok = True  
```  

## <a name="clear"></a> Vector:: Clear (STL/CLR)
Entfernt alle Elemente.  
  
### <a name="syntax"></a>Syntax  
  
```  
void clear();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion ruft tatsächlich [Vector:: Erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md) `(` [Vector:: begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md) `(),` [Vector:: End (STL/CLR)](../dotnet/vector-end-stl-clr.md) `())`. Sie verwenden es, um sicherzustellen, dass die kontrollierte Sequenz leer ist.  
  
### <a name="example"></a>Beispiel  
  
```  
// cliext_vector_clear.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  

## <a name="const_iterator"></a> Vector:: const_iterator (STL/CLR)
Der Typ eines konstanten Iterators für die gesteuerte Sequenz.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt vom angegebenen Typ `T2` , die als Konstante random-Access-Iterator für die gesteuerte Sequenz dienen kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_const_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reference"></a> Vector:: const_reference (STL/CLR)
Der Typ eines konstanten Verweises auf ein Element.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen konstanten Verweis auf ein Element.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_const_reference.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        cliext::vector<wchar_t>::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reverse_iterator"></a> Vector:: const_reverse_iterator (STL/CLR)
Der Typ eines Konstanten umgekehrten Iterators für die gesteuerte Sequenz...  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt vom angegebenen Typ `T4` , die als Konstanten umgekehrten Iterators für die gesteuerte Sequenz fungieren kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::vector<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::vector<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  

## <a name="difference_type"></a> Vector:: difference_type (STL/CLR)
Die Typen des Abstands mit Vorzeichen zwischen zwei Elementen.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein mit Vorzeichen Elementanzahl.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_difference_type.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::vector<wchar_t>::difference_type diff = 0;   
    for (cliext::vector<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::vector<wchar_t>::iterator it = c1.end();   
        it != c1.begin(); --it) --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
begin()-end() = -3  
```  

## <a name="empty"></a> Vector:: Empty (STL/CLR)
Testet, ob keine Elemente vorhanden sind.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool empty();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt „true“ für eine leere gesteuerte Sequenz zurück. Dies ist äquivalent zum [Vector:: Size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`() == 0`. Sie verwenden sie zum Überprüfen, ob der Vektor leer ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_empty.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  

## <a name="end"></a> Vector:: End (STL/CLR)
Legt das Ende der kontrollierten Sequenz fest.  
  
### <a name="syntax"></a>Syntax  
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einem Iterator mit zufälligem Zugriff, der direkt hinter das Ende der kontrollierten Sequenz verweist. Es mit der einen Iterator abrufen, bestimmt die `current` Ende der kontrollierten Sequenz, aber dessen Status kann ändern, wenn die Länge der gesteuerten Sequenz geändert wird.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_end.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    cliext::vector<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
 a x y  
```  

## <a name="erase"></a> Vector:: Erase (STL/CLR)
Entfernt Elemente an den angegebenen Positionen.  
  
### <a name="syntax"></a>Syntax  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Parameter  
 first  
 Anfang des Bereichs, der gelöscht.  
  
 last  
 Das Ende des Bereichs zu löschen.  
  
 wo  
 Element löschen.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion entfernt das Element der kontrollierten Sequenz verweist `where`. Es können Sie verwenden, um ein einzelnes Element zu entfernen.  
  
 Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich [`first`, `last`). Sie verwenden es, NULL oder mehr aufeinander folgende Elemente entfernt.  
  
 Beide Memberfunktionen geben einen Iterator, der das erste Element, das über alle Elemente entfernt wurden, oder [Vector:: End (STL/CLR)](../dotnet/vector-end-stl-clr.md) `()` Wenn kein solches Element vorhanden ist.  
  
 Wenn Elemente zu löschen, ist die Anzahl von Elementkopien linear zur Anzahl von Elementen zwischen dem Ende des Löschens und näher am Ende der Sequenz. (Wenn ein oder mehrere Elemente an einem Ende der Sequenz zu löschen, erfolgen keine Elementkopien.)  
  
### <a name="example"></a>Beispiel  
  
```cpp 
// cliext_vector_erase.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::vector<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  

## <a name="front"></a> Vector:: Front (STL/CLR)
Greift auf das erste Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
reference front();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Verweis auf das erste Element der gesteuerten Sequenz, die nicht leer sein darf. Sie verwenden ihn zum Lesen oder schreiben das erste Element, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_front.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front() = a  
 x b c  
```  

# <a name="front_item"></a> Vector:: front_item (STL/CLR)
Greift auf das erste Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
property value_type front_item;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaft greift auf das erste Element der gesteuerten Sequenz, die nicht leer sein darf. Sie verwenden ihn zum Lesen oder schreiben das erste Element, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_front_item.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front_item = a  
 x b c  
```  

# <a name="generic_container"></a> Vector::generic_container (STL/CLR)
Der Typ der generischen Schnittstelle für den Container.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef Microsoft::VisualC::StlClr::  
    IVector<generic_value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt die generische Schnittstelle für diese Vorlage Container-Klasse.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_generic_container.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(gc1->end(), L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push_back(L'e');   
  
    System::Collections::IEnumerator^ enum1 =   
        gc1->GetEnumerator();   
    while (enum1->MoveNext())   
        System::Console::Write(" {0}", enum1->Current);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c d  
a b c d e  
```  

## <a name="generic_iterator"></a> Vector::generic_iterator (STL/CLR)
Der Typ eines Iterators für die Verwendung mit der generischen Schnittstelle für den Container.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerRandomAccessIterator<generic_value>  
    generic_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen generischen Iterator, der für diese Vorlage Container-Klasse mit der generischen Schnittstelle verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::vector<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

# <a name="generic_reverse_iterator"></a> Vector::generic_reverse_iterator (STL/CLR)
Der Typ eines umgekehrten Iterators für die Verwendung mit der generischen Schnittstelle für den Container.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen generischen reverse-Iterator, der für diese Vorlage Container-Klasse mit der generischen Schnittstelle verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::vector<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();   
    cliext::vector<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a c c  
```  

## <a name="generic_value"></a> Vector::generic_value (STL/CLR)
Der Typ eines Elements für die Verwendung mit der generischen Schnittstelle für den Container.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt des Typs `GValue` , beschreibt die gespeicherten Elementwert für die Verwendung mit der generischen Schnittstelle für diese Vorlage Container-Klasse.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_generic_value.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::vector<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

## <a name="insert"></a> Vector:: Insert (STL/CLR)
Fügt Elemente an einer angegebenen Position hinzu.  
  
### <a name="syntax"></a>Syntax  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parameter  
 count  
 Die Anzahl einzufügender Elemente.  
  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 Rechts  
 Die Enumeration eingefügt.  
  
 Val  
 Der Wert des einzufügenden Elements.  
  
 wo  
 Die Position, im Container vor dem Einfügen.  
  
### <a name="remarks"></a>Hinweise  
 Jede der memberfunktionseinfügungen, vor dem Element verweist `where` in der gesteuerten Sequenz eine Sequenz von den verbleibenden Operanden angegeben.  
  
 Die erste Memberfunktion Fügt ein Element mit dem Wert `val` und gibt einen Iterator, der das neu eingefügte Element festlegt. Sie verwenden es um ein einzelnes Element vor einem Ort, ein Iterator bezeichnete einzufügen.  
  
 Die zweite Memberfunktion fügt eine Wiederholung der `count`-Elemente des Werts `val` ein. Sie verwenden ihn zum Einfügen von NULL oder mehr aufeinander folgende Elementen sind alle Kopien den gleichen Wert.  
  
 Wenn `InIt` ein Ganzzahltyp ist, verhält sich die dritte Memberfunktion genau wie `insert(where, (size_type)first, (value_type)last)`. Andernfalls fügt die Sequenz [`first`, `last`). Sie verwenden ihn zum Einfügen von NULL oder mehr zusammenhängender Elementen, die aus einer anderen Sequenz kopiert.  
  
 Die vierte Memberfunktion fügt die Sequenz, die vom angegebenen der `right`. Sie verwenden es, fügen Sie eine Sequenz, die durch einen Enumerator beschrieben.  
  
 Wenn Sie ein einzelnes Element einfügen, ist die Anzahl von Elementkopien linear zur Anzahl der Elemente zwischen der Einfügemarke und näher am Ende der Sequenz. (Wenn ein oder mehrere Elemente an einem Ende der Sequenz eingefügt wurden, erfolgen keine Elementkopien.) Wenn `InIt` ein input-Iterator, ist die dritte Memberfunktion führt eine einzelne Einfügung effektiv für jedes Element in der Sequenz. Andernfalls, beim Einfügen von `N` Elemente, die die Anzahl der Elementkopien ist linear `N` plus die Anzahl der Elemente zwischen der Einfügemarke und näher am Ende der Sequenz.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_insert.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::vector<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  
  
## <a name="iterator"></a> Vector:: Iterator (STL/CLR)
Der Typ eines Iterators für die gesteuerte Sequenz.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt vom angegebenen Typ `T1` , die als ein random-Access-Iterator für die gesteuerte Sequenz fungieren kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    it = c1.begin();   
    *it = L'x';   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x b c  
```  

## <a name="op_as"></a> Vector:: Operator = (STL/CLR)
Ersetzt die kontrollierte Sequenz.  
  
### <a name="syntax"></a>Syntax  
  
```  
vector<Value>% operator=(vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 Rechts  
 Der zu kopierende Container.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Operator Kopien `right` klicken Sie dann auf das Objekt gibt `*this`. Sie können ihn verwenden, um die kontrollierte Sequenz durch eine Kopie der kontrollierten Sequenz in `right` zu ersetzen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_operator_as.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="op"></a> Vector::Operator(STL/CLR)
Greift auf ein Element an einer angegebenen Position zu.  
  
### <a name="syntax"></a>Syntax  
  
```  
reference operator[](size_type pos);  
```  
  
#### <a name="parameters"></a>Parameter  
 pos  
 Position des Elements, auf das zugegriffen wird  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt eine Referene zurück, auf das Element an der Position `pos`. Sie verwenden es, auf ein Element zuzugreifen, deren Position Sie kennen.  
  
### <a name="example"></a>Beispiel  
  
```cpp 
// cliext_vector_operator_sub.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using subscripting   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1[1] = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  

## <a name="pop_back"></a> Vector:: pop_back (STL/CLR)
Entfernt das letzte Element.  
  
### <a name="syntax"></a>Syntax  
  
```  
void pop_back();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion entfernt das letzte Element der gesteuerten Sequenz, die nicht leer sein darf. Sie verwenden es, um indem Sie ein Element auf der Rückseite den Vektor zu verkürzen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_pop_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_back();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b  
```  

## <a name="push_back"></a> Vector:: push_back (STL/CLR)
Fügt ein neues Letztes Element hinzu.  
  
### <a name="syntax"></a>Syntax  
  
```  
void push_back(value_type val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion Fügt ein Element mit dem Wert `val` am Ende der kontrollierten Sequenz. Sie verwenden es, ein anderes Element in den Vektor angefügt werden soll.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_push_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="rbegin"></a> Vector:: rbegin (STL/CLR)
Legt den Anfang der umgekehrten kontrollierten Sequenz fest.  
  
### <a name="syntax"></a>Syntax  
  
```  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen umgekehrten Iterator, der das letzte Element der kontrollierten Sequenz oder nur vor dem Anfang einer leeren Sequenz zurück. Daher kennzeichnet es die `beginning` der umgekehrten Sequenz. Es mit der einen Iterator abrufen, bestimmt die `current` Anfang der kontrollierten Sequenz in umgekehrter Reihenfolge kann ändern, wenn die Länge der gesteuerten Sequenz geändert wird.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_rbegin.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
 a y x  
```  

## <a name="reference"></a> Vector:: Reference (STL/CLR)
Der Typ eines Verweises auf ein Element.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen Verweis auf ein Element.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_reference.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::vector<wchar_t>::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
  
// modify contents " a b c"   
    for (it = c1.begin(); it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::vector<wchar_t>::reference ref = *it;   
  
        ref += (wchar_t)(L'A' - L'a');   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
A B C  
```  

## <a name="rend"></a> Vector:: rend (STL/CLR)
Legt das Ende der umgekehrten kontrollierten Sequenz fest.  
  
### <a name="syntax"></a>Syntax  
  
```  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einem reverse-Iterator, verweist direkt hinter dem Anfang der kontrollierten Sequenz zurück. Daher kennzeichnet es die `end` der umgekehrten Sequenz. Es mit der einen Iterator abrufen, bestimmt die `current` Ende der kontrollierten Sequenz in umgekehrter Reihenfolge, aber dessen Status kann ändern, wenn die Länge der gesteuerten Sequenz geändert wird.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_rend.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
 y x c  
```  

## <a name="reserve"></a> Vector:: Reserve (STL/CLR)
Es wird sichergestellt, dass eine Erweiterung der Mindestkapazität für den Container.  
  
### <a name="syntax"></a>Syntax  
  
```  
void reserve(size_type count);  
```  
  
#### <a name="parameters"></a>Parameter  
 count  
 Neue Mindestkapazität des Containers.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion wird sichergestellt, dass `capacity()` künftig gibt mindestens `count`. Sie verwenden es, um sicherzustellen, dass der Container nicht Speicher neu zuordnen muss für die gesteuerte Sequenz bis er in die angegebene Größe geworden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_reserve.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
capacity() = 4, ok = True  
capacity() = 9, ok = True  
```  

## <a name="resize"></a> Vector:: Resize (STL/CLR)
Ändert die Anzahl der Elemente an.  
  
### <a name="syntax"></a>Syntax  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>Parameter  
 new_size  
 Neue Größe der gesteuerten Sequenz.  
  
 Val  
 Der Wert des Elements Auffüllung.  
  
### <a name="remarks"></a>Hinweise  
 Die beiden Memberfunktionen sicher, dass [Vector:: Size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `()` künftig gibt `new_size`. Wenn die gesteuerte Sequenz verlängert werden muss, fügt die erste Memberfunktion Elemente mit dem Wert `value_type()` an, während die zweite Memberfunktion Elemente mit dem Wert `val` anfügt. Um die gesteuerte Sequenz kürzere zu machen, beide Memberfunktionen effektiv das letzte Element löschen [Vector:: Size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `() -` `new_size` Zeiten. Sie können damit stellen Sie sicher, dass die kontrollierte Sequenz Größe hat `new_size`, indem Sie verkürzen oder Auffüllen von der aktuellen gesteuerten Sequenz.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_resize.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  

## <a name="reverse_iterator"></a> Vector:: reverse_iterator (STL/CLR)
Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt vom angegebenen Typ `T3` , die als umgekehrten Iterators für die gesteuerte Sequenz dienen kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
x b a  
```  

## <a name="size"></a> Vector:: Size (STL/CLR)
Ermittelt die Anzahl von Elementen.  
  
### <a name="syntax"></a>Syntax  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Länge der gesteuerten Sequenz zurück. Sie können erkennen, die Anzahl der Elemente, die derzeit in der kontrollierten Sequenz. Wenn Sie von Interesse ist, ob die Sequenz ungleich Größe finden Sie unter hat, [Vector:: Empty (STL/CLR)](../dotnet/vector-empty-stl-clr.md)`()`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_size.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 0 after clearing  
size() = 2 after adding 2  
```  

## <a name="size_type"></a> Vector:: size_type (STL/CLR)
Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein nicht negativer Elementanzahl.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_size_type.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::vector<wchar_t>::size_type diff = c1.end() - c1.begin();   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  
  
## <a name="swap"></a> Vector:: Swap (STL/CLR)
Vertauscht den Inhalt von zwei Containern.  
  
### <a name="syntax"></a>Syntax  
  
```  
void swap(vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 Rechts  
 Container für den Tausch von Inhalten.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion tauscht die kontrollierten Sequenzen zwischen `*this` und `right`aus. Dies erfolgt in konstanter Zeit, und es löst keine Ausnahmen. Sie verwenden es als eine schnelle Möglichkeit zum Austauschen von den Inhalt von zwei Containern.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_swap.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::vector<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x x x x x  
x x x x x  
a b c  
```  

## <a name="to_array"></a> Vector::to_array (STL/CLR)
Kopiert die gesteuerte Sequenz in ein neues Array.  
  
### <a name="syntax"></a>Syntax  
  
```  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt ein Array mit der kontrollierten Sequenz zurück. Sie können sie eine Kopie der gesteuerten Sequenz im Arrayform abrufen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_to_array.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  

## <a name="value_type"></a> Vector:: value_type (STL/CLR)
Der Typ eines Elements.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Value` dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_value_type.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::vector<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::vector<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="vector"></a> Vector:: Vector (STL/CLR)
Erstellt ein container-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parameter  
 count  
 Die Anzahl einzufügender Elemente.  
  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 Rechts  
 Einzufügendes Objekt bzw. einzufügender Bereich.  
  
 Val  
 Der Wert des einzufügenden Elements.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `vector();`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente. Sie können damit Geben Sie eine leere gesteuerte Sequenz.  
  
 Der Konstruktor:  
  
 `vector(vector<Value>% right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right.begin()`, `right.end()`). Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch das Vektorobjekt gesteuert wird `right`.  
  
 Der Konstruktor:  
  
 `vector(vector<Value>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right->begin()`, `right->end()`). Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die von der Vector-Objekt, dessen Handle, gesteuert wird `right`.  
  
 Der Konstruktor:  
  
 `explicit vector(size_type count);`  
  
 Initialisiert die gesteuerte Sequenz mit `count` jedes Elemente mit dem Wert `value_type()`. Sie verwenden es den Container mit Elementen gefüllt alle mit dem Standardwert.  
  
 Der Konstruktor:  
  
 `vector(size_type count, value_type val);`  
  
 Initialisiert die gesteuerte Sequenz mit `count` jedes Elemente mit dem Wert `val`. Sie verwenden sie den Container mit Elementen gefüllt alle mit dem gleichen Wert.  
  
 Der Konstruktor:  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`). Sie können damit der gesteuerten Sequenz eine Kopie einer anderen Sequenz erstellen.  
  
 Der Konstruktor:  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`. Sie können damit der gesteuerten Sequenz eine Kopie einer anderen Sequenz beschrieben durch einen Enumerator erstellen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  

## <a name="op_neq"></a> Operator! = (Vektor) (STL/CLR)
Vector-Vergleich nicht gleich sind.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value>  
    bool operator!=(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linker zu vergleichender Container.  
  
 Rechts  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `!(left == right)`. Verwenden sie zum Testen, ob `left` nicht sortiert wird, ist identisch mit `right` Wenn die beiden Vektoren verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_operator_ne.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  

## <a name="op_lt"></a> Operator&lt; (Vektor) (STL/CLR)
Vektor kleiner-als-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    bool operator<(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linker zu vergleichender Container.  
  
 Rechts  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator-Funktion gibt "true" zurück, wenn, für die niedrigste Position `i` für die `!(right[i] < left[i])` es ist auch, die "true" `left[i] < right[i]`. Andernfalls wird zurückgegeben `left->size() < right->size()` Sie zum Testen verwenden, ob `left` sortiert ist, bevor Sie `right` Wenn die beiden Vektoren verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_operator_lt.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  

## <a name="op_lteq"></a> Operator&lt;= (Vektor) (STL/CLR)
Vektor kleiner oder gleich Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    bool operator<=(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linker zu vergleichender Container.  
  
 Rechts  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `!(right < left)`. Sie zum Testen verwenden, ob `left` ist nicht geordnet nach `right` Wenn die beiden Vektoren verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_operator_le.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] <= [a b c] is True  
[a b d] <= [a b c] is False  
```  

## <a name="op_eq"></a> Operator == (Vektor) (STL/CLR)
Vektor gleich Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    bool operator==(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linker zu vergleichender Container.  
  
 Rechts  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Die Operatorfunktion gibt "true" nur, wenn die Sequenzen von gesteuert `left` und `right` haben die gleiche Länge und für die einzelnen Positionen `i`, `left[i] ==` `right[i]`. Sie verwenden es, um zu testen, ob `left` sortiert wird, ist identisch mit `right` Wenn die beiden Vektoren verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_operator_eq.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] == [a b c] is True  
[a b c] == [a b d] is False  
```  

## <a name="op_gt"></a> Operator&gt; (Vektor) (STL/CLR)
Der Vektor ist größer als-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    bool operator>(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linker zu vergleichender Container.  
  
 Rechts  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `right` `<` `left`. Sie zum Testen verwenden, ob `left` sortiert wird, ist nach `right` Wenn die beiden Vektoren verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_operator_gt.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] > [a b c] is False  
[a b d] > [a b c] is True  
```  

## <a name="op_gteq"></a> Operator&gt;= (Vektor) (STL/CLR)
Vektor größer oder gleich Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value>  
    bool operator>=(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linker zu vergleichender Container.  
  
 Rechts  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `!(left < right)`. Sie verwenden es, um zu testen, ob `left` nicht sortiert ist `right` Wenn die beiden Vektoren verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_vector_operator_ge.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] >= [a b c] is True  
[a b c] >= [a b d] is False  
```  
