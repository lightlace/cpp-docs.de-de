---
title: Hinweisdateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- cpp.hint
- vc.hint.file
dev_langs:
- C++
helpviewer_keywords:
- stop file
- cpp.hint
- hint file
- cpp.stop
- Class View, hint file
ms.assetid: 17194f66-cf62-4523-abec-77db0675ab65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98734522410b867d735d0af25f440d5b45874563
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393281"
---
# <a name="hint-files"></a>Hinweisdateien

Eine *Hinweisdatei* unterstützt die integrierte Visual Studio-Entwicklungsumgebung (IDE) dabei, Visual C++-Bezeichner wie die Namen von Funktionen und Makros zu interpretieren. Wenn Sie ein Visual C++-Projekt öffnen, analysiert das *Analysesystem* der IDE den Code in jeder Quelldatei des Projekts und sammelt Informationen zu jedem Bezeichner. Die IDE verwendet diese Informationen anschließend, um Features wie die **Klassenansicht** und die **Navigationsleiste** zu unterstützen.

Das Analysesystem, das in Visual C++ 2010 eingeführt wurde, versteht die C/C++-Syntax, kann jedoch Anweisungen falsch interpretieren, die Makros enthält. Die Anweisung kann falsch interpretiert werden, wenn das Makro dazu führt, dass der Quellcode syntaktisch falsch geschrieben ist. Die Syntax der Anweisung kann korrigiert werden, wenn der Quellcode kompiliert wird und der Präprozessor den [Makrobezeichner](../preprocessor/hash-define-directive-c-cpp.md) durch seine Definition ersetzt. Das Analysesystem funktioniert, ohne das Projekt erstellen zu müssen, da es Hinweisdateien verwendet, um Makros zu interpretieren. Aus diesem Grund steht eine Suchfunktion wie die **Klassenansicht** sofort zur Verfügung.

Eine Hinweisdatei enthält vom Benutzer anpassbare *Hinweise*, die die gleiche Syntax wie die C/C++-Makrodefinitionen aufweisen. Visual C++ enthält eine integrierte Hinweisdatei, die für die meisten Projekte ausreicht. Sie können jedoch eigene Hinweisdateien erstellen, um zu verbessern, wie Visual Studio Bezeichner verarbeitet.

> [!IMPORTANT]
> Wenn Sie eine Hinweisdatei ändern oder hinzufügen, müssen Sie die SDF-Datei und/oder die Datei „VC.db“ aus der Projektmappe löschen, damit die Änderungen wirksam werden.

## <a name="scenario"></a>Szenario

Nehmen Sie an, dass folgender Code sich in einer Quelldatei befindet, die Sie mit der **Klassenansicht** überprüfen. Das `STDMETHOD`-Makro deklariert eine Methode namens `myMethod`, die einen Parameter annimmt und einen Zeiger auf **HRESULT** zurückgibt.

```cpp
// Source code file.
STDMETHOD(myMethod)(int parameter1);
```

Die folgenden Makrodefinitionen befinden sich in einer separaten Headerdatei.

```cpp
// Header file.
#define STDMETHOD(method) HRESULT (STDMETHODCALLTYPE * method)
#define STDMETHODCALLTYPE __stdcall
#define HRESULT void*
```

Das Analysesystem kann den Quellcode nicht interpretieren, da eine Funktion namens `STDMETHOD` deklariert zu sein scheint. Diese Deklaration ist jedoch syntaktisch falsch, da sie über zwei Parameterlisten verfügt. Das Analysesystem öffnet nicht die Headerdatei, um die Definition für die Makros `STDMETHOD`, `STDMETHODCALLTYPE` und `HRESULT` zu ermitteln. Da das Analysesystem das Makro `STDMETHOD` nicht interpretieren kann, ignoriert es die gesamte Anweisung und setzt die Analyse fort.

Das Analysesystem verwendet keine Headerdateien, da Ihr Projekt möglicherweise von einer oder mehreren wichtigen Headerdateien abhängt. Wenn eine Headerdatei geändert wird, muss das Analysesystem alle Headerdateien im Projekt neu überprüfen, wodurch die Leistung der IDE verlangsamt wird. Stattdessen verwendet das Analysesystem Hinweise, die angeben, wie die Makros `STDMETHOD`, `STDMETHODCALLTYPE` und `HRESULT` verarbeitet werden.

Woher wissen Sie, dass Sie einen Hinweis benötigen? Wenn Sie einen Hinweis benötigen, welchen sollten Sie dann erstellen? Ein Zeichen dafür, dass ein Hinweis erforderlich ist, liegt vor, wenn die Ansicht eines Bezeichners in der **Klassenansicht** sich von der Ansicht im **Editor** unterscheidet. Die **Klassenansicht** zeigt beispielsweise einen Klassenmember nicht an, von dem Sie wissen, dass er vorhanden ist, oder der Name des Members ist falsch. Weitere Informationen zu den Hinweistypen, mit denen allgemeine Probleme gelöst werden können, finden Sie im Verlauf dieses Artikels unter „Welche Makros benötigen einen Hinweis?“.

## <a name="architecture"></a>Architektur

Hinweisdateien beziehen sich auf physische Verzeichnisse, nicht auf die lokalen Verzeichnisse, die im **Projektmappen-Explorer** dargestellt werden. Sie müssen eine Hinweisdatei nicht zu Ihrem Projekt hinzufügen, damit diese wirksam ist. Das Analysesystem verwendet Hinweisdateien nur, wenn es Quelldateien analysiert.

Jede Hinweisdatei heißt **cpp.hint**. Daher können viele Verzeichnisse eine Hinweisdatei enthalten, es kann jedoch nur eine Hinweisdatei pro Verzeichnis vorhanden sein.

Null oder mehr Hinweisdateien können Auswirkungen auf Ihr Projekt haben. Wenn keine Hinweisdateien vorhanden sind, verwendet das Analysesystem Wiederherstellungstechniken für Fehler, um den unlesbaren Quellcode zu ignorieren. Andernfalls verwendet das Analysesystem folgende Strategie, um Hinweise zu suchen und zu sammeln.

### <a name="search-order"></a>Suchreihenfolge

Das Analysesystem durchsucht Verzeichnisse in folgender Reihenfolge nach Hinweisdateien.

- Das Verzeichnis, das das Installationspaket für Visual C++ enthält (**vcpackages**). Dieses Verzeichnis enthält eine integrierte Hinweisdatei, die Symbole in häufig verwendeten Systemdateien (z.B. **windows.h**) beschreibt. Deshalb erbt Ihr Projekt automatisch die meisten erforderlichen Hinweise.

- Der Pfad vom Stammverzeichnis einer Quelldatei zu dem Verzeichnis, das die Quelldatei enthält. In einem typischen Visual C++-Projekt enthält das Stammverzeichnis die Projektmappen- oder die Projektdatei.

   Eine Ausnahme besteht darin, wenn sich eine *STOP-Datei* im Pfad zur Quelldatei befindet. Eine STOP-Datei ermöglicht eine zusätzliche Steuerung der Suchreihenfolge. Dazu zählen alle Dateien, die **cpp.stop** heißen. Statt im Stammverzeichnis zu beginnen, sucht das Analysesystem von dem Verzeichnis aus, das die STOP-Datei enthält, und beendet die Suche in dem Verzeichnis, das die Quelldatei enthält. In einem typischen Projekt benötigen Sie keine STOP-Datei.

### <a name="hint-gathering"></a>Sammeln von Hinweisen

Eine Hinweisdatei enthält null oder mehr *Hinweise*. Ein Hinweis wird genau wie ein C/C++-Makro definiert oder gelöscht. Das bedeutet, dass die Präprozessordirektive `#define` einen Hinweis erstellt oder neu definiert und die Direktive `#undef` einen Hinweis löscht.

Das Analysesystem öffnet jede Hinweisdatei in der zuvor beschriebenen Suchreihenfolge und sammelt die Hinweise in jeder Datei in einer Reihe von *effektiven Hinweisen*. Diese werden dann verwendet, um die Bezeichner im Code zu interpretieren.

Das Analysesystem verwendet folgende Regeln, um Hinweise zu sammeln.

- Wenn der neue Hinweis einen Namen festlegt, der noch nicht definiert ist, fügt der neue Hinweis den Namen zu den effektiven Hinweisen hinzu.

- Wenn der neue Hinweis einen Namen festlegt, der bereits definiert ist, definiert der neue Hinweis den vorhandenen Hinweisen neu.

- Wenn der neue Hinweis eine `#undef`-Direktive ist, die einen vorhandenen effektiven Hinweis angibt, löscht der neue Hinweis den vorhandenen Hinweis.

Die erste Regel bedeutet, dass effektive Hinweise von zuvor geöffneten Hinweisdateien geerbt werden. Die letzten beiden Regeln bedeuten, dass Hinweise, die später in der Suchreihenfolge auftreten, zuvor aufgetretene Hinweise überschreiben können. Sie können beispielsweise alle vorherigen Hinweise überschreiben, wenn Sie eine Hinweisdatei in dem Verzeichnis erstellen, das eine Quelldatei enthält.

Eine Darstellung, wie Hinweise gesammelt werden, finden Sie im Verlauf dieses Artikels im Abschnitt `Example`.

### <a name="syntax"></a>Syntax

Hinweise werden mit der gleichen Syntax erstellt und gelöscht, die die Präprozessordirektiven aufweisen, die Makros erstellen und löschen. Tatsächlich verwendet das Analysesystem den C/C++-Präprozessor, um die Hinweise auszuwerten. Weitere Informationen zu den Präprozessordirektiven finden Sie unter [#define Directive (C/C++) (#define-Direktive (C/C++))](../preprocessor/hash-define-directive-c-cpp.md) und [#undef Directive (C/C++) (#undef-Direktive (C/C++))](../preprocessor/hash-undef-directive-c-cpp.md).

Die einzigen ungewöhnlichen Syntaxelemente sind die Ersatzzeichenfolgen `@<`, `@=` und `@>`. Diese Ersatzzeichenfolgen sind für Hinweisdateien spezifisch und werden nur mit *Zuordnungsmakros* verwendet. Eine Zuordnung besteht aus mehreren Makros, die Daten, Funktionen oder Ereignisse mit anderen Daten, Funktionen oder Ereignishandlern in Verbindung bringen. `MFC` verwendet beispielsweise Zuordnungen, um [Meldungszuordnungen](../mfc/reference/message-maps-mfc.md) zu erstellen, und `ATL` verwendet Zuordnungen, um [Objektzuordnungen](../atl/reference/object-map-macros.md) zu erstellen. Die für die Hinweisdateien spezifischen Ersatzzeichenfolgen geben die Start-, Zwischen- und Endelemente einer Zuordnung an. Nur der Name eines Zuordnungsmakros ist relevant. Deshalb blendet jede Ersatzzeichenfolge die Implementierung des Makros absichtlich aus.

Hinweise verwenden folgende Syntax.

|Syntax|Bedeutung|
|------------|-------------|
|`#define` *Hinweisname* *Ersatzzeichenfolge*<br /><br /> `#define` *Hinweisname* `(` *Parameter*, ...`)`*Ersatzzeichenfolge*|Eine Präprozessordirektive, die einen neuen Hinweis definiert oder einen vorhandenen Hinweis neu definiert. Nach der Direktive ersetzt der Präprozessor jedes Vorkommen von *Hinweisname* im Quellcode mit *Ersatzzeichenfolge*.<br /><br /> Durch das zweite Syntaxformat wird ein funktionsähnlicher Hinweis definiert. Wenn ein funktionsähnlicher Hinweis im Quellcode vorkommt, ersetzt der Präprozessor zunächst jedes Vorkommen von *Parameter* in *Ersatzzeichenfolge* mit dem entsprechenden Argument im Quellcode. Anschließend wird *Hinweisname* durch *Ersatzzeichenfolge* ersetzt.|
|`@<`|Eine für Hinweisdateien spezifische *Ersatzzeichenfolge*, die den Anfang von einer Reihe von Zuordnungselementen definiert.|
|`@=`|Eine für Hinweisdateien spezifische *Ersatzzeichenfolge*, die ein Zwischenzuordnungselement definiert. Eine Zuordnung kann mehrere Zuordnungselemente enthalten.|
|`@>`|Eine für Hinweisdateien spezifische *Ersatzzeichenfolge*, die das Ende von einer Reihe von Zuordnungselementen definiert.|
|`#undef` *Hinweisname*|Die Präprozessordirektive, die einen vorhandenen Hinweis löscht. Der Name des Hinweises wird durch den Bezeichner *Hinweisname* bereitgestellt.|
|`//` *Kommentar*|Ein einzeiliger Kommentar.|
|`/*` *comment* `*/`|Ein mehrzeiliger Kommentar.|

## <a name="what-macros-require-a-hint"></a>Welche Makros erfordern einen Hinweis?

Bestimmte Arten von Makros können das Analysesystem beeinträchtigen. In diesem Abschnitt werden die Arten von Makros beschrieben, die Probleme verursachen können, sowie die Hinweistypen, die Sie erstellen können, um diese Probleme zu beheben.

### <a name="disruptive-macros"></a>Störende Makros

Einige Makros führen dazu, dass das Analysesystem den Quellcode falsch interpretiert. Diese können jedoch ignoriert werden, ohne die Suche zu beeinträchtigen. Die SAL-Makros ([Source Code Annotation Language](../c-runtime-library/sal-annotations.md)) werden beispielsweise in C++-Attribute aufgelöst, die Sie beim Suchen von Programmierfehlern unterstützen können. Wenn Sie SAL-Anmerkungen beim Durchsuchen von Code ignorieren möchten, sollten Sie eine Hinweisdatei erstellen, die diese ausblendet.

Im folgenden Quellcode ist der Parametertyp für die `FormatWindowClassName()`-Funktion `PXSTR`, und der Parametername ist `szBuffer`. Das Analysesystem verwechselt die SAL-Anmerkungen `_Pre_notnull_` und `_Post_z_` jedoch entweder mit dem Parametertyp oder mit dem Parameternamen.

**Quellcode:**

```cpp
static void FormatWindowClassName(_Pre_notnull__Post_z_ PXSTR szBuffer)
```

**Strategie:** NULL-Definition

Die Strategie besteht in dieser Situation darin, die SAL-Anmerkungen so zu behandeln, als wären sie nicht vorhanden. Geben Sie hierzu einen Hinweis an, dessen Ersatzzeichenfolge NULL ist. In Folge ignoriert das Analysesystem die Anmerkungen, und die **Klassenansicht** zeigt diese nicht an. (Visual C++ enthält eine integrierte Hinweisdatei, die SAL-Anmerkungen ausblendet.)

**Hinweisdatei:**

```cpp.hint
#define _Pre_notnull_
```

### <a name="concealed-cc-language-elements"></a>Ausgeblendete C/C++-Sprachelemente

Häufig ist der Grund dafür, dass das Analysesystem den Quellcode falsch interpretiert, dass ein Makro ein C++-Token für ein [Markierungszeichen](../cpp/punctuators-cpp.md) oder ein [Schlüsselwort](../cpp/keywords-cpp.md) ausblendet. Das bedeutet, dass ein Makro nur die Hälfte eines Paars von Markierungszeichen enthalten kann, z.B. `<>`, `[]`, `{}` und `()`.

Im folgenden Quellcode blendet das Makro `START_NAMESPACE` eine linke geschweifte Klammer (`{`) aus, die kein Paar bildet.

**Quellcode:**

```cpp
#define START_NAMESPACE namespace MyProject {
```

**Strategie:** direktes Kopieren

Wenn die Semantik eines Makros für die Suchfunktion wichtig ist, erstellen Sie einen Hinweis, der mit dem Makro identisch ist. Das Analysesystem löst das Makro in die Definition in der Hinweisdatei auf.

Wenn das Makro in der Quelldatei andere Makros enthält, sollten Sie beachten, dass diese nur interpretiert werden, wenn sie bereits in den effektiven Hinweisen enthalten sind.

**Hinweisdatei:**

```cpp.hint
#define START_NAMESPACE namespace MyProject {
```

### <a name="maps"></a>Karten

Eine Zuordnung besteht aus Makros, die ein Startelement, ein Endelement und null oder mehr Zwischenelemente festlegen. Das Analysesystem interpretiert Zuordnungen falsch, da jedes Zuordnungsmakro C/C++-Sprachelemente ausblendet und die Syntax einer vollständigen C/C++-Anweisung auf viele separate Makros verteilt ist.

Der folgende Quellcode definiert die Makros `BEGIN_CATEGORY_MAP`, `IMPLEMENTED_CATEGORY` und `END_CATEGORY_MAP`.

**Quellcode:**

```cpp
#define BEGIN_CATEGORY_MAP(x)\
static const struct ATL::_ATL_CATMAP_ENTRY* GetCategoryMap() throw() {\
static const struct ATL::_ATL_CATMAP_ENTRY pMap[] = {
#define IMPLEMENTED_CATEGORY( catid ) { _ATL_CATMAP_ENTRY_IMPLEMENTED, &catid },
#define END_CATEGORY_MAP()\
   { _ATL_CATMAP_ENTRY_END, NULL } };\
   return( pMap ); }
```

**Strategie:** Identifizieren von Zuordnungselementen

Geben Sie Hinweise für die Start-, Zwischen- und Endelemente einer Zuordnung an. Verwenden Sie die speziellen Ersatzzeichenfolgen für Zuordnungen (`@<`, `@=` und `@>`). Weitere Informationen finden Sie im Abschnitt `Syntax` dieses Artikels.

**Hinweisdatei:**

```cpp.hint
// Start of the map.
#define BEGIN_CATEGORY_MAP(x) @<
// Intermediate map element.
#define IMPLEMENTED_CATEGORY( catid ) @=
// Intermediate map element.
#define REQUIRED_CATEGORY( catid ) @=
// End of the map.
#define END_CATEGORY_MAP() @>
```

### <a name="composite-macros"></a>Zusammengesetzte Makros

Zusammengesetzte Makros enthalten einen oder mehrere Arten von Makros, die beim Analysesystem zu Verwechslungen führen.

Der folgende Quellcode enthält das Makro `START_NAMESPACE`, das den Anfang eines Namespacebereichs festlegt, sowie das Makro `BEGIN_CATEGORY_MAP`, das den Anfang einer Zuordnung festlegt.

**Quellcode:**

```cpp
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP
```

**Strategie:** direktes Kopieren

Erstellen Sie Hinweise für die Makros `START_NAMESPACE` und `BEGIN_CATEGORY_MAP`, und erstellen Sie dann einen Hinweis für das Makro `NSandMAP`, das mit dem übereinstimmt, das zuvor im Quellcode gezeigt wurde. Wenn ein zusammengesetztes Makro nur aus störenden Markos und Leerräumen besteht, können Sie alternativ einen Hinweis erstellen, dessen Ersatzzeichenfolge eine NULL-Definition ist.

Gehen Sie in diesem Beispiel davon aus, dass `START_NAMESPACE` wie in diesem Artikel unter `Concealed C/C++ Language Elements` beschrieben bereits einen Hinweis besitzt. Gehen Sie ebenfalls davon aus, dass `BEGIN_CATEGORY_MAP` wie zuvor unter `Maps` beschrieben einen Hinweis besitzt.

**Hinweisdatei:**

```cpp.hint
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP
```

### <a name="inconvenient-macros"></a>Unpraktische Makros

Einige Makros können vom Analysesystem interpretiert werden, der Quellcode ist jedoch schwer lesbar, da das Makro lang oder komplex ist. Aus Gründen der Lesbarkeit können Sie einen Hinweis bereitstellen, der die Anzeige des Makros vereinfacht.

**Quellcode:**

```cpp
#define STDMETHOD(methodName) HRESULT (STDMETHODCALLTYPE * methodName)
```

**Strategie:** Vereinfachung

Erstellen Sie einen Hinweis, der eine einfachere Makrodefinition anzeigt.

**Hinweisdatei:**

```cpp.hint
#define STDMETHOD(methodName) void* methodName
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Hinweise aus Hinweisdateien gesammelt werden. In diesem Beispiel werden keine STOP-Dateien verwendet.

Die folgende Abbildung stellt einige der physischen Verzeichnisse in einem Visual C++-Projekt dar. Hinweisdateien befinden sich in den Verzeichnissen `vcpackages`, `Debug`, `A1` und `A2`.

### <a name="hint-file-directories"></a>Hinweisdateiverzeichnisse

![Allgemeine und projektspezifische Hinweisdateiverzeichnisse](../ide/media/hintfile.png "Hinweisdatei")

### <a name="directories-and-hint-file-contents"></a>Verzeichnisse und Hinweisdateiinhalte

Die folgende Liste zeigt die Verzeichnisse in diesem Projekt an, die Hinweisdateien enthalten, sowie die Inhalte dieser Hinweisdateien. Es werden nur einige der vielen Hinweise in der Verzeichnishinweisdatei `vcpackages` aufgeführt.

- vcpackages

    ```cpp.hint
    // vcpackages (partial list)
    #define _In_
    #define _In_opt_
    #define _In_z_
    #define _In_opt_z_
    #define _In_count_(size)
    ```

- Debug

    ```cpp.hint
    // Debug
    #undef _In_
    #define OBRACE {
    #define CBRACE }
    #define RAISE_EXCEPTION(x) throw (x)
    #define START_NAMESPACE namespace MyProject {
    #define END_NAMESPACE }
    ```

- A1

    ```cpp.hint
    // A1
    #define START_NAMESPACE namespace A1Namespace {
    ```

- A2

    ```cpp.hint
    // A2
    #undef OBRACE
    #undef CBRACE
    ```

### <a name="effective-hints"></a>Effektive Hinweise

Die folgende Tabelle führt die effektiven Hinweise für die Quelldateien in diesem Projekt auf.

- Quelldatei: A1_A2_B.cpp

- Effektive Hinweise:

    ```cpp.hint
    // vcpackages (partial list)
    #define _In_opt_
    #define _In_z_
    #define _In_opt_z_
    #define _In_count_(size)
    // Debug...
    #define RAISE_EXCEPTION(x) throw (x)
    // A1
    #define START_NAMESPACE namespace A1Namespace {
    // ...Debug
    #define END_NAMESPACE }
    ```

Die folgenden Hinweise gelten für die vorangehende Liste.

- Die effektiven Hinweise stammen aus den Verzeichnissen `vcpackages`, `Debug`, `A1`, und `A2`.

- Die **#undef**-Direktive in der Hinweisdatei `Debug` hat den Hinweis `#define _In_` aus der Verzeichnishinweisdatei `vcpackages` gelöscht.

- Die Hinweisdatei im Verzeichnis `A1` definiert `START_NAMESPACE` neu.

- Der Hinweis `#undef` im Verzeichnis `A2` hat die Hinweise für `OBRACE` und `CBRACE` aus der Verzeichnishinweisdatei `Debug` gelöscht.

## <a name="see-also"></a>Siehe auch

[Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[#define-Direktive (C/C++)](../preprocessor/hash-define-directive-c-cpp.md)<br>
[#undef-Direktive (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md)<br>
[SAL-Anmerkungen](../c-runtime-library/sal-annotations.md)<br>
[Meldungszuordnungen](../mfc/reference/message-maps-mfc.md)<br>
[Meldungszuordnungsmakros](../atl/reference/message-map-macros-atl.md)<br>
[Objektzuordnungs-Makros](../atl/reference/object-map-macros.md)