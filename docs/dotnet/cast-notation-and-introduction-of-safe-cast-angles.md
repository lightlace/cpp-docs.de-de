---
title: "Umwandlungsnotation und Einf&#252;hrung in safe_cast&lt;&gt;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Umwandlung von Typen"
  - "C-stilartige Umwandlungen und /clr, Motive für neue Umwandlungsnotation"
  - "safe_cast-Schlüsselwort [C++]"
ms.assetid: 4eb1d000-3b93-4394-a37b-8b8563f8dc4d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Umwandlungsnotation und Einf&#252;hrung in safe_cast&lt;&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Umwandlungsnotation hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Das Ändern einer vorhandenen Struktur ist vollkommen anders und wesentlich schwieriger als das Erstellen der ursprünglichen Struktur,  bei dem der Entwickler über eine viel größere Freiheit verfügt. Die Lösung stellt immer einen Kompromiss zwischen einer idealen Restrukturierung und den praktischen Gegebenheiten dar, die durch die vorhandenen strukturellen Abhängigkeiten festgelegt werden.  
  
 Ein weiteres Beispiel dafür stellen Spracherweiterungen dar.  In den frühen 90er Jahren, als die objektorientierte Programmierung zu einem wichtigen Paradigma aufstieg, wurde ein typsicherer Downcastmechanismus für C\+\+ erforderlich.  Als Downcasting wird die explizite Umwandlung eines Basisklassenzeigers oder einer Basisklassenreferenz in einen Zeiger oder eine Referenz einer abgeleiteten Klasse durch den Benutzer bezeichnet.  Downcasting erfordert eine explizite Umwandlung.  Der Grund liegt darin, dass der aktuelle Typ des Basisklassenzeigers ein Aspekt der Laufzeit ist. Daher kann der Compiler den Typ nicht überprüfen.  Anders gesagt, ist für einen Downcastmechanismus genau wie für einen virtuellen Funktionsaufruf eine Form von dynamischer Auflösung erforderlich.  Dies wirft zwei Fragen auf:  
  
-   Warum ist Downcasting im objektorientierten Paradigma notwendig?  Ist der virtuelle Funktionsmechanismus nicht ausreichend?  Mit anderen Worten: Warum ist es falsch, zu behaupten, dass der Bedarf an Downcasting \(oder jeder Art von Umwandlung\) durch einen Designfehler entsteht?  
  
-   Warum sollte die Unterstützung für Downcasting in C\+\+ ein Problem darstellen?  Schließlich stellt dies in objektorientierten Sprachen wie Smalltalk \(oder auch Java und C\#\) kein Problem dar.  Was ist das Besondere an C\+\+, das die Unterstützung eines Downcastmechanismus so kompliziert macht?  
  
 Eine virtuelle Funktion stellt einen typabhängigen und für eine Familie von Typen üblichen Algorithmus dar. \(Dies bezieht sich nicht auf Schnittstellen, die von ISO\-C\+\+ nicht unterstützt werden, jedoch bei der CLR\-Programmierung verfügbar sind und eine interessante Designalternative darstellen.\)  Das Design dieser Familie wird üblicherweise durch eine Klassenhierarchie repräsentiert, die eine abstrakte Basisklasse mit der Definition der gemeinsamen Schnittstelle \(den virtuellen Funktionen\) sowie einen Satz konkreter, abgeleiteter Klassen enthält, die die aktuellen Typen der Familien in der Anwendungsdomäne darstellen.  
  
 So verfügt z. B. eine `Light`\-Hierarchie in einer CGI \(Computer Generated Imagery\)\-Anwendungsdomäne über gemeinsame Attribute wie `color`, `intensity`, `position`, `on`, `off` usw.  Man kann eine Reihe von Lampen über die gemeinsame Schnittstelle steuern, ohne sich darum zu kümmern, ob eine bestimmte Lampe ein Scheinwerfer, ein Richtstrahler, eine ungerichtete Lichtquelle \(wie die Sonne\) oder vielleicht eine Scheunentorbeleuchtung ist.  In diesem Fall ist kein Downcasting auf einen bestimmten Lampentyp erforderlich, um die virtuelle Schnittstelle zu verwenden.  In einer Produktionsumgebung kommt es jedoch auf Geschwindigkeit an.  An dieser Stelle könnte man sich für Downcasting entscheiden und jede Methode explizit aufzurufen, wenn man dadurch den Virtualitätsmechanismus umgehen und die Aufrufe inline ausführen kann.  
  
 Ein Grund für die Verwendung von Downcasting in C\+\+ besteht also darin, den Virtualitätsmechanismus zu unterdrücken, um dadurch eine relevante Leistungssteigerung zur Laufzeit zu erzielen. \(Beachten Sie, dass die Automatisierung dieser manuellen Optimierung ein aktiver Forschungsbereich ist.  Dieses Problem kann jedoch nicht gelöst werden, indem einfach die explizite Verwendung des `register`\-Schlüsselworts oder des `inline`\-Schlüsselworts ersetzt wird.\)  
  
 Ein zweiter Grund für Downcasting resultiert aus der dualen Natur der Polymorphie.  Eine Möglichkeit zur Annäherung an die Polymorphie besteht darin, diese als ein passives und ein dynamisches Paar von Formularen zu betrachten.  
  
 Ein virtueller Aufruf \(und ein Downcastmechanismus\) stellt den dynamischen Anwendungsfall der Polymorphie dar: Es wird eine Aktion ausgeführt, die auf dem aktuellen Typ des Basisklassenzeigers in einer bestimmten Instanz zum gegenwärtigen Zeitpunkt der Programmausführung basiert.  
  
 Das Zuweisen eines abgeleiteten Klassenobjekts an den zugehörigen Basisklassenzeiger ist jedoch eine passive Form der Polymorphie. Dabei wird die Polymorphie als Transportmechanismus verwendet.  Dies war beispielsweise in der CLR\-Programmierung der Haupteinsatzzweck von `Object`, bevor die generische CLR\-Programmierung möglich wurde.  Bei passiver Verwendung stellt der für Transport und Speicherung ausgewählte Basisklassenzeiger üblicherweise eine Schnittstelle bereit, die zu abstrakt ist.  So bietet z. B. `Object` über seine Schnittstelle ungefähr fünf Methoden. Wenn ein spezifischeres Verhalten gewünscht wird, ist explizites Downcasting erforderlich.  Um beispielsweise den Winkel oder den Lichtabfall eines Scheinwerfers zu ändern, müsste explizites Downcasting ausgeführt werden.  Es ist praktisch unmöglich, dass eine virtuelle Schnittstelle innerhalb einer Familie von Untertypen eine Obermenge aller möglichen Methoden der vielen untergeordneten Typen darstellt. Aus diesem Grund wird auch in einer objektorientierten Sprache immer ein Downcastmechanismus benötigt.  
  
 Wenn eine objektorientierte Sprache einen sicheren Downcastmechanismus benötigt, warum hat es so lange gedauert, bis C\+\+ einen entsprechenden Mechanismus erhielt?  Das Problem besteht darin, die Information bezüglich des Typs, den der Zeiger zur Laufzeit hat, zur Verfügung zu stellen.  Im Fall einer virtuellen Funktion werden die Laufzeitinformationen vom Compiler in zwei Teilen festgelegt:  
  
-   Das Klassenobjekt enthält einen zusätzlichen virtuellen Tabellenzeigermember \(entweder am Anfang oder am Ende des Klassenobjekts, was auch eine interessante Frage ist\), der auf die richtige virtuelle Tabelle verweist.  So verweist ein Scheinwerferobjekt auf die virtuelle Tabelle eines Scheinwerfers, ein Richtstrahler verweist auf eine virtuelle Tabelle eines Richtstrahlers usw.  
  
-   Jede virtuelle Funktion ist mit einer festen Position in der Tabelle verknüpft, und in der Tabelle ist eine Adresse gespeichert, die auf die aktuell aufzurufende Instanz verweist.  So könnte z. B. der virtuelle `Light`\-Destruktor mit Position 0 verknüpft sein, `Color` mit Position 1 usw.  Obwohl unflexibel, ist diese Strategie sehr effizient, da sie zur Kompilierzeit eingerichtet wird und nur minimalen Aufwand erzeugt.  
  
 Das Problem besteht nun darin, wie die Typinformation für den Zeiger verfügbar gemacht werden kann, ohne dass die Größe der C\+\+\-Zeiger geändert werden muss. Dazu kann entweder eine zweite Adresse oder eine Form der Typcodierung hinzugefügt werden.  Dies wäre für diejenigen Programmierer \(und Programme\) nicht akzeptabel gewesen, die weiterhin auf das objektorientierte Programmierparadigma verzichteten, was immerhin noch die Mehrheit der Benutzergemeinde betraf.  Eine andere Möglichkeit bestand in der Einführung eines speziellen Zeigers für polymorphe Klassentypen, aber das wäre verwirrend gewesen und hätte die gemeinsame Verwendung der beiden Zeigertypen verkompliziert, insbesondere hinsichtlich der Zeigerarithmetik.  Die Verwaltung einer Laufzeittabelle, die jeden Zeiger mit seinem aktuell zugeordneten Typ verknüpft, und die dynamische Aktualisierung dieser Tabelle wäre ebenso wenig akzeptabel gewesen.  
  
 Das Problem besteht also in zwei unterschiedlichen Benutzercommunitys, die verschiedene, aber nichtsdestotrotz legitime Programmieransätze verfolgen.  Die Lösung musste demnach ein Kompromiss zwischen beiden Communitys sein, wobei nicht nur jeder Ansatz umsetzbar sein sollte, sondern auch Interoperabilität zwischen beiden Ansätzen gewährleistet werden musste.  Dies bedeutete, dass die von beiden Seiten angebotenen Lösungen wahrscheinlich nicht durchsetzbar waren und die letztendlich implementierte Lösung vermutlich keine perfekte Lösung darstellen würde.  Die Lösung besteht in der Definition einer polymorphen Klasse: eine polymorphe Klasse enthält eine virtuelle Funktion.  Eine polymorphe Klasse unterstützt dynamisches, typsicheres Downcasting.  Auf diese Weise wird das Problem der Verwaltung des Zeigers als Adresse gelöst, da alle polymorphen Klassen den zusätzlichen Zeigermember enthalten, der auf die zugeordnete virtuelle Tabelle verweist.  Daher kann die zugeordnete Typinformation in einer erweiterten virtuellen Tabellenstruktur gespeichert werden.  Der Aufwand für typsicheres Downcasting entsteht \(fast\) ausschließlich für die Benutzer der Funktion.  
  
 Die Syntax stellte das nächste Problem beim typsicheren Downcasting dar.  Da es sich um eine Umwandlung handelt, wurde im ursprünglichen Vorschlag an das ISO\-C\+\+\-Komitee die reine Umwandlungssyntax verwendet, wie im folgenden Beispiel:  
  
```  
spot = ( SpotLight* ) plight;  
```  
  
 Der Vorschlag wurde jedoch vom Komitee abgelehnt, da der Benutzer auf diese Weise den mit der Umwandlung verbundenen Aufwand nicht beeinflussen konnte.  Wenn das dynamische, typsichere Downcasting über dieselbe Syntax wie die früher verwendete unsichere, aber statische Umwandlung verfügt, wird es lediglich zu einer Ersetzung, und der Benutzer hat keine Möglichkeit, den Aufwand zur Laufzeit zu unterdrücken, wenn dieser überflüssig und zu hoch ist.  
  
 Es gibt in C\+\+ im Allgemeinen immer einen Mechanismus, um die vom Compiler unterstützten Funktionen zu unterdrücken.  Man kann z. B. den Virtualitätsmechanismus deaktivieren, indem man entweder den Klassenbereichsoperator verwendet \(`Box::rotate(angle)`\) oder die virtuelle Methode über ein Klassenobjekt \(statt über einen Zeiger oder eine Referenz dieser Klasse\) aufruft.  Die letztere Variante wird von der Sprache nicht vorausgesetzt, sondern ist eine Frage der Implementierung, ähnlich wie bei der Konstruktionsunterdrückung eines temporären Objekts in einer Deklaration mit folgender Form:  
  
```  
// compilers are free to optimize away the temporary  
X x = X::X( 10 );  
```  
  
 Der Vorschlag wurde also zur Überarbeitung zurückgezogen, und es wurde eine Reihe alternativer Notationen in Betracht gezogen. Schließlich wurde dem Komitee ein neuer Vorschlag mit der Form \(`?type`\) unterbreitet, der die unbestimmte, also die dynamische Natur widerspiegelte.  Damit erhielt der Benutzer die Möglichkeit, zwischen der statischen und der dynamischen Form zu wählen, aber niemand war damit wirklich zufrieden.  Deshalb ging der Vorschlag zurück ans Reißbrett.  Die dritte und schließlich erfolgreiche Notation ist der jetzige Standard `dynamic_cast<type>`, der zu einem Satz von vier neuartigen Umwandlungsnotationen verallgemeinert wurde.  
  
 In ISO\-C\+\+ liefert `dynamic_cast` den Wert `0` zurück, wenn es auf einen falschen Zeigertyp angewendet wird, und bei Anwendung auf einen Referenztyp wird eine `std::bad_cast`\-Ausnahme ausgelöst.  In Managed Extensions for C\+\+ wurde bei der Anwendung von `dynamic_cast` auf einen verwalteten Referenztyp \(aufgrund der Darstellung als Zeiger\) immer `0` zurückgegeben.  `__try_cast<type>` wurde analog zu der Variante von `dynamic_cast` eingeführt, die eine Ausnahme auslöst, mit dem Unterschied, dass eine `System::InvalidCastException` ausgelöst wird, wenn die Umwandlung fehlschlägt.  
  
```  
public __gc class ItemVerb;  
public __gc class ItemVerbCollection {  
public:  
   ItemVerb *EnsureVerbArray() [] {  
      return __try_cast<ItemVerb *[]>  
         (verbList->ToArray(__typeof(ItemVerb *)));  
   }  
};  
```  
  
 In der neuen Syntax wurde `__try_cast` zu `safe_cast` umgeformt.  Hier ist das gleiche Codefragment in der neuen Syntax:  
  
```  
public ref class ItemVerb;  
public ref class ItemVerbCollection {  
public:  
   array<ItemVerb^>^ EnsureVerbArray() {  
      return safe_cast<array<ItemVerb^>^>  
         ( verbList->ToArray( ItemVerb::typeid ));  
   }  
};  
```  
  
 In der verwalteten Welt ist es wichtig, die Erstellung von verifizierbarem Code zu unterstützen, indem die Möglichkeiten der Programmierer eingeschränkt werden, Typumwandlungen durchzuführen, die den Code nicht mehr verifizierbar machen.  Dies ist ein wichtiger Aspekt des dynamischen Programmierparadigmas, das die neue Syntax darstellt.  Aus diesem Grund werden Instanzen von Umwandlungen im alten Stil intern zu Laufzeitumwandlungen umgeformt. Beispiel:  
  
```  
// internally recast into the   
// equivalent safe_cast expression above  
( array<ItemVerb^>^ ) verbList->ToArray( ItemVerb::typeid );   
```  
  
 Da die Polymorphie jedoch sowohl einen aktiven als auch einen passiven Modus bietet, ist es andererseits gelegentlich unumgänglich, Downcasting anzuwenden, um Zugang zu der nicht\-virtuellen API eines Untertyps zu erlangen.  Dies kann z. B. für die Member einer Klasse erforderlich werden, die auf alle Typen innerhalb der Hierarchie zugreifen möchten \(passive Polymorphie als Transportmechanismus\), für die jedoch die aktuelle Instanz in einem bestimmten Programmkontext bekannt ist.  In diesem Fall könnte die Überprüfung der Umwandlung zur Laufzeit als nicht akzeptabler Aufwand betrachtet werden.  Damit die neue Syntax zur Programmiersprache des verwalteten Systems werden kann, muss sie in irgendeiner Weise Downcasting zur Kompilierzeit ermöglichen, also statisches Downcasting.  Daher ist die Anwendung der `static_cast`\-Notation weiterhin als Downcasting zur Kompilierzeit gültig:  
  
```  
// ok: cast performed at compile-time.   
// No run-time check for type correctness  
static_cast< array<ItemVerb^>^>(verbList->ToArray(ItemVerb::typeid));  
```  
  
 Das Problem besteht darin, dass es keine Möglichkeit gibt zu garantieren, dass der Programmierer mit der Ausführung eines `static_cast` richtig liegt, und dass diese statische Umwandlung korrekt ist. Es besteht also keine Möglichkeit, die Verifizierbarkeit von verwaltetem Code zu erzwingen.  Dies stellt im dynamischen Programmierparadigma ein größeres Problem dar als bei systemeigenem Code. Es reicht jedoch nicht aus, einem Benutzer innerhalb einer Systemprogrammiersprache die Möglichkeit zum Umschalten zwischen der statischen Umwandlung und der Umwandlung zur Laufzeit zu verwehren.  
  
 Die neue Syntax enthält jedoch auch eine Leistungsfalle und einen Stolperstrick.  Beim systemeigenen Programmieren besteht kein Leistungsunterschied zwischen der Umwandlungsnotation im alten Stil und der neuen `static_cast`\-Notation.  In der neuen Syntax ist die Umwandlungsnotation im alten Stil jedoch wesentlich aufwändiger als die Verwendung der neuen `static_cast`\-Notation,  da der Compiler die Notation im alten Stil intern in eine Laufzeitüberprüfung umwandelt, die eine Ausnahme auslöst.  Darüber hinaus wird dadurch auch das Ausführungsprofil des Codes geändert, da die resultierende Ausnahme nicht abgefangen wird, was zur Beendigung der Anwendung führt. Dies ist durchaus sinnvoll, allerdings würde derselbe Fehler bei Verwendung der `static_cast`\-Notation keine Ausnahme auslösen.  Man könnte nun argumentieren, dass die Benutzer auf diese Weise dazu gezwungen werden, die neue Syntax zu verwenden.  Dies ist jedoch nur der Fall, wenn die Ausführung eines Programms fehlschlägt. Andernfalls würden Programme, in denen die Notation im alten Stil verwendet wird, ohne ersichtlichen Grund wesentlich langsamer ausgeführt werden. Ähnliches gilt für die folgenden Stolperstricke für C\-Programmierer:  
  
```  
// pitfall # 1:   
// initialization can remove a temporary class object,   
// assignment cannot  
Matrix m;  
m = another_matrix;  
  
// pitfall # 2: declaration of class objects far from their use  
Matrix m( 2000, 2000 ), n( 2000, 2000 );  
if ( ! mumble ) return;  
```  
  
## Siehe auch  
 [Allgemeine Sprachänderung](../dotnet/general-language-changes-cpp-cli.md)   
 [C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)   
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)