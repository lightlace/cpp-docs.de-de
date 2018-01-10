---
title: STL/CLR-Container | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1b8aa8ef5b1425d4aa41b1811dca5ec5d56acd1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="stlclr-containers"></a>STL/CLR-Container
Die STL/CLR-Bibliothek hat die gleichen Container, die in der C++-Standardbibliothek gefunden werden, aber er innerhalb der verwalteten Umgebung von .NET Framework ausgeführt wird. Wenn Sie bereits mit der C++-Standardbibliothek vertraut sind, ist die STL/CLR die beste Möglichkeit, um anzugeben, dass die Kenntnisse zu verwenden, die Sie bereits beim Aktualisieren von Code auf die common Language Runtime (CLR) entwickelt haben.  
  
 Dieses Dokument enthält eine Übersicht über die Container in STL/CLR, z. B. die Anforderungen für Containerelemente, die Typen von Elementen, Sie in den Containern einfügen können und den Besitz, mit den Elementen im Container ausstellt. Falls zutreffend, werden die Unterschiede zwischen dem systemeigenen C++-Standardbibliothek und STL/CLR erwähnt.  
  
## <a name="requirements-for-container-elements"></a>Anforderungen für Containerelemente  
 Alle Elemente, die in C++-Standardbibliothek Container eingefügt müssen bestimmte Richtlinien unterliegen. Weitere Informationen finden Sie unter [Anforderungen für STL/CLR-Containerelemente](../dotnet/requirements-for-stl-clr-container-elements.md).  
  
## <a name="valid-container-elements"></a>Gültige Containerelemente  
 STL/CLR-Container können einen von zwei Typen von Elementen enthalten:  
  
-   Verweistypen behandelt.  
  
-   Verweistypen.  
  
-   Nicht geschachtelte Werttypen.  
  
 Geschachtelte Werttypen können nicht in jedem der STL/CLR-Container eingefügt werden.  
  
### <a name="handles-to-reference-types"></a>Handles für Referenztypen  
 Sie können ein Handle für ein Verweistyp in einen STL/CLR-Container einfügen. In C++ die CLR-Handle ist analog zu einem Zeiger in systemeigenem C++. Weitere Informationen finden Sie unter [Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
#### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie ein Handle für ein Employee-Objekt in einem [cliext::set](../dotnet/set-stl-clr.md).  
  
```  
// cliext_container_valid_reference_handle.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // C++ Standard Library containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All C++ Standard Library containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All C++ Standard Library containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All C++ Standard Library containers require a public destructor.  
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
 Es ist auch möglich, einen Referenztyp darstellt (statt ein Handle für einen Referenztyp darstellt) in einen STL/CLR-Container eingefügt. Der Hauptunterschied besteht darin, dass wenn ein Container für Verweistypen gelöscht wird, für alle Elemente im Container enthaltene der Destruktor aufgerufen wird. In einem Container des Handles für Verweistypen würde die Destruktoren für diese Elemente nicht aufgerufen werden.  
  
#### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie zum Einfügen eines Objekts Mitarbeiter in einem `cliext::set`.  
  
```  
// cliext_container_valid_reference.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // C++ Standard Library containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All C++ Standard Library containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All C++ Standard Library containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All C++ Standard Library containers require a public destructor.  
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
 Sie können auch einen nicht geschachtelten Werttyp in einen STL/CLR-Container einfügen. Ein nicht geschachtelter Werttyp ist ein Werttyp, der nicht *geschachtelt* in einen Referenztyp darstellt.  
  
 Ein Wert Type-Element kann eine der standard Werttypen, wie z. B. ein `int`, oder es kann einen benutzerdefinierten Werttyp aufweist, z. B. eine `value class`. Weitere Informationen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)  
  
#### <a name="example"></a>Beispiel  
 Im folgende Beispiel ändert die im erste Beispiel, indem Sie die Mitarbeiter, die einen Werttyp-Klasse machen. Dieser Typ wird dann in eingefügt eine `cliext::set` wie im ersten Beispiel.  
  
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
  
### <a name="performance-and-memory-implications"></a>Leistung und Arbeitsspeicher Auswirkungen  
 Sie müssen mehrere Faktoren berücksichtigt, wenn bestimmt wird, ob die Handles verweisen auf Typen oder Werttypen als Containerelemente verwendet. Wenn Sie Werttypen verwenden möchten, denken Sie daran, dass eine Kopie des Elements erfolgt jedes Mal, wenn ein Element in den Container eingefügt wird. Für kleine Objekte Dies sollte kein Problem sein, aber wenn die Objekte, die eingefügte groß sind, kann die Leistung beeinträchtigt. Auch bei Verwendung von Werttypen ist es unmöglich, ein Element mehrere Container zur gleichen Zeit zu speichern, da jeder Container eine eigene Kopie des Elements müsste.  
  
 Wenn Sie Handles zu verwenden, um stattdessen auf Typen verweisen möchten, kann die Leistung erhöhen, da es ist nicht erforderlich, erstellen Sie eine Kopie des Elements, wenn es in den Container eingefügt wird. Auch kann im Gegensatz zu mit Werttypen, die dasselbe Element in mehreren Containern erstellt werden. Jedoch, wenn Sie Handles verwenden möchten, Sie müssen darauf achten, stellen Sie sicher, dass das Handle gültig ist und das Objekt, dem er verweist, nicht an anderer Stelle im Programm gelöscht wurde.  
  
## <a name="ownership-issues-with-containers"></a>Besitzprobleme mit Containern  
 Container in STL/CLR arbeiten Wertsemantik. Jedes Mal, wenn Sie ein Element in einen Container einfügen, wird eine Kopie des Elements eingefügt. Wenn der Verweis-ähnliche Semantik abgerufen werden soll, können Sie ein Handle für das Objekt selbst, sondern ein Objekt einfügen.  
  
 Wenn Sie Klartext aufrufen oder erase-Methode, der einen Container der Handle-Objekte, werden die Objekte, denen auf die Handles verweisen nicht aus dem Arbeitsspeicher freigegeben. Sie müssen entweder explizit das Objekt zu löschen oder, da diese Objekte, auf dem verwalteten Heap befinden der Garbage Collector den Arbeitsspeicher freizugeben, sobald es feststellt, dass das Objekt nicht mehr verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)