---
title: STL/CLR-Container
ms.date: 09/18/2018
ms.topic: reference
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
ms.openlocfilehash: 1787e18cb36c77429cd4957bab167c77d5e25d8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496082"
---
# <a name="stlclr-containers"></a>STL/CLR-Container

Die STL/CLR-Bibliothek besteht aus Containern, die ähnliche befinden sich in der C++-Standardbibliothek, aber sie innerhalb der verwalteten Umgebung von .NET Framework ausgeführt wird. Es wird nicht auf dem neuesten Stand mit der tatsächlichen C++-Standardbibliothek beibehalten und wird für die Unterstützung beibehalten.

Dieses Dokument enthält eine Übersicht über die Container in STL/CLR, z. B. die Anforderungen für Containerelemente, die Typen der Elemente, Sie in den Containern einfügen können und den Besitz mit den Elementen in den Containern gibt. Gegebenenfalls werden die Unterschiede zwischen dem systemeigenen C++-Standardbibliothek und STL/CLR erwähnt.

## <a name="requirements-for-container-elements"></a>Anforderungen für Containerelemente

Alle Elemente, die in STL/CLR-Container eingefügt müssen bestimmte Richtlinien unterliegen. Weitere Informationen finden Sie unter [Anforderungen für STL/CLR-Containerelemente](../dotnet/requirements-for-stl-clr-container-elements.md).

## <a name="valid-container-elements"></a>Gültige Container-Elemente

STL/CLR-Container können es sich um einen von zwei Typen von Elementen enthalten:

- Kümmert sich um Typen zu verweisen.

- Verweistypen.

- Nicht geschachtelte Werttypen.

Sie können keine geschachtelte Werttypen in jedem der STL/CLR-Container einfügen.

### <a name="handles-to-reference-types"></a>Handles für Referenztypen

Sie können ein Handle für ein Verweistyp in einen STL/CLR-Container einfügen. Ein Handle in C++, die die CLR ist analog zu einem Zeiger in systemeigenem C++. Weitere Informationen finden Sie unter [Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).

#### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie ein Handle für ein Employee-Objekt in Einfügen einer [cliext::set](../dotnet/set-stl-clr.md).

```
// cliext_container_valid_reference_handle.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // STL/CLR containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All STL/CLR containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All STL/CLR containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All STL/CLR containers require a public destructor.
    ~Employee() { }

    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee^ empl1419 = gcnew Employee();
    empl1419->Name = L"Darin Lockert";
    empl1419->EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee^>^ emplSet = gcnew set<Employee^>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee^ empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl->EmployeeNumber, empl->Name);
    }

    return 0;
}
```

### <a name="reference-types"></a>Verweistypen

Es ist auch möglich, einen Verweistyp handelt (statt ein Handle für einen Verweistyp) in einen STL/CLR-Container eingefügt. Der Hauptunterschied besteht hier ist, wenn ein Container für Verweistypen gelöscht wird, der Destruktor für alle Elemente im Container enthaltene aufgerufen wird. In einem Container von Handles für Verweistypen würde die Destruktoren für diese Elemente nicht aufgerufen werden.

#### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie zum Einfügen eines Objekts Mitarbeiter in einem `cliext::set`.

```
// cliext_container_valid_reference.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // STL/CLR containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All STL/CLR containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All STL/CLR containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All STL/CLR containers require a public destructor.
    ~Employee() { }

    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee empl1419;
    empl1419.Name = L"Darin Lockert";
    empl1419.EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee>^ emplSet = gcnew set<Employee>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee^ empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl->EmployeeNumber, empl->Name);
    }

    return 0;
}
```

### <a name="unboxed-value-types"></a>Nicht geschachtelte Werttypen

Sie können auch einen nicht geschachtelter Werttyp in einen STL/CLR-Container einfügen. Nicht geschachtelter Werttyp ist ein Werttyp, der nicht wurde *geschachtelt* in einen Verweistyp handelt.

Ein Value-Type-Element kann eine der standardmäßigen Werttypen, wie z. B. eine `int`, oder es kann ein benutzerdefinierter Wert z. B. eine `value class`. Weitere Informationen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)

#### <a name="example"></a>Beispiel

Das folgende Beispiel ändert die im erste Beispiel, indem Sie den Mitarbeiter, die einen Werttyp Klasse machen. Diesen Werttyp wird dann in eingefügt eine `cliext::set` wie im ersten Beispiel.

```
// cliext_container_valid_valuetype.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

value class Employee
{
public:
    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee empl1419;
    empl1419.Name = L"Darin Lockert";
    empl1419.EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee>^ emplSet = gcnew set<Employee>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl.EmployeeNumber, empl.Name);
    }

    return 0;
}
```

Wenn Sie versuchen, ein Handle für einen Werttyp in einen Container einfügen [Compilerfehler C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) wird generiert.

### <a name="performance-and-memory-implications"></a>Leistung und Arbeitsspeicher-Auswirkungen

Sie müssen mehrere Faktoren berücksichtigt, wenn bestimmt wird, ob Handles zum Verweisen auf Typen oder Werttypen als Elemente verwendet. Wenn Sie Werttypen verwenden möchten, denken Sie daran, dass eine Kopie des Elements erstellt wird, jedes Mal, wenn ein Element in den Container eingefügt wird. Für kleine Objekte Dies sollte kein Problem sein, aber wenn die Objekte, die eingefügte groß sind, die Leistung kann beeinträchtigt werden. Auch wenn Sie mit Werttypen arbeiten, ist es unmöglich, ein Element in mehreren Containern zur gleichen Zeit zu speichern, da jeder Container eine eigene Kopie des Elements verfügen würde.

Wenn Sie Handles zu verwenden, um Typen stattdessen verweisen möchten, kann die Leistung erhöhen, da es nicht erforderlich, erstellen Sie eine Kopie des Elements ein, wenn es in den Container eingefügt wird, ist. Darüber hinaus kann anders als bei Werttypen das gleiche Element in mehreren Containern vorhanden. Jedoch wenn Sie Handles verwenden möchten, müssen Sie darauf achten, stellen Sie sicher, dass das Handle gültig ist und das Objekt, auf die, dem es verweist, nicht an anderer Stelle im Programm gelöscht wurde.

## <a name="ownership-issues-with-containers"></a>Besitzprobleme mit Containern

Container in STL/CLR arbeiten Wertsemantik. Jedes Mal, wenn Sie ein Element in einen Container einfügen, wird eine Kopie des Elements eingefügt. Wenn Sie die Referenz-ähnlicher Semantik abrufen möchten, können Sie ein Handle für das Objekt selbst, sondern ein Objekt einfügen.

Wenn Sie Klartext aufrufen oder erase-Methode, eines Containers der Handle-Objekte, werden die Objekte, denen auf die Handles verweisen nicht aus dem Arbeitsspeicher freigegeben. Sie müssen entweder explizit Löschen des Objekts oder, da diese Objekte, auf dem verwalteten Heap befinden der Garbage Collector den Arbeitsspeicher freizugeben, sobald es feststellt, dass das Objekt nicht mehr verwendet wird.

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
