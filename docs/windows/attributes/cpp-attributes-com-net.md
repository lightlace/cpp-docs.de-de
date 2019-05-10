---
title: C++-Attribute für COM und .NET
ms.custom: index-page
ms.date: 11/19/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI], reference topics
ms.assetid: 613a3611-b3eb-4347-aa38-99b654600e1c
ms.openlocfilehash: 9b985799849a268010dff63f9f7bc25e474b365e
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448517"
---
# <a name="c-attributes-for-com-and-net"></a>C++-Attribute für COM und .NET

Microsoft definiert einen Satz von C++-Attribute, die COM-Programmierung und .NET Framework common Language Runtime-Entwicklung zu vereinfachen. Wenn Sie Attribute in Ihren Quelldateien einschließen, arbeitet der Compiler, mit dem Anbieter-DLLs zum Einfügen von Code oder ändern den Code in die generierten Objektdateien. Diese Attribute bei der die Erstellung von IDL-Dateien, Schnittstellen, Typbibliotheken und anderen COM-Elementen. In der integrierten Entwicklungsumgebung (IDE) werden die Attribute von den Assistenten und das Fenster "Eigenschaften" unterstützt.

Während einige der ausführliche das Schreiben von Code zum Schreiben von COM-Objekte erforderlich sind Attribute vermeiden, benötigen Sie einen Hintergrund in [com-Grundlagen](/windows/desktop/com/the-component-object-model) optimal genutzt werden.

> [!NOTE]
> Wenn Sie für C++-standard-Attribute suchen, finden Sie unter [Attribute](../../cpp/attributes.md).

## <a name="purpose-of-attributes"></a>Attributzwecke

Attribute erweitern C++ in Anweisungen, die derzeit nicht möglich, ohne die klassischen Struktur der Sprache. Attribute können Anbieter (separate DLLs), um Funktionalität Language dynamisch zu erweitern. Das Hauptziel von Attributen ist zur Vereinfachung der Erstellung von COM-Komponenten sowie gleichzeitig die Produktivität der Komponentenentwickler. Es können Attribute angewendet werden, nahezu jedem C++-Konstrukt, wie z. B. Klassen, die Datenmember oder Memberfunktionen. Im folgenden finden eine Hervorhebung der Vorteile dieser neuen Technologie:

- Stellt eine vertraute und einfache Aufrufkonvention.

- Verwendet eingefügten Code, der, im Gegensatz zu Makros, die vom Debugger erkannt wird.

- Ermöglicht die einfache Ableitung von Basisklassen ohne aufwändige Implementierungsdetails.

- Ersetzt die große Menge der IDL-Code, die von einer COM‑Komponente, einige Attribute, die präzise erforderlich.

Beispielsweise um einen einfachen Ereignisempfänger für eine generische ATL-Klasse zu implementieren, Sie können Anwenden der [Event_receiver](event-receiver.md) Attribut für eine bestimmte Objektklasse, z. B. `CMyReceiver`. Die `event_receiver` Attribut wird dann kompiliert, das Microsoft C++ -Compiler, der den entsprechenden Code in der Objektdatei einfügt.

```cpp
[event_receiver(com)]
class CMyReceiver
{
   void handler1(int i) { ... }
   void handler2(int i, float j) { ... }
}
```

Anschließend können Sie festlegen, um die `CMyReceiver` Methoden `handler1` und `handler2` zum Behandeln von Ereignissen (verwenden die intrinsische Funktion [__hook](../../cpp/hook.md)) aus einer Ereignisquelle, die Sie erstellen können, mit [Event_source](event-source.md).

## <a name="basic-mechanics-of-attributes"></a>Grundlegende Funktionsweise der Attribute

Es gibt drei Möglichkeiten zum Einfügen von Attributen in Ihr Projekt. Erstens können Sie sie manuell in Ihren Quellcode einfügen. Zweitens können Sie sie mit dem Eigenschaftenraster eines Objekts in Ihrem Projekt einfügen. Schließlich können Sie mithilfe der verschiedenen Assistenten einfügen. Weitere Informationen zur Verwendung der **Eigenschaften** Fenster und die verschiedenen Assistenten, finden Sie unter [Visual Studio-Projekte – C++ ](../../build/creating-and-managing-visual-cpp-projects.md).

Als wenn das Projekt erstellt wird, analysiert, der Compiler jede C++-Quelldatei, erzeugt eine Objektdatei. Allerdings ist es, wenn der Compiler ein Attribut trifft, analysiert und syntaktisch überprüft. Der Compiler ruft dann dynamisch ein Attributanbieters zum Einfügen von Code oder andere Änderungen vornehmen, zum Zeitpunkt der Kompilierung. Die-Implementierung des Anbieters, hängt von den Typ des Attributs ab. ATL-bezogene Attribute werden beispielsweise durch Atlprov.dll implementiert.

Die folgende Abbildung veranschaulicht die Beziehung zwischen dem Compiler und Attributanbieter.

![Komponentenattributkommunikation](../media/vccompattrcomm.gif "komponentenattributkommunikation")

> [!NOTE]
> Verwendung von Attributen wird den Inhalt der Quelldatei nicht geändert werden. Nur dann, die der generierten Attributcode sichtbar ist, ist während des Debuggens von Sitzungen. Darüber hinaus können für jede Quelldatei im Projekt, eine Textdatei generiert werden, in dem die Ergebnisse der Ersetzung Attribut angezeigt. Weitere Informationen zu dieser Vorgehensweise finden Sie unter [/FX (eingefügten Code zusammenführen)](../../build/reference/fx-merge-injected-code.md) und [Debuggen von Injiziertem Code](/visualstudio/debugger/how-to-debug-injected-code).

-Attribute haben eine Reihe von Eigenschaften, die ihre ordnungsgemäße Nutzung definiert, wie die meisten C++-Konstrukte. Dies wird als den Kontext des Attributs bezeichnet und ist in der Tabelle der Attribut-Kontext für jedes Attribut-Referenzthema behoben wurden. Z. B. die [Co-Klasse](coclass.md) Attribut kann nur auf einer vorhandenen Klasse oder Struktur angewendet werden, im Gegensatz zu der [Cpp_quote](cpp-quote.md) -Attribut, das in eine beliebige Stelle eingefügt werden, kann eine C++ Quelldatei.

## <a name="building-an-attributed-program"></a>Erstellen eines attributierten Programms

Nachdem Sie Visual einfügen C++ Attribute in Ihren Quellcode, sollten Sie die Microsoft C++ Compiler eine Typ-Bibliothek und IDL-Datei für Sie erstellt. Die folgenden Linkeroptionen können Sie TLB-Datei und IDL-Dateien:

- [/IDLOUT](../../build/reference/idlout-name-midl-output-files.md)

- [/IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)

- [/MIDL](../../build/reference/midl-specify-midl-command-line-options.md)

- [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)

Einige Projekte enthalten mehrere unabhängige IDL-Dateien. Diese werden verwendet, um zwei oder mehr .tlb-Dateien erstellen und binden sie optional in den Ressourcenblock. Dieses Szenario ist nicht aktuell in Visual C++ unterstützt.

Darüber hinaus gibt der Visual C++-Linker alle IDL-Attribut-Informationen in eine einzelne MIDL-Datei. Es werden keine Möglichkeit, zwei Typbibliotheken aus einem einzelnen Projekt zu generieren.

## <a name="contexts"></a> Attributkontexte

C++-Attribute können mithilfe von vier grundlegende Felder beschrieben werden: das Ziel, die sie auf angewendet werden können (**gilt für**), wenn sie wiederholbar oder nicht sind (**wiederholbare**), wird die Vorhandenseins anderer Attribute (erforderlich **Erforderliche Attribute**), und die Inkompatibilitäten mit anderen Attributen (**ungültige Attribute**). Diese Felder sind in einer zugehörigen Tabelle im Referenzthema für jedes Attribut des aufgeführt. Jedes dieser Felder wird unten beschrieben.

### <a name="applies-to"></a>Gilt für

Dieses Feld beschreibt die verschiedenen C++-Sprachelemente, die sind rechtliche Ziele für das angegebene Attribut. Z. B. wenn ein Attribut "Class" in gibt der **gilt für** Feld Dies gibt an, dass das Attribut nur auf eine rechtliche C++-Klasse angewendet werden kann. Wenn das Attribut auf eine Memberfunktion einer Klasse angewendet wird, führt ein Syntaxfehler.

Weitere Informationen finden Sie unter [Attribute nach Verwendung](attributes-by-usage.md).

### <a name="repeatable"></a>Wiederholbar

Dieses Feld gibt an, ob das Attribut mehrmals an dasselbe Ziel angewendet werden kann. Die meisten Attribute sind nicht wiederholbar.

### <a name="required-attributes"></a>Erforderliche Attribute

Dieses Feld Listet weitere Attribute, die sich für das angegebene Attribut ordnungsgemäß funktioniert (die an dasselbe Ziel angewendet werden) vorhanden. Es ist ungewöhnlich, dass ein Attribut aus, die Einträge für dieses Feld vorhanden sind.

### <a name="invalid-attributes"></a>Ungültige Attribute

Dieses Feld Listet weitere Attribute, die mit dem angegebenen Attribut nicht kompatibel sind. Es ist ungewöhnlich, dass ein Attribut aus, die Einträge für dieses Feld vorhanden sind.

## <a name="in-this-section"></a>In diesem Abschnitt

[Fragen und Antworten zur attributierten Programmierung](attribute-programming-faq.md)<br/>
[Attribute nach Gruppen](attributes-by-group.md)<br/>
[Attribute nach Verwendung](attributes-by-usage.md)<br/>
[Alphabetische Attributreferenz](attributes-alphabetical-reference.md)