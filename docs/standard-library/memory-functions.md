---
title: '&lt;memory&gt;-Funktionen'
ms.date: 02/06/2019
f1_keywords:
- memory/std::addressof
- memory/std::align
- memory/std::allocate_shared
- memory/std::const_pointer_cast
- memory/std::declare_no_pointers
- memory/std::declare_reachable
- memory/std::default_delete
- memory/std::dynamic_pointer_cast
- memory/std::get_deleter
- memory/std::get_pointer_safety
- xmemory/std::get_temporary_buffer
- memory/std::make_shared
- memory/std::make_unique
- memory/std::owner_less
- xmemory/std::return_temporary_buffer
- memory/std::static_pointer_cast
- memory/std::swap
- memory/std::undeclare_no_pointers
- memory/std::undeclare_reachable
- memory/std::uninitialized_copy
- memory/std::uninitialized_copy_n
- memory/std::uninitialized_fill
- memory/std::uninitialized_fill_n
- memory/std::get_temporary_buffer
- memory/std::return_temporary_buffer
ms.assetid: 3e1898c2-44b7-4626-87ce-84962e4c6f1a
helpviewer_keywords:
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::swap [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
ms.openlocfilehash: 14818e93e79a0be9960ba67088f81d51d402b717
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448493"
---
# <a name="ltmemorygt-functions"></a>&lt;memory&gt;-Funktionen

## <a name="addressof"></a>AddressOf

Ruft die echte Adresse eines Objekts ab.

```cpp
template <class T>
    T* addressof(T& Val);
```

### <a name="parameters"></a>Parameter

*Ster*\
Das Objekt oder die Funktion, für das bzw. die die echte Adresse abgerufen wird.

### <a name="return-value"></a>Rückgabewert

Die tatsächliche Adresse des Objekts oder der Funktion, auf die von *Val*verwiesen wird, `operator&()` selbst wenn ein überladener vorhanden ist.

### <a name="remarks"></a>Hinweise

## <a name="align"></a>abzustimmen

Passt Speicher in der vorgegebenen Größe – ausgerichtet mithilfe der festgelegten Ausrichtungsspezifikation – in die erste mögliche Adresse des angegebenen Speichers ein.

```cpp
void* align(
    size_t Alignment, // input
    size_t Size,      // input
    void*& Ptr,        // input/output
    size_t& Space     // input/output
);
```

### <a name="parameters"></a>Parameter

*Richt*\
Die auszuprobierende Ausrichtungsgrenze.

*Größe*\
Die Größe in Bytes für den ausgerichteten Speicher.

*PTR*\
Die Startadresse des verfügbaren zusammenhängenden Speicherpools, der verwendet werden soll. Dieser Parameter ist auch ein Output-Parameter und wird so festgelegt, dass die neue Startadresse enthalten ist, wenn die Ausrichtung erfolgreich ist. Wenn `align()` nicht erfolgreich ist, wird dieser Parameter nicht geändert.

*BRaum*\
Der gesamte verfügbare Speicherplatz, den `align()` beim Erstellen des ausgerichteten Speichers verwendet. Dieser Parameter ist auch ein Ausgabeparameter und enthält den angepassten Speicherplatz, der im Speicherpuffer verblieben ist, nachdem der ausgerichtete Speicher und der zugeordnete Mehraufwand subtrahiert wurden.

Wenn `align()` nicht erfolgreich ist, wird dieser Parameter nicht geändert.

### <a name="return-value"></a>Rückgabewert

Ein NULL-Zeiger, wenn der angeforderte ausgerichtete Puffer nicht in den verfügbaren Platz passt. andernfalls der neue Wert von *ptr*.

### <a name="remarks"></a>Hinweise

Mit den geänderten *ptr* -und *Space* -Parametern `align()` können Sie wiederholt im gleichen Puffer aufzurufen, möglicherweise mit verschiedenen Werten für *Ausrichtung* und *Größe*. Im folgenden Codeausschnitt wird eine Verwendung von `align()` veranschaulicht:

```cpp
#include <type_traits> // std::alignment_of()
#include <memory>
//...
char buffer[256]; // for simplicity
size_t alignment = std::alignment_of<int>::value;
void * ptr = buffer;
std::size_t space = sizeof(buffer); // Be sure this results in the true size of your buffer

while (std::align(alignment, sizeof(MyObj), ptr, space)) {
    // You now have storage the size of MyObj, starting at ptr, aligned on
    // int boundary. Use it here if you like, or save off the starting address
    // contained in ptr for later use.
    // ...
    // Last, move starting pointer and decrease available space before
    // the while loop restarts.
    ptr = reinterpret_cast<char*>(ptr) + sizeof(MyObj);
    space -= sizeof(MyObj);
}
// At this point, align() has returned a null pointer, signaling it is not
// possible to allow more aligned storage in this buffer.
```

## <a name="allocate_shared"></a>allocate_shared

Erstellt einen `shared_ptr` auf Objekte, die einem angegebenen Typ mit einer angegebenen Zuweisung zugeordnet und dafür erstellt werden. Gibt `shared_ptr` zurück.

```cpp
template <class Type, class Allocator, class... Types>
    shared_ptr<Type> allocate_shared(Allocator Alloc, Types&&... Args);
```

### <a name="parameters"></a>Parameter

*Zuordnungseinheits*\
Die Zuweisung wird zur Erstellung von Objekten verwendet.

*Args*\
Keine oder mehrere Argumente, die zu Objekten werden.

### <a name="remarks"></a>Hinweise

Die-Funktion erstellt das `shared_ptr<Type>`Objekt, ein Zeiger `Type(Args...)` auf, *wie von der*Zuweisung zugeordnet und erstellt.

## <a name="atomic_compare_exchange_strong"></a>atomic_compare_exchange_strong

```cpp
template<class T>
    bool atomic_compare_exchange_strong(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_weak"></a>atomic_compare_exchange_weak

```cpp
template<class T>
    bool atomic_compare_exchange_weak(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_strong_explicit"></a>atomic_compare_exchange_strong_explicit

```cpp
template<class T>
    bool atomic_compare_exchange_strong_explicit(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w, memory_order success, memory_order failure);
```

## <a name="atomic_compare_exchange_weak_explicit"></a>atomic_compare_exchange_weak_explicit

```cpp
template<class T>
    bool atomic_compare_exchange_weak_explicit(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w, memory_order success, memory_order failure);
```

## <a name="atomic_exchange"></a>atomic_exchange

```cpp
template<class T>
    shared_ptr<T> atomic_exchange(shared_ptr<T>* p, shared_ptr<T> r);
```

## <a name="atomic_exchange_explicit"></a>atomic_exchange_explicit

```cpp
template<class T>
    shared_ptr<T> atomic_exchange_explicit(shared_ptr<T>* p, shared_ptr<T> r, memory_order mo);
```

## <a name="atomic_is_lock_free"></a>atomic_is_lock_free

```cpp
template<class T>
    bool atomic_is_lock_free(const shared_ptr<T>* p);
```

## <a name="atomic_load"></a>atomic_load

```cpp
template<class T>
    shared_ptr<T> atomic_load(const shared_ptr<T>* p);
```

## <a name="atomic_load_explicit"></a>atomic_load_explicit

```cpp
template<class T>
    shared_ptr<T> atomic_load_explicit(const shared_ptr<T>* p, memory_order mo);
```

## <a name="atomic_store"></a>atomic_store

```cpp
template<class T>
    void atomic_store(shared_ptr<T>* p, shared_ptr<T> r);
```

## <a name="atomic_store_explicit"></a>atomic_store_explicit

```cpp
template<class T>
    void atomic_store_explicit(shared_ptr<T>* p, shared_ptr<T> r, memory_order mo);
```

## <a name="const_pointer_cast"></a>const_pointer_cast

Konstantenumwandlung in shared_ptr (gemeinsamer Zeiger).

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> const_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der Typ, der vom zurückgegebenen gemeinsamen Zeiger (shared pointer) gesteuert wird.

*Außer*\
Der Typ, der vom Argument für den gemeinsamen Zeiger gesteuert wird.

*Außer*\
Das Argument für den gemeinsamen Zeiger.

### <a name="remarks"></a>Hinweise

Die Vorlagen Funktion gibt ein leeres shared_ptr-Objekt `const_cast<Ty*>(sp.get())` zurück, wenn einen NULL-Zeiger zurückgibt; andernfalls gibt Sie ein [shared_ptr Class](../standard-library/shared-ptr-class.md)\<Ty-> Objekt zurück, `sp`das die Ressource besitzt, die im Besitz von ist. Der Ausdruck `const_cast<Ty*>(sp.get())` muss gültig sein.

### <a name="example"></a>Beispiel

```cpp
// std__memory__const_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int);
    std::shared_ptr<const int> sp1 =
        std::const_pointer_cast<const int>(sp0);

*sp0 = 3;
    std::cout << "sp1 == " << *sp1 << std::endl;

    return (0);
}
```

```Output
sp1 == 3
```

## <a name="declare_no_pointers"></a>declare_no_pointers

Einem Garbage Collector wird mitgeteilt, dass die Zeichen im Speicherblock, der von einem Basisadressenzeiger und -blockgröße definiert wurde, keine nachweisbaren Zeiger enthalten.

```cpp
void declare_no_pointers(char* ptr, size_t _Size);
```

### <a name="parameters"></a>Parameter

*PTR*\
Adresse des ersten Zeichens, das keinen nachweisbaren Zeiger mehr enthält.

*_Size*\
Blockgröße, die bei *ptr* beginnt und keine nachvollziehbaren Zeiger enthält.

### <a name="remarks"></a>Hinweise

Die-Funktion informiert alle Garbage Collector, dass der Adress `[ ptr, ptr + _Size)` Bereich keine nachvollziehbaren Zeiger mehr enthält. (Alle Zeiger auf zugeordneten Speicher dürfen nicht dereferenziert werden, es sei denn, Sie wurden erreichbar gemacht.)

## <a name="declare_reachable"></a>declare_reachable

Der Garbage Collection wird mitgeteilt, dass die angegebene Adresse von zugewiesenem Speicher erreichbar ist.

```cpp
void declare_reachable(void* ptr);
```

### <a name="parameters"></a>Parameter

*PTR*\
Ein Zeiger auf einen erreichbaren zugewiesenen gültigen Speicherbereich.

### <a name="remarks"></a>Hinweise

Wenn *ptr* nicht NULL ist, informiert die Funktion jeden Garbage Collector, dass *ptr* im Anschluss erreichbar ist (verweist auf gültigen zugeordneten Speicher).

## <a name="default_delete"></a>default_delete

Löscht mit **Operator new**zugeordnete-Objekte. Kann mit `unique_ptr` verwendet werden.

```cpp
struct default_delete {
   constexpr default_delete() noexcept = default;
   template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>
        default_delete(const default_delete<Other>&) noexcept;
   void operator()(T* Ptr) const noexcept;
};
```

### <a name="parameters"></a>Parameter

*PTR*\
Zeiger auf das zu löschende Objekt.

*Außer*\
Die anderen Typen von Elementen im Array, die gelöscht werden sollen.

### <a name="remarks"></a>Hinweise

Die Vorlagen Klasse beschreibt einen `deleter` , mit dem skalare Objekte gelöscht werden, die mit dem **Operator new**zugeordnet sind `unique_ptr`und für die Verwendung mit der Vorlagen Klasse geeignet Außerdem ist die explizite Spezialisierung `default_delete<Type[]>` vorhanden.

## <a name="destroy_at"></a>destroy_at

```cpp
template <class T>
    void destroy_at(T* location);
```

Wie in `location->~T()`.

## <a name="destroy"></a>zerstören

```cpp
template <class ForwardIterator>
    void destroy(ForwardIterator first, ForwardIterator last);
```

Wie in `for (; first!=last; ++first) destroy_at(addressof(*first)); `.

## <a name="destroy_n"></a>destroy_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator destroy_n(ForwardIterator first, Size n);
```

Wie in `for (; n > 0; (void)++first, --n) destroy_at(addressof(*first)); return first;`.

## <a name="dynamic_pointer_cast"></a>dynamic_pointer_cast

Dynamische Umwandlung in shared_ptr (gemeinsamer Zeiger).

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> dynamic_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der Typ, der vom zurückgegebenen gemeinsamen Zeiger (shared pointer) gesteuert wird.

*Außer*\
Der Typ, der vom Argument für den gemeinsamen Zeiger gesteuert wird.

*El*\
Das Argument für den gemeinsamen Zeiger.

### <a name="remarks"></a>Hinweise

Die Vorlagen Funktion gibt ein leeres shared_ptr-Objekt `dynamic_cast<Ty*>(sp.get())` zurück, wenn einen NULL-Zeiger zurückgibt; andernfalls gibt Sie ein [shared_ptr Class](../standard-library/shared-ptr-class.md)\<Ty-> Objekt zurück, das die Ressource besitzt, die im Besitz von *SP*ist. Der Ausdruck `dynamic_cast<Ty*>(sp.get())` muss gültig sein.

### <a name="example"></a>Beispiel

```cpp
// std__memory__dynamic_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    virtual ~base() {}
    int val;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::dynamic_pointer_cast<derived>(sp0);

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="get_deleter"></a>get_deleter

Einen Deleter aus shared_ptr abrufen.

```cpp
template <class D, class Ty>
    D* get_deleter(const shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Parameter

*D*\
Der Deleter-Typ.

*Genossenschaft*\
Der vom freigegebenen Zeiger gesteuerte Typ.

*El*\
Der freigegebene Zeiger.

### <a name="remarks"></a>Hinweise

Die Vorlagen Funktion gibt einen Zeiger auf den Deleter des Typs *D* zurück, der zum [shared_ptr-Klassen](../standard-library/shared-ptr-class.md) Objekt *SP*gehört. Wenn *SP* keinen Deleter hat oder der Deleter nicht vom Typ *D* ist, gibt die Funktion 0 zurück.

### <a name="example"></a>Beispiel

```cpp
// std__memory__get_deleter.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
};

struct deleter
{
    void operator()(base *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<base> sp0(new base);

    sp0->val = 3;
    std::cout << "get_deleter(sp0) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp0) != 0) << std::endl;

    std::shared_ptr<base> sp1(new base, deleter());

    sp0->val = 3;
    std::cout << "get_deleter(sp1) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp1) != 0) << std::endl;

    return (0);
}
```

```Output
get_deleter(sp0) != 0 == false
get_deleter(sp1) != 0 == true
```

## <a name="get_pointer_safety"></a>get_pointer_safety

Gibt den Typ der Zeigersicherheit zurück, der von einem Garbage Collector angenommen wird.

```cpp
pointer_safety get_pointer_safety();
```

### <a name="remarks"></a>Hinweise

Die-Funktion gibt den Typ der Zeiger Sicherheit zurück, der von allen automatischen Garbage Collector angenommen wird.

## <a name="get_temporary_buffer"></a>get_temporary_buffer

Weist temporären Speicher für eine Elementsequenz zu, die eine bestimmte Anzahl von Elementen nicht überschreitet.

```cpp
template <class Type>
    pair<Type *, ptrdiff_t> get_temporary_buffer(ptrdiff_t count);
```

### <a name="parameters"></a>Parameter

*Countdown*\
Die maximale Anzahl der angeforderten Elemente, denen Speicher zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein `pair`, dessen erste Komponente ein Zeiger auf den zugewiesenen Speicher ist, und dessen zweite Komponente die Größe des Puffers angibt; sie gibt die maximale Zahl an Elementen an, die gespeichert werden kann.

### <a name="remarks"></a>Hinweise

Die Funktion fordert Speicher an; möglicherweise wird diese Anforderung aber zurückgewiesen. Wenn kein Puffer zugewiesen ist, gibt die Funktion „pair“ zurück; dabei ist die zweite Komponente entspricht null und die erste Komponente dem NULL-Zeiger.

Diese Funktion sollte nur für temporären Speicher verwendet werden.

### <a name="example"></a>Beispiel

```cpp
// memory_get_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
   // Create an array of ints
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300, 1000, 2000 };
   int count = sizeof ( intArray ) / sizeof ( int );
   cout << "The number of integers in the array is: "
      << count << "." << endl;

   pair<int *, ptrdiff_t> resultPair;
   resultPair = get_temporary_buffer<int>( count );

   cout << "The number of elements that the allocated memory\n"
        << "could store is given by: resultPair.second = "
        << resultPair.second << "." << endl;
}
```

```Output
The number of integers in the array is: 9.
The number of elements that the allocated memory
could store is given by: resultPair.second = 9.
```

## <a name="make_shared"></a>make_shared

Erstellt `shared_ptr`, das auf die zugeordneten Objekte, die mithilfe der Standardbelegung von keinen oder mehreren Argumenten erstellt werden, oder gibt es zurück. Weist sowohl ein Objekt des angegebenen Typs als auch `shared_ptr` zu und erstellt sie, um die Freigabe des Objekts zu verwalten, und gibt `shared_ptr` zurück.

```cpp
template <class Type, class... Types>
    shared_ptr<Type> make_shared(Types&&... _Args);
```

### <a name="parameters"></a>Parameter

*_Args*\
Null oder mehr Konstruktorargumente. Die Funktion leitet auf Grundlage der bereitgestellten Argumente die erforderliche die Konstruktorüberladung ab.

### <a name="remarks"></a>Hinweise

Verwenden Sie `make_shared` als einfache und effizientere Möglichkeit, um ein Objekt und `shared_ptr` zu erstellen, um den gemeinsamen, gleichzeitigen Zugriff auf das Objekt zu verwalten. Semantisch gesehen sind diese beiden Anweisungen äquivalent:

```cpp
auto sp = std::shared_ptr<Example>(new Example(argument));
auto msp = std::make_shared<Example>(argument);
```

Die erste Anweisung ergibt jedoch zwei Zuordnungen, und wenn die Zuordnung von `shared_ptr` fehlschlägt, nachdem die Zuordnung des `Example`-Objekts erfolgreich war, geht das unbenannte `Example`-Objekt verloren. Die Anweisung, die `make_shared` verwendet, ist einfacher, da nur ein Funktionsaufruf beteiligt ist. Sie ist effizienter, da die Bibliothek eine einzige Zuordnung für das Objekt und den intelligenten Zeiger vornehmen kann. Dies ist schneller und führt zu einer geringeren Speicherfragmentierung; zudem kann es nicht bei nur einer Zuordnung zu einer Ausnahme kommen. Die Leistung wird durch einen besseren Speicherort für den Code verbessert, der auf das Objekt verweist und den Verweiszähler im intelligenten Zeiger aktualisiert.

Ziehen Sie die Verwendung von [make_unique](../standard-library/memory-functions.md#make_unique) in Betracht, wenn Sie keinen gemeinsamen Zugriff auf das Objekt benötigen. Verwenden Sie [allocate_shared](../standard-library/memory-functions.md#allocate_shared), wenn Sie eine benutzerdefinierte Zuweisung für das Objekt angeben müssen. Sie können `make_shared` nicht verwenden, wenn das Objekt einen benutzerdefinierten Deleter benötigt, da es keine Möglichkeit gibt, den Deleter als Argument zu übergeben.

Im folgenden Beispiel wird die Erstellung freigegebener Zeiger auf einen Typ mithilfe bestimmter Konstruktorüberladungen veranschaulicht.

### <a name="example"></a>Beispiel

```cpp
// stl_make_shared.cpp
// Compile by using: cl /W4 /EHsc stl_make_shared.cpp
#include <iostream>
#include <string>
#include <memory>
#include <vector>

class Song {
public:
   std::wstring title_;
   std::wstring artist_;

   Song(std::wstring title, std::wstring artist) : title_(title), artist_(artist) {}
   Song(std::wstring title) : title_(title), artist_(L"Unknown") {}
};

void CreateSharedPointers() {
   // Okay, but less efficient to have separate allocations for
   // Song object and shared_ptr control block.
   auto song = new Song(L"Ode to Joy", L"Beethoven");
   std::shared_ptr<Song> sp0(song);

   // Use make_shared function when possible. Memory for control block
   // and Song object are allocated in the same call:
   auto sp1 = std::make_shared<Song>(L"Yesterday", L"The Beatles");
   auto sp2 = std::make_shared<Song>(L"Blackbird", L"The Beatles");

   // make_shared infers which constructor to use based on the arguments.
   auto sp3 = std::make_shared<Song>(L"Greensleeves");

   // The playlist vector makes copies of the shared_ptr pointers.
   std::vector<std::shared_ptr<Song>> playlist;
   playlist.push_back(sp0);
   playlist.push_back(sp1);
   playlist.push_back(sp2);
   playlist.push_back(sp3);
   playlist.push_back(sp1);
   playlist.push_back(sp2);
   for (auto&& sp : playlist) {
      std::wcout << L"Playing " << sp->title_ <<
         L" by " << sp->artist_ << L", use count: " <<
         sp.use_count() << std::endl;
   }
}

int main() {
   CreateSharedPointers();
}
```

Das Beispiel generiert die folgende Ausgabe:

```Output
Playing Ode to Joy by Beethoven, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
Playing Greensleeves by Unknown, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
```

## <a name="make_unique"></a>make_unique

Erstellt ein [unique_ptr](../standard-library/unique-ptr-class.md)-Element und gibt es an ein Objekt des angegebenen Typs zurück, das mithilfe der angegebenen Argumente erstellt wird.

```cpp
// make_unique<T>
template <class T, class... Types>
    unique_ptr<T> make_unique(Types&&... Args)
    {
        return (unique_ptr<T>(new T(forward<Types>(Args)...)));
    }

// make_unique<T[]>
template <class T>
    make_unique(size_t Size)
    {
        return (unique_ptr<T>(new Elem[Size]()));
    }

// make_unique<T[N]> disallowed
template <class T, class... Types>
    typename enable_if<extent<T>::value != 0, void>::type make_unique(Types&&...) = delete;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der Typ des Objekts, auf das `unique_ptr` zeigt.

*Typen*\
Die von *args*angegebenen Typen der Konstruktorargumente.

*Args*\
Die Argumente, die an den Konstruktor des Objekts vom Typ *T*übergeben werden.

*Elem*\
Ein Array von Elementen des Typs *T*.

*Größe*\
Die Anzahl von Elementen, denen im neue Array ein Bereich zugeordnet werden soll.

### <a name="remarks"></a>Hinweise

Die erste Überladung wird für einzelne Objekte verwendet, die zweite Überladung wird für Arrays aufgerufen, und die dritte Überladung verhindert die Angabe einer Array Größe im Typargument (make_unique\<T [N] >). diese Konstruktion wird vom aktuellen-Objekt nicht unterstützt. Norm. Wenn Sie `make_unique` verwenden, um `unique_ptr` in ein Array zu erstellen, müssen die Arrayelemente separat initialisiert werden. Bei Berücksichtigung dieser Überladung ist die Verwendung von [std::vector](../standard-library/vector-class.md) eventuell besser.

Da `make_unique` sorgfältig für die Ausnahmesicherheit implementiert wird, wird empfohlen, `make_unique` zu verwenden, anstatt `unique_ptr` -Konstruktoren direkt aufzurufen.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `make_unique`. Weitere Beispiele finden Sie unter [Vorgehensweise: Erstellen und Verwenden von unique_ptr](../cpp/how-to-create-and-use-unique-ptr-instances.md)-Instanzen.

[!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]

Wenn der Fehler "C2280" in Verbindung mit `unique_ptr` angezeigt wird, ist der Grund dafür fast sicherlich, der Versuch, den Kopierkonstruktor aufzurufen, der eine gelöschte Funktion ist.

## <a name="owner_less"></a>owner_less

Ermöglicht Mischvergleiche, die auf Besitz basieren, freigegebener und schwacher Zeiger. Gibt " **true** " zurück, wenn der linke Parameter von der Element Funktion `owner_before`vor dem rechten Parameter geordnet ist.

```cpp
template <class Type>
    struct owner_less; // not defined

template <class Type>
struct owner_less<shared_ptr<Type>> {
    bool operator()(
    const shared_ptr<Type>& left,
    const shared_ptr<Type>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Type>& right);
};

template <class Type>
struct owner_less<weak_ptr<Type>>
    bool operator()(
    const weak_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Ty>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);
};
```

### <a name="parameters"></a>Parameter

*_left*\
Ein freigegebener oder schwacher Zeiger.

*Richting*\
Ein freigegebener oder schwacher Zeiger.

### <a name="remarks"></a>Hinweise

Die Vorlagenklassen definieren, dass alle ihre Memberoperatoren `left.owner_before(right)` zurückgeben.

## <a name="return_temporary_buffer"></a>return_temporary_buffer

Gibt den temporären Speicher frei, der mithilfe der `get_temporary_buffer`-Vorlagenfunktion zugeordnet wurde.

```cpp
template <class Type>
    void return_temporary_buffer(Type* _Pbuf);
```

### <a name="parameters"></a>Parameter

*_Pbuf*\
Ein Zeiger auf dem freizugebenden Speicher.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nur für temporären Speicher verwendet werden.

### <a name="example"></a>Beispiel

```cpp
// memory_ret_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
   // Create an array of ints
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300 };
   int count = sizeof ( intArray ) / sizeof ( int );
   cout << "The number of integers in the array is: "
         << count << "." << endl;

   pair<int *, ptrdiff_t> resultPair;
   resultPair = get_temporary_buffer<int>( count );

   cout << "The number of elements that the allocated memory\n"
         << " could store is given by: resultPair.second = "
         << resultPair.second << "." << endl;

   int* tempBuffer = resultPair.first;

   // Deallocates memory allocated with get_temporary_buffer
   return_temporary_buffer ( tempBuffer );
}
```

```Output
The number of integers in the array is: 7.
The number of elements that the allocated memory
could store is given by: resultPair.second = 7.
```

## <a name="static_pointer_cast"></a>static_pointer_cast

Statische Umwandlung in shared_ptr (gemeinsamer Zeiger).

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> static_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der Typ, der vom zurückgegebenen gemeinsamen Zeiger (shared pointer) gesteuert wird.

*Außer*\
Der Typ, der vom Argument für den gemeinsamen Zeiger gesteuert wird.

*Außer*\
Das Argument für den gemeinsamen Zeiger.

### <a name="remarks"></a>Hinweise

Die Vorlagen Funktion gibt ein leeres shared_ptr-Objekt `sp` zurück, wenn `shared_ptr` ein leeres-Objekt ist; andernfalls gibt Sie ein [shared_ptr Class](../standard-library/shared-ptr-class.md)\<Ty-> Objekt zurück, das `sp`die Ressource besitzt, die im Besitz von ist. Der Ausdruck `static_cast<Ty*>(sp.get())` muss gültig sein.

### <a name="example"></a>Beispiel

```cpp
// std__memory__static_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::static_pointer_cast<derived>(sp0);

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="swap"></a>Wechsel

Tauscht zwei shared_ptr- oder weak_ptr-Objekte.

```cpp
template <class Ty, class Other>
    void swap(shared_ptr<Ty>& left, shared_ptr<Other>& right);

template <class Ty, class Other>
    void swap(weak_ptr<Ty>& left, weak_ptr<Other>& right);
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der vom linken gemeinsamen/schwachen Zeiger gesteuerte Typ.

*Außer*\
Der vom rechten gemeinsamen/schwachen Zeiger gesteuerte Typ.

*linken*\
Der linke gemeinsame/schwache Zeiger.

*Richting*\
Der rechte gemeinsame/schwache Zeiger.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktionen rufen `left.swap(right)` auf.

### <a name="example"></a>Beispiel

```cpp
// std__memory__swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="undeclare_no_pointers"></a>undeclare_no_pointers

Einem Garbage Collector wird mitgeteilt, dass die Zeichen im Speicherblock, der von einem Basisadressenzeiger und -blockgröße definiert wurde, jetzt möglicherweise nachweisbare Zeiger enthalten.

```cpp
void undeclare_no_pointers(char* ptr, size_t _Size);
```

### <a name="remarks"></a>Hinweise

Die-Funktion informiert alle Garbage Collector, dass der Adress `[ptr, ptr + _Size)` Bereich nun möglicherweise nachvollziehbare Zeiger enthält.

## <a name="undeclare_reachable"></a>undeclare_reachable

Widerruft eine Deklaration der Erreichbarkeit für einen angegebenen Speicher Speicherort.

```cpp
template <class Type>
    Type *undeclare_reachable(Type* ptr);
```

### <a name="parameters"></a>Parameter

*PTR*\
Ein Zeiger auf die Speicheradresse, die als nicht erreichbar deklariert werden soll.

### <a name="remarks"></a>Hinweise

Wenn *ptr* nicht **nullptr**ist, informiert die Funktion alle Garbage Collector, dass *ptr* nicht mehr erreichbar ist. Es gibt einen sicheren abgeleiteten Zeiger zurück, der mit *ptr*übereinstimmt.

## <a name="uninitialized_copy"></a>uninitialized_copy

Es werden Objekte aus einem angegebenen Quellbereich in einen nicht initialisierten Zielbereich kopiert.

```cpp
template <class InputIterator, class ForwardIterator>
    ForwardIterator uninitialized_copy(InputIterator first, InputIterator last, ForwardIterator dest);
```

### <a name="parameters"></a>Parameter

*erstes*\
Ein Eingabeiterator, der das erste Element im Quellbereich adressiert.

*letzten*\
Ein Eingabeiterator, der das letzte Element im Quellbereich adressiert.

*dest*\
Ein Forward-Iterator, der das erste Element im Zielbereich adressiert.

### <a name="return-value"></a>Rückgabewert

Ein forward-Iterator, der die erste Position über dem Zielbereich hinaus adressiert, es sei denn, der Quellbereich war leer.

### <a name="remarks"></a>Hinweise

Dieser Algorithmus ermöglicht die Entkopplung der Speicherbelegung von der Objekterstellung.

Die Vorlagenfunktion führt Folgendes aus:

```cpp
while (first != last) {
    new (static_cast<void*>(&* dest++))
        typename iterator_traits<InputIterator>::value_type(*first++);
}
return dest;
```

es sei denn, der Code löst eine Ausnahme aus. In diesem Fall sind alle erstellten Objekte zerstört und die Ausnahme wird erneut ausgelöst.

### <a name="example"></a>Beispiel

```cpp
// memory_uninit_copy.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer
{
public:
    Integer(int x) : val(x) {}
    int get() { return val; }
private:
    int val;
};

int main()
{
    int Array[] = { 10, 20, 30, 40 };
    const int N = sizeof(Array) / sizeof(int);

    int i;
    cout << "The initialized Array contains " << N << " elements: ";
    for (i = 0; i < N; i++)
    {
        cout << " " << Array[i];
    }
    cout << endl;

    Integer* ArrayPtr = (Integer*)malloc(N * sizeof(int));
    Integer* LArrayPtr = uninitialized_copy(
        Array, Array + N, ArrayPtr);  // C4996

    cout << "Address of position after the last element in the array is: "
        << &Array[0] + N << endl;
    cout << "The iterator returned by uninitialized_copy addresses: "
        << (void*)LArrayPtr << endl;
    cout << "The address just beyond the last copied element is: "
        << (void*)(ArrayPtr + N) << endl;

    if ((&Array[0] + N) == (void*)LArrayPtr)
        cout << "The return value is an iterator "
        << "pointing just beyond the original array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the original array." << endl;

    if ((void*)LArrayPtr == (void*)(ArrayPtr + N))
        cout << "The return value is an iterator "
        << "pointing just beyond the copied array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the copied array." << endl;

    free(ArrayPtr);

    cout << "Note that the exact addresses returned will vary\n"
        << "with the memory allocation in individual computers."
        << endl;
}
```

## <a name="uninitialized_copy_n"></a>uninitialized_copy_n

Eine Kopie einer angegebenen Anzahl von Elementen aus einem Eingabeiterator wird erstellt. Die Kopien werden in einen Forward-Iterator abgelegt.

```cpp
template <class InputIterator, class Size, class ForwardIterator>
ForwardIterator uninitialized_copy_n(
    InputIterator first,
    Size count,
    ForwardIterator dest);
```

### <a name="parameters"></a>Parameter

*erstes*\
Ein Eingabeiterator, der auf das zu kopierende Objekt verweist.

*Countdown*\
Ein Ganzzahltyp mit oder ohne Vorzeichen, der die Anzahl von Kopiervorgängen für das Objekt angibt.

*dest*\
Ein Forward-Iterator, der auf den Speicherort der neuen Kopien verweist.

### <a name="return-value"></a>Rückgabewert

Ein Forward-Iterator, der die erste Position nach dem Ziel adressiert. Wenn der Quellbereich leer war, adressiert der Iterator *zuerst*.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion führt effektiv Folgendes aus:

```cpp
    for (; 0 < count; --count)
        new (static_cast<void*>(&* dest++))
            typename iterator_traits<InputIterator>::value_type(*first++);
    return dest;
```

es sei denn, der Code löst eine Ausnahme aus. In diesem Fall sind alle erstellten Objekte zerstört und die Ausnahme wird erneut ausgelöst.

## <a name="uninitialized_default_construct"></a>uninitialized_default_construct

```cpp
template <class ForwardIterator>
    void uninitialized_default_construct(ForwardIterator first, ForwardIterator last); 
```

### <a name="remarks"></a>Hinweise

Identisch mit:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type;
```

## <a name="uninitialized_default_construct_n"></a>uninitialized_default_construct_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator uninitialized_default_construct_n(ForwardIterator first, Size n)
```

### <a name="remarks"></a>Hinweise

Identisch mit:

```cpp
for (; n>0; (void)++first, --n)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type; return first;
```

## <a name="uninitialized_fill"></a>uninitialized_fill

Objekte eines angegebenen Werts werden in einen nicht initialisierten Zielbereich kopiert.

```cpp
template <class ForwardIterator, class Type>
    void uninitialized_fill(ForwardIterator first, ForwardIterator last, const Type& val);
```

### <a name="parameters"></a>Parameter

*erstes*\
Ein Forward-Iterator, der die Position des ersten Elements im zu initiierenden Zielbereich adressiert.

*letzten*\
Ein Forward-Iterator, der die Position des letzten Elements im zu initiierenden Zielbereich adressiert.

*ster*\
Der Wert, der zum Initialisieren des Zielbereichs verwendet wird.

### <a name="remarks"></a>Hinweise

Dieser Algorithmus ermöglicht die Entkopplung der Speicherbelegung von der Objekterstellung.

Die Vorlagenfunktion führt Folgendes aus:

```cpp
while (first != last)
    new (static_cast<void*>(&* first ++))
        typename iterator_traits<ForwardIterator>::value_type (val);
```

es sei denn, der Code löst eine Ausnahme aus. In diesem Fall sind alle erstellten Objekte zerstört und die Ausnahme wird erneut ausgelöst.

### <a name="example"></a>Beispiel

```cpp
// memory_uninit_fill.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

class Integer {         // No default constructor
   public:
      Integer( int x ) : val( x ) {}
      int get( ) { return val; }
   private:
      int val;
};

int main( )
{
   const int N = 10;
   Integer val ( 25 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill( Array, Array + N, val );
   int i;
   cout << "The initialized Array contains: ";
      for ( i = 0 ; i < N; i++ )
      {
         cout << Array [ i ].get( ) << " ";
      }
   cout << endl;
}
```

```Output
The initialized Array contains: 25 25 25 25 25 25 25 25 25 25
```

## <a name="uninitialized_fill_n"></a>uninitialized_fill_n

Objekte einer angegebenen Anzahl von Elementen werden in einen nicht initialisierten Zielbereich kopiert.

```cpp
template <class FwdIt, class Size, class Type>
    void uninitialized_fill_n(ForwardIterator first, Size count, const Type& val);
```

### <a name="parameters"></a>Parameter

*erstes*\
Ein Forward-Iterator, der die Position des ersten Elements im zu initiierenden Zielbereich adressiert.

*Countdown*\
Die Anzahl von zu initialisierenden Elementen.

*ster*\
Der Wert, der zum Initialisieren des Zielbereichs verwendet wird.

### <a name="remarks"></a>Hinweise

Dieser Algorithmus ermöglicht die Entkopplung der Speicherbelegung von der Objekterstellung.

Die Vorlagenfunktion führt Folgendes aus:

```cpp
while (0 < count--)
    new (static_cast<void*>(&* first++))
        typename iterator_traits<ForwardIterator>::value_type(val);
```

es sei denn, der Code löst eine Ausnahme aus. In diesem Fall sind alle erstellten Objekte zerstört und die Ausnahme wird erneut ausgelöst.

### <a name="example"></a>Beispiel

```cpp
// memory_uninit_fill_n.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer {   // No default constructor
public:
   Integer( int x ) : val( x ) {}
   int get( ) { return val; }
private:
   int val;
};

int main() {
   const int N = 10;
   Integer val ( 60 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill_n( Array, N, val );  // C4996
   int i;
   cout << "The uninitialized Array contains: ";
   for ( i = 0 ; i < N; i++ )
      cout << Array [ i ].get( ) <<  " ";
}
```

## <a name="uninitialized_move"></a>uninitialized_move

```cpp
template <class InputIterator, class ForwardIterator>
    ForwardIterator uninitialized_move(InputIterator first, InputIterator last, ForwardIterator result); 
```

### <a name="remarks"></a>Hinweise

Identisch mit:

```cpp
for (; first != last; (void)++result, ++first)
    ::new (static_cast<void*>(addressof(*result)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first)); 
        return result;
```

Wenn eine Ausnahme ausgelöst wird, bleiben einige Objekte im Bereich möglicherweise in einem gültigen, aber nicht angegebenen Zustand.

## <a name="uninitialized_move_n"></a>uninitialized_move_n

```cpp
template <class InputIterator, class Size, class ForwardIterator>
    pair<InputIterator, ForwardIterator> uninitialized_move_n(InputIterator first, Size n, ForwardIterator result);
```

### <a name="remarks"></a>Hinweise

Identisch mit:

```cpp
for (; n > 0; ++result, (void) ++first, --n)
    ::new (static_cast<void*>(addressof(*result)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first)); return {first,result};
```

Wenn eine Ausnahme ausgelöst wird, bleiben einige Objekte im Bereich möglicherweise in einem gültigen, aber nicht angegebenen Zustand.

## <a name="uninitialized_value_construct"></a>uninitialized_value_construct

```cpp
template <class ForwardIterator>
    void uninitialized_value_construct(ForwardIterator first, ForwardIterator last);
```

### <a name="remarks"></a>Hinweise

Identisch mit:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type();
```

## <a name="uninitialized_value_construct_n"></a>uninitialized_value_construct_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator uninitialized_value_construct_n(ForwardIterator first, Size n);
```

Identisch mit:
```cpp
for (; n>0; (void)++first, --n)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type(); return first;
```

## <a name="uses_allocator_v"></a>uses_allocator_v

```cpp
template <class T, class Alloc>
    inline constexpr bool uses_allocator_v = uses_allocator<T, Alloc>::value;
```

## <a name="see-also"></a>Siehe auch

[\<memory>](../standard-library/memory.md)
