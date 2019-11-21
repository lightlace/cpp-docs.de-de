---
title: 'How to: Design for exception safety'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 19ecc5d4-297d-4c4e-b4f3-4fccab890b3d
ms.openlocfilehash: 48a2f5a94eb2695c0a08a0ae397d02080e7e1261
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246513"
---
# <a name="how-to-design-for-exception-safety"></a>How to: Design for exception safety

Einer der Vorteile des Ausnahmemechanismus ist, dass die Ausführung – zusammen mit Daten zur Ausnahme – direkt von der Anweisung, die die Ausnahme auslöst, zur ersten catch-Anweisung springt, die sie behandelt. Der Handler kann sich in der Aufrufliste auf einer beliebig höheren Ebene befinden. Funktionen, die zwischen der try- und der throw-Anweisung aufgerufen werden, müssen nicht über Informationen über die ausgelöste Ausnahme verfügen.  Sie müssen jedoch so gestaltet werden, dass sie an jedem Punkt, an dem eine Ausnahme von unten nach oben verteilt wird, den Gültigkeitsbereich "unerwartet" verlassen können. Dabei dürfen sie keine teilweise erstellten Objekte, Speicherverluste oder Datenstrukturen, die in unbrauchbarem Zustand sind, hinterlassen.

## <a name="basic-techniques"></a>Basic techniques

Eine solide Ausnahmebehandlungsrichtlinie erfordert sorgfältige Überlegungen und sollte Teil des Entwurfsprozesses sein. Im Allgemeinen werden die meisten Ausnahmen auf den niedrigeren Ebenen einer Softwarekomponente erkannt und ausgelöst. Diese Ebenen haben in der Regel aber nicht genügend Kontext, um den Fehler zu behandeln oder eine Meldung für den Endbenutzer verfügbar zu machen. Auf den mittleren Ebenen können Funktionen eine Ausnahme abfangen und erneut auslösen, wenn sie das Ausnahmeobjekt überprüfen müssen oder über zusätzliche nützliche Informationen verfügen, die sie für die obere Ebene bereitstellen, die letztendlich die Ausnahme abfängt. Eine Funktion sollte eine Ausnahme nur dann abfangen und behalten, wenn sie sie vollständig behandeln kann. In vielen Fällen ist das richtige Verhalten auf den mittleren Ebenen, eine Ausnahme in der Aufrufliste nach oben weiterzugeben. Sogar auf der höchsten Ebene kann es sinnvoll sein, ein Programm durch einen Ausnahmefehler beenden zu lassen, wenn die Ausnahme das Programm in einem Zustand belässt, in dem nicht garantiert werden kann, dass das Programm korrekt ausgeführt wird.

Egal wie eine Funktion eine Ausnahme behandelt, sie muss nach den folgenden grundlegenden Regeln entworfen werden, um wirklich "ausnahmesicher" zu sein.

### <a name="keep-resource-classes-simple"></a>Keep resource classes simple

When you encapsulate manual resource management in classes, use a class that does nothing except manage a single resource. By keeping the class simple, you reduce the risk of introducing resource leaks. Use [smart pointers](smart-pointers-modern-cpp.md) when possible, as shown in the following example. Dieses Beispiel ist bewusst künstlich und vereinfacht, um die Unterschiede bei der Verwendung von `shared_ptr` hervorzuheben.

```cpp
// old-style new/delete version
class NDResourceClass {
private:
    int*   m_p;
    float* m_q;
public:
    NDResourceClass() : m_p(0), m_q(0) {
        m_p = new int;
        m_q = new float;
    }

    ~NDResourceClass() {
        delete m_p;
        delete m_q;
    }
    // Potential leak! When a constructor emits an exception,
    // the destructor will not be invoked.
};

// shared_ptr version
#include <memory>

using namespace std;

class SPResourceClass {
private:
    shared_ptr<int> m_p;
    shared_ptr<float> m_q;
public:
    SPResourceClass() : m_p(new int), m_q(new float) { }
    // Implicitly defined dtor is OK for these members,
    // shared_ptr will clean up and avoid leaks regardless.
};

// A more powerful case for shared_ptr

class Shape {
    // ...
};

class Circle : public Shape {
    // ...
};

class Triangle : public Shape {
    // ...
};

class SPShapeResourceClass {
private:
    shared_ptr<Shape> m_p;
    shared_ptr<Shape> m_q;
public:
    SPShapeResourceClass() : m_p(new Circle), m_q(new Triangle) { }
};
```

### <a name="use-the-raii-idiom-to-manage-resources"></a>Use the RAII idiom to manage resources

To be exception-safe, a function must ensure that objects that it has allocated by using `malloc` or **new** are destroyed, and all resources such as file handles are closed or released even if an exception is thrown. The *Resource Acquisition Is Initialization* (RAII) idiom ties management of such resources to the lifespan of automatic variables. Wenn eine Funktion den Bereich verlässt, indem sie normal oder aufgrund einer Ausnahme zurückgegeben wird, werden die Destruktoren für alle vollständig konstruierten automatischen Variablen aufgerufen. Ein RAII-Wrapperobjekt wie beispielsweise ein intelligenter Zeiger ruft die entsprechende delete- oder close-Funktion in seinem Destruktor auf. In ausnahmesicherem Code ist es sehr wichtig, den Besitz von jeder Ressource sofort an eine Art von RAII-Objekt zu übergeben. Note that the `vector`, `string`, `make_shared`, `fstream`, and similar classes handle acquisition of the resource for you.  However, `unique_ptr` and traditional `shared_ptr` constructions are special because resource acquisition is performed by the user instead of the object; therefore, they count as *Resource Release Is Destruction* but are questionable as RAII.

## <a name="the-three-exception-guarantees"></a>The three exception guarantees

Typically, exception safety is discussed in terms of the three exception guarantees that a function can provide: the *no-fail guarantee*, the *strong guarantee*, and the *basic guarantee*.

### <a name="no-fail-guarantee"></a>No-fail guarantee

Die NO-FAIL-Garantie (oder "NO-THROW") ist die stärkste Garantie, die eine Funktion bereitstellen kann. Sie gibt an, dass die Funktion keine Ausnahme auslöst oder keine Weitergabe einer Ausnahme zulässt. Sie können jedoch eine solche Garantie nur dann zuverlässig bereitstellen, wenn folgende Voraussetzungen zutreffen: (a) Sie wissen, dass alle von dieser Funktion aufgerufenen Funktionen ebenfalls NO-FAIL sind, oder (b) Sie wissen, dass alle ausgelösten Ausnahmen abgefangen werden, bevor sie diese Funktion erreichen, oder (c) Sie wissen, wie Sie alle Ausnahmen abfangen und ordnungsgemäß behandeln, die möglicherweise diese Funktion erreichen.

Sowohl die starke Garantie als auch die grundlegende Garantie basieren auf der Annahme, dass die Destruktoren NO-FAIL sind. Alle Container und Typen in der Standardbibliothek garantieren, dass ihre Destruktoren keine Ausnahmen auslösen. Es gibt auch eine entgegengesetzte Anforderung: Die Standardbibliothek erfordert, dass benutzerdefinierte Typen, die für sie angegeben werden – z. B. Vorlagenargumente – nicht auslösende Destruktoren besitzen.

### <a name="strong-guarantee"></a>Strong guarantee

Die starke Garantie gibt an, dass eine Funktion, wenn sie den Bereich aufgrund einer Ausnahme verlässt, keinen Speicherverlust verursacht, und dass der Programmzustand unverändert bleibt. Eine Funktion, die eine starke Garantie bereitstellt, ist im Wesentlichen eine Transaktion, die Commit- oder Zurücksetzungssemantik besitzt: entweder sie wird vollständig abgeschlossen oder sie hat keine Auswirkungen.

### <a name="basic-guarantee"></a>Basic guarantee

Die grundlegende Garantie ist die schwächste der drei Garantien. Sie kann aber die beste Lösung sein, wenn eine starke Garantie zu viel Speicher oder Leistung in Anspruch nimmt. Die grundlegende Garantie gibt an, dass beim Auftreten einer Ausnahme kein Speicherverlust verursacht wird und das Objekt in einem verwendbaren Zustand bleibt, obwohl die Daten möglicherweise geändert wurden.

## <a name="exception-safe-classes"></a>Exception-safe classes

Eine Klasse kann dazu beitragen, ihre eigene Ausnahmesicherheit sicherzustellen, selbst wenn sie von unsicheren Funktionen genutzt wird. Dazu verhindert die Klasse, dass sie teilweise konstruiert oder zerstört wird. Wird ein Klassenkonstruktor vor dem Abschließen beendet, wird das Objekt nie erstellt und dessen Destruktor nie aufgerufen. Für automatische, vor der Ausnahme initialisierte Variablen werden zwar deren Destruktoren aufgerufen. Aber für dynamisch reservierten Speicher oder Ressourcen, die nicht über einen intelligenten Zeiger oder eine ähnliche automatische Variable verwaltet werden, hat dies einen Verlust zur Folge.

Die integrierten Datentypen sind alle NO-FAIL, und die Standardbibliothekstypen unterstützen mindestens die grundlegende Garantie. Beachten Sie für jeden benutzerdefinierten Typ, der ausnahmesicher sein muss, die folgenden Richtlinien:

- Verwenden Sie zum Verwalten aller Ressourcen intelligente Zeiger oder andere RAII-Typwrapper. Vermeiden Sie Ressourcenverwaltungsfunktionalität im Klassendestruktor, da der Destruktor nicht aufgerufen wird, wenn der Konstruktor eine Ausnahme auslöst. Wenn allerdings die Klasse ein dedizierter Ressourcen-Manager ist, der nur eine Ressource steuert, dann ist es akzeptabel, den Destruktor zum Verwalten von Ressourcen zu verwenden.

- Eine Ausnahme, die in einem Basisklassenkonstruktor ausgelöst wird, kann nicht von einem abgeleiteten Klassenkonstruktor behalten werden. Wenn Sie die Basisklassenausnahme übersetzen und in einem abgeleiteten Konstruktor erneut auslösen möchten, verwenden Sie einen Funktions-Try-Block.

- Ziehen Sie in Betracht, alle Klassenzustände in einem Datenmember zu speichern, das von einem intelligenten Zeiger umschlossen wird. Dies gilt insbesondere, wenn eine Klasse ein Initialisierungskonzept hat, das einen Fehler zulässt. C++ lässt zwar nicht initialisierte Datenmember zu, unterstützt aber keine nicht initialisierten oder teilinitialisierten Klasseninstanzen. Ein Konstruktor muss erfolgreich sein oder einen Fehler aufweisen. Es wird kein Objekt erstellt, wenn der Konstruktor nicht ausgeführt wird, bis er abgeschlossen ist.

- Lassen Sie Ausnahmen nicht von Destruktoren auslösen. Ein allgemeiner Grundsatz von C++ besagt, dass Destruktoren nie zulassen dürfen, dass eine Ausnahme in der Aufrufliste nach oben weitergegeben wird. Wenn ein Destruktor einen Vorgang ausführen muss, der möglicherweise eine Ausnahme auslösen kann, muss er dies in einem try/catch-Block durchführen und die Ausnahme behalten. Die Standardbibliothek stellt diese Garantie für alle von ihr definierten Destruktoren bereit.

## <a name="see-also"></a>Siehe auch

[Modern C++ best practices for exceptions and error handling](errors-and-exception-handling-modern-cpp.md)<br/>
[Vorgehensweise: Verbinden von Code, der Ausnahmen zulässt, mit Code ohne Ausnahmen](how-to-interface-between-exceptional-and-non-exceptional-code.md)
