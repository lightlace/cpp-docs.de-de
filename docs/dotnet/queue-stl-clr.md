---
title: Warteschlange (STL/CLR) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue
- cliext::operator!=
- cliext::operator<
- cliext::operator<=
- cliext::operator==
- cliext::operator>
- cliext::operator>=
- cliext::queue::assign
- cliext::queue::back
- cliext::queue::back_item
- cliext::queue::const_reference
- cliext::queue::container_type
- cliext::queue::difference_type
- cliext::queue::empty
- cliext::queue::front
- cliext::queue::front_item
- cliext::queue::generic_container
- cliext::queue::generic_value
- cliext::queue::get_container
- cliext::queue::operator=
- cliext::queue::pop
- cliext::queue::push
- cliext::queue::queue
- cliext::queue::reference
- cliext::queue::size
- cliext::queue::size_type
- cliext::queue::to_array
- cliext::queue::value_type
dev_langs:
- C++
helpviewer_keywords:
- <queue> header [STL/CLR]
- queue class [STL/CLR]
- <cliext/queue> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- push member [STL/CLR]
- queue member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: adf65c4af70b0ba6bc1f089576d69160ab21a5b6
ms.sourcegitcommit: bad2441d1930275ff506d44759d283d94cccd1c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2018
ms.locfileid: "39375996"
---
# <a name="queue-stlclr"></a>queue (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge Sequenz von Elementen steuert, die First in First Out Zugriff hat. Verwenden des Adapters Container `queue` einen zugrunde liegenden Container wie eine Warteschlange zu verwalten.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit *Wert* , wenn die zweite ein Ref-Typ ist, in diesem Fall ist es `Value^`. Auf ähnliche Weise `GContainer` ist identisch mit *Container* , wenn die zweite ein Ref-Typ ist, in diesem Fall ist es `Container^`.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    ref class queue  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>  
    { ..... };  
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
 *Container*  
 Der Typ des zugrunde liegenden Containers.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext bzw. einer neuen Warteschlange >  
  
 **Namespace:** Cliext  

## <a name="declarations"></a>Deklarationen  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[queue::const_reference (STL/CLR)](#const_reference)|Der Typ eines konstanten Verweises auf ein Element.|  
|[queue::container_type (STL/CLR)](#container_type)|Der Typ des zugrunde liegenden Containers.|  
|[queue::difference_type (STL/CLR)](#difference_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[queue::generic_container (STL/CLR)](#generic_container)|Der Typ der generischen Schnittstelle für den Containeradapter.|  
|[queue::generic_value (STL/CLR)](#generic_value)|Der Typ eines Elements für die generische Schnittstelle für den Containeradapter.|  
|[queue::reference (STL/CLR)](#reference)|Der Typ eines Verweises auf ein Element.|  
|[queue::size_type (STL/CLR)](#size_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[queue::value_type (STL/CLR)](#value_type)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[queue::assign (STL/CLR)](#assign)|Ersetzt alle Elemente.|  
|[queue::back (STL/CLR)](#back)|Greift auf das letzte Element zu.|  
|[queue::empty (STL/CLR)](#empty)|Testet, ob keine Elemente vorhanden sind.|  
|[queue::front (STL/CLR)](#front)|Greift auf das erste Element zu.|  
|[queue::get_container (STL/CLR)](#get_container)|Greift auf die zugrunde liegenden Containers.|  
|[queue::pop (STL/CLR)](#pop)|Entfernt das erste Element.|  
|[queue::push (STL/CLR)](#push)|Fügt ein neues Letztes Element hinzu.|  
|[queue::queue (STL/CLR)](#queue)|Erstellt ein container-Objekt.|  
|[queue::size (STL/CLR)](#size)|Ermittelt die Anzahl von Elementen.|  
|[queue::to_array (STL/CLR)](#to_array)|Kopiert die kontrollierte Sequenz in ein neues Array.|  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|[queue::back_item (STL/CLR)](#back_item)|Greift auf das letzte Element zu.|  
|[queue::front_item (STL/CLR)](#front_item)|Greift auf das erste Element zu.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[queue::operator= (STL/CLR)](#op_as)|Ersetzt die kontrollierte Sequenz.|  
|[operator!= (queue) (STL/CLR)](#op_neq)|Bestimmt, ob eine `queue` Objekt ist nicht gleich einem anderen `queue` Objekt.|  
|[operator< (queue) (STL/CLR)](#op_lt)|Bestimmt, ob eine `queue` Objekt ist kleiner als ein anderes `queue` Objekt.|  
|[operator<= (queue) (STL/CLR)](#op_lteq)|Bestimmt, ob eine `queue` Objekt ist kleiner als oder gleich einem anderen `queue` Objekt.|  
|[operator== (queue) (STL/CLR)](#op_eq)|Bestimmt, ob eine `queue` Objekt ist gleich einem anderen `queue` Objekt.|  
|[operator> (queue) (STL/CLR)](#op_gt)|Bestimmt, ob eine `queue` Objekt ist größer als ein anderer `queue` Objekt.|  
|[operator>= (queue) (STL/CLR)](#op_gteq)|Bestimmt, ob eine `queue` Objekt ist größer als oder gleich einem anderen `queue` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|IQueue\<-Wert, der Container >|Behalten Sie die generischen Container-Adapter.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist speicherbelegungen und-Freigaben für die gesteuerte Sequenz durch eine zugrunde liegenden Containers, eines Typs `Container`, speichert `Value` Elemente und wächst nach Bedarf. Objekts schränkt den Zugriff auf Sie übertragen nur das erste Element und entfernt das letzte Element, in die Implementierung einer First in First Out Warteschlange (auch bekannt als eine FIFO-Warteschlange oder einfach eine Warteschlange).  
  
## <a name="members"></a>Member

## <a name="assign"></a> Queue::Assign (STL/CLR)
Ersetzt alle Elemente.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
void assign(queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *right*  
 Der Containeradapter, einfügen.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion weist `right.get_container()` in den zugrunde liegenden Container. Damit können Sie um den gesamten Inhalt der Warteschlange zu ändern.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_assign.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Myqueue c2;   
    c2.assign(c1);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="back"></a> Queue:: Back (STL/CLR)
Greift auf das letzte Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
reference back();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Verweis auf das letzte Element der kontrollierten Sequenz, die nicht leer sein darf. Damit können Sie das letzte Element zuzugreifen, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_back.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1.get_container())   
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

## <a name="back_item"></a> Queue::back_item (STL/CLR)
Greift auf das letzte Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
property value_type back_item;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaft greift auf das letzte Element der kontrollierten Sequenz, die nicht leer sein darf. Sie verwenden ihn zum Lesen oder schreiben das letzte Element, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_back_item.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
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

## <a name="const_reference"></a> Queue::const_reference (STL/CLR)
Der Typ eines konstanten Verweises auf ein Element.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen konstanten Verweis auf ein Element.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_const_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Myqueue::const_reference cref = c1.front();   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="container_type"></a> Queue:: container_type (STL/CLR)
Der Typ des zugrunde liegenden Containers.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef Container value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Container` dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_container_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Myqueue::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="difference_type"></a> Queue::difference_type (STL/CLR)
Die Typen des Abstands zwischen den beiden Elementen mit Vorzeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine möglicherweise negative Elementanzahl.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_difference_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute negative difference   
    Myqueue::difference_type diff = c1.size();   
    c1.push(L'd');   
    c1.push(L'e');   
    diff -= c1.size();   
    System::Console::WriteLine("pushing 2 = {0}", diff);   
  
// compute positive difference   
    diff = c1.size();   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("popping 3 = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
pushing 2 = -2  
popping 3 = 3  
```  

## <a name="empty"></a> Queue:: Empty (STL/CLR)
Testet, ob keine Elemente vorhanden sind.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
bool empty();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt „true“ für eine leere gesteuerte Sequenz zurück. Dies ist äquivalent zum [Queue:: Size (STL/CLR)](../dotnet/queue-size-stl-clr.md)`() == 0`. Damit können Sie überprüfen, ob die Warteschlange leer ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_empty.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.pop();   
    c1.pop();   
    c1.pop();   
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

## <a name="front"></a> Queue:: Front (STL/CLR)
Greift auf das erste Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
reference front();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Verweis auf das erste Element der kontrollierten Sequenz, die nicht leer sein darf. Damit können Sie das erste Element, zugreifen, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_front.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1.get_container())   
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

## <a name="front_item"></a> Queue::front_item (STL/CLR)
Greift auf das erste Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
property value_type front_item;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaft greift auf das erste Element der kontrollierten Sequenz, die nicht leer sein darf. Sie verwenden ihn zum Lesen oder schreiben das erste Element, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_front_item.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter last item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
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

## <a name="generic_container"></a> Queue::generic_container (STL/CLR)
Der Typ der generischen Schnittstelle für den Containeradapter.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef Microsoft::VisualC::StlClr::IQueue<Value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt die generische Schnittstelle für diese Container Adapter-Vorlagenklasse.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_generic_container.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myqueue::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push(L'e');   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
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

## <a name="generic_value"></a> Queue::generic_value (STL/CLR)
Der Typ eines Elements für die Verwendung mit der generischen Schnittstelle für den Container.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt des Typs `GValue` , beschreibt den gespeichertes Element-Wert für die Verwendung mit der generischen Schnittstelle für diese Vorlage Container-Klasse. (`GValue` ist entweder `value_type` oder `value_type^` Wenn `value_type` ist ein Ref-Typ.)  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_generic_value.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get interface to container   
    Myqueue::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display in order using generic_value   
    for (; !gc1->empty(); gc1->pop())   
        {   
        Myqueue::generic_value elem = gc1->front();   
  
        System::Console::Write(" {0}", elem);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a b c  
```  

## <a name="get_container"></a> Queue:: get_container (STL/CLR)
Greift auf die zugrunde liegenden Containers.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
container_type^ get_container();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt den zugrunde liegenden Container zurück. Damit können Sie um die Einschränkungen, die vom Container Wrapper zu umgehen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_get_container.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="op_as"></a> Queue::Operator = (STL/CLR)
Ersetzt die kontrollierte Sequenz.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
queue <Value, Container>% operator=(queue <Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *right*  
 Der Containeradapter, zu kopieren.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Operator Kopien *rechten* klicken Sie dann auf das Objekt, gibt `*this`. Damit können Sie die kontrollierte Sequenz durch eine Kopie der kontrollierten Sequenz in ersetzen *rechten*.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_operator_as.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
a b c  
a b c  
```  

## <a name="pop"></a> Queue:: POP (STL/CLR)
Entfernt das letzte Element.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
void pop();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion entfernt das letzte Element der kontrollierten Sequenz, die nicht leer sein darf. Sie verwenden, um ein Element an der Rückseite die Warteschlange zu verkürzen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_pop.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop();   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
b c  
```  

## <a name="push"></a> Queue:: Push (STL/CLR)
Fügt ein neues Letztes Element hinzu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
void push(value_type val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion Fügt ein Element mit dem Wert `val` am Ende der Warteschlange. Damit können Sie ein Element an die Warteschlange angefügt werden soll.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_push.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="queue"></a> Queue:: Queue (STL/CLR)
Erstellt ein Containerobjekt für den Adapter.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
queue();  
queue(queue<Value, Container>% right);  
queue(queue<Value, Container>^ right);  
explicit queue(container_type% wrapped);  
```  
  
#### <a name="parameters"></a>Parameter  
 *right*  
 Zu kopierende Objekt.  
  
 *Umschlossen*  
 Umschlossene Container verwenden.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `queue();`  
  
 erstellt einen leeren umschlossenen Container an. Damit können Sie eine leere gesteuerte Sequenz angeben.  
  
 Der Konstruktor:  
  
 `queue(queue<Value, Container>% right);`  
  
 erstellt einen Wrapper-Container, die eine Kopie des `right.get_container()`. Damit können Sie eine gesteuerte Sequenz angeben, die eine Kopie der gesteuerte Sequenz durch das Queue-Objekt ist *rechten*.  
  
 Der Konstruktor:  
  
 `queue(queue<Value, Container>^ right);`  
  
 erstellt einen Wrapper-Container, die eine Kopie des `right->get_container()`. Damit können Sie eine gesteuerte Sequenz angeben, die eine Kopie der gesteuerte Sequenz durch das Queue-Objekt ist `*right`.  
  
 Der Konstruktor:  
  
 `explicit queue(container_type wrapped);`  
  
 den vorhandenen Container verwendet *umschlossen* als umschlossene Container. Damit können Sie um eine Warteschlange aus einem vorhandenen Container zu erstellen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/list>   
  
typedef cliext::queue<wchar_t> Myqueue;   
typedef cliext::list<wchar_t> Mylist;   
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;   
int main()   
    {   
// construct an empty container   
    Myqueue c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Mylist v2(5, L'x');   
    Myqueue_list c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myqueue_list c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Myqueue_list c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
size() = 0  
 x x x x x  
 x x x x x  
 x x x x x  
```  

## <a name="reference"></a> Queue::Reference (STL/CLR)
Der Typ eines Verweises auf ein Element.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen Verweis auf ein Element.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify back of queue and redisplay   
    Myqueue::reference ref = c1.back();   
    ref = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b x  
```  

## <a name="size"></a> Queue:: Size (STL/CLR)
Ermittelt die Anzahl von Elementen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
size_type size();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Länge der gesteuerten Sequenz zurück. Damit können Sie die Anzahl der Elemente, die derzeit in der kontrollierten Sequenz bestimmt. Wenn Sie besonders interessierenden lediglich, ob die Reihenfolge größer, finden Sie unter hat [Queue:: Empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md)`()`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_size.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 2 after popping  
size() = 4 after adding 2  
```  

## <a name="size_type"></a> Queue:: size_type (STL/CLR)
Der Typ eines Abstands zwischen den beiden Elementen mit Vorzeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine nicht Negative Elementanzahl.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_size_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Myqueue::size_type diff = c1.size();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("size difference = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
size difference = 2  
```  

## <a name="to_array"></a> Queue::to_array (STL/CLR)
Kopiert die kontrollierte Sequenz in ein neues Array.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt ein Array mit der kontrollierten Sequenz zurück. Damit können Sie eine Kopie der kontrollierten Sequenz in Arrayform abrufen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_to_array.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push(L'd');   
    for each (wchar_t elem in c1.get_container())   
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

## <a name="value_type"></a> Queue:: value_type (STL/CLR)
Der Typ eines Elements.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter *Wert*.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_value_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " a b c" using value_type   
    for (; !c1.empty(); c1.pop())   
        {   // store element in value_type object   
        Myqueue::value_type val = c1.front();   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
a b c  
```  

## <a name="op_neq"></a> Operator! = (Warteschlange) (STL/CLR)
Nicht gleich-Vergleich in die Warteschlange.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator!=(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, die Operatorfunktion `!(left == right)`. Damit können Sie testen, ob *linken* nicht sortiert wird, ist identisch mit *rechten* bei beiden Warteschlangen verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_operator_ne.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
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

## <a name="op_lt"></a> Operator&lt; (Warteschlange) (STL/CLR)
Die Warteschlange kleiner als-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator<(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator-Funktion gibt "true" zurück, wenn, für die niedrigste Position `i` für die `!(right[i] < left[i])` es ist auch, die "true" `left[i] < right[i]`. Andernfalls wird `left->` [Queue:: Size (STL/CLR)](../dotnet/queue-size-stl-clr.md) `() <` `right->size()` damit können Sie testen, ob *linken* sortiert ist, bevor Sie *rechten* Wenn die zwei Warteschlangen verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_operator_lt.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
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

## <a name="op_lteq"></a> Operator&lt;= (Warteschlange) (STL/CLR)
Kleiner oder gleich in die Warteschlange Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator<=(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, die Operatorfunktion `!(right < left)`. Damit können Sie testen, ob *linken* wird nicht nach dem sortiert *rechten* bei beiden Warteschlangen verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_operator_le.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
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

## <a name="op_eq"></a> Operator == (Warteschlange) (STL/CLR)
Queue-gleich-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator==(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Die Operatorfunktion gibt "true" nur dann, wenn die Sequenzen von gesteuert *linken* und *rechten* die gleiche Länge aufweisen und für jede Position `i`, `left[i] ==` `right[i]`. Damit können Sie testen, ob *linken* sortiert wird, ist identisch mit *rechten* bei beiden Warteschlangen verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_operator_eq.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
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

## <a name="op_gt"></a> Operator&gt; (Warteschlange) (STL/CLR)
Die Warteschlange ist größer als-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator>(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, die Operatorfunktion `right` `<` `left`. Damit können Sie testen, ob *linken* sortiert wird, ist nach *rechten* bei beiden Warteschlangen verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_operator_gt.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
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

## <a name="op_gteq"></a> Operator&gt;= (Warteschlange) (STL/CLR)
Warteschlange, die größer als oder gleich-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator>=(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, die Operatorfunktion `!(left < right)`. Damit können Sie testen, ob *linken* ist nicht geordnet, bevor Sie *rechten* bei beiden Warteschlangen verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_queue_operator_ge.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
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