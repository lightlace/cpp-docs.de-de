---
title: "Werttypsemantik | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__pin-Schlüsselwort"
  - "Vererbung, Werttypen"
  - "interior_ptr-Schlüsselwort [C++]"
  - "pin_ptr-Schlüsselwort [C++]"
  - "Festhalten von Zeigern"
  - "Virtuelle Funktionen, Werttypen"
ms.assetid: 7f065589-ad25-4850-baf1-985142e35e52
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Werttypsemantik
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Werttypsemantik hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Dies ist der kanonische, einfache Werttyp, der in der Spezifikation von Managed Extensions for C\+\+ verwendet wird:  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
```  
  
 In Managed Extensions können vier syntaktische Varianten von Werttypen vorkommen \(wobei Form 2 und 3 semantisch gleich sind\):  
  
```  
V v = { 0 };       // Form (1)  
V *pv = 0;         // Form (2) an implicit form of (3)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0; // Form (4) must be local   
```  
  
## Aufrufen geerbter virtueller Methoden  
 `Form (1)` ist das kanonische Wertobjekt. Dies ist verhältnismäßig gut zu verstehen, solange niemand versucht, eine geerbte virtuelle Methode wie `ToString()` aufzurufen.  Beispiel:  
  
```  
v.ToString(); // error!  
```  
  
 Da diese Methode in `V` nicht überschrieben wird, muss der Compiler, um sie aufzurufen, Zugriff auf die zugeordnete virtuelle Tabelle der Basisklasse haben.  Da sich Werttypen ohne den zugeordneten Zeiger auf die virtuelle Tabelle \(vptr\) im Zustandsspeicher befinden, muss `v` geschachtelt sein.  Im Sprachdesign von Managed Extensions wird implizites Boxing nicht unterstützt, sondern muss explizit durch den Programmierer angegeben werden, wie in  
  
```  
__box( v )->ToString(); // Managed Extensions: note the arrow  
```  
  
 Das Hauptmotiv für dieses Design ist pädagogischer Natur: Den Programmierern soll der zugrunde liegende Mechanismus sichtbar gemacht werden. Sie sollen den Aufwand verstehen, der dadurch entsteht, dass innerhalb des Werttyps keine Instanz bereitgestellt wird.  Enthielte `V` eine Instanz von `ToString`, wäre das Boxing nicht notwendig.  
  
 Die lexikalische Komplexität expliziten Boxings des Objekts entfällt in der neuen Syntax, nicht jedoch der damit verbundene Aufwand:  
  
```  
v.ToString(); // new syntax  
```  
  
 Allerdings täuscht dies möglicherweise den Klassendesigner bezüglich des Aufwands, der dadurch entsteht, keine explizite Instanz der `ToString`\-Methode innerhalb von `V` bereitzustellen.  Implizites Boxing wird aus folgenden Gründen bevorzugt: Üblicherweise gibt es nur einen Klassendesigner, jedoch viele Benutzer, die nicht die Berechtigung besitzen, `V` zu ändern, um das möglicherweise lästige explizite Boxing zu beseitigen.  
  
 Als Kriterien für die Entscheidung, ob innerhalb einer Wertklasse eine überschreibende Instanz von `ToString` bereitgestellt wird, bieten sich Ort und Häufigkeit ihrer Verwendung an.  Wenn sie sehr selten aufgerufen wird, bietet ihre Definition natürlich wenig Nutzen.  Ebenso wird sie die allgemeine Leistung der Anwendung nicht spürbar verbessern, wenn sie in einem nicht\-leistungsfähigen Bereich der Anwendung aufgerufen wird.  Alternativ kann ein Trackinghandle für den geschachtelten Wert eingerichtet werden, da Aufrufe über den Handle kein Boxing erfordern.  
  
## Einen Standardkonstruktor für Wertklassen gibt es nicht mehr  
 Ein weiterer Unterschied der neuen Syntax gegenüber Managed Extensions bezüglich Werttypen ist die fehlende Unterstützung eines Standardkonstruktors.  Das liegt daran, dass die CLR unter Umständen während der Ausführung eine Instanz des Werttyps erstellen kann, ohne den zugeordneten Standardkonstruktor aufzurufen.  Die Unterstützung eines Standardkonstruktors innerhalb eines Werttyps konnte unter Managed Extensions in der Praxis nicht gewährleistet werden.  Daher wurde es als besser angesehen, auf die Unterstützung insgesamt zu verzichten, als sie unbestimmt in der Anwendung zu belassen.  
  
 Dieser Ansatz ist nicht so schlecht, wie es zunächst scheint.  Denn jedes einzelne Objekt eines Werttyps wird automatisch eliminiert \(d. h., jeder Typ wird mit seinem Standardwert initialisiert\).  Das heißt, die Member einer lokalen Instanz sind nie undefiniert.  In diesem Sinne ist das Fehlen der Möglichkeit, einen trivialen Standardkonstruktor zu definieren, überhaupt kein Verlust, vielmehr erhöht es die Effizienz bei der Ausführung durch die CLR.  
  
 Problematisch kann es werden, wenn ein Benutzer von Managed Extensions einen nicht\-trivialen Standardkonstruktor definiert.  Für diesen gibt es keine Zuordnung in der neuen Syntax.  Der Code innerhalb des Konstruktors muss dann in eine benannte Initialisierungsmethode migriert werden, die anschließend durch den Benutzer explizit aufgerufen werden muss.  
  
 Im Übrigen ist die Deklaration eines Werttypobjekts in der neuen Syntax unverändert.  Andererseits sind dadurch Werttypen zum Umschließen systemeigener Typen aus den folgenden Gründen nur unzureichend geeignet:  
  
-   Es gibt keine Unterstützung für einen Destruktor innerhalb eines Werttyps.  Das bedeutet, dass es keine Möglichkeit gibt, am Ende der Lebensdauer eines Objekts automatisch eine Reihe von Aktionen auszulösen.  
  
-   Eine systemeigene Klasse kann nur in einem verwalteten Typ als Zeiger enthalten sein, der dann auf dem systemeigenen Heap zugeordnet wird.  
  
 Eine kleine systemeigene Klasse wird besser mit einem Werttyp umschlossen als mit einem Referenztyp, um eine doppelte Reservierung auf dem Heap zu vermeiden: Für den systemeigenen Typ auf dem systemeigenen Heap und für den verwalteten Wrapper auf dem CLR\-Heap.  Durch das Umschließen einer systemeigenen Klasse mit einem Werttyp können Sie die Reservierung auf dem verwalteten Heap vermeiden, der Speicher auf dem systemeigenen Heap wird jedoch nicht automatisch freigegeben.  Referenztypen sind die einzigen verwalteten Typen, mit denen nicht\-triviale systemeigene Klassen umschlossen werden können.  
  
## Innere Zeiger  
 Die oben genannten `Form (2)` und `Form (3)` können nahezu alles adressieren \(d. h. alles, was verwaltet oder systemeigen ist\).  Deshalb sind in Managed Extensions alle folgenden Beispiele zulässig:  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
  
V v = { 0 };  // Form (1)  
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
  
 Somit kann ein `V*` einen Speicherort innerhalb eines lokalen Blocks adressieren \(ein "hängender" Zeiger\), auf globaler Gültigkeitsebene, innerhalb des systemeigenen Heaps \(z. B., wenn das adressierte Objekt bereits gelöscht wurde\), innerhalb des CLR\-Heaps \(weshalb es verfolgt wird, falls es durch die Garbage Collection verschoben wird\) und innerhalb eines Verweisobjekts auf dem CLR\-Heap \(wo es als so genannter innerer Zeiger ebenfalls transparent verfolgt wird\).  
  
 In Managed Extensions gibt es keine Möglichkeit, die systemeigenen Aspekte eines `V*` voneinander zu trennen; d. h., es wird inklusiv behandelt, womit der Möglichkeit, ein Objekt oder ein Unterobjekt auf dem verwalteten Heap zu adressieren, Rechnung getragen wird.  
  
 In der neuen Syntax werden Werttypzeiger in zwei Typen unterteilt: `V*`, das auf nicht\-CLR\-Heap\-Speicherorte beschränkt ist, und der interne Zeiger `interior_ptr<V>`, der eine Adresse auf dem verwalteten Heap unterstützt, aber nicht erfordert.  
  
```  
// may not address within managed heap   
V *pv = 0;   
  
// may or may not address within managed heap  
interior_ptr<V> pvgc = nullptr;   
```  
  
 `Form (2)` und `Form (3)` der Managed Extensions sind `interior_ptr<V>` zugeordnet.  `Form (4)` ist ein Trackinghandle.  Es adressiert das gesamte Objekt, das innerhalb des verwalteten Heaps geschachtelt worden ist.  Es wird in der neuen Syntax in ein `V^` übersetzt.  
  
```  
V^ pvbx = nullptr; // __box V* pvbx = 0;    
```  
  
 Alle folgenden Deklarationen in Managed Extensions sind in der neuen Syntax inneren Zeigern zugeordnet. \(Es handelt sich um Werttypen innerhalb des `System`\-Namespaces.\)  
  
```  
Int32 *pi;   // => interior_ptr<Int32> pi;  
Boolean *pb; // => interior_ptr<Boolean> pb;  
E *pe;       // => interior_ptr<E> pe; // Enumeration  
```  
  
 Die integrierten Typen werden nicht als verwaltete Typen betrachtet, obwohl sie als Aliase für die Typen im `System`\-Namespace dienen.  Somit gelten die folgenden Zuordnungen sowohl in Managed Extensions als auch in der neuen Syntax:  
  
```  
int * pi;     // => int* pi;  
int __gc * pi2; // => interior_ptr<int> pi2;  
```  
  
 Beim Übersetzen eines `V*` in einem bestehenden Programm besteht die konservativste Strategie darin, es immer in einen `interior_ptr<V>` umzuwandeln.  Dies entspricht der Behandlung unter Managed Extensions.  In der neuen Syntax hat ein Programmierer statt des internen Zeigers die Option, einen Werttyp mit `V*` auf Adressen des nicht\-verwalteten Heaps zu beschränken.  Wenn Sie beim Übersetzen des Programms einen transitiven Schluss all seiner Verwendungen erreichen können und sicher sein können, dass sich im verwalteten Heap keine zugeordnete Adresse befindet, können Sie es als `V*` belassen.  
  
## Feste Zeiger  
 Der Garbage Collector kann Objekte, die sich auf dem CLR\-Heap befinden, wahlweise an andere Speicherorte innerhalb des Heaps verschieben. Dies geschieht normalerweise während einer Komprimierungsphase.  Eine solche Verschiebung ist für Trackinghandles, Nachverfolgungsverweise und innere Zeiger unproblematisch, da diese Entitäten transparent aktualisiert werden.  Problematisch wird diese Verschiebung jedoch, wenn der Benutzer die Adresse eines Objekts auf dem CLR\-Heap außerhalb der Laufzeitumgebung übergeben hat.  In diesem Fall führt die flüchtige Verschiebung des Objekts wahrscheinlich zu einem Laufzeitfehler.  Um Objekte wie diese vor einer Verschiebung zu schützen, müssen wir sie an ihrem Speicherort lokal fixieren, sofern sie außerhalb verwendet werden.  
  
 In Managed Extensions wird ein *fester Zeiger* deklariert, indem eine Zeigerdeklaration mit dem `__pin`\-Schlüsselwort qualifiziert wird.  Es folgt ein leicht abgewandeltes Beispiel der Managed Extensions\-Spezifikation:  
  
```  
__gc struct H { int j; };  
  
int main()   
{  
   H * h = new H;  
   int __pin * k = & h -> j;  
  
   // …  
};  
```  
  
 Im neuen Sprachdesign werden feste Zeiger syntaktisch analog zu internen Zeigern deklariert.  
  
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
  
   // …  
}  
```  
  
 In der neuen Syntax ist ein fester Zeiger ein Sonderfall eines inneren Zeigers.  Die ursprünglichen Einschränkungen für feste Zeiger bleiben erhalten.  Sie können z. B. nicht als Parameter oder als Rückgabetyp einer Methode verwendet werden; sie können nur für ein lokales Objekt deklariert werden.  Allerdings wurden in der neuen Syntax eine Reihe zusätzlicher Einschränkungen hinzugefügt.  
  
 Der Standardwert eines festen Zeigers ist `nullptr`, nicht `0`.  Ein `pin_ptr<>` kann nicht mit `0` initialisiert werden. Auch kann ihm dieser Wert nicht zugewiesen werden.  Alle Zuweisungen von `0` in vorhandenem Code müssen in `nullptr` geändert werden.  
  
 Unter Managed Extensions durfte ein fester Zeiger ein gesamtes Objekt adressieren, wie im folgenden Beispiel der Managed Extensions\-Spezifikation:  
  
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
  
 In der neuen Syntax wird das Fixieren des ganzen, vom `new`\-Ausdruck zurückgegebenen Objekts nicht unterstützt.  Stattdessen muss die Adresse des inneren Members fixiert werden.  Beispiel:  
  
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
  
## Siehe auch  
 [Werttypen und ihr Verhalten \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)   
 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)