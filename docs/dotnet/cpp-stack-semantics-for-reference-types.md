---
title: C++-Stack-Semantik für Referenztypen
ms.date: 11/04/2016
helpviewer_keywords:
- reference types, C++ stack semantics for
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
ms.openlocfilehash: 69771de120dc413496a3b7b0613e51a13d208e22
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772604"
---
# <a name="c-stack-semantics-for-reference-types"></a>C++-Stack-Semantik für Referenztypen

Vor Visual C++ 2005 eine Instanz eines Referenztyps kann nur erstellt werden mithilfe der `new` -Operator, der Erstellung des Objekts auf dem Garbage gesammelten Heap. Allerdings können Sie jetzt erstellen eine Instanz eines Referenztyps mit derselben Syntax, die Sie verwenden eine Instanz eines systemeigenen Typs auf dem Stapel zu erstellen. Also, Sie müssen nicht mit [Ref neue Gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) ein Objekt eines Verweistyps erstellt. Und wenn das Objekt den Gültigkeitsbereich verlässt, ruft der Compiler des Destruktors des Objekts.

## <a name="remarks"></a>Hinweise

Wenn Sie eine Instanz eines Referenztyps mit Stapelsemantik erstellen, erstellt der Compiler intern die Instanz auf dem Heap mit Garbage collection (mit `gcnew`).

Wenn die Signatur "oder" Return "-Typ, der eine Funktion eine Instanz eines Verweistyps als Wert enthält, wird die Funktion in den Metadaten erfordern besondere Behandlung (mit Modreq) gekennzeichnet. Diese besondere Behandlung ist derzeit nur von Visual C++-Clients; bereitgestellt. andere Sprachen werden derzeit nicht unterstützt, Funktionen oder Daten, die Verweistypen, die mit Stapelsemantik erstellt verwenden.

Ein Grund für die Verwendung `gcnew` (dynamische speicherbelegung) anstelle von Stack Semantik wäre, wenn der Typ keinen Destruktor aufweist. Darüber hinaus wäre mit Verweistypen mit Stapelsemantik Funktionssignaturen im erstellten nicht möglich, wenn Sie Ihre Funktionen, die von anderen Sprachen als Visual C++ verwendet werden soll.

Nicht generiert der Compiler einen Kopierkonstruktor für einen Verweistyp handelt. Wenn Sie eine Funktion definieren, die ein Verweistyp als Wert in der Signatur verwendet wird, müssen Sie daher einen Kopierkonstruktor für den Verweistyp definieren. Ein Kopierkonstruktor für einen Verweistyp hat eine Signatur mit dem folgenden Format: `R(R%){}`.

Der Compiler generiert einen standardzuweisungsoperator für einen Verweistyp nicht. Ein Zuweisungsoperator, können Sie ein Objekt, das mithilfe von Stapelsemantik erstellen und initialisieren Sie es mit einem vorhandenen Objekt, das mithilfe von Stapelsemantik erstellt. Ein Zuweisungsoperator für einen Verweistyp hat eine Signatur mit dem folgenden Format: `void operator=( R% ){}`.

Wenn der Destruktor des Typs kritische Ressourcen frei, und Sie Stapelsemantik für Referenztypen verwenden, müssen Sie nicht den Destruktor explizit aufruft (oder rufen Sie `delete`). Weitere Informationen zu Destruktoren in Verweistypen, finden Sie unter [Destruktoren und Finalizer unter How to: Definieren und Verarbeiten von Klassen und Strukturen (C++ / CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Ein vom Compiler generierten Zuweisungsoperator führen Sie die üblichen standard C++-Regeln mit den folgenden Ergänzungen:

- Nicht statische Daten, Elemente, deren Typ ein Handle für ein Verweistyp ist, flache kopierten (z. B. einen nicht statischen Datenmember, dessen Typ ein Zeiger ist, behandelt).

- Alle nicht statischen Datenmember, dessen Typ ist, dass ein Werttyp flache werden, kopiert.

- Alle nicht statischen Datenmember, dessen Typ eine Instanz eines Verweistyps ist, wird einen Aufruf an den Verweistyp Kopierkonstruktor aufgerufen.

Der Compiler bietet auch eine `%` unäroperator, um eine Instanz eines Referenztyps mit Stapelsemantik in den Handletyp der zugrunde liegende erstellt zu konvertieren.

Die folgenden Verweistypen sind nicht verfügbar, für die Verwendung mit Stapelsemantik:

- [delegate (Komponentenerweiterungen für C++)](../extensions/delegate-cpp-component-extensions.md)

- [Arrays](../extensions/arrays-cpp-component-extensions.md)

- <xref:System.String>

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Codebeispiel zeigt, wie zum Deklarieren von Instanzen von Verweistypen mit Stapelsemantik, wie der Zuweisungsoperator und Copy-Konstruktor funktionieren und wie einen Nachverfolgungsverweis mit Verweistyp mithilfe von Stapelsemantik erstellt initialisiert.

### <a name="code"></a>Code

```cpp
// stack_semantics_for_reference_types.cpp
// compile with: /clr
ref class R {
public:
   int i;
   R(){}

   // assignment operator
   void operator=(R% r) {
      i = r.i;
   }

   // copy constructor
   R(R% r) : i(r.i) {}
};

void Test(R r) {}   // requires copy constructor

int main() {
   R r1;
   r1.i = 98;

   R r2(r1);   // requires copy constructor
   System::Console::WriteLine(r1.i);
   System::Console::WriteLine(r2.i);

   // use % unary operator to convert instance using stack semantics
   // to its underlying handle
   R ^ r3 = %r1;
   System::Console::WriteLine(r3->i);

   Test(r1);

   R r4;
   R r5;
   r5.i = 13;
   r4 = r5;   // requires a user-defined assignment operator
   System::Console::WriteLine(r4.i);

   // initialize tracking reference
   R % r6 = r4;
   System::Console::WriteLine(r6.i);
}
```

### <a name="output"></a>Output

```Output
98
98
98
13
13
```

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../extensions/classes-and-structs-cpp-component-extensions.md)
