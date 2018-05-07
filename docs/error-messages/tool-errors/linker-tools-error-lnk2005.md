---
title: Linkertoolfehler Lnk2005 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2005
dev_langs:
- C++
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f853bec220c7d46ed2a0c44ac1e1d45fbca8318f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2005"></a>Linkertoolfehler LNK2005
*Symbol* bereits im-Objekt definiert.  
  
Das Symbol *Symbol* wurde mehrmals definiert.   
  
Diesem Fehler folgt der schwerwiegende Fehler [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).  
  
### <a name="possible-causes-and-solutions"></a>Mögliche Ursachen und Lösungen  
  
Im Allgemeinen, dieser Fehler weist darauf hin Ihre unterbrochen der *eine Definition-Regel*, wodurch nur eine Definition für jede verwendete Vorlage, eine Funktion, ein Typ oder eine Objekt in einer bestimmten Objektdatei "und" nur eine Definition für die gesamte ausführbare Datei für extern sichtbaren Objekte oder Funktionen.  
  
Hier sind einige häufige Ursachen für diesen Fehler.  
  
-   Dieser Fehler kann auftreten, wenn eine Headerdatei eine Variable definiert. Wenn Sie diese Headerdatei in mehr als einer Quelldatei in Ihrem Projekt einfügen, ergibt z. B. ein Fehler auf:  
  
    ```h  
    // LNK2005_global.h  
    int global_int;  // LNK2005
    ```  
  
    Folgende Lösungen sind möglich:  
  
    -   Deklarieren Sie die Variable `extern` in der Headerdatei: `extern int global_int;`, definieren Sie ihn, und initialisieren Sie es wahlweise in nur eine Quelldatei: `int global_int = 17;`. Diese Variable ist jetzt ein globaler, dass Sie in beliebigen Quelldateien verwenden können, indem Sie sie deklarieren `extern`, z. B. indem Sie die Headerdatei einschließen. Wir empfehlen diese Lösung für Variablen, die global sein muss, aber Softwareentwicklung praktischen minimiert, globale Variablen.  
    
    -   Deklarieren Sie die Variable [statische](../../cpp/storage-classes-cpp.md#static): `static int static_int = 17;`. Dies schränkt den Bereich der Definition der aktuellen Objektdatei und ermöglicht mehrere Objektdateien, ihre eigenen Kopie der Variablen verfügen. Wird nicht empfohlen, dass Sie statische Variablen in den Headerdateien aufgrund potenzieller Probleme mit globalen Variablen definieren. Statische Variable Definitionen in den Quelldateien zu verschieben, die sie verwenden möchten.  
  
    -   Deklarieren Sie die Variable [Selectany](../../cpp/selectany.md): `__declspec(selectany) int global_int = 17;`. Das weist den Linker aus, um eine Definition für die Verwendung durch alle externen Verweise auswählen und verwerfen den Rest. Diese Lösung ist manchmal hilfreich, wenn Importbibliotheken kombinieren. Andernfalls wird kein diese als eine Möglichkeit zur Vermeidung von Linkerfehler empfohlen.  
  
-   Dieser Fehler kann auftreten, wenn eine Headerdatei eine Funktion definiert, die nicht `inline`. Wenn Sie diese Headerdatei in mehr als einer Quelldatei einschließen, erhalten Sie mehrere Definitionen der Funktion in der ausführbaren Datei.  
    
    ```h  
    // LNK2005_func.h  
    int sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```  
  
    Folgende Lösungen sind möglich:  
  
    -   Hinzufügen der `inline` Schlüsselwort, um die Funktion: 

        ```h  
        // LNK2005_func_inline.h  
        inline int sample_function(int k) { return 42 * (k % 167); }  
        ```  
  
    -   Aufheben der Headerdatei der Hauptteil der Funktion lassen Sie nur die Deklaration, und implementieren Sie die Funktion in eine und nur genau eine Quelldatei:  
  
        ```h  
        // LNK2005_func_decl.h  
        int sample_function(int);  
        ```  
  
        ```cpp  
        // LNK2005_func_impl.cpp  
        int sample_function(int k) { return 42 * (k % 167); }  
        ```  
-   Dieser Fehler kann auch auftreten, wenn Sie in einer Headerdatei Memberfunktionen außerhalb der Klassendeklaration definieren:  
  
    ```h  
    // LNK2005_member_outside.h  
    class Sample {
    public:
        int sample_function(int);  
    };
    int Sample::sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```  
  
    Um dieses Problem zu beheben, verschieben Sie die Funktionsdefinitionen des Elements innerhalb der Klasse. Memberfunktionen, die innerhalb einer Klassendeklaration definiert sind implizit Inline.  
  
    ```h  
    // LNK2005_member_inline.h  
    class Sample {
    public:
        int sample_function(int k) { return 42 * (k % 167); }  
    };
    ```  
  
-   Dieser Fehler kann auftreten, wenn Sie mehr als eine Version der Standardbibliothek oder CRT verknüpfen. Wenn Sie versuchen, die sowohl den Einzelhandel und CRT-Debugbibliotheken oder die statischen und dynamischen Versionen einer Bibliothek oder zwei verschiedene Versionen einer standard-Bibliothek mit der ausführbaren Datei zu verknüpfen, kann dieser Fehler beispielsweise oft gemeldet werden. Um dieses Problem zu beheben, entfernen Sie alle außer einer Kopie für jede Bibliothek von Link-Befehl. Wir empfehlen nicht Mischen Einzelhandel und Bibliotheken oder verschiedene Versionen einer Bibliothek, in die ausführbare Datei zu debuggen.  
  
    Geben Sie anzuweisen, den Linker an, in der Befehlszeile andere Bibliotheken als die Standardwerte verwenden der Bibliotheken verwenden, und die [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) Option aus, um die Standardbibliotheken zu deaktivieren. Fügen Sie in der IDE Verweise im Projekt an, die Bibliotheken, und öffnen Sie dann die **Eigenschaftenseiten** Dialogfeld für das Projekt, und klicken Sie in der **Linker**, **Eingabe** Eigenschaft Seite, legen Sie entweder **alle Standardbibliotheken ignorieren**, oder **bestimmte Standardbibliotheken ignorieren** Eigenschaften, um die Standardbibliotheken zu deaktivieren.   
  
-   Dieser Fehler kann auftreten, wenn Sie die Verwendung der statischen und dynamischen Bibliotheken kombinieren, bei der Verwendung der ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) Option. Dieser Fehler kann beispielsweise auftreten, wenn Sie eine DLL für die Verwendung in der ausführbaren Datei, das einen Link in der statischen CRT erstellen. Um dieses Problem zu beheben, verwenden Sie nur statische Bibliotheken oder nur dynamische Bibliotheken, für die gesamte ausführbare und für alle Bibliotheken, die Sie erstellen, um in die ausführbare Datei zu verwenden.  
  
-   Dieser Fehler kann auftreten, ist das Symbol eine Paketfunktion (erstellt durch Kompilierung mit [/Gy](../../build/reference/gy-enable-function-level-linking.md)) und in mehr als eine Datei enthalten war, aber zwischen Kompilationen geändert. Um dieses Problem zu beheben, kompilieren Sie alle Dateien, die die Paketfunktion enthalten.  
  
-   Dieser Fehler kann auftreten, wenn das Symbol ist in zwei Memberobjekten in verschiedenen Bibliotheken unterschiedlich definiert, und beide Memberobjekte verwendet werden. Eine Möglichkeit, dieses Problem zu beheben, wenn die Bibliotheken statisch verknüpft sind, werden die Member-Objekt aus nur eine Bibliothek, und schließen diese Bibliothek zuerst in der Linker-Befehlszeile ab. Wenn beide Symbole verwenden möchten, müssen Sie eine Möglichkeit, diese Unterscheidung erstellen. Wenn Sie die Bibliotheken aus der Quelle erstellen können, können Sie z. B. jede Bibliothek in einen eindeutigen Namespace umschließen. Alternativ können Sie eine neue Wrapperbibliothek erstellen, die eindeutige Namen für die Verweise auf eine der ursprünglichen Bibliotheken umschließen Sie die neue Bibliothek verknüpfen, um die ursprüngliche Bibliothek, und verknüpfen die ausführbare Datei für die neue Bibliotheksfreigabe anstelle der ursprünglichen Bibliothek verwendet.  
  
-   Dieser Fehler kann auftreten, wenn ein `extern const` Variable zweimal definiert ist, und einen anderen Wert in jeder Definition aufweist. Um dieses Problem zu beheben, definieren Sie die Konstanten nur einmal oder Namespaces verwenden oder `enum class` Definitionen, um die Konstanten zu unterscheiden.  
  
-   Dieser Fehler kann auftreten, wenn Sie uuid.lib in Kombination mit anderen .lib-Dateien verwenden, die GUIDs (z. B. oledb.lib und adsiid.lib) definieren. Zum Beispiel:  
  
    ```Output  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     Um dieses Problem zu beheben, fügen [/Force: Multiple](../../build/reference/force-force-file-output.md) auf die Linker-Befehlszeilenoptionen, und stellen Sie sicher, dass uuid.lib die zuerst referenzierte Bibliothek ist.
  
## <a name="additional-information"></a>Zusätzliche Informationen  
  
Wenn Sie eine ältere Version des Toolsets verwenden, finden Sie in folgenden Knowledge Base-Artikeln für Weitere Informationen zu spezifischen Ursachen für diesen Fehler:  
  
-   [Ein LNK2005-Fehler tritt bei der CRT-Bibliothek und MFC-Bibliotheken, in der falschen Reihenfolge in Visual C++ verknüpft sind](https://support.microsoft.com/kb/148652)  
  
-   [FIX: Global überladener Delete-Operator verursacht LNK2005](https://support.microsoft.com/kb/140440)  
  
-   [Sie erhalten LNK2005-Fehler beim Kompilieren eines ATL-ausführbare Datei (.exe)-Projekts in Visual C++](https://support.microsoft.com/kb/184235).  
  
