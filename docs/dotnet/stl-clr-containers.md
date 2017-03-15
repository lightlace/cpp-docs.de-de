---
title: "STL/CLR-Container | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Container, STL/CLR"
  - "STL/CLR, Container"
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# STL/CLR-Container
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die STL\/CLR\-Bibliothek hat dieselben Container, die in der C\+\+\-Standardbibliothek gefunden werden, aber sie wird innerhalb der verwalteten Umgebung von .NET Framework ausgeführt.  Wenn Sie mit der Standardvorlagenbibliothek \(STL\) bereits vertraut sind, ist STL\/CLR die beste Methode, weiterhin Fähigkeiten zu verwenden, die Sie bereits beim Aktualisieren des Codes, die auf der Common Language Runtime \(CLR\) abzielt entwickelt haben.  
  
 Dieses Dokument bietet eine Übersicht der Container in STL\/CLR, wie Anforderungen für Containerelemente, Typen von Elementen, die Sie in die Container einfügen können, und den Besitz gibt mit den Elementen in den Containern aus.  Gegebenenfalls werden Unterschiede zwischen der systemeigenen und der Standardvorlagenbibliothek STL\/CLR erwähnt.  
  
## Anforderungen für Containerelemente  
 Alle Elemente, die in STL\-Container eingefügt werden, müssen bestimmte Richtlinien befolgen.  Weitere Informationen finden Sie unter [Anforderungen für STL\/CLR\-Containerelemente](../dotnet/requirements-for-stl-clr-container-elements.md).  
  
## Gültige Containerelemente  
 STL\/CLR\-Container können einen von zwei Typen Elemente enthalten:  
  
-   Steuerpunkte in Verweistypen.  
  
-   Referenztypen.  
  
-   Nicht geschachtelte Werttypen.  
  
 Sie können geschachtelte Werttypen nicht in allen der STL\/CLR\-Container einfügen.  
  
### Steuerpunkte in Verweistypen  
 Sie können einen Handletyp zu einem Verweistyp in STL einen\/CLR\-Container einfügen.  Ein Handle in C\+\+, die auf CLR abzielt, ist ein Zeiger in nativem C\+\+ analog.  Weitere Informationen finden Sie unter [Handle für Objekt \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
#### Beispiel  
 Das folgende Beispiel zeigt, wie ein Handle zu einem Mitarbeiterobjekt in [cliext::set](../dotnet/set-stl-clr.md) eingefügt.  
  
```  
// cliext_container_valid_reference_handle.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // STL containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All STL containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All STL containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All STL containers require a public destructor.  
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
  
### Verweistypen  
 Es ist auch möglich, einen Referenztyp \(statt ein Handle zu einem Verweistyp\) in STL einen\/CLR\-Container einzufügen.  Der Hauptunterschied besteht hier darin, dass, wenn ein Container Referenztypen gelöscht, wird der Destruktor für alles den darin enthaltenen Elementen aufgerufen wird, die Container.  In einem Container Handles zu den Destruktoren Verweistypen, werden die für diese Elemente nicht aufgerufen.  
  
#### Beispiel  
 Das folgende Beispiel zeigt, wie ein Mitarbeiterobjekt in `cliext::set` einfügen.  
  
```  
// cliext_container_valid_reference.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // STL containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All STL containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All STL containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All STL containers require a public destructor.  
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
  
### Nicht geschachtelte Werttypen  
 Sie können einen nicht geschachtelten Werttyp in STL einen\/CLR\-Container auch einfügen.  Ein nicht geschachtelter Werttyp ist ein Werttyp, der nicht in einen Verweistyp *geschachtelt worden* ist.  
  
 Ein Werttypelement kann einer der Standardwerttypen, wie `int` sein, oder es kann ein benutzerdefinierter Werttyp, wie beispielsweise `value class`.  Weitere Informationen finden Sie unter [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)  
  
#### Beispiel  
 Im folgenden Beispiel wird das erste Beispiel, indem die Mitarbeiterklasse einen Werttyp macht.  Dieser Werttyp wird dann in `cliext::set` wie im ersten Beispiel eingefügt.  
  
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
  
 Wenn Sie versuchen, ein Handle auf einen Werttyp in einen Container einfügen, wird [Compilerfehler C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) generiert.  
  
### Leistungs\- Arbeitsspeicher\-Auswirkungen  
 Sie müssen mehrere Faktoren Bestimmen prüfen, ob Handles für den oder Verweistypen in Werttypen als Containerelemente verwendet.  Wenn Sie sich entscheiden, Werttypen verwenden, beachten Sie, dass eine Kopie des Elements jedes Mal ein Element wurde eingefügt in den Container erstellt wird.  Für kleine Objekte sollte dieses Problem nicht auftreten, jedoch, wenn die Objekte, die eingefügt werden, groß sind, litte Leistung werden.  Wenn Sie Werttypen verwenden, ist es nicht möglich, ein Element in mehreren Containern gleichzeitig zu speichern, da jeder Container eine eigene Kopie des Elements verfügen würde.  
  
 Wenn Sie sich entscheiden, Handles für Referenztypen den stattdessen zu verwenden, kann sich die Leistung, da es nicht notwendig ist, eine Kopie des Elements zu erstellen, wenn sie im Container eingefügten wird.  Auch als mit Werttypen, kann dasselbe Element in mehreren Containern sind.  Wenn Sie sich entscheiden, Handles zu verwenden, müssen Sie beim gut, um sicherzustellen, dass das Handle gültig ist und dass das Objekt, das es verweist, nicht an anderer Stelle im Programm gelöscht wurde.  
  
## Besitz\-Probleme mit Containern  
 Container in STL\/CLR\-Arbeit über Wertsemantik bezeichnet.  Jedes Mal wenn Sie ein Element in einen Container einfügen, wird eine Kopie dieses Elements eingefügt.  Wenn Sie ähnliche Semantik Verweis abrufen möchten, können Sie ein Handle zu einem Objekt statt das Objekt selbst einfügen.  
  
 Wenn Sie den freien Speicherplatz aufrufen oder Methode eines Containers Handleobjekte löschen, werden die Objekte, die die Handles, nicht vom Arbeitsspeicher freigegeben.  Sie müssen entweder das Objekt explizit löschen, oder, da diese Objekte auf dem verwalteten Heap befinden, können Sie die Garbage Collector, um den Arbeitsspeicher freizugeben, sobald dieser bestimmt, dass das Objekt nicht mehr verwendet wird.  
  
## Siehe auch  
 [Standard Template Library](../misc/standard-template-library.md)