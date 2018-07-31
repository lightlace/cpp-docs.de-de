---
title: Stack (STL/CLR) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack
- cliext::operator!=
- cliext::operator<
- cliext::operator<=
- cliext::operator==
- cliext::operator>
- cliext::operator>=
- cliext::stack::assign
- cliext::stack::const_reference
- cliext::stack::container_type
- cliext::stack::difference_type
- cliext::stack::empty
- cliext::stack::generic_container
- cliext::stack::generic_value
- cliext::stack::get_container
- cliext::stack::operator=
- cliext::stack::pop
- cliext::stack::push
- cliext::stack::reference
- cliext::stack::size
- cliext::stack::size_type
- cliext::stack::stack
- cliext::stack::to_array
- cliext::stack::top
- cliext::stack::top_item
- cliext::stack::value_type
dev_langs:
- C++
helpviewer_keywords:
- <stack> header [STL/CLR]
- <cliext/stack> header [STL/CLR]
- stack class [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- stack member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 09368f3a43a5ba7a5a1c4247fdbbccdf345b0b21
ms.sourcegitcommit: bad2441d1930275ff506d44759d283d94cccd1c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2018
ms.locfileid: "39376208"
---
# <a name="stack-stlclr"></a>stack (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das eine Elementsequenz variabler Länge Sequenz von Elementen steuert, die Last in First Out Zugriff hat. Verwenden des Adapters Container `stack` einen zugrunde liegenden Container als Pushdown-Stack zu verwalten.  
  
 In der folgenden Beschreibung `GValue` ist identisch mit *Wert* , wenn die zweite ein Ref-Typ ist, in diesem Fall ist es `Value^`. Auf ähnliche Weise `GContainer` ist identisch mit *Container* , wenn die zweite ein Ref-Typ ist, in diesem Fall ist es `Container^`.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
    { ..... };  
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Der Typ eines Elements in der kontrollierten Sequenz.  
  
 *Container*  
 Der Typ des zugrunde liegenden Containers.  

## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Stack >  
  
 **Namespace:** Cliext  
  
## <a name="declarations"></a>Deklarationen  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[stack::const_reference (STL/CLR)](#const_reference)|Der Typ eines konstanten Verweises auf ein Element.|  
|[stack::container_type (STL/CLR)](#container_type)|Der Typ des zugrunde liegenden Containers.|  
|[stack::difference_type (STL/CLR)](#difference_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[stack::generic_container (STL/CLR)](#generic_container)|Der Typ der generischen Schnittstelle für den Containeradapter.|  
|[stack::generic_value (STL/CLR)](#generic_value)|Der Typ eines Elements für die generische Schnittstelle für den Containeradapter.|  
|[stack::reference (STL/CLR)](#reference)|Der Typ eines Verweises auf ein Element.|  
|[stack::size_type (STL/CLR)](#size_type)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[stack::value_type (STL/CLR)](#value_type)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[stack::assign (STL/CLR)](#assign)|Ersetzt alle Elemente.|  
|[stack::empty (STL/CLR)](#empty)|Testet, ob keine Elemente vorhanden sind.|  
|[stack::get_container (STL/CLR)](#get_container)|Greift auf die zugrunde liegenden Containers.|  
|[stack::pop (STL/CLR)](#pop)|Entfernt das letzte Element.|  
|[stack::push (STL/CLR)](#push)|Fügt ein neues Letztes Element hinzu.|  
|[stack::size (STL/CLR)](#size)|Ermittelt die Anzahl von Elementen.|  
|[stack::stack (STL/CLR)](#stack)|Erstellt ein container-Objekt.|  
|[stack::top (STL/CLR)](#top)|Greift auf das letzte Element zu.|  
|[stack::to_array (STL/CLR)](#to_array)|Kopiert die kontrollierte Sequenz in ein neues Array.|  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|[stack::top_item (STL/CLR)](#top_item)|Greift auf das letzte Element zu.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[stack::operator= (STL/CLR)](#op_as)|Ersetzt die kontrollierte Sequenz.|  
|[operator!= (stack) (STL/CLR)](#op_neq)|Bestimmt, ob eine `stack` Objekt ist nicht gleich einem anderen `stack` Objekt.|  
|[operator< (stack) (STL/CLR)](#op_lt)|Bestimmt, ob eine `stack` Objekt ist kleiner als ein anderes `stack` Objekt.|  
|[operator<= (stack) (STL/CLR)](#op_lteq)|Bestimmt, ob eine `stack` Objekt ist kleiner als oder gleich einem anderen `stack` Objekt.|  
|[operator== (stack) (STL/CLR)](#op_eq)|Bestimmt, ob eine `stack` Objekt ist gleich einem anderen `stack` Objekt.|  
|[operator> (stack) (STL/CLR)](#op_gt)|Bestimmt, ob eine `stack` Objekt ist größer als ein anderer `stack` Objekt.|  
|[operator>= (stack) (STL/CLR)](#op_gteq)|Bestimmt, ob eine `stack` Objekt ist größer als oder gleich einem anderen `stack` Objekt.|  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Duplizieren Sie ein Objekt.|  
|IStack\<-Wert, der Container >|Behalten Sie die generischen Container-Adapter.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt weist speicherbelegungen und-Freigaben für die gesteuerte Sequenz durch eine zugrunde liegenden Containers, eines Typs *Container*, speichert *Wert* Elemente und wächst nach Bedarf. Das Objekt schränkt den Zugriff mithilfe von Push übertragen und die Anzeige nur des letzten Elements, implementieren eine Last in First Out-Warteschlange (auch bekannt als eine LIFO-Warteschlange oder Stack).  
 
## <a name="members"></a>Member

## <a name="assign"></a> Stack::Assign (STL/CLR)
Ersetzt alle Elemente.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
void assign(stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *right*  
 Der Containeradapter, einfügen.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion weist `right.get_container()` in den zugrunde liegenden Container. Damit können Sie den gesamten Inhalt des Stapels ändern.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_assign.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Mystack c2;   
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

## <a name="const_reference"></a> Stack::const_reference (STL/CLR)
Der Typ eines konstanten Verweises auf ein Element.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen konstanten Verweis auf ein Element.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_const_reference.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " c b a"   
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Mystack::const_reference cref = c1.top();   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
```  

## <a name="container_type"></a> Stack:: container_type (STL/CLR)
Der Typ des zugrunde liegenden Containers.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef Container value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist synonym mit dem Vorlagenparameter *Container*.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_container_type.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Mystack::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
a b c  
```  

## <a name="difference_type"></a> Stack::difference_type (STL/CLR)
Die Typen des Abstands zwischen den beiden Elementen mit Vorzeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine möglicherweise negative Elementanzahl.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_difference_type.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute negative difference   
    Mystack::difference_type diff = c1.size();   
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

## <a name="empty"></a> Stack:: Empty (STL/CLR)
Testet, ob keine Elemente vorhanden sind.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
bool empty();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt „true“ für eine leere gesteuerte Sequenz zurück. Dies ist äquivalent zum [Stack:: Size (STL/CLR)](../dotnet/stack-size-stl-clr.md)`() == 0`. Damit können Sie überprüfen, ob der Stapel leer ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_empty.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
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
  
## <a name="generic_container"></a> Stack::generic_container (STL/CLR)
Der Typ der generischen Schnittstelle für den Containeradapter.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef Microsoft::VisualC::StlClr::IStack<Value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt die generische Schnittstelle für diese Container Adapter-Vorlagenklasse.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_generic_container.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get interface to container   
    Mystack::generic_container^ gc1 = %c1;   
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
  
## <a name="generic_value"></a> Stack::generic_value (STL/CLR)
Der Typ eines Elements für die Verwendung mit der generischen Schnittstelle für den Container.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt ein Objekt des Typs `GValue` , beschreibt den gespeichertes Element-Wert für die Verwendung mit der generischen Schnittstelle für diese Vorlage Container-Klasse. (`GValue` ist entweder `value_type` oder `value_type^` Wenn `value_type` ist ein Ref-Typ.)  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_generic_value.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get interface to container   
    Mystack::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display in reverse using generic_value   
    for (; !gc1->empty(); gc1->pop())   
        {   
        Mystack::generic_value elem = gc1->top();   
  
        System::Console::Write(" {0}", elem);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
c b a  
```  
  
## <a name="get_container"></a> Stack:: get_container (STL/CLR)
Greift auf die zugrunde liegenden Containers.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
container_type^ get_container();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Handle für den zugrunde liegenden Containers zurück. Damit können Sie um die Einschränkungen, die vom Container Wrapper zu umgehen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_get_container.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Mystack::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="op_as"></a> standardbibliotheksbeispiel = (STL/CLR)
Ersetzt die kontrollierte Sequenz.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
stack <Value, Container>% operator=(stack <Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *right*  
 Der Containeradapter, zu kopieren.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Operator Kopien *rechten* klicken Sie dann auf das Objekt, gibt `*this`. Damit können Sie die kontrollierte Sequenz durch eine Kopie der kontrollierten Sequenz in ersetzen *rechten*.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_operator_as.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
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

## <a name="pop"></a> Stack:: POP (STL/CLR)
Entfernt das letzte Element.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
void pop();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion entfernt das letzte Element der kontrollierten Sequenz, die nicht leer sein darf. Damit können Sie den Stapel um ein Element an der Rückseite zu verkürzen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_pop.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
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
a b  
```  

## <a name="push"></a> Stack:: Push (STL/CLR)
Fügt ein neues Letztes Element hinzu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
void push(value_type val);  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion Fügt ein Element mit Wert `val` am Ende der kontrollierten Sequenz. Damit können Sie ein anderes Element an den Stapel angefügt werden soll.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_push.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
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

## <a name="reference"></a> Stack::Reference (STL/CLR)
Der Typ eines Verweises auf ein Element.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt einen Verweis auf ein Element.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_reference.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify top of stack and redisplay   
    Mystack::reference ref = c1.top();   
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
  
## <a name="size"></a> Stack:: Size (STL/CLR)
Ermittelt die Anzahl von Elementen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
size_type size();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Länge der gesteuerten Sequenz zurück. Damit können Sie die Anzahl der Elemente, die derzeit in der kontrollierten Sequenz bestimmt. Wenn Sie besonders interessierenden lediglich, ob die Reihenfolge größer, finden Sie unter hat [Stack:: Empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)`()`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_size.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
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

## <a name="size_type"></a> Stack:: size_type (STL/CLR)
Der Typ eines Abstands zwischen den beiden Elementen mit Vorzeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine nicht Negative Elementanzahl.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_size_type.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mystack::size_type diff = c1.size();   
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
  
## <a name="stack"></a> Stack:: Stack (STL/CLR)
Erstellt ein Containerobjekt für den Adapter.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### <a name="parameters"></a>Parameter  
 *right*  
 Zu kopierende Objekt.  
  
 *Umschlossen*  
 Umschlossene Container verwenden.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `stack();`  
  
 erstellt einen leeren umschlossenen Container an. Damit können Sie eine leere gesteuerte Sequenz angeben.  
  
 Der Konstruktor:  
  
 `stack(stack<Value, Container>% right);`  
  
 erstellt einen Wrapper-Container, die eine Kopie des `right.get_container()`. Damit können Sie eine gesteuerte Sequenz angeben, die eine Kopie der gesteuerte Sequenz durch das Stack-Objekt ist *rechten*.  
  
 Der Konstruktor:  
  
 `stack(stack<Value, Container>^ right);`  
  
 erstellt einen Wrapper-Container, die eine Kopie des `right->get_container()`. Damit können Sie eine gesteuerte Sequenz angeben, die eine Kopie der gesteuerte Sequenz durch das Stack-Objekt ist `*right`.  
  
 Der Konstruktor:  
  
 `explicit stack(container_type% wrapped);`  
  
 den vorhandenen Container verwendet *umschlossen* als umschlossene Container. Damit können Sie um einen Stapel aus einem vorhandenen Container zu erstellen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
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

## <a name="to_array"></a> Stack::to_array (STL/CLR)
Kopiert die kontrollierte Sequenz in ein neues Array.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt ein Array mit der kontrollierten Sequenz zurück. Damit können Sie eine Kopie der kontrollierten Sequenz in Arrayform abrufen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_to_array.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
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

## <a name="top"></a> Stack:: Top (STL/CLR)
Greift auf das letzte Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
reference top();  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen Verweis auf das letzte Element der kontrollierten Sequenz, die nicht leer sein darf. Damit können Sie das letzte Element zuzugreifen, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_top.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top() = {0}", c1.top());   
  
// alter last item and reinspect   
    c1.top() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
top() = c  
 a b x  
```  

## <a name="top_item"></a> Stack:: die top_item (STL/CLR)
Greift auf das letzte Element zu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
property value_type top_item;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Eigenschaft greift auf das letzte Element der kontrollierten Sequenz, die nicht leer sein darf. Sie verwenden ihn zum Lesen oder schreiben das letzte Element, wenn Sie wissen, dass es vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_top_item.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top_item = {0}", c1.top_item);   
  
// alter last item and reinspect   
    c1.top_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
top_item = c  
 a b x  
```  

## <a name="value_type"></a> Stack:: value_type (STL/CLR)
Der Typ eines Elements.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter *Wert*.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_value_type.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " a b c" using value_type   
    for (; !c1.empty(); c1.pop())   
        {   // store element in value_type object   
        Mystack::value_type val = c1.top();   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
c b a  
```  

## <a name="op_neq"></a> Operator! = (Stapel) (STL/CLR)
Der Stapel nicht gleich-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator!=(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, die Operatorfunktion `!(left == right)`. Damit können Sie testen, ob *linken* ist nicht identisch mit geordnet *rechten* bei beiden Stapeln verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_operator_ne.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
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

## <a name="op_lt"></a> Operator&lt; (Stapel) (STL/CLR)
Stapel ist kleiner als Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator<(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator-Funktion gibt "true" zurück, wenn, für die niedrigste Position `i` für die `!(right[i] < left[i])` es ist auch, die "true" `left[i] < right[i]`. Andernfalls wird `left->` [Stack:: Size (STL/CLR)](../dotnet/stack-size-stl-clr.md) `() <` `right->size()` damit können Sie testen, ob *linken* sortiert ist, bevor Sie *rechten* Bei beiden Stapeln verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_operator_lt.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
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

## <a name="op_lteq"></a> Operator&lt;= (Stapel) (STL/CLR)
Kleiner oder gleich Stack Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator<=(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, die Operatorfunktion `!(right < left)`. Damit können Sie testen, ob *linken* wird nicht nach dem sortiert *rechten* bei beiden Stapeln verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_operator_le.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
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

## <a name="op_eq"></a> Operator == (Stapel) (STL/CLR)
Stack-gleich-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator==(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Die Operatorfunktion gibt "true" nur dann, wenn die Sequenzen von gesteuert *linken* und *rechten* die gleiche Länge aufweisen und für jede Position `i`, `left[i] ==` `right[i]`. Damit können Sie testen, ob *linken* sortiert wird, ist identisch mit *rechten* bei beiden Stapeln verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_operator_eq.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
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
  
## <a name="op_gt"></a> Operator&gt; (Stapel) (STL/CLR)
Der Stapel ist größer als-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator>(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, die Operatorfunktion `right` `<` `left`. Damit können Sie testen, ob *linken* sortiert wird, ist nach *rechten* bei beiden Stapeln verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_operator_gt.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
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
  
## <a name="op_gteq"></a> Operator&gt;= (Stapel) (STL/CLR)
Stapel, die größer als oder gleich-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
template<typename Value,  
    typename Container>  
    bool operator>=(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 *left*  
 Linker zu vergleichender Container.  
  
 *right*  
 Rechter zu vergleichender Container.  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, die Operatorfunktion `!(left < right)`. Damit können Sie testen, ob *linken* ist nicht geordnet, bevor Sie *rechten* bei beiden Stapeln verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_stack_operator_ge.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
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