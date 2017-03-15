---
title: "Hinweisdateien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cpp.hint"
  - "vc.hint.file"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STOP-Datei"
  - "cpp.hint"
  - "HINT-Datei"
  - "cpp.stop"
  - "Klassenansicht, Hinweisdatei"
ms.assetid: 17194f66-cf62-4523-abec-77db0675ab65
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# Hinweisdateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein *Hint-Datei* unterstützt die Visual Studio IDE (IDE) interpretiert, Visual C++-Bezeichner, z. B. die Namen der Funktionen und Makros. Wenn Sie eine Visual C++-Projekts, der IDE öffnen *Analysesystem* analysiert den Code in jeder Quelldatei im Projekt und erfasst Informationen zu allen Bezeichnern. Die IDE diese Informationen verwendet, um Funktionen zu unterstützen, z. B. die **Klassenansicht** Browser und **Navigationsleiste**.  
  
 Eingeführte Analysesystem [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)], versteht die C/C++-Syntax, aber eine Anweisung, die ein Makro enthält fehlinterpretiert werden kann. Die Anweisung kann falsch interpretiert werden, wenn das Makro bewirkt, der Quellcode dass und syntaktisch falsch geschrieben. Die Anweisung wird syntaktisch richtig, wenn der Quellcode kompiliert wird und der Preprocesser ersetzt die [Makrobezeichner](../preprocessor/hash-define-directive-c-cpp.md) mit ihrer Definition. Das Analysesystem funktioniert, ohne das Projekt zu erstellen, da sie Hinweisdateien verwendet, um Makros zu interpretieren. Daher z. B. feature eine Durchsuchen **Klassenansicht** ist sofort verfügbar.  
  
 Hint-Datei enthält benutzerdefinierbare *Hinweise*, die dieselbe Syntax wie C/C++-Makrodefinitionen haben. Visual C++ enthält eine integrierten Hint-Datei, die für die meisten Projekte ausreichend ist, aber Sie können eigene Hinweisdateien zum Verbessern der Bezeichner in Visual Studio behandelt erstellen.  
  
> [!IMPORTANT]
>  Wenn Sie ändern oder eine Hint-Datei hinzufügen, müssen Sie die SDF-Datei und/oder VC.db-Datei in der Projektmappe, damit die Änderungen wirksam werden löschen.  
  
## <a name="scenario"></a>Szenario  
 Angenommen, der folgende Code in einer Quelldatei, die Sie durch Überprüfen der **Klassenansicht** Browser. Die `STDMETHOD` Makro deklariert eine Methode namens `myMethod` die einen Parameter und gibt einen Zeiger auf ein **HRESULT**.  
  
```  
// Source code file.  
STDMETHOD(myMethod)(int parameter1);  
```  
  
 Die folgenden Makrodefinitionen befinden sich in einer separaten Headerdatei.  
  
```  
// Header file.  
#define STDMETHOD(method) HRESULT (STDMETHODCALLTYPE * method)  
#define STDMETHODCALLTYPE __stdcall  
#define HRESULT void*  
```  
  
 Das Analysesystem Quellcode nicht interpretieren kann, da eine Funktion mit dem Namen STDMETHOD deklariert werden angezeigt, und diese Deklaration ist syntaktisch falsch, da sie zwei Parameterlisten enthält. Das Analysesystem wird zum Ermitteln der Definitionen für die Header-Datei nicht geöffnet die `STDMETHOD`, `STDMETHODCALLTYPE`, und `HRESULT` Makros. Da das Analysesystem nicht interpretieren kann die `STDMETHOD` -Makro, es die gesamte Anweisung ignoriert, und setzt die Analyse fort.  
  
 Das Analysesystem verwendet keine Headerdateien, da das Projekt möglicherweise auf einem oder mehreren wichtigen Headerdateien abhängen. Wenn eine Headerdatei ändert, müssen möglicherweise das Analysesystem alle Headerdateien im Projekt nochmals die verlangsamt die Leistung der IDE. Stattdessen verwendet das Analysesystem Hinweise, die angeben, wie behandeln die `STDMETHOD`, `STDMETHODCALLTYPE`, und `HRESULT` Makros.  
  
 Woher wissen Sie, dass ein Hinweis benötigt? Und wenn ein Hinweis benötigt wird, welche Art sollten Sie erstellen? Ein Zeichen, dass ein Hinweis benötigt wird, ist wenn die Ansicht eines Bezeichners in **Klassenansicht** stimmt nicht mit der Ansicht in der **Editor**. Z. B. **Klassenansicht** möglicherweise nicht angezeigt, die ein Klassenmember, die Sie kennen vorhanden ist, oder der Name des Members ist falsch. Weitere Informationen zu den Arten von hinweisen, die allgemeine Probleme beheben, finden Sie in der was-Makros erfordern ein Hinweis? weiter unten in diesem Thema.  
  
## <a name="architecture"></a>Architektur  
 Hinweisdateien beziehen sich auf physische Verzeichnisse, nicht auf die logischen Verzeichnisse in dargestellten **Projektmappen-Explorer**. Sie müssen nicht das Projekt für die Hint-Datei wirksam Hint-Datei hinzugefügt. Das Analysesystem verwendet Hinweisdateien nur, wenn es Quelldateien analysiert.  
  
 Jede Hint-Datei heißt **cpp.hint**. Daher viele Verzeichnisse können Hint-Datei enthalten, aber nur ein Hint-Datei in einem bestimmten Verzeichnis auftreten kann.  
  
 Ihr Projekt kann von 0 (null) oder mehrere Hinweisdateien beeinflusst werden. Wenn keine Hinweisdateien vorhanden sind, verwendet das Analysesystem Fehler Wiederherstellungstechniken unlesbare Quellcode ignoriert werden sollen. Andernfalls verwendet das Analysesystem die folgende Strategie zum Suchen und Hinweise zu sammeln.  
  
### <a name="search-order"></a>Suchreihenfolge  
 Das Analysesystem sucht Verzeichnissen nach Hinweisdateien in der folgenden Reihenfolge.  
  
-   Das Verzeichnis, das Installationspaket für Visual C++ enthält (**Vcpackages**). Dieses Verzeichnis enthält eine integrierte Hint-Datei, die Symbole in häufig verwendeten Systemdateien, z. B. beschreibt **windows.h**. Daher erbt das Projekt automatisch die meisten der Hinweise, die er benötigt.  
  
-   Der Pfad vom Stammverzeichnis einer Quelldatei in das Verzeichnis, das die Quelldatei selbst enthält. In einem normalen Visual C++-Projekt enthält das Stammverzeichnis die Projektmappe oder das Projekt die Datei.  
  
     Die Ausnahme von dieser Regel ist wenn ein *Stoppdatei* befindet sich im Pfad zur Quelldatei. Eine Stoppdatei enthält zusätzliche Kontrolle über die Suchreihenfolge und ist eine Datei mit dem Namen **cpp.stop**. Statt aus dem Stammverzeichnis, durchsucht das Analysesystem aus dem Verzeichnis mit der Stoppdatei in das Verzeichnis, die die Quelldatei enthält. In einem typischen Projekt benötigen Sie keine Stoppdatei.  
  
### <a name="hint-gathering"></a>Erfassen von Hinweisen  
 Hint-Datei enthält keine oder mehrere *Hinweise*. Ein Hinweis wird definiert oder wie ein C/C++-Makro gelöscht. D. h. die `#define` Präprozessordirektive erstellt oder definiert einen Hinweis neu und `#undef` -Direktive löscht einen Hinweis.  
  
 Das Analysesystem öffnet jede Hint-Datei in den Suchergebnissen weiter oben beschriebenen, sammelt die Hinweise aller Dateien in einen Satz von *effektiven Hinweise*, und klicken Sie dann die effektiven Hinweise interpretiert die Bezeichner im Code verwendet.  
  
 Das Analysesystem verwendet die folgenden Regeln, um Hinweise zu sammeln.  
  
-   Wenn der neue Hinweis einen Namen, der noch nicht definiert ist angibt, fügt der neue Hinweis den zum effektiven Hinweisen.  
  
-   Wenn der neue Hinweis einen Namen, der bereits definiert ist angibt, wird der neue Hinweis den vorhandenen Hinweis neu definiert.  
  
-   Wenn der neue Hinweis eine `#undef` Richtlinie, die einen vorhandenen effektiven Hinweis angibt, löscht der neue Hinweis den vorhandenen Hinweis.  
  
 Die erste Regel besagt, dass effektive Hinweise von zuvor geöffneten Hinweisdateien geerbt werden. Die letzten beiden Regeln bedeuten, dass Hinweise, die später in der Suchreihenfolge Hinweise überschreiben können, die zuvor aufgetreten sind. Beispielsweise können Sie alle vorherigen Hinweise überschreiben, wenn Sie eine Hint-Datei im Verzeichnis erstellen, die eine Quelldatei enthält.  
  
 Eine Darstellung von Hinweisen werden, finden Sie unter der `Example` Weiter unten in diesem Thema.  
  
### <a name="syntax"></a>Syntax  
 Hinweise werden erstellt und gelöscht, die mit derselben Syntax wie die Präprozessordirektiven, die Makros erstellen und löschen. Das Analysesystem verwendet die C/C++-Präprozessor Hinweise ausgewertet. Weitere Informationen zu den Präprozessordirektiven, finden Sie unter [#define-Direktive (C/C++)](../preprocessor/hash-define-directive-c-cpp.md) und [#undef-Direktive (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md).  
  
 Die einzigen außergewöhnlichen Syntaxelemente sind die `@<`, `@=`, und `@>` Ersatzzeichenfolgen. Hierbei handelt es sich um Hinweisdateien spezifische Ersetzungszeichenfolgen, die nur mit verwendet werden *Zuordnung* Makros. Eine Zuordnung ist eine Reihe von Makros, die Daten, Funktionen oder Ereignissen auf andere Daten, Funktionen oder Ereignishandler beziehen. Z. B. `MFC` verwendet Zuordnungen erstellen [meldungszuordnungen](../mfc/reference/message-maps-mfc.md), und `ATL` verwendet Zuordnungen erstellen [-Objekt Maps](../atl/reference/object-map-macros.md). Die Hinweisdateien spezifische Ersetzungszeichenfolgen geben die Start-, zwischen- und Endelemente Elemente einer Zuordnung an. Nur der Namen eines Makros für die Karte dar. Daher blendet jede Ersetzungszeichenfolge die Implementierung des Makros absichtlich aus.  
  
 Hinweise verwenden die folgende Syntax.  
  
|Syntax|Bedeutung|  
|------------|-------------|  
|`#define` *Hinweis-Name* *Ersetzungszeichenfolge*<br /><br /> `#define` *Hinweis-Name* `(` *Parameter*, ...`)`*Ersetzungszeichenfolge*|Eine Präprozessordirektive, die einen neuen Hinweis definiert oder einen vorhandenen Hinweis definiert. Nach der Direktive ersetzt der Präprozessor jedes Vorkommen von *Hinweis-Name* im Quellcode mit *Ersetzungszeichenfolge*.<br /><br /> Das zweite Syntaxformat definiert einen funktionsähnliches Hinweis. Tritt ein funktionsähnliches Hinweis im Quellcode, ersetzt der Präprozessor zuerst jedes Vorkommen von *Parameter* in *Ersetzungszeichenfolge* durch das entsprechende Argument in Quellcode, und klicken Sie dann ersetzt *Hinweis-Name* mit *Ersetzungszeichenfolge*.|  
|`@<`|Eine bestimmte Hinweisdateien *Ersetzungszeichenfolge* der der Anfang einer Gruppe von Zuordnungselementen angibt.|  
|`@=`|Eine bestimmte Hinweisdateien *Ersetzungszeichenfolge* der ein Element Zwischenelement der Zuordnung angibt. Eine Karte kann mehrere Elemente enthalten.|  
|`@>`|Eine bestimmte Hinweisdateien *Ersetzungszeichenfolge* der das Ende einer Gruppe von Zuordnungselementen angibt.|  
|`#undef` *Hinweis-Name*|Die Präprozessordirektive, die einen vorhandenen Hinweis löscht. Der Name des Hinweises angegeben wird, indem die *Hinweis-Name* Bezeichner.|  
|`//` *Kommentar*|Ein einzeiliger Kommentar.|  
|`/*` *Kommentar* `*/`|Einen mehrzeiligen Kommentar.|  
  
## <a name="what-macros-require-a-hint"></a>Welche Makros erfordern einen Hinweis?  
 Bestimmte Typen von Makros können das Analysesystem beeinträchtigen. Dieser Abschnitt beschreibt die Typen von Makros, die zu einem Problem führen können, und den Typ der Hinweis, dass Sie erstellen können, um dieses Problem zu lösen.  
  
### <a name="disruptive-macros"></a>Störende Makros  
 Einige Makros dazu führen, dass das Analysesystem Quellcode falsch interpretiert, aber ohne Beeinträchtigung des Browsers ignoriert werden können. Zum Beispiel die Source Code Annotation Language ([SAL](../c-runtime-library/sal-annotations.md)) Makros, die in C++-Attribute, mit denen Sie Programmierfehler finden zu beheben. Wenn Sie SAL-Anmerkungen zu ignorieren, da Sie Code suchen möchten, empfiehlt es sich, eine Hint-Datei zu erstellen, die Anmerkung ausgeblendet.  
  
 Im folgenden Code, der Parametertyp für die `FormatWindowClassName()` -Funktion ist `PXSTR`, und der Parametername ist `szBuffer`. Allerdings die Analyse System Fehler der `_Pre_notnull_` und `_Post_z_` SAL-Anmerkungen für den Parametertyp oder der Name des Parameters.  
  
 **Quellcode:**  
  
```  
static void FormatWindowClassName(_Pre_notnull__Post_z_ PXSTR szBuffer)  
```  
  
 **Strategie:** Null-Definition  
  
 Die Strategie in dieser Situation ist die SAL-Anmerkungen behandelt, als ob sie nicht vorhanden war. Geben Sie hierzu einen Hinweis an, dessen Ersetzungszeichenfolge null ist. Infolgedessen ignoriert das Analysesystem die Anmerkungen und **Klassenansicht** Browser nicht angezeigt. (Visual C++ umfasst eine integrierte Hint-Datei, die SAL-Anmerkung ausblendet.)  
  
 **Hint-Datei:**  
  
```  
#define _Pre_notnull_  
```  
  
### <a name="concealed-cc-language-elements"></a>Verborgene C/C++-Sprachelemente  
 Ist ein häufiger Grund, dass das Analysesystem Quellcode Datenpakete falsch interpretiert wird, wenn ein Makro blendet Sie aus einer C/C++- [Markierungszeichen](../cpp/punctuators-cpp.md) oder [Schlüsselwort](../cpp/keywords-cpp.md) token. D. h. ein Makro enthalten nur einen Teil der Markierungszeichen, wie z. B. `<>`, `[]`, `{}`, und `()`.  
  
 Im folgenden Code der `START_NAMESPACE` Makro blendet eine linke geschweifte Klammer (`{`).  
  
 **Quellcode:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
 **Strategie:** direkte Kopie  
  
 Wenn die Semantik eines Makros für die Browsererfahrung entscheidend sind, erstellen Sie einen Hinweis, der mit dem Makro identisch ist. Das Analysesystem löst das Makro in der Definition in der Hint-Datei.  
  
 Beachten Sie, dass das Makro in der Quelldatei andere Makros enthält, die Makros interpretiert werden, nur, wenn sie bereits in der Menge der effektiven Hinweise sind.  
  
 **Hint-Datei:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
### <a name="maps"></a>Zuordnungen  
 Eine Zuordnung besteht aus Makros, die ein Startelement EndElement und keine oder mehrere Zwischenelemente festlegen. Das Analysesystem Datenpakete falsch interpretiert wird Maps da jedes Makro Map C/C++-Sprachelemente ausgeblendet, und die Syntax der vollständige C/C++-Anweisung über viele separate Makros verteilt ist.  
  
 Der folgende Quellcode definiert die `BEGIN_CATEGORY_MAP`, `IMPLEMENTED_CATEGORY`, und `END_CATEGORY_MAP` Makros.  
  
 **Quellcode:**  
  
```  
#define BEGIN_CATEGORY_MAP(x)\  
static const struct ATL::_ATL_CATMAP_ENTRY* GetCategoryMap() throw() {\  
static const struct ATL::_ATL_CATMAP_ENTRY pMap[] = {  
#define IMPLEMENTED_CATEGORY( catid ) { _ATL_CATMAP_ENTRY_IMPLEMENTED, &catid },  
#define END_CATEGORY_MAP()\  
   { _ATL_CATMAP_ENTRY_END, NULL } };\  
   return( pMap ); }  
```  
  
 **Strategie:** identifizieren Zuordnungselementen  
  
 Geben Sie Hinweise für die Start-, Mittel-(sofern vorhanden) und einer Zuordnung. Verwenden Sie die Ersatzzeichenfolgen spezielle Zuordnung `@<`, `@=`, und `@>`. Weitere Informationen finden Sie unter den `Syntax` in diesem Thema.  
  
 **Hint-Datei:**  
  
```  
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
 Zusammengesetzte Makros enthalten ein oder mehrere Typen von Makros, die das Analysesystem durcheinanderbringen.  
  
 Im folgenden Quellcode enthält die `START_NAMESPACE` -Makro, das den Beginn eines Bereichs Namespace angibt, und die `BEGIN_CATEGORY_MAP` -Makro, das den Beginn einer Zuordnung angibt.  
  
 **Quellcode:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
 **Strategie:** direkte Kopie  
  
 Hinweise zum Erstellen der `START_NAMESPACE` und `BEGIN_CATEGORY_MAP` Makros, und erstellen Sie einen Hinweis für die `NSandMAP` Makro, das gleiche wie zuvor für den Quellcode dargestellt ist. Alternativ können Sie ein zusammengesetztes Makro nur aus störenden Makros und Leerstellen umfasst, können Sie einen Hinweis definieren, dessen Ersetzungszeichenfolge eine null-Definition ist.  
  
 In diesem Beispiel wird davon `START_NAMESPACE` bereits einen Hinweis wie in diesem Thema in der `Concealed C/C++ Language Elements` Untertitel. Und vorausgesetzt `BEGIN_CATEGORY_MAP` verfügt über einen Hinweis, wie zuvor im `Maps`.  
  
 **Hint-Datei:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
### <a name="inconvenient-macros"></a>Umständliche Makros  
 Einige Makros können vom Analysesystem interpretiert werden, aber der Quellcode ist schwer zu lesen, da das Makro lang oder komplex ist. Aus Gründen der besseren Lesbarkeit können Sie einen Hinweis bereitstellen, der die Anzeige des Makros vereinfacht.  
  
 **Quellcode:**  
  
```  
#define STDMETHOD(methodName) HRESULT (STDMETHODCALLTYPE * methodName)  
```  
  
 **Strategie:** Vereinfachung  
  
 Erstellen Sie einen Hinweis, der eine einfachere Makrodefinition anzeigt.  
  
 **Hint-Datei:**  
  
```  
#define STDMETHOD(methodName) void* methodName  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie Hinweise aus Hinweisdateien zusammengefasst werden. Stoppdateien werden in diesem Beispiel nicht verwendet.  
  
 Die folgende Abbildung stellt einige physische Verzeichnisse in einem Visual C++-Projekt. Hinweisdateien befinden sich der `vcpackages`, `Debug`, `A1`, und `A2` Verzeichnisse.  
  
### <a name="hint-file-directories"></a>Hinweisdateiverzeichnisse  
 ![Allgemeine und Projekt &#45; bestimmte Hinweisdateiverzeichnisse.](../ide/media/hintfile.png "HintFile")  
  
### <a name="directories-and-hint-file-contents"></a>Verzeichnisse und Inhalt der Hint-Datei  
 Die folgende Liste enthält die Verzeichnisse in diesem Projekt, die Hinweisdateien und den Inhalt dieser Dateien Hinweis enthalten. Nur einige der vielen Hinweise in der `vcpackages` Directory Hint-Datei aufgeführt sind.  
  
-   vcpackages  
  
    ```  
    // vcpackages (partial list)  
    #define _In_  
    #define _In_opt_  
    #define _In_z_  
    #define _In_opt_z_  
    #define _In_count_(size)  
    ```  
  
-   Debuggen  
  
    ```  
    // Debug  
    #undef _In_  
    #define OBRACE {  
    #define CBRACE }  
    #define RAISE_EXCEPTION(x) throw (x)  
    #define START_NAMESPACE namespace MyProject {  
    #define END_NAMESPACE }  
    ```  
  
-   A1  
  
    ```  
    // A1  
    #define START_NAMESPACE namespace A1Namespace {  
    ```  
  
-   A2  
  
    ```  
    // A2  
    #undef OBRACE  
    #undef CBRACE  
    ```  
  
### <a name="effective-hints"></a>Effektive Hinweise  
 In der folgenden Tabelle sind die effektiven Hinweise für die Quelldateien in diesem Projekt aufgeführt.  
  
-   Quelldatei: A1_A2_B.cpp  
  
-   Effektive Hinweise:  
  
    ```  
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
  
 Die folgenden Hinweise gelten für der vorangehenden Liste.  
  
-   Die effektiven Hinweise stammen aus den `vcpackages`, `Debug`, `A1`, und `A2` Verzeichnisse.  
  
-   Die **#undef** -Direktive in der `Debug` Hint-Datei entfernt die `#define _In_` -Hinweis in die `vcpackages` Directory Hint-Datei.  
  
-   Hint-Datei in das `A1` Verzeichnis definiert `START_NAMESPACE`.  
  
-   Die `#undef` -Hinweis in die `A2` Verzeichnis entfernt die Hinweise für `OBRACE` und `CBRACE` in der `Debug` Directory Hint-Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Erstellen und Steuern von Umgebungsfenstern](../Topic/Creating%20and%20Controlling%20Environment%20Windows.md)   
 [#define-Direktive (C/C++)](../preprocessor/hash-define-directive-c-cpp.md)   
 [#undef-Direktive (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md)   
 [SAL-Anmerkungen](../c-runtime-library/sal-annotations.md)   
 [Meldungszuordnungen](../mfc/reference/message-maps-mfc.md)   
 [Meldungszuordnungsmakros](../atl/reference/message-map-macros-atl.md)   
 [Map-Makros](../atl/reference/object-map-macros.md)