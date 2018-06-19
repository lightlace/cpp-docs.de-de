---
title: C++-Stapelsemantik für Referenztypen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- reference types, C++ stack semantics for
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b3ed886d1bdeb4972122049854b5d288767aa5b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111353"
---
# <a name="c-stack-semantics-for-reference-types"></a>C++-Stack-Semantik für Referenztypen
Vor Visual C++ 2005 eine Instanz eines Verweistyps konnte nur erstellt werden mithilfe der `new` -Operator, der das Objekt, auf die Garbage erstellt Collection Heap. Allerdings können Sie jetzt erstellen eine Instanz eines Verweistyps mit derselben Syntax, mit denen Sie eine Instanz eines systemeigenen Typs auf dem Stapel zu erstellen. Also, Sie müssen nicht mit [Ref neue Gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) So erstellen ein Objekt eines Verweistyps. Und wenn das Objekt den Gültigkeitsbereich verlässt, wird der Compiler ruft der Destruktor des Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie eine Instanz eines Verweistyps mit Stapelsemantik erstellen, erstellt der Compiler intern die Instanz auf dem Heap mit Garbage collection (mit `gcnew`).  
  
 Wenn der Typ Signatur oder des Rückgabetyps einer Funktion eine Instanz eines Verweistyps per-Wert enthält, wird die Funktion in den Metadaten erfordern eine besondere Behandlung (mit Modreq) gekennzeichnet. Diese besondere Behandlung wird derzeit nur von Visual C++-Clients bereitgestellt. andere Sprachen unterstützen verbrauchende Funktionen oder Daten, die Verweistypen, die mit Stapelsemantik erstellt verwenden derzeit nicht.  
  
 Ein Grund für das verwenden `gcnew` (dynamische Zuordnung) anstatt Stapels Semantik wäre, wenn der Typ keinen Destruktor aufweist. Darüber hinaus mit Verweistypen, die mit den Funktionssignaturen im Stack-Semantik erstellt nicht möglich, wenn Sie Funktionen, die von anderen Sprachen als Visual C++ verwendet werden soll.  
  
 Der Compiler generiert keinen Kopierkonstruktor für einen Referenztyp darstellt. Wenn Sie eine Funktion definieren, die einen Verweistyp als Wert in der Signatur verwendet wird, müssen Sie daher einen Kopierkonstruktor für den Verweistyp definieren. Ein Kopierkonstruktor für einen Verweistyp hat eine Signatur der folgenden Form: `R(R%){}`.  
  
 Der Compiler generiert keinen standardzuweisungsoperator für einen Referenztyp darstellt. Ein Zuweisungsoperator können Sie ein Objekt mithilfe von Stapelsemantik erstellen und initialisieren Sie es mit einem vorhandenen Objekt, das mithilfe von Stapelsemantik erstellt. Ein Zuweisungsoperator für einen Verweistyp hat eine Signatur der folgenden Form: `void operator=( R% ){}`.  
  
 Wenn der Destruktor des Typs kritische Ressourcen frei, und Sie Stapelsemantik für Referenztypen verwenden, müssen Sie nicht den Destruktor explizit aufruft (oder rufen Sie `delete`). Weitere Informationen über Destruktoren in Verweistypen, finden Sie unter [Destruktoren und Finalizer wie: definieren und Verarbeiten von Klassen und Strukturen (C + c++ / CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Ein vom Compiler generierten Zuweisungsoperator führen Sie die üblichen standard C++-Regeln mit den folgenden Ergänzungen:  
  
-   Nicht statische Daten-Elemente, deren Typ ein Handle für ein Verweistyp ist, flache kopierten (z. B. einen nicht statischen Datenmember, dessen Typ ein Zeiger ist, behandelt).  
  
-   Alle nicht statischen Datenmember, dessen Typ ist ein Werttyp flache kann, kopiert.  
  
-   Nicht statischen Datenmember, dessen Typ eine Instanz eines Verweistyps ist, wird einen Aufruf der Verweistyp Kopierkonstruktor aufgerufen.  
  
 Der Compiler bietet auch eine `%` unäroperator, um eine Instanz eines Verweistyps mithilfe von Stapelsemantik in den Handletyp der zugrunde liegende erstellt zu konvertieren.  
  
 Die folgenden Verweistypen sind nicht für die Verwendung mit Stapelsemantik verfügbar:  
  
-   [delegate (Komponentenerweiterungen für C++)](../windows/delegate-cpp-component-extensions.md)  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   <xref:System.String>  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Codebeispiel wird veranschaulicht, wie Instanzen von Verweistypen mit Stapelsemantik, deklariert wie die Zuweisungsoperator und Kopie Konstruktor funktioniert und wie einen Nachverfolgungsverweis mit Verweistyp mithilfe von Stapelsemantik erstellt initialisiert.  
  
### <a name="code"></a>Code  
  
```  
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
  
### <a name="output"></a>Ausgabe  
  
```  
98  
98  
98  
13  
13  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)