---
title: Umwandlungsnotation und Einführung von "safe_cast"&lt; &gt; | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- casting
- C-style casts and /clr, motivation for new cast notation
- safe_cast keyword [C++]
ms.assetid: 4eb1d000-3b93-4394-a37b-8b8563f8dc4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 88e8165bde08b65b4f078c4b48863c2088132fca
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427862"
---
# <a name="cast-notation-and-introduction-of-safecastltgt"></a>Umwandlungsnotation und Einführung von "safe_cast"&lt;&gt;

Die Umwandlungsnotation wurde von Managed Extensions für C++ in Visual C++ geändert.

Ändern einer vorhandenen Struktur ist eine Umgebung anders und schwieriger als das Erstellen der ursprünglichen Struktur. Es gibt weniger Freiheitsgrade, und die Lösung wird zumeist auf einen Kompromiss zwischen einer idealen umstrukturieren und was durchführbar ist, erhalten die vorhandenen strukturellen Abhängigkeiten.

Erweiterung der Sprache ist ein weiteres Beispiel. Als objektorientierte Programmierung ein Paradigma wichtig ist, wurde die Notwendigkeit einer Typumwandlung typsichere-Einrichtung in C++ wieder in den frühen 1990er Jahren drücken. Typumwandlung ist der Benutzer explizite Konvertierung einer Basisklasse Zeiger oder Verweis auf einen Zeiger oder Verweis von einer abgeleiteten Klasse. Typumwandlung ist eine explizite Umwandlung erforderlich. Der Grund dafür ist, dass der tatsächliche Typ des Zeigers Basisklasse ein Aspekt der Laufzeit ist. aus diesem Grund kann der Compiler nicht überprüfen. Alternativ dazu können Sie zum formulieren, die Sie neu, erfordert eine Typumwandlung Einrichtung, genau wie einen virtuellen Funktionsaufruf, eine Form von dynamische Auflösung. Dies löst zwei Fragen:

- Warum sollte eine Umwandlung in den objektorientierten Paradigma erforderlich sein? Nicht Mechanismus der virtuellen Funktion reicht aus? Also behaupten kann nicht warum zu, dass Notwendigkeit einer Typumwandlung (oder eine Umwandlung irgendeiner Art) ein Fehler Entwurf ist?

- Warum sollte die Unterstützung für eine Typumwandlung in C++ ein Problem sein? Schließlich ist es möglich, es ist kein Problem in objektorientierten Sprachen wie z. B. Smalltalk (oder später, Java und c#)? Was ist das Informationen über C++, mit der Unterstützung einer Typumwandlung Einrichtung schwierig?

Eine virtuelle Funktion stellt einen allgemeine typabhängige-Algorithmus für eine Reihe von Typen dar. (Wir sind nicht unter Berücksichtigung der Schnittstellen, die ISO-C++-werden nicht unterstützt, jedoch stehen im CLR-Programmierung und die eine interessante Alternative für den Entwurf darstellen). Das Design dieser Familie wird in der Regel durch eine Klassenhierarchie dargestellt in der es eine abstrakte Basisklasse deklarieren ist, die allgemeine Schnittstelle (die virtuellen Funktionen) und einen Satz von konkrete abgeleitete Klassen, die Darstellung der tatsächlichen Familien Typen in der Anwendung die Domäne.

Ein `Light` besitzen-Hierarchie in einen Computer generierten Bilder (CGI), z. B. allgemeine Attribute wie z. B. `color`, `intensity`, `position`, `on`, `off`und so weiter. Eine kann mehrere Lichter, steuern, indem Sie die allgemeine Schnittstelle verwenden, ohne sich Gedanken machen, ob eine bestimmte eine Spotlight, eine direktionale Beleuchtung, eine nicht direktionale (Stellen Sie sich der Sonne), oder vielleicht ein innen nach außen-Tür Licht leuchtet. Typumwandlung in einen bestimmten Light-Typ, der die virtuelle Schnittstelle ist in diesem Fall nicht erforderlich. In einer produktionsumgebung unbedingt jedoch Geschwindigkeit. Eine Typumwandlung möglicherweise und jede Methode explizit aufzurufen, wenn hierfür Inlineausführung Aufrufe ausgeführt werden kann, statt mit dem virtuellen Mechanismus.

Ein Grund für die Typumwandlung in C++ ist den virtuelle Mechanismus als Gegenleistung für einen erheblichen Leistungsgewinn Runtime unterdrückt werden sollen. (Beachten Sie, dass die Automatisierung dieser manuellen Optimierung einen lebendigen Bereich der Forschung. Es ist jedoch schwieriger zu lösen, die explizite Verwendung von ersetzt die `register` oder `inline` Schlüsselwort.)

Ein zweiter Grund eine Umwandlung fällt aus der dualen Natur von Polymorphie. Eine Möglichkeit, Polymorphie betrachten, ist in ein paar passiven und dynamische Formulare unterteilt wird.

Ein virtueller Aufruf (und eine Typumwandlung Einrichtung) stellt dynamische Verwendungen von Polymorphie: eine führt eine Aktion basierend auf der tatsächliche Typ des Zeigers Basisklasse auf diese spezielle Instanz der Ausführung des Programms.

Der Zeiger für die Basisklasse ein abgeleitetes Klassenobjekt zuzuweisen, ist jedoch eine passive Form von Polymorphie. Es wird die Polymorphie als Transportmechanismus verwendet. Dies ist die haupteinsatzmöglichkeit `Object`, z. B. in bereits generische CLR-Programmierung. Wenn Passiv verwendet wird, bietet der Basisklasse Zeiger für den Transport und Speicher ausgewählt sind, in der Regel eine Schnittstelle, die zu abstrakt ist. `Object`, z. B. bietet ungefähr fünf Methoden über die Schnittstelle; spezifischeres Verhalten erfordert eine explizite Typumwandlung. Beispielsweise, wenn wir den Winkel des unserem Spotlight und die Rate der Fall deaktiviert anpassen möchten, müssten eine Umwandlung explizit wir. Eine virtuelle Schnittstelle in eine Familie von Untertypen nicht praktisch eine Obermenge aller möglichen Methoden viele seiner untergeordneten Elemente und daher eine Typumwandlung Funktion immer erforderlich, in eine objektorientierte Sprache.

Wenn eine sichere Typumwandlung ist in einer objektorientierten Sprache Einrichtung erforderlich, und warum C++ so lange gedauert eine hinzufügen? Das Problem ist wie die Informationen bezüglich der Laufzeittyp des Zeigers verfügbar zu machen. Im Fall von einer virtuellen Funktion wird die Laufzeitinformationen in zwei Teile vom Compiler eingerichtet:

- Das Klassenobjekt enthält einen zusätzliche virtuelle Tabelle Zeiger-Member (entweder am Anfang oder Ende des Klassenobjekts; der hat eine interessante Geschichte an sich) adressiert, die entsprechende virtuelle Tabelle. Z. B. behandelt ein Spotlight-Objekt, eine virtuelle Spotlight-Tabelle, eine direktionale Beleuchtung, eine direktionale hell virtuelle Tabelle und usw.

- Jede virtuelle Funktion verfügt über eine zugeordnete festen Position in der Tabelle, und die tatsächliche Instanz zum Aufrufen wird dargestellt, durch die Adresse, die in der Tabelle gespeichert. Z. B. das virtuelle `Light` Destruktor möglicherweise gegen den Slot 0 (null) zugeordneten `Color` mit slot 1 und so weiter. Dies ist eine Strategie für die effiziente, wenn unflexibel, da er zum Zeitpunkt der Kompilierung eingerichtet ist, und einen minimalen Mehraufwand stellt.

Das Problem ist, wie Sie die Typinformationen für den Zeiger verfügbar gemacht werden kann, ohne die Größe der C++-Zeiger ändern, indem Sie eine zweite Adresse oder durch das direkte hinzufügen eine Art der Codierung des Typs. Dies wäre nicht akzeptabel, die Programmierer (und Programme), die nicht den objektorientierten Paradigma - verwenden möchten, das immer noch die Benutzergemeinde wurde. Eine andere Möglichkeit bestand, einen speziellen Zeiger für polymorphe Klassentypen einzuführen, aber dies verwirrend sein, und machen es schwierig, zwischen die beiden, insbesondere hinsichtlich der Zeigerarithmetik zu kombinieren. Es wäre auch nicht akzeptabel, eine Laufzeit-Tabelle zu verwalten, die jeden Zeiger dynamisch aktualisiert wird, und der aktuell zugeordneten Typ zugeordnet.

Das Problem ist ein Paar von Benutzergruppen für die verschiedenen, aber legitime Programmieransätze. Die Lösung muss ein Kompromiss zwischen den zwei Communitys, sodass jeder nicht nur umsetzbar, aber die Möglichkeit, die zusammenarbeiten. Dies bedeutet, dass die Lösungen von beiden Seiten sind wahrscheinlich nicht realisierbar, und zum Schluss der Lösung implementieren nicht immer perfekt sein. Die Lösung besteht in der Definition eine polymorphe Klasse: eine polymorphe Klasse ist eine virtuelle Funktion enthält. Eine polymorphe Klasse unterstützt eine dynamische, typsichere Typumwandlung. Das löst das Problem der Warten-der-Zeiger-als-Adresse, da alle polymorphe Klassen dieses Element zusätzliche Zeiger auf die zugeordnete virtuelle Tabelle enthalten. Die zugeordnete Typinformationen, kann daher in einer erweiterten virtuelle Tabelle gespeichert werden. Die Kosten für die Typumwandlung typsichere ist für Benutzer von der Funktion (fast) lokalisiert.

Das nächste Problem bei der die Typumwandlung typsichere wurde die Syntax. Da es sich um eine Umwandlung ist, verwendet der ursprüngliche Vorschlag dem ISO-C++-Ausschuss der Umwandlungssyntax, wie im folgenden Beispiel aus:

```
spot = ( SpotLight* ) plight;
```

aber dies wurde vom Committee zurückgewiesen, weil es nicht, dass den Benutzer zum Kontrollieren der Kosten für die Typumwandlung zuließ. Verfügt die dynamische typsichere Typumwandlung dieselbe Syntax wie die zuvor verwendete unsichere aber statische Umwandlungsnotation, dann wird als Ersatz, und der Benutzer hat keine Möglichkeit, den Aufwand zur Laufzeit zu unterdrücken, wenn es nicht erforderlich und ist zu hoch ist.

Im Allgemeinen in C++ besteht immer ein Mechanismus, mit dem Compiler unterstützten Funktionen unterdrückt werden sollen. Beispielsweise können wir virtuelle Mechanismus deaktivieren, indem Sie entweder mit dem Operator für (`Box::rotate(angle)`), oder rufen die virtuelle Methode über ein Objekt der Klasse (statt ein Zeiger oder Verweis von dieser Klasse). Diese zweite Unterdrückung ist von der Sprache nicht erforderlich, aber es ist eine Qualität der Implementierungsproblem, ähnlich wie die Unterdrückung der Erstellung eines temporären in einer Deklaration des Formulars:

```
// compilers are free to optimize away the temporary
X x = X::X( 10 );
```

Damit das Angebot erneut, weiter berücksichtigen sollten erstellt wurde, mehrere alternative Schreibweisen berücksichtigt wurden und die zurückgesetzt des Ausschusses der Form war (`?type`), der angegebenen unbestimmt -, also die Dynamik. Erhielt des Benutzers die Möglichkeit zum Umschalten zwischen den beiden Formaten – statische oder dynamische –, aber niemand wurde zu zufrieden. So war es an das Board zeichnen. Die dritte und erfolgreiche Notation ist nun standard `dynamic_cast<type>`, die auf einen Satz von vier neuen-Typumwandlung Notationen generalisiert wurde.

In ISO C++- `dynamic_cast` gibt `0` Wenn auf einen falschen Zeigertyp angewendet, und löst eine `std::bad_cast` Ausnahme bei Anwendung auf einen Verweistyp handelt. In Managed Extensions für C++ Anwenden von `dynamic_cast` in einen verwalteten Verweistyp (aufgrund der Darstellung als Zeiger) immer zurückgegeben `0`. `__try_cast<type>` wurde analog eingeführt, auf die Ausnahme auslösen Variante der `dynamic_cast`, außer dass löst `System::InvalidCastException` schlägt die Umwandlung fehl.

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

In der neuen Syntax `__try_cast` umgeformt wurden `safe_cast`. Hier ist das gleiche Codefragment in der neuen Syntax ein:

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

In der verwalteten Umgebung ist es wichtig, die überprüfbaren Code durch die Möglichkeit einschränken von Programmierern umzuwandelnde Differenzierung von Typen in der Weise, die den Code nicht überprüfbaren verlassen ermöglichen. Dies ist ein wichtiger Aspekt, der die dynamische Programmierparadigma, die durch die neue Syntax dargestellt wird. Aus diesem Grund Instanzen von Umwandlungen im alten Stil umgeformt intern als Laufzeit Umwandlungen, also, um beispielsweise:

```
// internally recast into the
// equivalent safe_cast expression above
( array<ItemVerb^>^ ) verbList->ToArray( ItemVerb::typeid );
```

Da Polymorphie sowohl einer aktiven und passiven Modus bietet, ist es andererseits, manchmal erforderlich, um eine Typumwandlung nur für den Zugriff auf die nicht virtuelle-API, der ein Untertyp auszuführen. Dies ist möglich, mit die Mitglieder einer Klasse, die z. B. Adresse alle Typen innerhalb der Hierarchie (passive Polymorphie als Transportmechanismus), aber für die die aktuelle Instanz in einem bestimmten Programmkontext bekannt ist. In diesem Fall möglich müssen eine laufzeitüberprüfung der Umwandlung ein akzeptabler Aufwand. Ist die neue Syntax als die Programmiersprache verwalteten Systemen verwendet werden, müssen sie angeben, dass einige bedeutet, dass eine während der Kompilierung zu ermöglichen (d. h. statische) Typumwandlung. Daher die Anwendung von der `static_cast` Notation ist zulässig, eine Typumwandlung Kompilierzeit bleiben:

```
// ok: cast performed at compile-time.
// No run-time check for type correctness
static_cast< array<ItemVerb^>^>(verbList->ToArray(ItemVerb::typeid));
```

Das Problem besteht darin, dass es keine Möglichkeit zu gewährleisten, dass den Programmierer die `static_cast` ist richtig und arglose; d.h., besteht keine Möglichkeit zum Erzwingen von verwalteten Codes, der überprüfbar sein. Dies ist ein größeres Problem dar, gemäß dem Programmierparadigma dynamische als bei systemeigenem Code, aber es ist nicht ausreichend innerhalb eines Systems, die Programmiersprache, die Benutzer zu unterbinden, der Möglichkeit zum Umschalten zwischen einem statischen und zur Laufzeit umgewandelt.

Es gibt eine Leistungsfalle und fallen bei der neuen Syntax jedoch. In der Programmierung mit native, besteht kein Leistungsunterschied zwischen den alten Umwandlungsnotation und die neue Formatvorlage `static_cast` Notation. Aber in der neuen Syntax Umwandlungsnotation im alten Stil ist deutlich teurer als die Verwendung der neuen-Formatvorlage `static_cast` Notation. Der Grund ist, dass der Compiler intern die Verwendung der alten Notation in eine laufzeitüberprüfung transformiert, die eine Ausnahme auslöst. Darüber hinaus auch ändert das Ausführungsprofil des Codes, da eine nicht abgefangene Ausnahme führt der Anwendung – vielleicht klug, aber der gleiche Fehler würde diese Ausnahme nicht, wenn die `static_cast` Notation verwendet wurden. Eine sind vielleicht der Meinung, dass auf diese Weise werden Benutzer in die Verwendung der neuen-Schreibweise. Aber nur, wenn ein Fehler auftritt. Andernfalls wird Programme, die die alten Notation verwenden, ohne ein sichtbar Verständnis, warum, bedeutend langsamer ausgeführt der ersichtlichen ähnelt:

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

[Allgemeine Sprachänderungen (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
[C-stilartige Umwandlungen mit/CLR (C++ / CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)<br/>
["safe_cast"](../windows/safe-cast-cpp-component-extensions.md)