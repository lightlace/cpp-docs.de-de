---
title: pimpl für Compilierungszeitkapselung (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: f1eb06ad3a52be486f085babf699677951b1ee71
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245178"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>pimpl für Compilierungszeitkapselung (Modern C++)

Das *pimpl-Idiom* ist ein C++ modernes Verfahren zum Ausblenden der Implementierung, zum Minimieren der Kopplung und zum Trennen von Schnittstellen. Pimpl ist für "Zeiger auf Implementierung" kurz. Möglicherweise sind Sie bereits mit dem Konzept vertraut, aber Sie kennen es durch andere Namen wie z. b. Cheshire Cat oder compilerfirewall.

## <a name="why-use-pimpl"></a>Gründe für die Verwendung von pimpl

Im folgenden wird erläutert, wie die pimpl-Sprache den Lebenszyklus der Softwareentwicklung verbessern kann:

- Minimierung von Kompilierungs Abhängigkeiten.

- Trennung von Schnittstelle und Implementierung.

- Verlangen.

## <a name="pimpl-header"></a>Pimpl-Header

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

Das pimpl-Idiom vermeidet das Neuerstellen von Kaskaden und spröden Objekt Layouts. Es eignet sich gut für (transitiv) beliebte Typen.

## <a name="pimpl-implementation"></a>Pimpl-Implementierung

Definieren Sie die `impl`-Klasse in der CPP-Datei.

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>Bewährte Methoden

Stellen Sie sich vor, ob Sie die Unterstützung für die nicht ausgelöste swapspezialisierung

## <a name="see-also"></a>Siehe auch

[Willkommen zurück beiC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
