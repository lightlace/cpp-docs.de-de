---
title: Wert Typsemantik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interior_ptr keyword [C++]
- virtual functions, value types
- inheritance, value types
- pinning pointers
- pin_ptr keyword [C++]
- __pin keyword
ms.assetid: 7f065589-ad25-4850-baf1-985142e35e52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 44662f2ad8e79712b4aab17e2784a72e01ec4116
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="value-type-semantics"></a>Werttypsemantik
Werttypsemantik haben sich von Managed Extensions für C++ in Visual C++ geändert.  
  
 So sieht die kanonische einfacher Werttyp in Managed Extensions für C++-Spezifikation verwendet:  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
```  
  
 In Managed Extensions können wir haben vier syntaktische Varianten eines Werttyps (wobei entsprechen Forms 2 und 3 semantisch):  
  
```  
V v = { 0 };       // Form (1)  
V *pv = 0;         // Form (2) an implicit form of (3)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0; // Form (4) must be local   
```  
  
## <a name="invoking-inherited-virtual-methods"></a>Geerbte virtuelle Methoden aufrufen  
 `Form (1)` ist die kanonische, und es ist ausreichend gut verstanden, außer wenn jemand versucht, auf eine geerbte virtuelle Methode aufrufen, wie z. B. `ToString()`. Zum Beispiel:  
  
```  
v.ToString(); // error!  
```  
  
 Um diese Methode aufzurufen, da er nicht in überschrieben wird `V`, der Compiler muss Zugriff auf die zugeordnete virtuelle Tabelle der Basisklasse haben. Da Werttypen ohne den zugeordneten Zeiger auf die virtuelle Tabelle (Vptr) im Zustandsspeicher sind, dies erfordert, dass `v` geschachtelt werden. In der Managed Extensions-Language-Entwurf implizites Boxing wird nicht unterstützt, jedoch muss explizit angegeben werden vom Programmierer, wie in  
  
```  
__box( v )->ToString(); // Managed Extensions: note the arrow  
```  
  
 Die primären Durchführbarkeit dieses Design ist pädagogischer Natur: zugrunde liegende Mechanismus muss sichtbar gemacht werden, damit sie verstehen, die Kosten für eine Instanz in ihrem Werttyp nicht bereitgestellt wird. Wurden `V` enthält eine Instanz von `ToString`, das Boxing wäre nicht erforderlich.  
  
 Die lexikalische Komplexität von explizit boxing des Objekts, aber nicht die zugrunde liegenden Kosten für das Boxing selbst wird in der neuen Syntax entfernt:  
  
```  
v.ToString(); // new syntax  
```  
  
 jedoch wird möglicherweise der Klassen-Designer auf die Kosten müssen explizite Instanz nicht angegeben irreführend der `ToString` Methode innerhalb `V`. Der Grund für implizites Boxing ist, dass zwar gibt es in der Regel nur eine Klassen-Designer, es eine unbegrenzte Anzahl von Benutzern gibt, none, von denen müsste die Freiheit gibt, ändern Sie `V` explizite Feld möglicherweise sehr aufwändig zu vermeiden.  
  
 Die Kriterien, um zu bestimmen, ob eine überschreibende Instanz der bieten `ToString` Klasse sollte in einem Wert sein, die Häufigkeit und Position Verwendungen. Wenn sie sehr selten aufgerufen wird, ist natürlich wenig Vorteile in ihrer Definition. Auf ähnliche Weise, wenn sie in nicht-leistungsfähigen Bereiche der Anwendung aufgerufen wird, werden hinzufügen auch nicht messbar die allgemeine Leistung der Anwendung hinzufügen. Klicken Sie alternativ eine kann ein Trackinghandle für den geschachtelten Wert beibehalten und Aufrufe über den Handle ist kein Boxing notwendig.  
  
## <a name="there-is-no-longer-a-value-class-default-constructor"></a>Es ist nicht mehr eine Default-Wert Klassenkonstruktor  
 Ein weiterer Unterschied mit einem Werttyp zwischen Managed Extensions und der neuen Syntax ist das Entfernen der Unterstützung für einen Standardkonstruktor. Dies ist da während der Ausführung in der CLR eine Instanz des Werttyps erstellen kann Gesicht, ohne den zugeordneten Standardkonstruktor aufrufen. Der Versuch in Managed Extensions, die einen trivialen Konstruktor innerhalb eines Werttyps unterstützen kann, also nicht in der Praxis garantiert werden. Angesichts dieser Abwesenheit Garantie, wurde es sind zu besser sein, die Unterstützung zu löschen, anstatt es in ihrer Anwendung nicht deterministisch sein.  
  
 Dies ist nicht als fehlerhaft, wie es ursprünglich scheint. Dies ist, da jedes Objekt eines Werttyps wird automatisch eliminiert (d. h., jeder Typ wird auf den Standardwert initialisiert). Dies hat zur Folge, dass die Mitglieder einer lokalen Instanz nie nicht definiert. In diesem Sinn der Verlust der Fähigkeit, die einen trivialen Standardkonstruktor definieren ist wirklich keine Verlust überhaupt - und in der Tat ist jedoch effizienter, wenn von der CLR ausgeführt.  
  
 Das Problem ist, wenn ein Benutzer von Managed Extensions einen nicht trivialen Standardkonstruktor definiert. Dies hat keine Zuordnung in die neue Syntax. Der Code im Konstruktor müssen in eine benannte Initialisierungsmethode migriert werden, die anschließend explizit vom Benutzer aufgerufen werden muss.  
  
 Die Deklaration eines Objekts vom Typ Wert in der neuen Syntax ist andernfalls nicht geändert. Der Nachteil dieses ist, dass Werttypen nicht aus den folgenden Gründen für die Einbindung der systemeigenen Typen sind:  
  
-   Es gibt keine Unterstützung für einen Destruktor innerhalb eines Werttyps. Es ist also keine Möglichkeit, eine Reihe von Aktionen, die ausgelöst wird, indem am Ende der Lebensdauer eines Objekts zu automatisieren.  
  
-   Eine systemeigene Klasse kann nur innerhalb eines verwalteten Typs als Zeiger enthalten sein, der dann auf dem systemeigenen Heap zugeordnet ist.  
  
 Wir möchten gerne umschließen eine kleine systemeigene Klasse ein Werttyp, statt ein Verweistyp eine doppelte Heapzuweisung zu vermeiden: systemeigenen Heap, die den systemeigenen Typ und dem CLR-Heap auf den verwalteten Wrapper. Umschließen einer systemeigenen Klasse innerhalb eines Werttyps ermöglicht Ihnen, zu den verwalteten Heap zu vermeiden, bietet jedoch keine Möglichkeit, die Freigabe von Speicher auf dem systemeigenen Heap zu automatisieren. Verweistypen sind die einzigen verwalteten Typen, in dem nicht triviale systemeigene Klassen zu umschließen.  
  
## <a name="interior-pointers"></a>Inneren Zeigern  
 `Form (2)` und `Form (3)` höher können beheben nahezu alles in dieser Welt oder bei der nächsten (d. h. alles, was verwaltetem oder systemeigenem). Deshalb sind z. B. Folgendes in Managed Extensions zulässig:  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
  
V v = { 0 };  // Form (1)  
V *pv = 0;  // Form (2)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0;  // Form (4)  
  
R* r;  
  
pv = &v;            // address a value type on the stack  
pv = __nogc new V;  // address a value type on native heap  
pv = pvgc;          // we are not sure what this addresses  
pv = pvbx;          // address a boxed value type on managed heap  
pv = &r->vr;        // an interior pointer to value type within a  
                    //    reference type on the managed heap  
```  
  
 Deshalb eine `V*` können einen Speicherort innerhalb eines lokalen Blocks adressieren (und daher Verbleibend werden können), im globalen Gültigkeitsbereich, in dem systemeigenen heap (z. B., wenn das Objekt, das er adressiert bereits gelöscht wurde), in dem CLR-Heap (und daher wird nachverfolgt werden, wenn es sollten verlagert werden während der Garbagecollection), und klicken Sie im inneren eines Verweis-Objekts auf dem CLR-Heap (ein innerer Zeiger wie diese aufgerufen wird, ist ebenfalls transparent nachverfolgt).  
  
 In Managed Extensions besteht keine Möglichkeit, die systemeigenen Aspekte auszusondern eine `V*`; d. h. es wird behandelt inklusiv behandelt die Möglichkeit, dass ein Objekt oder ein Unterobjekt auf dem verwalteten Heap zu adressieren.  
  
 In der neuen Syntax wird der Zeiger ein Wert vom Typ in der zwei Arten berücksichtigt: `V*`, also auf nicht-CLR-Heap-Speicherorte und der inneren Zeiger beschränkt `interior_ptr<V>`, die ermöglicht jedoch eine Adresse im verwalteten Heap ist nicht erforderlich.  
  
```  
// may not address within managed heap   
V *pv = 0;   
  
// may or may not address within managed heap  
interior_ptr<V> pvgc = nullptr;   
```  
  
 `Form (2)` und `Form (3)` Zuordnen von Managed Extensions `interior_ptr<V>`. `Form (4)` ist ein Trackinghandle. Behandelt das gesamte Objekt, das auf dem verwalteten Heap mittels Boxing konvertiert wurde. Er wird in der neuen Syntax in übersetzt eine `V^`,  
  
```  
V^ pvbx = nullptr; // __box V* pvbx = 0;    
```  
  
 Die folgenden Deklarationen in Managed Extensions alle inneren Zeigern in der neuen Syntax zugeordnet. (sie sind Werttypen, die innerhalb der `System` Namespace.)  
  
```  
Int32 *pi;   // => interior_ptr<Int32> pi;  
Boolean *pb; // => interior_ptr<Boolean> pb;  
E *pe;       // => interior_ptr<E> pe; // Enumeration  
```  
  
 Die integrierten Typen werden nicht verwaltete Typen berücksichtigt, obwohl sie als Aliase für die Typen im dienen der `System` Namespace. So halten Sie die folgenden Zuordnungen zwischen Managed Extensions und der neuen Syntax "true":  
  
```  
int * pi;     // => int* pi;  
int __gc * pi2; // => interior_ptr<int> pi2;  
```  
  
 Beim Übersetzen einer `V*` in das vorhandene Programm die konservative Strategie ist immer aktivieren Sie auf eine `interior_ptr<V>`. Dies ist, wie er in Managed Extensions behandelt wurde. In der neuen Syntax der Programmierer hat einen Werttyp an nicht verwalteten Heaps Adressen einschränken, durch Angabe `V*` anstelle eines inneren Zeigers. Wenn beim Übersetzen des Programms an, Sie können alle Verwendungen einen transitiven Abschluss und achten Sie darauf, dass keine zugewiesene Adresse auf dem verwalteten Heap ist, dann seinen Arbeitsplatz verlässt als `V*` ist in Ordnung.  
  
## <a name="pinning-pointers"></a>Festhalten von Zeigern  
 Der Garbage Collector kann optional Objekte verschieben, die sich auf dem CLR-Heap an verschiedene Positionen innerhalb des Heaps in der Regel während einer Komprimierungsphase befinden. Diese Bewegung ist kein Problem zum Nachverfolgen von Handles, Nachverfolgungsverweisen und inneren Zeigern, die diese Entitäten transparent zu aktualisieren. Diese Bewegung ist jedoch ein Problem, wenn der Benutzer die Adresse eines Objekts auf dem CLR-Heap außerhalb der Common Language Runtime-Umgebung überschritten hat. In diesem Fall wird die flüchtige Verschiebung des Objekts wahrscheinlich eines Laufzeitfehlers verursachen. Ausgenommen Objekte wie diese verschoben werden, müssen wir diese lokal an ihrem Speicherort für das Ausmaß der äußeren Verwendungsbeispielen anheften.  
  
 In Managed Extensions wird einem *feste Zeiger* wird deklariert, indem eine Zeigerdeklaration mit der `__pin` Schlüsselwort. Hier ist ein Beispiel, die von der Spezifikation von Managed Extensions etwas geändert:  
  
```  
__gc struct H { int j; };  
  
int main()   
{  
   H * h = new H;  
   int __pin * k = & h -> j;  
  
   // ...  
};  
```  
  
 In der neuen Sprache Entwurf ist ein fester Zeiger mit der Syntax, die analog zu einem inneren Zeiger deklariert.  
  
```  
ref struct H  
{  
public:  
   int j;  
};  
  
int main()  
{  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
  
   // ...  
}  
```  
  
 Ein fester Zeiger in der neuen Syntax ist ein Sonderfall eines inneren Zeigers. Die ursprünglichen Einschränkungen für einen festen Zeiger bleiben. Angenommen, sie kann nicht als Parameter verwendet werden oder Rückgabetyp einer Methode; Es kann nur auf ein lokales Objekt deklariert werden. Eine Reihe von zusätzlichen Beschränkungen wurden jedoch in der neuen Syntax hinzugefügt.  
  
 Der Standardwert eines festen Zeigers ist `nullptr`, nicht `0`. Ein `pin_ptr<>` kann nicht initialisiert oder zugewiesen `0`. Alle Zuweisungen von `0` in vorhandenem Code müssen geändert werden, um `nullptr`.  
  
 Ein fester Zeiger in Managed Extensions wurde zugelassen, um ein ganzes Objekt, wie im folgenden Beispiel stammt aus der Managed Extensions-Spezifikation zu beheben:  
  
```  
__gc class G {  
public:  
   void incr(int* pi) { pi += 1; }  
};  
__gc struct H { int j; };  
void f( G * g ) {  
   H __pin * pH = new H;     
   g->incr(& pH -> j);     
};  
```  
  
 In der neuen Syntax anheften als ganze Objekt zurückgegeben, indem die `new` Ausdruck wird nicht unterstützt. Stattdessen muss die Adresse des inneren Elements angeheftet werden. Ein auf ein Objekt angewendeter  
  
```  
ref class G {  
public:  
   void incr(int* pi) { *pi += 1; }  
};  
ref struct H { int j; };  
void f( G^ g ) {  
   H ^ph = gcnew H;  
   Console::WriteLine(ph->j);  
   pin_ptr<int> pj = &ph->j;  
   g->incr(  pj );  
   Console::WriteLine(ph->j);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Werttypen und ihr Verhalten (C + c++ / CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Interior_ptr (C + c++ / CLI)](../windows/interior-ptr-cpp-cli.md)   
 [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)