---
title: "Umwandlungsnotation und Einführung in Safe_cast&lt; &gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- casting
- C-style casts and /clr, motivation for new cast notation
- safe_cast keyword [C++]
ms.assetid: 4eb1d000-3b93-4394-a37b-8b8563f8dc4d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 80d1a6e8b1a1691b4e76bfdc1232c95c22d01408
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cast-notation-and-introduction-of-safecastltgt"></a>Umwandlungsnotation und Einführung von "safe_cast"&lt;&gt;
Die Umwandlungsnotation hat gegenüber Managed Extensions für C++ in Visual C++ geändert.  
  
 Ändern einer vorhandenen Struktur umfasst eine unterschiedlich und schwieriger als das Erstellen der ursprünglichen Struktur. Es gibt weniger Freiheitsgrade, und die Lösung tendiert einen Kompromiss zwischen einem idealen Umstrukturierung und was bei Berücksichtigung der vorhandenen strukturellen Abhängigkeiten durchführbar ist.  
  
 Erweiterung der Sprache ist ein weiteres Beispiel. Als objektorientierte Programmierung ein wichtiger Paradigma wurde, wurde die Notwendigkeit für eine Verweisklasse als typsicherer-Funktion in der C++ zurück in den frühen 1990ern drücken. Downcasting ist der Benutzer explizite Konvertierung einer Basisklasse Zeiger oder Verweis auf einen Zeiger oder Verweis von einer abgeleiteten Klasse. Downcasting ist eine explizite Umwandlung erforderlich. Der Grund hierfür ist, dass der tatsächliche Typ des Zeigers Basisklasse einen Aspekt der Laufzeit ist; aus diesem Grund kann der Compiler nicht überprüfen. Oder um, die zu formulieren, erfordert eine Verweisklasse Einrichtung, genau wie einen virtuellen Funktionsaufruf, eine Form der dynamische Auflösung. Dies löst zwei Fragen:  
  
-   Warum sollte eine Umwandlung in die objektorientierte Paradigma nicht erforderlich? Ist der nicht Mechanismus der virtuellen Funktion ausreichend? D. h. behaupten kann nicht warum eine, dass eine Umwandlung (oder eine Umwandlung irgendeiner Art) müssen einen Entwurf handelt?  
  
-   Warum sollten Unterstützung für eine Verweisklasse in C++ ein Problem werden? Nachdem alle, es ist kein Problem in objektorientierten Sprachen wie z. B. Smalltalk (oder später, Java und c#)? Was ist C++, die macht Ihre Unterstützung einer Verweisklasse Einrichtung schwierig?  
  
 Eine virtuelle Funktion stellt einen allgemeine typabhängige-Algorithmus für eine Familie von Typen dar. (Es werden nicht unter Berücksichtigung der Schnittstellen, die in ISO C++ nicht unterstützt, jedoch stehen im CLR-Programmierung und die Alternative Entwurf interessante darstellen). Das Design dieser Familie ist in der Regel von einer Klassenhierarchie dargestellt in dem es eine abstrakte Basisklasse ist, deklarieren die allgemeine Schnittstelle (den virtuellen Funktionen) und einen Satz von konkrete abgeleitete Klassen, die die tatsächlichen Familie Typen in der Anwendung darstellen Domäne.  
  
 Ein `Light` Hierarchie in einer generierten Bilder CGI (Computer) Anwendungsdomäne, z. B. haben dieselben Attribute wie z. B. `color`, `intensity`, `position`, `on`, `off`und so weiter. Eine kann mehrere Leuchten steuern, über die allgemeine Schnittstelle unabhängig von, ob eine bestimmte eine Spotlight, eine direktionale, eine hell nicht direktionale (Reaktionszeiten der Sonne), oder vielleicht ein Streifen Tür Licht leuchtet. Downcasting auf einen bestimmten Light-Typ, der die virtuelle Schnittstelle ist in diesem Fall nicht erforderlich. In einer produktionsumgebung unbedingt jedoch Geschwindigkeit. Eine Verweisklasse kann und jede Methode explizit aufzurufen, wenn dadurch Inlineausführung der Aufrufe ausgeführt werden kann, anstatt Sie mithilfe des Mechanismus der virtuellen.  
  
 Ein Grund für das Verweisklasse in C++ ist den virtuelle Mechanismus gegen einen erheblichen Leistungsgewinn in Leistung zur Laufzeit zu unterdrücken. (Beachten Sie, dass die Automatisierung von manuellen Optimierung einer aktiven Forschungsbereich ist. Allerdings ist es schwieriger, und Ersetzen Sie dabei die ausdrückliche Verwendung von gelöst der `register` oder `inline` Schlüsselwort.)  
  
 Ein zweiter Grund für Downcasting liegt außerhalb des gültigen dualer Aufbau von Polymorphie. Eine Möglichkeit, die von Polymorphie ist in ein paar passiven und dynamische Formulare unterteilt wird.  
  
 Ein virtueller Aufruf (und eine Verweisklasse Einrichtung) darstellt dynamische Verwendungen von Polymorphie: eine führt eine Aktion basierend auf den tatsächlichen Typ des Zeigers Basisklasse auf diese spezielle Instanz der Ausführung des Programms.  
  
 Ein abgeleitetes Klassenobjekt seiner Basisklassenzeiger zuweisen, ist jedoch eine passive Form der Polymorphie. Es wird die Polymorphie als Transportmechanismus verwendet. Dies ist die haupteinsatzmöglichkeit `Object`, z. B. in vorab generische CLR-Programmierung. Wenn Passiv verwendet, bietet der Basisklasse Zeiger ausgewählt für Transport und Speicherung in der Regel eine Schnittstelle, die zu abstrakt ist. `Object`, z. B. bietet ungefähr fünf Methoden über die Schnittstelle; jedes spezifische Verhalten erfordert eine explizite Umwandlung. Z. B. wenn wir den Winkel des unsere Spotlight oder der Rate der fallen off anpassen möchten, würden wir umgewandelt explizit haben. Eine virtuelle Schnittstelle innerhalb einer Familie von Untertypen nicht Untertypen eine Obermenge aller möglichen Methoden der vielen untergeordneten, und daher eine Verweisklasse Funktion immer benötigt werden innerhalb einer objektorientierten Programmiersprachen.  
  
 Wenn eine Verweisklasse Safe ist Facility in eine objektorientierte Sprache erforderlich, und warum C++ so lange dauert einen hinzufügen? Das Problem wird wie die Informationen bezüglich der Laufzeittyp des Zeigers verfügbar zu machen. Im Fall einer virtuellen Funktion wird die Laufzeitinformationen in zwei Teilen durch den Compiler einrichten:  
  
-   Das Klassenobjekt enthält einen zusätzliche virtuelle Tabelle Zeiger-Member (entweder am Anfang oder Ende des Klassenobjekts; die verfügt über eine interessante Verlauf in sich selbst), die die entsprechende virtuelle Tabelle behandelt. Z. B. Adressen Spotlight-Objekt, eine virtuelle Spotlight-Tabelle, ein gerichtetes Licht, direktionale hell virtuelle Tabelle usw.  
  
-   Jede virtuelle Funktion verfügt über eine zugeordnete feste Slot in der Tabelle, und die tatsächliche Instanz zum Aufrufen durch die Adresse, die in der Tabelle gespeicherten dargestellt wird. Z. B. das virtuelle `Light` Destruktor möglicherweise Einschubfach 0 (null) zugeordnet werden `Color` mit slot 1 und so weiter. Dies ist eine effizient, wenn unflexibel Strategie, da er zum Zeitpunkt der Kompilierung festgelegt ist, und stellt einen minimalen Aufwand dar.  
  
 Das Problem ist, wie Sie die Typinformationen für den Zeiger verfügbar gemacht werden kann, ohne die Größe der C++-Zeiger, entweder indem Sie eine zweite Adresse hinzufügen oder indem Sie direkt irgendeine der Codierung des Typs. Dies würde nicht zulässig, diese Programmierer (und Programme) sein, die nicht das Paradigma objektorientierte - verwenden weiterhin die vorherrschende Benutzercommunity war möchten. Eine weitere Möglichkeit zum Einfügen eines speziellen Zeigers für polymorphe Klassentypen wurde, aber dies verwirrend sein, und der beiden, insbesondere hinsichtlich der Zeigerarithmetik erschweren. Dies würde auch nicht zulässig, eine Tabelle zur Laufzeit zu verwalten, die ordnet jeden Zeiger mit seinem aktuell zugeordneten Typ, und es dynamisch zu aktualisieren.  
  
 Das Problem ist ein Paar von Benutzercommunitys, die verschiedenen, aber legitime Programmieransätze. Die Lösung muss ein Kompromiss zwischen den zwei Communitys, sodass jeder nicht nur für umsetzbar als jedoch für die Fähigkeit, zusammenarbeiten sein. Dies bedeutet, dass die Lösungen, die von beiden Seiten angeboten werden wahrscheinlich unmöglich ist, und schließlich kleiner als genau Implementieren der Lösung. Die Lösung besteht in der Definition einer polymorphen Klasse: eine polymorphe Klasse ist eine virtuelle Funktion enthält. Eine polymorphe Klasse unterstützt eine dynamische, typsichere Downcasting. Dies löst das Beibehalten der-Zeiger-als Adresse-Problem, da alle polymorphe Klassen dieses zusätzlichen Zeigers-Element, um die zugeordnete virtuelle Tabelle enthalten sind. Die zugeordneten Typinformationen kann daher in einer erweiterten virtuellen Tabellenstruktur gespeichert werden. Die Kosten für die typsichere Downcasting ist für Benutzer der Funktion (fast) lokalisiert.  
  
 Das nächste Problem mit der typsichere Downcasting wurde in der Syntax. Da es sich um eine Umwandlung handelt, verwendet der ursprüngliche Vorschlag die ISO-C++-Committee Umwandlungssyntax, wie in diesem Beispiel:  
  
```  
spot = ( SpotLight* ) plight;  
```  
  
 aber dies wurde durch die Committee zurückgewiesen, weil er nicht, dass den Benutzer zum Kontrollieren der Kosten der Umwandlung zuließ. Verfügt die dynamische, typsichere Downcasting die gleiche Syntax wie zuvor unsafe jedoch statische Umwandlungsnotation, und es wird eine Ersetzung, und der Benutzer hat keine Möglichkeit, die die Laufzeit-Overhead zu unterdrücken, wenn es nicht erforderlich und möglicherweise zu teuer ist.  
  
 Im Allgemeinen in C++ ist es immer ein Mechanismus, mit dem Compiler unterstützten Funktionen zu unterdrücken. Beispielsweise können wir virtuelle Mechanismus deaktivieren, indem Sie entweder mit der Klasse Bereichsoperator (`Box::rotate(angle)`), oder rufen die virtuelle Methode über ein Klassenobjekt (statt einem Zeiger oder Verweis von dieser Klasse). Dieses zweite Unterdrückung ist nicht erforderlich, von der Programmiersprache jedoch ist ein Qualität der Implementierungsproblem, ähnlich wie die Unterdrückung der Konstruktion eines temporären in einer Deklaration des Formulars:  
  
```  
// compilers are free to optimize away the temporary  
X x = X::X( 10 );  
```  
  
 Damit Vorschlag wieder für weitere Überlegung verfügten, und mehrere alternative Notationen berücksichtigt wurden und die zurück an den Ausschuss geschaltet des Formulars war (`?type`), dem angegebenen unbestimmt -, also der dynamischen Natur. Dies führte zu dem Benutzer die Möglichkeit zum Umschalten zwischen den beiden Formaten - statische oder dynamische - aber niemand zu zufrieden wurde. Damit sie wieder zum Zeichnen Board war. Die dritte und erfolgreiche Notation ist jetzt standard `dynamic_cast<type>`, die auf einen Satz von vier neue Formatvorlage Umwandlungsnotationen generalisiert wurde.  
  
 In ISO-C++- `dynamic_cast` gibt `0` Wenn auf einen falschen Zeigertyp angewendet, und löst eine `std::bad_cast` Ausnahme bei Anwendung auf einen Referenztyp darstellt. In Managed Extensions for C++ Anwenden von `dynamic_cast` in eine verwaltete Verweise (aufgrund der Darstellung als Zeiger) immer zurückgegebenen Typ `0`. `__try_cast<type>`Analog eingeführt wurde, auf die Ausnahme auslösen Variante des der `dynamic_cast`, außer dass es löst `System::InvalidCastException` schlägt die Umwandlung fehl.  
  
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
  
 In der neuen Syntax `__try_cast` wurde als Nachrichtenfilter wurde `safe_cast`. Hier ist das gleiche Codefragment in der neuen Syntax:  
  
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
  
 In der verwalteten Umgebung ist es wichtig, um zu ermöglichen, indem Sie die Möglichkeit Programmierer mit sich bringen, die Umwandlung zwischen Typen in Methoden, die den Code nicht überprüfbaren verlassen einschränken überprüfbaren Code. Dies ist ein wichtiger Aspekt der dynamischen Programmierparadigma, dargestellt durch die neue Syntax. Aus diesem Grund Instanzen von Umwandlungen im alten Stil sind Nachrichtenfilter intern als zur Laufzeit Umwandlungen, also, beispielsweise:  
  
```  
// internally recast into the   
// equivalent safe_cast expression above  
( array<ItemVerb^>^ ) verbList->ToArray( ItemVerb::typeid );   
```  
  
 Da Polymorphie einer aktiven und passiven Modus bietet, ist es hingegen, manchmal erforderlich, um eine Verweisklasse nur zum Zugriff auf die nicht virtuelle API eines Untertyps auszuführen. Dieses Problem kann auftreten, z. B. mit die Mitglieder einer Klasse, die den Adresse alle Typen innerhalb der Hierarchie (passive Polymorphie als Transportmechanismus), aber für die die aktuelle Instanz in einem bestimmten Programmkontext bekannt ist. In diesem Fall möglich müssen eine Überprüfung zur Laufzeit die Umwandlung einen unzulässigen Aufwand. Ist die neue Syntax als die Programmiersprache verwalteten Systemen verwendet werden, müssen sie Möglichkeiten zum Zulassen einer Kompilierung bereitstellen (d. h. statische) umgewandelt. Diesem Grund wird die Anwendung von der `static_cast` Notation ist eine Verweisklasse Kompilierzeit bleiben zulässig:  
  
```  
// ok: cast performed at compile-time.   
// No run-time check for type correctness  
static_cast< array<ItemVerb^>^>(verbList->ToArray(ItemVerb::typeid));  
```  
  
 Das Problem besteht darin, dass es keine Möglichkeit zu gewährleisten, dass den Programmierer die `static_cast` ist richtig und Exploit; d. h. Es gibt keine Möglichkeit zum Erzwingen von verwalteten Codes zu überprüfbar zu sein. Dies geht dringenderen gemäß dem Programmierparadigma dynamische als bei systemeigenem Code, aber ist nicht ausreichend innerhalb eines Systems Programmiersprache, die Benutzer zu unterbinden, die Möglichkeit, zwischen einer statischen und zur Laufzeit umgewandelt zu wechseln.  
  
 Es ist ein Trap für Leistung und Fehlers in der neuen Syntax, jedoch. In systemeigene Programmierung besteht kein Leistungsunterschied zwischen der Umwandlungsnotation im alten Stil und die neue Formatvorlage `static_cast` Notation. In der neuen Syntax der im alten Stil Umwandlungsnotation ist deutlich teurer als die Verwendung des neuen Formats jedoch `static_cast` Notation. Der Grund ist, dass der Compiler intern die Verwendung der im alten Stil Notation in eine laufzeitüberprüfung transformiert, die eine Ausnahme auslöst. Darüber hinaus wird auch geändert das Ausführungsprofil des Codes, da er bewirkt, dass eine nicht abgefangene Ausnahme, die der Anwendung – vielleicht mit Bedacht zu schalten, aber der gleiche Fehler würde nicht, wird diese Ausnahme aus, wenn die `static_cast` Notation verwendet wurden. Eine möglicherweise argumentieren, dass auf diese Weise werden Benutzer in der Verwendung der neuen-Schreibweise. Aber nur, wenn ein Fehler auftritt. Es wird hingegen bewirken, dass Programme mit der im alten Stil Notation eventuell deutlich langsamer ohne sichtbar zu verstehen und einen Grund ausgeführt der ersichtlichen ähnelt:  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine Sprachänderungen (C + c++ / CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [C-stilartige Umwandlungen mit/CLR (C + c++ / CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)   
 ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md)