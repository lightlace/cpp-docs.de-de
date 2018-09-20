---
title: Deklaration eines CLR-Verweisklassenobjekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- types [C++], reference types
- reference types, CLR
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f3e8ec6407e12d0c26331d45dc1659277feed016
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444579"
---
# <a name="declaration-of-a-clr-reference-class-object"></a>Deklaration eines CLR-Verweisklassenobjekts

Die Syntax zum Deklarieren und instanziieren ein Objekt eines Verweistyps für die Klasse verfügt über Visual c++ von Managed Extensions for C++ geändert.

In Managed Extensions ist ein Verweisklassenobjekt wahlweise unter Verwendung des mit der Syntax ISO-C++-Zeiger deklariert die `__gc` Schlüsselwort auf der linken Seite des Sterns (`*`). Hier sind beispielsweise eine Vielzahl von Verweis Klassendeklarationen Typ-Objekt in der Managed Extensions-Syntax:

```
public __gc class Form1 : public System::Windows::Forms::Form {
private:
   System::ComponentModel::Container __gc *components;
   Button __gc *button1;
   DataGrid __gc *myDataGrid;
   DataSet __gc *myDataSet;

   void PrintValues( Array* myArr ) {
      System::Collections::IEnumerator* myEnumerator =
         myArr->GetEnumerator();

      Array *localArray;
      myArr->Copy(myArr, localArray, myArr->Length);
   }
};
```

In der neuen Syntax, Sie ein Objekt vom Typ Verweisklasse deklarieren, indem Sie ein neues Token für die deklarative (`^`) formal als bezeichnet ein *Trackinghandle* und informell als eine *Hat*. (Tracking bedeutet, dass ein Verweistyp im CLR-Heap befindet und daher bei der Garbage Collection-Heap-Komprimierung auf transparent verschieben kann. Ein Trackinghandle wird während der Laufzeit transparent aktualisiert. Zwei ähnliche Konzepte der *Nachverfolgungsverweis* (`%`), und die *innerer Zeiger* (`interior_ptr<>`), erläutert in [Werttypsemantik](../dotnet/value-type-semantics.md).

Die Hauptgründe, verschieben Sie die deklarative Syntax eine Wiederverwendung der Zeiger ISO-C++-Syntax lauten wie folgt aus:

- Die Verwendung der Zeigersyntax die überladene Operatoren, die direkt auf ein Verweisobjekt angewendet werden nicht zulässig. Stattdessen eine den Operator aufrufen, indem Sie seinen internen Namen, z. B. mit musste `rV1->op_Addition(rV2)` statt die stärker intuitive `rV1+rV2`.

- Eine Anzahl von Zeiger-Vorgänge, z. B. die Umwandlung und Zeigerarithmetik, die nicht zulässig für Objekte, die auf einen Garbage gespeicherten gesammelten Heap. Das Konzept der ein Trackinghandle besser erfasst das Wesen ein CLR-Verweistyp.

Die `__gc` -Modifizierer in der ein Trackinghandle ist nicht erforderlich und wird nicht unterstützt. Die Verwendung des Objekts selbst wird nicht geändert haben. immer noch auf Member zugreift, über der Zeiger-Memberauswahloperator (`->`). Hier ist beispielsweise im vorherigen Codebeispiel für Managed Extensions in der neuen Syntax übersetzt:

```
public ref class Form1: public System::Windows::Forms::Form {
private:
   System::ComponentModel::Container^ components;
   Button^ button1;
   DataGrid^ myDataGrid;
   DataSet^ myDataSet;

   void PrintValues( Array^ myArr ) {
      System::Collections::IEnumerator^ myEnumerator =
         myArr->GetEnumerator();

      Array ^localArray;
      myArr->Copy(myArr, localArray, myArr->Length);   }
};
```

## <a name="dynamic-allocation-of-an-object-on-the-clr-heap"></a>Dynamische Zuordnung von einem Objekt auf dem CLR-Heap

In Managed Extensions das Vorhandensein von zwei `new` Ausdrücke, die zwischen dem systemeigenen und verwalteten Heap zugeordnet war größtenteils transparent. In fast allen Fällen kann der Compiler den Kontext verwenden, um zu bestimmen, ob Arbeitsspeicher aus dem systemeigenen oder verwalteten Heap belegt. Ein auf ein Objekt angewendeter

```
Button *button1 = new Button; // OK: managed heap
int *pi1 = new int;           // OK: native heap
Int32 *pi2 = new Int32;       // OK: managed heap
```

Wenn Sie nicht, dass die kontextbezogene Heapzuordnung möchten, Sie können den Compiler anweisen, entweder mit der `__gc` oder `__nogc` Schlüsselwort. In der neuen Syntax der separaten Natur der beiden neuen Ausdrücke werden zu expliziten Informationen mit der Einführung der `gcnew` Schlüsselwort. Beispielsweise sehen die drei vorherigen Deklarationen in der neuen Syntax wie folgt:

```
Button^ button1 = gcnew Button;        // OK: managed heap
int * pi1 = new int;                   // OK: native heap
Int32^ pi2 = gcnew Int32; // OK: managed heap
```

Hier ist die Initialisierung Managed Extensions die `Form1` Member deklariert wird, im vorherigen Abschnitt:

```
void InitializeComponent() {
   components = new System::ComponentModel::Container();
   button1 = new System::Windows::Forms::Button();
   myDataGrid = new DataGrid();

   button1->Click +=
      new System::EventHandler(this, &Form1::button1_Click);
}
```

Hier ist die gleiche Initialisierung der neuen Syntax. Beachten Sie, dass die Hut nicht für den Referenztyp erforderlich ist, wenn es das Ziel ist eine `gcnew` Ausdruck.

```
void InitializeComponent() {
   components = gcnew System::ComponentModel::Container;
   button1 = gcnew System::Windows::Forms::Button;
   myDataGrid = gcnew DataGrid;

   button1->Click +=
      gcnew System::EventHandler( this, &Form1::button1_Click );
}
```

## <a name="a-tracking-reference-to-no-object"></a>Ein Nachverfolgungsverweis auf kein Objekt

In der neuen Syntax `0` mehr steht für eine null-Adresse, aber so behandelt, als eine ganze Zahl, die identisch mit `1`, `10`, oder `100`. Ein neues Token für die spezielles stellt einen null-Wert für ein Nachverfolgungsverweis dar. In Managed Extensions initialisieren wir z. B. einen Referenztyp, der kein Objekt wie folgt beheben:

```
// OK: we set obj to refer to no object
Object * obj = 0;

// Error: no implicit boxing
Object * obj2 = 1;
```

Der neuen Syntax wird jede Initialisierung oder Zuweisung eines Werts eingeben, ein `Object` bewirkt, dass ein implizites Boxing von diesem Typ. In der neuen Syntax sowohl `obj` und `obj2` behandelt geschachtelte Int32-Objekten, die die Werte 0 und 1, jeweils mit initialisiert werden. Zum Beispiel:

```
// causes the implicit boxing of both 0 and 1
Object ^ obj = 0;
Object ^ obj2 = 1;
```

Aus diesem Grund um explizite Initialisierung, Zuweisung und ein Trackinghandle für null-Vergleich auszuführen, verwenden Sie ein neues Schlüsselwort, `nullptr`.  Die korrekte Überarbeitung des ursprünglichen Beispiels sieht wie folgt aus:

```
// OK: we set obj to refer to no object
Object ^ obj = nullptr;

// OK: we initialize obj2 to a Int32^
Object ^ obj2 = 1;
```

Dies verkompliziert die etwas das Portieren von vorhandenem Code in der neuen Syntax. Betrachten Sie beispielsweise die folgende Klassendeklaration für den Wert ein:

```
__value struct Holder {
   Holder( Continuation* c, Sexpr* v ) {
      cont = c;
      value = v;
      args = 0;
      env = 0;
   }

private:
   Continuation* cont;
   Sexpr * value;
   Environment* env;
   Sexpr * args __gc [];
};
```

Hier beide `args` und `env` CLR-Verweistypen sind. Die Initialisierung des dieser beiden Member mit `0` im Konstruktor kann nicht unverändert in die Umstellung auf die neue Syntax. Sie müssen stattdessen geändert werden, um `nullptr`:

```
value struct Holder {
   Holder( Continuation^ c, Sexpr^ v )
   {
      cont = c;
      value = v;
      args = nullptr;
      env = nullptr;
   }

private:
   Continuation^ cont;
   Sexpr^ value;
   Environment^ env;
   array<Sexpr^>^ args;
};
```

Auf ähnliche Weise für die Elemente vergleichen diese tests `0` muss ebenfalls geändert werden, um die Elemente vergleichen `nullptr`. Hier ist die Managed Extensions-Syntax ein:

```
Sexpr * Loop (Sexpr* input) {
   value = 0;
   Holder holder = Interpret(this, input, env);

   while (holder.cont != 0) {
      if (holder.env != 0) {
         holder=Interpret(holder.cont,holder.value,holder.env);
      }
      else if (holder.args != 0) {
         holder =
         holder.value->closure()->
         apply(holder.cont,holder.args);
      }
   }

   return value;
}
```

Hier ist die Revision, und Ersetzen Sie dabei jeweils `0` Instanz mit einem `nullptr`. Die Übersetzungstool kann diese Transformation durch die Automatisierung viele, wenn nicht alle Vorkommen, einschließlich der Verwendung von der `NULL` Makro.

```
Sexpr ^ Loop (Sexpr^ input) {
   value = nullptr;
   Holder holder = Interpret(this, input, env);

   while ( holder.cont != nullptr ) {
      if ( holder.env != nullptr ) {
         holder=Interpret(holder.cont,holder.value,holder.env);
      }
      else if (holder.args != nullptr ) {
         holder =
         holder.value->closure()->
         apply(holder.cont,holder.args);
      }
   }

   return value;
}
```

Die `nullptr` , die in ein beliebiges Handle Zeiger- oder konvertiert wird, aber nicht in einen ganzzahligen Typ heraufgestuft wird. In den folgenden Satz von Initialisierungen, beispielsweise die `nullptr` ist nur als einen Anfangswert für die ersten beiden gültig.

```
// OK: we set obj and pstr to refer to no object
Object^ obj = nullptr;
char*   pstr = nullptr; // 0 would also work here

// Error: no conversion of nullptr to 0
int ival = nullptr;
```

Auf ähnliche Weise erhalten einen überladenen Satz von Methoden wie z. B. Folgendes:

```
void f( Object^ ); // (1)
void f( char* );   // (2)
void f( int );     // (3)
```

Ein Aufruf mit `nullptr` literal, z. B. Folgendes ein,

```
// Error: ambiguous: matches (1) and (2)
f(  nullptr );
```

ist mehrdeutig, da die `nullptr` entspricht sowohl ein Trackinghandle und ein Zeiger ist, und es gibt keine Einstellung für einen Typ angegeben wird, gegenüber der anderen. (Dies erfordert eine explizite Umwandlung, um eindeutig zu machen.)

Ein Aufruf mit `0` entspricht genau Instanz (3):

```
// OK: matches (3)
f( 0 );
```

Da `0` vom typinteger ist. Wurden `f(int)` nicht vorhanden ist, der Aufruf eindeutig entsprechen `f(char*)` über eine standardkonvertierung. Geben Sie die Abgleichsregeln Rangfolge eine genaue Übereinstimmung über eine standardkonvertierung. In einer genauen Übereinstimmung vorhanden ist wird eine standardkonvertierung Vorrang über ein implizites Boxing eines Werttyps zugewiesen. Aus diesem Grund ist es keine Mehrdeutigkeit.

## <a name="see-also"></a>Siehe auch

[Verwaltete Typen (C++ / CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)<br/>
[nullptr](../windows/nullptr-cpp-component-extensions.md)