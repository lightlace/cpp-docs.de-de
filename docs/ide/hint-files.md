---
title: Hinweis Dateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cpp.hint
- vc.hint.file
dev_langs: C++
helpviewer_keywords:
- stop file
- cpp.hint
- hint file
- cpp.stop
- Class View, hint file
ms.assetid: 17194f66-cf62-4523-abec-77db0675ab65
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c82128fb40577544b28eb50dc0a107e14c41cbd0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="hint-files"></a>Hinweisdateien
Ein *Hinweisdatei* kann Visual Studio integrierten Entwicklungsumgebung (IDE) interpretieren Visual C++-Bezeichnern, z. B. die Namen der Funktionen und Makros. Wenn Sie eine Visual C++-Projekts, der IDE öffnen *Analysesystem* analysiert den Code in jeder Quelldatei im Projekt, und sammelt Informationen zu jeder Bezeichner. Die IDE diese Informationen verwendet, um Funktionen zu unterstützen, wie die **Klassenansicht** Browser und **Navigationsleiste**.  
  
 Das Analysesystem, die in Visual C++ 2010 eingeführt wird, versteht die C/C++-Syntax, jedoch kann fälschlicherweise eine Anweisung, die ein Makro enthält. Die Anweisung kann fehlinterpretiert werden, wenn das Makro bewirkt, Quellcode dass und syntaktisch falsch geschrieben werden. Die Anweisung kann syntaktisch richtig werden, wenn der Quellcode kompiliert wird und die Preprocesser ersetzt die [Makrobezeichner](../preprocessor/hash-define-directive-c-cpp.md) mit seiner Definition. Das Analysesystem funktioniert, ohne das Projekt zu erstellen, da Hinweisdateien verwendet wird, um Makros zu interpretieren. Aus diesem Grund wie z. B. feature eine Durchsuchen **Klassenansicht** ist sofort verfügbar.  
  
 Hint-Datei enthält Benutzer anpassbaren *Hinweise*, wofür die gleiche Syntax wie C/C++-Makrodefinitionen. Visual C++ enthält eine integrierten Hint-Datei, die für die meisten Projekte ausreichend ist, aber Sie können eigene Hinweisdateien zum Verbessern der Visual Studio Bezeichner behandelt erstellen.  
  
> [!IMPORTANT]
>  Wenn Sie ändern oder eine Hint-Datei hinzufügen, müssen Sie die SDF-Datei und/oder VC.db-Datei in der Reihenfolge, damit die Änderungen wirksam werden in der Projektmappe löschen.  
  
## <a name="scenario"></a>Szenario  
 Angenommen, dass der folgende Code in einer Quelldatei, die Sie überprüfen, mit der **Klassenansicht** Browser. Die `STDMETHOD` Makro deklariert eine Methode namens `myMethod` , die einen Parameter annimmt, und gibt einen Zeiger auf eine **HRESULT**.  
  
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
  
 Das Analysesystem Quellcode nicht interpretiert werden kann, da eine Funktion namens STDMETHOD anscheinend deklariert werden, und diese Deklaration ist syntaktisch falsch, da sie zwei Parameterlisten verfügt. Das Analysesystem ist nicht geöffnet werden die Header-Datei, um die Definitionen für Ermitteln der `STDMETHOD`, `STDMETHODCALLTYPE`, und `HRESULT` Makros. Da das Analysesystem nicht interpretieren kann die `STDMETHOD` -Makro, es ignoriert die gesamte Anweisung und setzt die Analyse fort.  
  
 Das Analysesystem verwendet nicht Headerdateien, da das Projekt möglicherweise eine oder mehrere wichtige Headerdateien abhängig. Wenn alle Header-Datei geändert wird, möglicherweise die Analysesystem aller Headerdateien im Projekt nochmals die verlangsamt die Leistung der IDE. Stattdessen verwendet das Analysesystem Hinweise, die angeben, wie behandelt die `STDMETHOD`, `STDMETHODCALLTYPE`, und `HRESULT` Makros.  
  
 Woher wissen Sie, dass Sie einen Hinweis benötigen? Und wenn Sie einen Hinweis, welche Art sollten Sie erstellen? Ist ein Zeichen dafür, dass ein Hinweis erforderlich ist wenn die Ansicht eines Bezeichners in **Klassenansicht** ist inkonsistent mit der Ansicht in der **Editor**. Beispielsweise **Klassenansicht** möglicherweise nicht anzeigen, die ein Klassenmember, die Sie kennen vorhanden ist, oder der Name des Members ist falsch. Weitere Informationen zu den Arten von hinweisen, die allgemeine Probleme gelöst werden, finden Sie unter der was-Makros erfordern ein Hinweis? weiter unten in diesem Thema.  
  
## <a name="architecture"></a>Architektur  
 Hinweisdateien beziehen sich auf physische Verzeichnisse, nicht auf die logischen Verzeichnisse in dargestellten **Projektmappen-Explorer**. Sie müssen keinen Hint-Datei dem Projekt für eine Auswirkung hat die Hint-Datei hinzufügen. Das Analysesystem verwendet Hinweisdateien nur, wenn es Quelldateien analysiert.  
  
 Jede Hint-Datei heißt **cpp.hint**. Daher viele Verzeichnisse können Hint-Datei enthalten, sondern nur eine Hint-Datei in einem bestimmten Verzeichnis auftreten kann.  
  
 Das Projekt kann von NULL oder mehr Hinweisdateien beeinflusst werden. Wenn keine Hinweisdateien vorhanden sind, verwendet das Analysesystem Fehler Wiederherstellungstechniken, unlesbare Quellcode ignoriert werden sollen. Andernfalls verwendet das Analysesystem die folgende Strategie zum Suchen und Hinweise zu sammeln.  
  
### <a name="search-order"></a>Suchreihenfolge  
 Das Analysesystem sucht Verzeichnisse für Hinweisdateien in der folgenden Reihenfolge an.  
  
-   Das Verzeichnis, das das Installationspaket für Visual C++ enthält (**Vcpackages**). Dieses Verzeichnis enthält eine integrierte Hint-Datei, die Symbole in häufig verwendeten Systemdateien, wie z. B. beschreibt **windows.h**. Daher erbt das Projekt automatisch die meisten dieser Hinweise, die benötigt werden.  
  
-   Der Pfad aus dem Stammverzeichnis einer Quelldatei in das Verzeichnis, das die Quelldatei selbst enthält. In einem typischen Visual C++-Projekt enthält das Stammverzeichnis die Projektmappe bzw. im Projekt-Datei.  
  
     Ausnahme dieser Regel besteht, wenn eine *Stoppdatei* befindet sich im Pfad zur Quelldatei. Eine Stoppdatei enthält zusätzliche Kontrolle über die Suchreihenfolge und ist Datei mit dem Namen **cpp.stop**. Sucht statt aus dem Stammverzeichnis, das Analysesystem aus dem Verzeichnis, das die Stoppdatei in das Verzeichnis enthält, die die Quelldatei enthält. In einem typischen Projekt benötigen Sie keine Stoppdatei.  
  
### <a name="hint-gathering"></a>Erfassen von Hinweisen  
 Hint-Datei enthält keinen oder mehr *Hinweise*. Ein Hinweis definiert wird, oder wie ein C/C++-Makro gelöscht. D. h. die `#define` Präprozessordirektive erstellt oder definiert einen Hinweis, und die `#undef` -Direktive löscht einen Hinweis.  
  
 Analysesystem jedes Hint-Datei in der zuvor beschriebenen Suchreihenfolge öffnet, sammelt Hinweise für jede Datei in einen Satz von *effektive Hinweise*, und klicken Sie dann die effektive Hinweise verwendet, um die Bezeichner im Code zu interpretieren.  
  
 Das Analysesystem verwendet die folgenden Regeln, um Hinweise zu sammeln.  
  
-   Wenn der neue Hinweis einen Namen, der noch nicht definiert ist angibt, wird der Name der neue Hinweis effektive hinweisen hinzugefügt.  
  
-   Wenn der neue Hinweis einen Namen, der bereits definiert ist angibt, wird der neue Hinweis vorhandenen Hinweis neu definiert.  
  
-   Wenn der neue Hinweis ist ein `#undef` Richtlinie, die einen vorhandenen effektiven Hinweis angibt, der neue Hinweis löscht den vorhandenen Hinweis.  
  
 Die erste Regel besagt, dass effektive Hinweise von zuvor geöffneten Hinweisdateien geerbt werden. Die letzten beiden Regeln bedeuten, dass Hinweise, die später in die Suchreihenfolge auftreten Hinweise überschreiben können, die zuvor aufgetreten sind. Beispielsweise können Sie alle vorherigen Hinweise überschreiben, wenn Sie eine Hint-Datei im Verzeichnis erstellen, die eine Quelldatei enthält.  
  
 Eine Darstellung von Hinweisen sind, finden Sie unter der `Example` weiter unten in diesem Thema.  
  
### <a name="syntax"></a>Syntax  
 Hinweise werden erstellt und mit derselben Syntax wie die Präprozessordirektiven, die erstellen und Löschen von Makros gelöscht. Tatsächlich verwendet das Analysesystem die C/C++-Präprozessor die Hinweise ausgewertet. Weitere Informationen zu den Präprozessordirektiven, finden Sie unter [#define-Direktive (C/C++)](../preprocessor/hash-define-directive-c-cpp.md) und [#undef-Direktive (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md).  
  
 Die einzigen ungewöhnlichen Syntaxelemente werden die `@<`, `@=`, und `@>` Ersatzzeichenfolgen. Hierbei handelt es sich um Hinweisdateien spezifische Ersetzungszeichenfolgen, die mit, nur verwendet werden *Zuordnung* Makros. Eine Karte ist ein Satz von Makros, die Daten, Funktionen oder Ereignissen auf anderen Daten, Funktionen oder Ereignishandler beziehen. Beispielsweise `MFC` verwendet Zuordnungen, um erstellen [meldungszuordnungen](../mfc/reference/message-maps-mfc.md), und `ATL` verwendet Zuordnungen, um erstellen [Objekt-Zuordnungen](../atl/reference/object-map-macros.md). Die spezifische Ersetzungszeichenfolgen Hinweisdatei Geben Sie die Start-, die intermediate und die Endadresse Elemente einer Zuordnung an. Nur der Name eines Zuordnungsmakros spielt. Aus diesem Grund blendet jede Ersetzungszeichenfolge die Implementierung des Makros absichtlich aus.  
  
 Hinweise verwenden die folgende Syntax.  
  
|Syntax|Bedeutung|  
|------------|-------------|  
|`#define`*Hinweis-Name* *Ersetzungszeichenfolge*<br /><br /> `#define`*Hinweis-Name* `(` *Parameter*,... `)` *Ersetzungszeichenfolge*|Eine Präprozessordirektive, die einen neuen Hinweis definiert oder einen vorhandenen Hinweis definiert. Nach der Richtlinie ersetzt der Präprozessor jedes Vorkommen von *Hinweis-Name* im Quellcode mit *Ersetzungszeichenfolge*.<br /><br /> Das zweite Syntaxformat definiert einen funktionsähnliche Hinweis. Tritt ein funktionsähnliche Hinweis im Quellcode, ersetzt der Präprozessor zuerst jedes Vorkommen von *Parameter* in *Ersetzungszeichenfolge* mit der entsprechenden Arguments in Quellcode, und klicken Sie dann ersetzt *Hinweis-Name* mit *Ersetzungszeichenfolge*.|  
|`@<`|Eine bestimmte Hinweisdateien *Ersetzungszeichenfolge* , der den Anfang eines Satzes von Zuordnungselementen angibt.|  
|`@=`|Eine bestimmte Hinweisdateien *Ersetzungszeichenfolge* , der ein intermediate kartenelement angibt. Eine Karte kann mehrere Elemente enthalten.|  
|`@>`|Eine bestimmte Hinweisdateien *Ersetzungszeichenfolge* , der das Ende eines Satzes von Zuordnungselementen angibt.|  
|`#undef`*Hinweis-Name*|Die Präprozessordirektive angegeben, durch den einen vorhandenen Hinweis, der gelöscht werden. Der Name des Hinweises wird bereitgestellt, indem die *Hinweis-Name* Bezeichner.|  
|`//`*Kommentar*|Ein einzeiliger Kommentar.|  
|`/*` *comment* `*/`|Keinen mehrzeiligen Kommentar.|  
  
## <a name="what-macros-require-a-hint"></a>Was Makros erfordern einen Hinweis?  
 Bestimmte Arten von Makros können das Analysesystem beeinträchtigen. Dieser Abschnitt beschreibt die Typen von Makros, die zu einem Problem führen können, und den Typ der Hinweis, dass Sie erstellen können, um dieses Problem zu beheben.  
  
### <a name="disruptive-macros"></a>Störende Makros  
 Einige Makros dazu führen, dass das Analysesystem Quellcode fälschlicherweise, aber ohne Beeinträchtigung des Browsers ignoriert werden können. Z. B. der Source Code Annotation Language ([SAL](../c-runtime-library/sal-annotations.md)) Makros in C++-Attribute, mit denen Sie Programmierfehler finden aufgelöst. Wenn Sie SAL-Anmerkungen zu ignorieren, da Sie Code durchsuchen möchten, empfiehlt es sich um Hint-Datei zu erstellen, die die Anmerkung ausblendet.  
  
 In den folgenden Quellcode der Parametertyp für die `FormatWindowClassName()` Funktion `PXSTR`, und der Name des Parameters ist `szBuffer`. Allerdings die Analyse System Fehler der `_Pre_notnull_` und `_Post_z_` SAL-Anmerkungen für den Parametertyp oder der Name des Parameters.  
  
 **Quellcode:**  
  
```  
static void FormatWindowClassName(_Pre_notnull__Post_z_ PXSTR szBuffer)  
```  
  
 **Strategie:** Null-Definition  
  
 Die Strategie in dieser Situation ist die SAL-Anmerkungen behandelt, als wäre sie nicht vorhanden war. Zu diesem Zweck geben Sie einen Hinweis, dessen Ersetzungszeichenfolge null ist. Folglich Analysesystem die Anmerkungen ignoriert und die **Klassenansicht** Browser nicht angezeigt. (Visual C++ enthält eine integrierten Hint-Datei, die SAL-Anmerkung ausblendet.)  
  
 **Hint-Datei:**  
  
```  
#define _Pre_notnull_  
```  
  
### <a name="concealed-cc-language-elements"></a>Verdeckten C-/C++-Sprachelemente  
 Wird ein typischer Grund dafür, dass das Analysesystem Quellcode Datenpakete falsch interpretiert wird, wenn ein Makro blendet Sie aus C/C++ [Markierungszeichen](../cpp/punctuators-cpp.md) oder [Schlüsselwort](../cpp/keywords-cpp.md) token. D. h., ein Makro möglicherweise enthalten die Hälfte eines Paars von Markierungszeichen, z. B. `<>`, `[]`, `{}`, und `()`.  
  
 In den folgenden Quellcode der `START_NAMESPACE` Makro blendet eine linke geschweifte Klammer (`{`).  
  
 **Quellcode:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
 **Strategie:** direkte Kopie  
  
 Wenn die Semantik eines Makros für die browsing-Erlebnis entscheidend sind, erstellen Sie einen Hinweis, der mit dem Makro identisch ist. Das Analysesystem löst das Makro in der Definition in der Hint-Datei.  
  
 Beachten Sie, dass das Makro in der Quelldatei andere Makros enthält, diese Makros interpretiert werden, nur dann, wenn sie bereits in der Menge der effektiven Hinweise sind.  
  
 **Hint-Datei:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
### <a name="maps"></a>Karten  
 Eine Zuordnung besteht aus Makros, die ein Startelement Endwert Element und NULL oder mehr Zwischenelemente festlegen. Das Analysesystem Datenpakete falsch interpretiert wird Maps daran, dass jede Zuordnung Makro blendet Sie aus C/C++-Sprachelemente, und die Syntax einer vollständigen C-/C++-Anweisung über viele separate Makros verteilt ist.  
  
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
  
 **Strategie:** kartenelemente identifizieren  
  
 Geben Sie Hinweise für die Start-, Mittel-(sofern vorhanden) und Elemente einer Zuordnung. Verwenden Sie die spezielle Zuordnung Ersatzzeichenfolgen `@<`, `@=`, und `@>`. Weitere Informationen finden Sie unter der `Syntax` Abschnitt dieses Themas.  
  
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
 Zusammengesetzte Makros enthalten eine oder mehrere der Typen von Makros, die das Analysesystem zu verwechseln.  
  
 Der folgenden Quellcode enthält die `START_NAMESPACE` -Makro, das den Anfang einen Namespacebereich gibt an, und die `BEGIN_CATEGORY_MAP` -Makro, das den Beginn einer Zuordnung angibt.  
  
 **Quellcode:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
 **Strategie:** direkte Kopie  
  
 Erstellen Sie die Hinweise für die `START_NAMESPACE` und `BEGIN_CATEGORY_MAP` Makros, und erstellen Sie einen Hinweis für die `NSandMAP` Makro, das mit der vorher gezeigten des Quellcodes übereinstimmt. Alternativ können Sie können ein zusammengesetztes Makro nur störende Makros und Leerzeichen besteht, Sie einen Hinweis definieren, dessen Ersetzungszeichenfolge eine null-Definition ist.  
  
 In diesem Beispiel wird davon ausgegangen `START_NAMESPACE` gelten bereits einen Hinweis aus, wie in diesem Thema im Abschnitt der `Concealed C/C++ Language Elements` Subheading. Und vorausgesetzt `BEGIN_CATEGORY_MAP` verfügt über einen Hinweis, wie dies zuvor im `Maps`.  
  
 **Hint-Datei:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
### <a name="inconvenient-macros"></a>Unpraktisch Makros  
 Einige Makros vom Analysesystem interpretiert werden können, aber der Quellcode ist schwer zu lesen, da das Makro lang oder zu komplex ist. Aus Gründen der besseren Lesbarkeit können Sie einen Hinweis geben möchten, der die Anzeige des Makros vereinfacht.  
  
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
 Im folgende Beispiel wird veranschaulicht, wie Hinweise aus Hinweisdateien kumuliert werden. Stoppdateien werden in diesem Beispiel nicht verwendet.  
  
 Die folgende Abbildung zeigt einige der physischen Verzeichnisse in einem Visual C++-Projekt. Hinweisdateien befinden sich in der `vcpackages`, `Debug`, `A1`, und `A2` Verzeichnisse.  
  
### <a name="hint-file-directories"></a>Hinweisdateiverzeichnisse  
 ![Allgemeine und Projekt &#45; bestimmte Hinweisdateiverzeichnisse. ] (../ide/media/hintfile.png "HintFile")  
  
### <a name="directories-and-hint-file-contents"></a>Verzeichnisse und Hinweisdateiinhalte  
 Die folgende Liste enthält die Verzeichnisse in diesem Projekt, die Hinweisdateien und den Inhalt dieser Hinweis Dateien enthalten. Nur einige der vielen Hinweise in der `vcpackages` Directory Hint-Datei aufgeführt sind.  
  
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
 Die folgende Tabelle enthält die effektive Hinweise für die Quelldateien in diesem Projekt.  
  
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
  
 Die folgenden Hinweise gelten für der vorangehenden Liste aufgeführt.  
  
-   Die effektiven Hinweise stammen aus den `vcpackages`, `Debug`, `A1`, und `A2` Verzeichnisse.  
  
-   Die **#undef** -Direktive in der `Debug` Hint-Datei entfernt die `#define _In_` -Hinweis in die `vcpackages` Directory Hint-Datei.  
  
-   Hint-Datei in die `A1` Directory definiert `START_NAMESPACE`.  
  
-   Die `#undef` -Hinweis in die `A2` Verzeichnis entfernt die Hinweise für `OBRACE` und `CBRACE` in die `Debug` Directory Hint-Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)    
 [#define-Direktive (C/C++)](../preprocessor/hash-define-directive-c-cpp.md)   
 [#undef-Direktive (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md)   
 [SAL-Anmerkungen](../c-runtime-library/sal-annotations.md)   
 [Meldungszuordnungen](../mfc/reference/message-maps-mfc.md)   
 [Meldungszuordnungsmakros](../atl/reference/message-map-macros-atl.md)   
 [Objektzuordnungs-Makros](../atl/reference/object-map-macros.md)