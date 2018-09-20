---
title: CLR-Enumerationstyp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scope, of CLR enum
- enum struct keyword [C++]
- enum class keyword [C++]
ms.assetid: 4541d952-97bb-4e35-a7f8-d14f5f6a6606
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a39c451bcff7b5b3b1d7dd9f0d3925616b9d6aab
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436224"
---
# <a name="clr-enum-type"></a>CLR-Enumerationstyp

Die Deklaration und das Verhalten von Enumerationen hat gegenüber Managed Extensions for C++ geändert für Visual C++.

Der Managed Extensions-Enum-Deklaration steht das `__value` Schlüsselwort. Die Idee dabei ist, damit die systemeigene Enumeration von der CLR-Enumeration kann abgeleitet wird `System::ValueType`, während eine analoge Funktionalität bietet. Zum Beispiel:

```
__value enum e1 { fail, pass };
public __value enum e2 : unsigned short  {
   not_ok = 1024,
   maybe, ok = 2048
};
```

Die neue Syntax löst die Problem der Unterscheidung systemeigener und CLR-Enumerationen von der Art der Klasse der letztere statt auf ihren Wert Typ Wurzeln hervorgehoben. Daher ist es möglich, die `__value` Schlüsselwort wird verworfen, mit dem Schlüsselwortpaar Abstand ersetzt `enum class`. Dies bietet eine Symmetrie gekoppelten Schlüsselwort für die Deklarationen der der Verweis, Wert und Schnittstellenklassen:

```
enum class ec;
value class vc;
ref class rc;
interface class ic;
```

Die Übersetzung des Enumerationspaars `e1` und `e2` in der neuen Syntax sieht wie folgt aus:

```
enum class e1 { fail, pass };
public enum class e2 : unsigned short {
   not_ok = 1024,
   maybe, ok = 2048
};
```

Abgesehen von dieser kleinen Änderung syntaktische wurde das Verhalten von der CLR-Enumerationstyp auf verschiedene Arten geändert:

- Eine Vorwärtsdeklaration einer CLR-Enumeration wird nicht mehr unterstützt. Keine Zuordnung ist vorhanden. Es wird einfach als ein Fehler während der Kompilierung gekennzeichnet.

```
__value enum status; // Managed Extensions: ok
enum class status;   // new syntax: error
```

- Die Auflösung von funktionsüberladungen zwischen den integrierten arithmetischen Typen und die `Object` Klassenhierarchie ist zwischen den zwei Sprachversionen rückgängig gemacht! Als Nebeneffekt werden die CLR-Enumerationen nicht mehr implizit in arithmetischen Typen konvertiert.

- In der neuen Syntax verwaltet eine CLR-Enumeration einen eigenen Bereich, der nicht in Managed Extensions der Fall ist. Zuvor waren die Enumeratoren sichtbar innerhalb des enthaltenen Bereichs der Enumeration. Jetzt sind die Enumeratoren innerhalb des Bereichs der Enumeration gekapselt.

## <a name="clr-enums-are-a-kind-of-object"></a>CLR-Enumerationen sind eine Art von Objekt

Betrachten Sie das folgende Codefragment:

```
__value enum status { fail, pass };

void f( Object* ){ Console::WriteLine("f(Object)\n"); }
void f( int ){ Console::WriteLine("f(int)\n"); }

int main()
{
   status rslt = fail;

   f( rslt ); // which f is invoked?
}
```

Für die C++-Programmierer der natürlichen zu beantworten, auf die Frage, welche Instanz des überladenen `f()` wird aufgerufen, mit dem des `f(int)`. Eine Enumeration ist eine symbolische ganzzahlige Konstante und es beteiligt ist, in der standard ganzzahligen Erweiterungen, die in diesem Fall Vorrang.  Und tatsächlich wurde dies in Managed Extensions die Instanz, in der der Aufruf aufgelöst wird. Dies darauf zurückzuführen, dass eine Anzahl von überraschungen - nicht verwendet wurde, in einem systemeigenen C++ Frame -, aber wenn wir sie für die Interaktion mit dem vorhandenen BCL (Base Class Library)-Framework benötigt, in denen ein `Enum` ist eine Klasse indirekt von abgeleitete `Object`. In der Visual C++-Sprachentwurf, die Instanz von `f()` aufgerufen wird, die von `f(Object^)`.

Die Möglichkeit, die Visual C++ ausgewählt wurde, dies durchzusetzen ist implizite Konvertierungen zwischen einer CLR-Enumerationstyp und arithmetische Typen nicht zu unterstützen. Dies bedeutet, dass jede Zuweisung eines Objekts von einem CLR-Enumerationstyp auf einen arithmetischen Typ eine explizite Umwandlung erforderlich sind. Also z. B. angegeben.

```
void f( int );
```

als nicht überladene Methode, in dem Aufruf von Managed Extensions

```
f( rslt ); // ok: Managed Extensions; error: new syntax
```

Ok, und der Wert enthaltenen `rslt` wird implizit in einen ganzzahligen Wert konvertiert. In Visual C++ kann diesen Aufruf nicht kompiliert werden. Um es richtig zu übersetzen, müssen wir einen Konvertierungsoperator einfügen:

```
f( safe_cast<int>( rslt )); // ok: new syntax
```

## <a name="the-scope-of-the-clr-enum-type"></a>Der Bereich von der CLR-Enumerationstyp

Eine der Änderungen zwischen den Sprachen C und C++ war das Hinzufügen in C++ Bereich innerhalb des Gebäudes, Struktur. In C ist eine Struktur nur ein Datenaggregat ohne Unterstützung von einer Schnittstelle oder einem zugeordneten Bereich. Dies war ziemlich radikale Änderung zum Zeitpunkt und wurde ein strittigen Problem für viele neue C++-Benutzer, die von der Programmiersprache C. Die Beziehung zwischen dem systemeigenen und CLR-Enumeration entspricht.

In Managed Extensions wurde versucht, schwach eingefügte Namen für die Enumeratoren einer CLR-Enumeration zu definieren, um das Fehlen des Bereichs in systemeigenen Enumeration zu simulieren. Dies nicht erfolgreich verlaufen sind. Das Problem ist, dass dies bewirkt, die Enumeratoren in den globalen Namespace, die schwer dass zu und Namenskonflikte überläuft. In der neuen Syntax ist haben wir auf die anderen CLR-Sprachen bei der Unterstützung von Bereichen in der CLR-Enumeration entspricht.

Dies bedeutet, dass alle nicht qualifizierte Nutzung eines Enumerators einer CLR-Enumeration nicht durch die neue Syntax erkannt werden. Sehen wir uns ein praktisches Beispiel an.

```
// Managed Extensions supporting weak injection
__gc class XDCMake {
public:
   __value enum _recognizerEnum {
      UNDEFINED,
      OPTION_USAGE,
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,
      XDC0002_ERR_CANNOT_WRITE_TO = 2,
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,
      XDC0004_WRN_XML_LOAD_FAILURE = 4,
      XDC0006_WRN_NONEXISTENT_FILES = 6,
   };

   ListDictionary* optionList;
   ListDictionary* itagList;

   XDCMake() {
      optionList = new ListDictionary;

      // here are the problems...
      optionList->Add(S"?", __box(OPTION_USAGE)); // (1)
      optionList->Add(S"help", __box(OPTION_USAGE)); // (2)

      itagList = new ListDictionary;
      itagList->Add(S"returns",
         __box(XDC0004_WRN_XML_LOAD_FAILURE)); // (3)
   }
};
```

Jeder der drei nicht qualifizierten Namen Enumerator verwendet (`(1)`, `(2)`, und `(3)`) bei der Übersetzung in der neuen Syntax in der Reihenfolge für die zu kompilierenden Quellcode qualifiziert werden müssen. Hier ist eine ordnungsgemäße Übersetzung von den ursprünglichen Quellcode:

```
ref class XDCMake {
public:
   enum class _recognizerEnum {
      UNDEFINED, OPTION_USAGE,
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,
      XDC0002_ERR_CANNOT_WRITE_TO = 2,
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,
      XDC0004_WRN_XML_LOAD_FAILURE = 4,
      XDC0006_WRN_NONEXISTENT_FILES = 6
   };

   ListDictionary^ optionList;
   ListDictionary^ itagList;

   XDCMake() {
      optionList = gcnew ListDictionary;
      optionList->Add("?",_recognizerEnum::OPTION_USAGE); // (1)
      optionList->Add("help",_recognizerEnum::OPTION_USAGE); //(2)
      itagList = gcnew ListDictionary;
      itagList->Add( "returns",
         _recognizerEnum::XDC0004_WRN_XML_LOAD_FAILURE); //(3)
   }
};
```

Dadurch wird die Entwurfsstrategie zwischen systemeigenen und eine CLR-Enumeration. Eine CLR-Enumeration, die einen zugeordneten Gültigkeitsbereich in Visual C++ verwaltet ist es weder erforderlich noch effektiv, die Deklaration der Enumeration innerhalb einer Klasse zu kapseln. Dieses Idiom ständig weiterentwickelt, ungefähr zum Zeitpunkt der Veröffentlichung von Cfront 2.0 in den Bell Laboratories auch um die globalen Namen der Verunreinigung Problem zu beheben.

In der ursprünglichen Beta-Version des neuen Iostream-Bibliothek von Jerry Schwarz in den Bell Laboratories nicht gekapselt alle zugehörigen Enumerationen definiert, die für die Bibliothek, und die allgemeinen Enumeratoren wie z. B. `read`, `write`, `append`usw. , machten es nahezu unmöglich ist, damit Benutzer ihren vorhandenen Code zu kompilieren. Eine Lösung wäre gewesen, die die Namen, z. B. mangle `io_read`, `io_write`usw. Eine zweite Lösung, die Sprache zu ändern, indem Sie eine Enumeration Bereich hinzugefügt hätte, aber dies war nicht zum Zeitpunkt durchführbar. Die mittlere Lösung war zum Kapseln der Enumeration in der Klasse oder Klassenhierarchie, den Gültigkeitsbereich der einschließenden Klasse sowohl den Tagnamen und Enumeratoren der Enumeration, in denen auffüllen.) Platzieren von Enumerationen in Klassen, zumindest ursprünglich war, also nicht philosophischer, jedoch eine praktische Reaktion auf das globale-Namespace der Verunreinigung Problem.

Mit der Visual C++-Enumeration ist nicht mehr keinen nennenswerten Vorteil Kapseln einer Enumeration innerhalb einer Klasse. Tatsächlich ist bei Betrachtung der `System` Namespaces, sehen Sie, Enumerationen, Klassen und Schnittstellen, die alle im selben Deklarationsabschnitt darstellen.

## <a name="see-also"></a>Siehe auch

[Werttypen und ihr Verhalten (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[Enumerationsklasse](../windows/enum-class-cpp-component-extensions.md)