---
title: Linkertoolfehler LNK2005
ms.date: 11/04/2016
f1_keywords:
- LNK2005
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
ms.openlocfilehash: 8b4f75b90254c702ecb2afb65108278a59df69ed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299204"
---
# <a name="linker-tools-error-lnk2005"></a>Linkertoolfehler LNK2005

> *Symbol* bereits im-Objekt definiert.

Das Symbol *Symbol* wurde mehrmals definiert.

Diesem Fehler folgt der schwerwiegende Fehler [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).

### <a name="possible-causes-and-solutions"></a>Mögliche Ursachen und Lösungen

Dieser Fehler bedeutet in der Regel, sind Sie nicht die *eine Richtliniendefinition*, wodurch nur eine Definition für alle verwendeten Vorlage, eine Funktion, ein Typ oder eine Objekt in einer Datei für die angegebene Objekt und nur eine Definition für die gesamte ausführbare Datei für extern sichtbaren Objekte oder Funktionen.

Hier sind einige häufige Ursachen für diesen Fehler.

- Dieser Fehler kann auftreten, wenn eine Headerdatei eine Variable definiert. Z. B. Wenn Sie diese Headerdatei in mehr als einer Quelldatei im Projekt einschließen, tritt ein Fehler auf:

    ```h
    // LNK2005_global.h
    int global_int;  // LNK2005
    ```

   Folgende Lösungen sind möglich:

   - Deklarieren Sie die Variable `extern` in der Headerdatei: `extern int global_int;`, definieren Sie es dann und initialisieren Sie es optional in nur eine Quelldatei: `int global_int = 17;`. Diese Variable ist nun eine globale, dass Sie in jeder Quelldatei verwenden können, indem Sie es deklarieren `extern`, z. B. durch Einschließen der Headerdatei. Es wird empfohlen, diese Lösung für Variablen, die global sein muss, jedoch gute Softwareentwicklung Praxis hält, globale Variablen.

   - Deklarieren Sie die Variable [statische](../../cpp/storage-classes-cpp.md#static): `static int static_int = 17;`. Dies schränkt den Bereich der Definition der aktuellen Objektdatei und ermöglicht mehrere Objektdateien, um ihre eigene Kopie der Variablen zu erhalten. Es wird nicht empfohlen, dass Sie statische Variablen in den Headerdateien aufgrund der Vermeidung von Verwirrung bezüglich mit globalen Variablen definieren. Möchten Sie statische Variable Definitionen in die Quelldateien zu verschieben, die diese verwenden.

   - Deklarieren Sie die Variable [Selectany](../../cpp/selectany.md): `__declspec(selectany) int global_int = 17;`. Dies weist den Linker aus, wählen Sie eine Definition für die Verwendung durch alle externen Verweise und den Rest zu verwerfen. Diese Lösung ist manchmal hilfreich, wenn es sich bei Importbibliotheken kombinieren. Andernfalls, empfehlen wir nicht es als eine Möglichkeit zum Linker-Fehler zu vermeiden.

- Dieser Fehler kann auftreten, wenn eine Headerdatei eine Funktion definiert, die nicht `inline`. Wenn Sie in mehr als einer Quelldatei diese Headerdatei einschließen, erhalten Sie mehrere Definitionen der Funktion in der ausführbaren Datei.

    ```h
    // LNK2005_func.h
    int sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   Folgende Lösungen sind möglich:

   - Hinzufügen der `inline` Schlüsselwort, um die Funktion:

        ```h
        // LNK2005_func_inline.h
        inline int sample_function(int k) { return 42 * (k % 167); }
        ```

   - Entfernen Sie der Hauptteil der Funktion aus der Headerdatei, und klicken Sie dann lassen Sie nur die Deklaration dann implementieren Sie die Funktion in nur eine Quelldatei:

        ```h
        // LNK2005_func_decl.h
        int sample_function(int);
        ```

        ```cpp
        // LNK2005_func_impl.cpp
        int sample_function(int k) { return 42 * (k % 167); }
        ```

- Dieser Fehler kann auch auftreten, wenn Sie in einer Headerdatei Memberfunktionen außerhalb der Klassendeklaration definieren:

    ```h
    // LNK2005_member_outside.h
    class Sample {
    public:
        int sample_function(int);
    };
    int Sample::sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   Um dieses Problem zu beheben, verschieben Sie die Memberdefinitionen für die Funktion innerhalb der Klasse. Memberfunktionen, die innerhalb einer Klassendeklaration definiert sind implizit Inline.

    ```h
    // LNK2005_member_inline.h
    class Sample {
    public:
        int sample_function(int k) { return 42 * (k % 167); }
    };
    ```

- Dieser Fehler kann auftreten, wenn Sie mehr als eine Version der CRT oder standard-Bibliothek verknüpfen. Wenn Sie versuchen, die sowohl Einzelhandels- und CRT-Debugbibliotheken oder die statischen und dynamischen Versionen einer Bibliothek oder zwei verschiedene Versionen einer standard-Bibliothek mit der ausführbaren Datei verknüpfen, kann dieser Fehler beispielsweise oft gemeldet werden. Um dieses Problem zu beheben, entfernen Sie alle bis auf eine Kopie der einzelnen Bibliotheken aus dem Linkbefehl. Wir empfehlen nicht, Sie im Einzelhandel kombinieren und zu debuggen, Bibliotheken oder verschiedene Versionen einer Bibliothek, in die ausführbare Datei.

   Teilen Sie den Linker an, verwenden Sie Bibliotheken als die Standardwerte in der Befehlszeile, geben Sie die Bibliotheken, und verwenden Sie die [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) Option aus, um die Standardbibliotheken zu deaktivieren. Fügen Sie in der IDE Verweise zu Ihrem Projekt an die Bibliotheken, und öffnen Sie dann die **Eigenschaftenseiten** Dialogfeld für das Projekt, und klicken Sie in der **Linker**, **Eingabe** Eigenschaft Seite, legen Sie entweder **alle Standardbibliotheken ignorieren**, oder **bestimmte Standardbibliotheken ignorieren** Eigenschaften, die die Standardbibliotheken zu deaktivieren.

- Dieser Fehler kann auftreten, wenn Sie die Verwendung von statischen und dynamischen Bibliotheken kombinieren, bei der Verwendung der ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) Option. Dieser Fehler kann beispielsweise auftreten, wenn Sie eine DLL für die Verwendung in der ausführbaren Datei, die in der statischen CRT verknüpft erstellen. Um dieses Problem zu beheben, verwenden Sie nur statische Bibliotheken oder nur dynamische Bibliotheken, für die gesamte ausführbare Datei, und für alle Bibliotheken, die Sie erstellen, um in die ausführbare Datei zu verwenden.

- Dieser Fehler kann auftreten, wenn das Symbol eine Paketfunktion (erstellt durch Kompilierung mit [/Gy](../../build/reference/gy-enable-function-level-linking.md)) und es in mehr als eine Datei enthalten war, aber zwischen Kompilationen geändert. Um dieses Problem zu beheben, kompilieren Sie alle Dateien, die die Funktion des App-Pakete enthalten.

- Dieser Fehler kann auftreten, wenn das Symbol ist in zwei Memberobjekten in verschiedenen Bibliotheken unterschiedlich definiert, und beide Memberobjekte werden verwendet. Eine Möglichkeit, dieses Problem zu beheben, wenn die Bibliotheken statisch verknüpft sind, werden die Member-Objekt aus nur einer Bibliothek, und diese Bibliothek zunächst auf der Befehlszeile des Linkers enthalten ab. Um beide Symbole zu verwenden, müssen Sie eine Möglichkeit, um sie zu unterscheiden erstellen. Wenn Sie die Bibliotheken aus der Quelle erstellen können, können Sie z. B. jede Bibliothek in einen eindeutigen Namespace umschließen. Alternativ können Sie eine neue Wrapperbibliothek erstellen, die eindeutige Namen zum Verweisen auf eine der ursprünglichen Bibliotheken zu umschließen, verknüpfen die neue Bibliothek, mit der ursprünglichen Bibliothek, und verknüpfen die ausführbare Datei mit der neuen Bibliothek anstelle der ursprünglichen Bibliothek verwendet.

- Dieser Fehler kann auftreten, wenn ein `extern const` Variable zweimal definiert ist, und verfügt über einen anderen Wert in jeder Definition. Um dieses Problem zu beheben, Definieren der Konstanten nur einmal, oder Verwenden von Namespaces oder `enum class` Definitionen von Konstanten zu unterscheiden.

- Dieser Fehler kann auftreten, wenn Sie uuid.lib in Kombination mit anderen .lib-Dateien verwenden, die GUIDs (zum Beispiel oledb.lib und adsiid.lib) zu definieren. Zum Beispiel:

    ```Output
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject
    already defined in uuid.lib(go7.obj)
    ```

   Um dieses Problem zu beheben, fügen [Multiple](../../build/reference/force-force-file-output.md) zu den Optionen des Linkers über die Befehlszeile, und stellen Sie sicher, dass uuid.lib die zuerst referenzierte Bibliothek ist.
