---
title: Namespaces und Typsichtbarkeit (C++/CX)
ms.date: 12/30/2016
ms.assetid: cbc01a3a-3b69-4ded-9c42-ecbf0fd0a00e
ms.openlocfilehash: 02a73f84314d4406c5fb8e9b8635a307c30e4c3d
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693893"
---
# <a name="namespaces-and-type-visibility-ccx-"></a>Namespaces und Typsichtbarkeit (C++/CX)

Ein Namespace ist ein Standard-C++-Konstrukt zum Gruppieren von Typen mit ähnlichen Funktionen und zum Verhindern von Namenskonflikten in Bibliotheken. Die Windows-Runtime-Typsystem ist erforderlich, dass alle öffentliche Windows-Runtime-Typen, einschließlich der in Ihrem eigenen Code in einem Namespace im Namespacebereich deklariert werden müssen. Öffentliche Typen, die im globalen Gültigkeitsbereich deklariert oder innerhalb einer anderen Klasse geschachtelt werden, verursachen einen Kompilierungsfehler.

Eine WinMD-Datei muss denselben Namen wie der Stammnamespace haben. Zum Beispiel kann eine Klasse namens A.B.C.MyClass nur instanziiert werden, wenn sie in einer Metadatendatei definiert ist, die A.winmd oder A.B.winmd oder A.B.C.winmd heißt. Der Name der ausführbaren Datei muss nicht mit dem Namen der WINMD-Datei übereinstimmen.

## <a name="type-visibility"></a>Typsichtbarkeit

In einem Namespace, die Windows-Runtime-Typen – im Gegensatz zu C++-Standardtypen, private oder öffentliche zugreifbarkeit besitzen. Standardmäßig ist die Barrierefreiheit privat. Nur ein öffentlicher Typ ist für Metadaten sichtbar und kann von Apps und Komponenten verwendet werden, die in anderen Sprachen als C++ geschrieben sind. Im Allgemeinen sind die Regeln für sichtbare Typen restriktiver als die Regeln für nicht sichtbare Typen, da sichtbare Typen nur C++-spezifischen Konzepte verfügbar machen können, die von .NET-Sprachen oder JavaScript unterstützt werden.

> [!NOTE]
> Metadaten werden nur zur Laufzeit von .NET-Sprachen und JavaScript verwendet. Wenn eine App oder Komponente in C++ mit einer anderen C++-App oder -Komponente kommuniziert – dies schließt Windows-Komponenten ein, die alle in C++ geschrieben sind – ist keine Verwendung von Metadaten zur Laufzeit erforderlich.

## <a name="member-accessibility-and-visibility"></a>Memberbarrierefreiheit und -sichtbarkeit

In einer privaten Verweisklasse, Schnittstelle oder einem privaten Delegat werden keine Member an Metadaten ausgegeben, auch wenn sie über öffentliche Barrierefreiheit verfügen. In öffentlichen Verweisklassen können Sie die Sichtbarkeit von Membern in den Metadaten unabhängig von ihrer Barrierefreiheit im Quellcode steuern. Wie in Standard-C++ wenden Sie das Prinzip der minimalen Berechtigungen an. Machen Sie die Member in den Metadaten nur sichtbar, wenn es absolut sein muss.

Verwenden Sie die folgenden Zugriffsmodifizierer, um die Sichtbarkeit der Metadaten und die Quellcodebarrierefreiheit zu steuern.

||||
|-|-|-|
|Modifizierer|Bedeutung|An Metadaten ausgegeben?|
|private|Die Standardeinstellung für die Barrierefreiheit. Dieselbe Bedeutung wie in Standard-C++.|Nein|
|protected|Dieselbe Bedeutung wie in Standard-C++, sowohl innerhalb der Anwendung oder Komponente als auch in den Metadaten.|Ja|
|public|Dieselbe Bedeutung wie in Standard-C++.|Ja|
|`public protected` - oder - `protected public`|Geschützte Barrierefreiheit in den Metadaten, öffentlich innerhalb der App oder Komponente.|Ja|
|`protected private` oder `private protected`|In den Metadaten nicht sichtbar. Geschützte Barrierefreiheit innerhalb der App oder Komponente.||
|`internal` oder `private public`|Der Member ist innerhalb der Anwendung oder Komponente öffentlich, aber nicht in den Metadaten sichtbar.|Nein|

## <a name="windows-runtime-namespaces"></a>Windows-Runtime-namespaces

Die Windows-API besteht aus Typen, die in der Windows deklariert werden::\* Namespaces. Diese Namespaces werden für Windows reserviert, und es können ihnen keine Typen hinzugefügt werden. Im **Objektkatalog**können Sie diese Namespaces in der Datei Windows.winmd anzeigen. Eine Dokumentation zu diesen Namespaces finden Sie unter [Windows-API](/uwp/api/).

## <a name="ccx-namespaces"></a>C++/CX-Namespaces

C++ / CX definieren bestimmte Typen in diesen Namespaces als Teil der Projektion von der Windows-Runtime-Typsystem.

|||
|-|-|
|**Namespace**|**Beschreibung**|
|default|Enthält die integrierten numerischen und char16-Typen. Diese Typen befinden sich in jedem Namespace im Bereich. Eine `using` -Anweisung ist nicht erforderlich.|
|Plattform|Enthält hauptsächlich öffentliche Typen, die von Windows-Runtime-Typen, z. B. entsprechen `Array<T>`, `String`, `Guid`, und `Boolean`. Schließt auch spezielle Hilfsprogrammtypen wie `Platform::Agile<T>` und `Platform::Box<T>`ein.|
|Platform::Collections|Enthält die Sammlung von konkreten Klassen, die die Windows-Runtime-Sammelschnittstellen implementieren `IVector`, `IMap`und so weiter. Diese Typen werden in einer Headerdatei, collection.h, und nicht in der Datei platform.winmd definiert.|
|Platform::Details|Enthält Typen, die vom Compiler verwendet werden und nicht für die öffentliche Nutzung vorgesehen sind.|

## <a name="see-also"></a>Siehe auch

[Typsystem (C++/CX)](../cppcx/type-system-c-cx.md)