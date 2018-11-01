---
title: Objektlebenszeit und Ressourcenverwaltung (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
ms.openlocfilehash: d7bf45881ef82ecf0d11892e5ddf3d3c16a437cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609936"
---
# <a name="object-lifetime-and-resource-management-modern-c"></a>Objektlebenszeit und Ressourcenverwaltung (Modern C++)

Im Gegensatz zu verwalteten Sprachen keine C++ Garbagecollection (GC), die keine länger-verwendete Arbeitsspeicher automatisch freigibt, während ein Programm ausgeführt wird. In C++ bezieht ressourcenverwaltung direkt auf die Lebensdauer eines Objekts. Dieses Dokument beschreibt die Faktoren, die Objektlebensdauer in C++ für die Verwaltung auswirken.

C++ keinen GC, hauptsächlich, weil es nicht Arbeitsspeicherressourcen nicht behandelt. Deterministische Destruktoren wie in C++ können Arbeitsspeicher-und nicht nur gleichermaßen behandeln. GC verfügt auch über andere Probleme, wie die höheren Verarbeitungsaufwand im Arbeitsspeicher und CPU-Auslastung und Ort. Aber Universalität ist ein grundlegendes Problem, das nicht durch intelligente Optimierungen beseitigen lassen.

## <a name="concepts"></a>Konzepte

Wichtig: in der Verwaltung der Objektlebensdauer ist die Kapselung, wissen, welche Ressourcen für das Objekt besitzt, oder wie Sie sie zu entfernen oder sogar gibt an, ob sie alle Ressourcen überhaupt besitzt keine Personen ein Objekt verwendet wird. Er muss lediglich das Objekt zu zerstören. Die C++-Kernsprache stellen Sie sicher, dass Objekte, also zu den richtigen Zeitpunkten, zerstört werden soll, wie Blöcke, in umgekehrter Reihenfolge der Konstruktion beendet werden. Wenn ein Objekt zerstört wird, werden seine Basen und Membern in einer bestimmten Reihenfolge zerstört.  Die Sprache zerstört Objekte automatisch, wenn Sie besondere Dinge wie Heapzuordnung oder ein neues Platzierung ausführen.  Z. B. [intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md) wie `unique_ptr` und `shared_ptr`, und wie Sie C++-standardbibliothekscontainer `vector`, kapseln **neue** /  **Löschen Sie** und `new[]` / `delete[]` in Objekte, die Destruktoren haben. Deshalb so wichtig für intelligente Zeiger und C++-Standardbibliothek-Container verwenden kann.

Ein weiteres wichtiges Konzept in Prozesslebensdauer-Verwaltung: Destruktoren. Destruktoren kapseln die Version der Ressource.  (Das häufig verwendete mnemonische Zeichen ist RRID, Ressourcenfreigabe ist die Zerstörung).  Eine Ressource ist etwas, das Sie aus "System" und später wieder gewähren zu müssen.  Arbeitsspeicher ist die am häufigsten verwendeten Ressource, aber es gibt auch Dateien, Sockets, Texturen und andere Ressourcen ohne Speicher. "Besitzer" einer Ressource bedeutet, dass Sie sie verwenden können, wenn Sie ihn benötigen aber außerdem müssen Sie es freigeben, wenn Sie damit fertig sind.  Wenn ein Objekt zerstört wird, gibt der Destruktor die Ressourcen, die sie im Besitz frei.

Das endgültige Konzept ist der DAG (gerichtetes azyklisches Diagramm).  Die Struktur des Besitzes in einem Programm bildet eine DAG an. Kein Objekt kann selbst betreiben – das ist nicht nur möglich, aber grundsätzlich auch ohne Bedeutung. Aber zwei Objekte können den Besitz der ein drittes Objekt freigeben.  Verschiedene Arten von Links sind in einem gerichteten azyklischen Graph wie folgt möglich: A ist Mitglied der B (B ist ein Besitzer), C speichert eine `vector<D>` (C, besitzt jedes Element D), E speichert eine `shared_ptr<F>` (E freigegeben hat den Besitz von F, möglicherweise mit anderen Objekten), und so weiter.  Solange es sich um keine Zyklen und jede Verbindung in der DAG wird durch ein Objekt dargestellt, bei dem einen Destruktor (statt ein unformatierter Zeiger, Handle oder anderen Mechanismus), und klicken Sie dann Ressourcenverluste sind nicht möglich, da die Sprache, die sie nicht. Ressourcen werden freigegeben, sobald sie nicht mehr benötigt werden, ohne einen Garbage Collector ausgeführt wird. Die Lebensdauer, die nachverfolgung ist für Stack-Bereich, Basen, Mitglieder und ähnlichen Fällen Mehraufwand – kostenlos und für kostengünstig `shared_ptr`.

### <a name="heap-based-lifetime"></a>Heapbasierte Lebensdauer

Verwenden Sie für die Lebensdauer der Heap-Objekts, [intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md). Verwendung `shared_ptr` und `make_shared` als der Standardzeiger und der Zuweisung. Verwendung `weak_ptr` Zyklen unterbrechen, führen die Zwischenspeicherung und beobachten von Objekten ohne Auswirkungen auf oder Wenn irgendetwas über ihre Lebensdauer.

```cpp
void func() {

auto p = make_shared<widget>(); // no leak, and exception safe
...
p->draw();

} // no delete required, out-of-scope triggers smart pointer destructor
```

Verwendung `unique_ptr` für eindeutigen Besitz, z. B. in der *"pimpl"* Idiom. (Finden Sie unter [Pimpl für Kompilierzeitkapselung](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md).) Stellen Sie eine `unique_ptr` die primäre Zielgruppe für alle expliziten **neue** Ausdrücke.

```cpp
unique_ptr<widget> p(new widget());
```

Sie können unformatierte Zeiger für nichtbesitz und Beobachtung verwenden. Ein Zeiger nicht besitzt möglicherweise Leinwand, erlangt, aber es nicht möglich.

```cpp
class node {
  ...
  vector<unique_ptr<node>> children; // node owns children
  node* parent; // node observes parent, which is not a concern
  ...
};
node::node() : parent(...) { children.emplace_back(new node(...) ); }
```

Bei der Optimierung der Leistung erforderlich ist, müssen Sie möglicherweise mit *gut gekapseltes* zuständige Zeiger und explizite Aufrufe zu löschen. Ein Beispiel ist, wenn Sie Ihre eigenen Low-Level-Datenstruktur implementieren.

### <a name="stack-based-lifetime"></a>Stapelbasierte Lebensdauer

In modernem C++ *stapelbasierte Bereiche* ist eine leistungsstarke Möglichkeit, robusten Code schreiben, da sie automatische kombiniert *Stack Lebensdauer* und *Data Member Lebensdauer* mit hohe Effizienz: Lebensdauer, die nachverfolgung ist im Wesentlichen der Mehraufwand. Heap-Objektlebensdauer kann gewissenhaft manuelle Verwaltung erfordert und die Quelle der Ressourcenverluste und Ineffizienz, insbesondere dann, wenn Sie mit reinen Zeigern arbeiten. Betrachten Sie diesen Code, der stapelbasierte Bereiche veranschaulicht:

```cpp
class widget {
private:
    gadget g;   // lifetime automatically tied to enclosing object
public:
    void draw();
};

void functionUsingWidget () {
    widget w;   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.g gadget member
    // ...
    w.draw();
    // ...
} // automatic destruction and deallocation for w and w.g
  // automatic exception safety,
  // as if "finally { w.dispose(); w.g.dispose(); }"
```

Verwenden Sie die statische Lebensdauer nur selten (globale statische, lokale statische Funktion), da Probleme auftreten können. Was geschieht, wenn der Konstruktor eines globalen Objekts eine Ausnahme auslöst? In der Regel der app-Fehlern in eine Möglichkeit, die schwer zu debuggen sein können. Reihenfolge der Konstruktion ist für die Lebensdauer der statischen Objekte problematisch, und es ist nicht nebenläufigkeitssicher. Objekterstellung ist nicht nur ein Problem, Zerstörungsreihenfolge kann kompliziert sein, insbesondere bei der Polymorphismus beteiligt ist. Auch wenn Ihr Objekt oder die Variable nicht polymorph ist und keine komplexen-Erstellung/Zerstörung, Sortierung, besteht weiterhin die Ausgabe des Thread-sichere Parallelität. Eine Multithread-app kann nicht sicher auf die Daten in statische Objekte ändern, ohne lokalen Thread-Speicher, Ressourcensperren und andere besonderen Vorsichtsmaßnahmen.

## <a name="see-also"></a>Siehe auch

[Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)