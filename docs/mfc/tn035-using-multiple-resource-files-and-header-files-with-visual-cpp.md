---
title: 'TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++'
ms.date: 11/04/2016
f1_keywords:
- vc.resources
helpviewer_keywords:
- resource files, multiple
- TN035
ms.assetid: 1f08ce5e-a912-44cc-ac56-7dd93ad73fb6
ms.openlocfilehash: 0493dd45caf5eb78da435987a4590442a908a5a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305514"
---
# <a name="tn035-using-multiple-resource-files-and-header-files-with-visual-c"></a>TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

In diesem Hinweis wird beschrieben, wie der Visual C++-Ressourcen-Editor mehrere entweder in einem einzelnen Projekt oder in mehreren Projekten gemeinsam genutzte Ressourcendateien und Headerdateien unterstützt und wie Sie von dieser Unterstützung profitieren. In dem Hinweis werden folgende Fragen beantwortet:

- Wenn Sie möchten Teilen eines Projekts in mehrere Ressourcendateien und/oder Headerdateien, und wie Sie dies tun

- Wie Sie einen allgemeinen Header freigeben. H-Datei zwischen zwei. RC-Dateien

- Wie Sie Projektressourcen in mehrere unterteilen. RC-Dateien

- Wie Sie (und die Tools) Buildabhängigkeiten zwischen verwalten. RC-VERSION. CPP, und. H-Dateien

Wenn Sie Ihrem Projekt eine zusätzliche Ressourcendatei hinzufügen, erkennt ClassWizard die Ressourcen in der hinzugefügten Datei nicht.

Die oben genannten Fragen werden in diesem Hinweis anhand der folgenden Gliederung beantwortet:

- **Übersicht über die wie Visual C++ verwaltet Ressourcendateien und Headerdateien** bietet einen Überblick darüber, wie der Befehl Ressourcenincludes festgelegt, in Visual C++ mehrere Ressourcendateien und Headerdateien im selben Projekt verwenden kann.

- **Die Analyse von AppWizard erstellten. RC und. H-Dateien** untersucht die mehrerer Ressourcen- und Headerdateien-Dateien, die von einer von AppWizard erstellte Anwendung verwendet werden. Diese Dateien sind ein gutes Beispiel für zusätzliche Ressourcen- und Headerdateien, die Sie dem Projekt hinzufügen können.

- **Einschließlich zusätzlicher Headerdateien** wird beschrieben, in dem Sie mehrere Headerdateien hinzufügen möchten, und beschreibt, wie das geht.

- **Freigeben einer Headerdatei für zwei. RC-Dateien** zeigt, wie Sie eine einzelne Headerdatei für mehrere freigeben können. RC-Dateien in verschiedenen Projekten oder vielleicht im selben Projekt.

- **Verwenden von mehreren Ressourcendateien im selben Projekt** wird beschrieben, in dem Sie Ihr Projekt in mehrere aufteilen möchten. RC-Dateien und beschreibt detailliert, wie das geht.

- **Erzwingung von nicht-bearbeitbaren Visual C++ Files** wird beschrieben, wie Sie sicherstellen können, dass Visual C++ nicht bearbeitet und versehentlich umformatiert eine benutzerdefinierte Ressource.

- **Verwalten von Symbolen, die von mehreren Visual C++ bearbeiteten gemeinsam verwendet werden. RC-Dateien** beschreibt, wie Sie die gleichen Symbole in mehreren gemeinsam zu nutzen. RC-Dateien und so verhindern Sie doppelte numerische ID-Werte zuweist.

- **Verwalten von Abhängigkeiten zwischen. RC-VERSION. CPP, und. H-Dateien** wird beschrieben, wie Visual C++ vermeidet unnötige neu kompilieren zu müssen. CPP-Dateien, die von ressourcensymboldateien abhängig sind.

- **Wie Visual C++ verwaltet enthält Informationen zum** enthält technische Details zur wie Visual C++ verfolgt mehrere (geschachtelte) des. RC-Dateien und mehrere Headerdateien, die # mit #include eingebundenen durch ein. RC-Datei.

**Übersicht über die Visual C++ verwaltet Ressourcendateien und Headerdateien**

Visual C++ verwaltet eine einzelne RC-Ressourcendatei und eine entsprechende H-Headerdatei als eng gekoppeltes Dateienpaar. Wenn Sie Ressourcen in einer RC-Datei bearbeiten und speichern, bearbeiten und speichern Sie indirekt Symbole in der entsprechenden H-Datei. Obwohl Sie (über die MDI-Benutzeroberfläche von Visual C++) mehrere RC-Dateien gleichzeitig für eine RC-Datei öffnen und bearbeiten können, bearbeiten Sie indirekt genau eine entsprechende Headerdatei.

**Symbolheaderdatei**

Standardmäßig wird der entsprechenden Headerdatei in Visual C++ immer der Name RESOURCE.H zugewiesen, unabhängig vom Namen der Ressourcendatei (z. B. MYAPP.RC). Mithilfe der **Ressourcenincludes** Befehl die **Ansicht** Menü in Visual C++ können Sie den Namen dieser Headerdatei ändern, durch die Aktualisierung der Datei "Symbolheaderdatei" im der **Gruppeenthält**Dialogfeld.

**Anweisungen für schreibgeschützte Symbole**

Obwohl in Visual C++ nur jeweils eine Headerdatei für eine RC-Datei bearbeitet werden kann, unterstützt Visual C++ Verweise auf Symbole, die in zusätzlichen schreibgeschützten Headerdateien definiert sind. Mithilfe der **Ressourcenincludes** Befehl die **Ansicht** Menü in Visual C++ können Sie eine beliebige Anzahl von zusätzlichen schreibgeschützten Headerdateien als Anweisungen für schreibgeschützte Symbole angeben. Die Einschränkung "schreibgeschützt" bedeutet, dass Sie beim Hinzufügen einer neuen Ressource in der RC-Datei ein Symbol verwenden können, das in der schreibgeschützten Headerdatei definiert ist. Wenn Sie die Ressource löschen, bleibt das Symbol weiterhin in der schreibgeschützten Headerdatei definiert. Sie können den numerischen Wert nicht ändern, der einem schreibgeschützten Symbol zugewiesen ist.

**Kompilierzeitdirektiven**

Visual C++ unterstützt auch die Schachtelung von Ressourcendateien, bei der eine RC-Datei mit #include in eine andere eingebunden wird. Wenn Sie eine bestimmte RC-Datei mit Visual C++ bearbeiten, sind die Ressourcen in den mit #include eingebundenen Dateien nicht sichtbar. Wenn Sie die RC-Datei jedoch kompilieren, werden die mit #include eingebundenen Dateien ebenfalls kompiliert. Mithilfe der **Ressourcenincludes** Befehl die **Ansicht** Menü in Visual C++ können Sie können eine beliebige Anzahl von angeben # mit #include eingebundenen. RC-Dateien als Kompilierzeitdirektiven.

Beachten Sie, was geschieht, wenn Sie in Visual C++ einlesen ein. RC-Datei, die #include eine andere. RC-Datei, die *nicht* als eine Kompilierzeitdirektive angegeben. Dieser Fall kann eintreten, wenn Sie eine RC-Datei in Visual C++ übertragen, die Sie zuvor manuell mit einem Text-Editor verwaltet haben. Wenn Visual C++ die mit #include eingebundene RC-Datei liest, werden die mit #include eingebundenen Ressourcen in der übergeordneten RC-Datei zusammengeführt. Wenn Sie die übergeordnete RC-Datei speichern, wird die #include-Anweisung durch die mit #include eingebundenen Ressourcen ersetzt. Wenn Sie diese Zusammenführung nicht wünschen, sollten Sie entfernen die #include-Anweisung vom übergeordneten Element. RC-Datei *vorherige* dem Einlesen in Visual C++; klicken Sie dann mit Visual C++ hinzufügen wieder dasselbe #include-Anweisung als Direktive während der Kompilierung.

Visual C++ speichert in ein. RC-Datei die drei Arten der oben genannten Gruppe enthält Informationen (Symbolheaderdatei, schreibgeschützte Symboldirektiven und Kompilierzeitdirektiven) in #include-Direktiven *und* in TEXTINCLUDE-Ressourcen. Die TEXTINCLUDE-Ressourcen, ein Implementierungsdetail, die Sie normalerweise nicht müssen für den Umgang mit, werden in erläutert [wie Visual C++ verwaltet Set enthält Information](#_mfcnotes_tn035_set_includes).

**Die Analyse von AppWizard erstellten. RC und. H-Dateien**

Eine Überprüfung des von AppWizard erzeugten Anwendungscodes liefert Informationen darüber, wie in Visual C++ mehrere Ressourcendateien und Headerdateien verwaltet werden. Die nachfolgend untersuchten Codeauszüge stammen von einer MYAPP-Anwendung, die von AppWizard unter Verwendung der Standardoptionen erstellt wurde.

Eine von AppWizard erstellte Anwendung verwendet mehrere Ressourcendateien und mehrere Headerdateien, wie im folgenden Diagramm dargestellt:

```
RESOURCE.H     AFXRES.H
\       /
\     /
    MYAPP.RC
|
|
    RES\MYAPP.RC2
    AFXRES.RC
    AFXPRINT.RC
```

Sie können diese Beziehungen zwischen mehreren Dateien mit dem Befehl "Visual C++-Datei/Gruppe enthält" anzeigen.

"MYAPP". RC-Ressourcendatei der Anwendung, die Sie bearbeiten mit Visual C++.

RESOURCE.H ist die anwendungsspezifische Headerdatei. Sie erhält von AppWizard immer den Namen RESOURCE.H, entsprechend der Standardbenennung der Headerdatei in Visual C++. Die #include-Direktive für diese Headerdatei ist die erste Anweisung in der Ressourcendatei (MYAPP.RC):

```
//Microsoft Visual C++ generated resource script
//
#include "resource.h"
```

RES\MYAPP. RC2 enthält Ressourcen, die nicht von Visual C++ bearbeitet werden, jedoch werden in der letzten Kompilierung enthalten sein. EXE-Datei. AppWizard erstellt solche Ressourcen nicht standardmäßig, da Visual C++ alle Standardressourcen bearbeiten kann, einschließlich der Versionsressource (eine neue Funktion in diesem Release). Von AppWizard wird eine leere Datei generiert, falls Sie dieser Datei eigene benutzerdefinierte formatierte Ressourcen hinzufügen möchten.

Wenn Sie benutzerdefinierte formatierte Ressourcen verwenden, können Sie sie zu RES\MYAPP.RC2 hinzufügen und mit dem Visual C++-Text-Editor bearbeiten.

AFXRES.RC und AFXPRINT.RC enthalten die Standardressourcen, die von bestimmten Funktionen des Frameworks benötigt werden. Wie RES\MYAPP.RC2 werden diese zwei vom Framework bereitgestellten Ressourcendateien mit #include am Ende von MYAPP.RC eingebunden. Zudem werden sie in den Kompilierzeitdirektiven des Dialogfelds „Gruppe enthält“ angegeben. So werden diese Frameworkressourcen beim Bearbeiten von MYAPP.RC in Visual C++ nicht direkt angezeigt oder bearbeitet, sie werden jedoch in die binäre RES-Datei der Anwendung und die finale EXE-Datei kompiliert. Weitere Informationen für die standard Frameworkressourcen, einschließlich der Verfahren zum Ändern, finden Sie unter [technischer Hinweis 23](../mfc/tn023-standard-mfc-resources.md).

AFXRES.H definiert Standardsymbole, wie z. B. `ID_FILE_NEW`, die vom Framework und insbesondere in AFXRES.RC verwendet werden. AFXRES.H bindet mit #include auch die Datei WINRES.H ein, die eine Teilmenge von WINDOWS.H enthält. Diese wird von den von Visual C++ generierten RC-Dateien sowie AFXRES.RC benötigt. Die in AFXRES.H definierten Symbole stehen beim Bearbeiten der Anwendungsressourcendatei (MYAPP.RC) zur Verfügung. `ID_FILE_NEW` wird beispielsweise für das Menüelement "Neue Datei" in der Menüressource von MYAPP.RC verwendet. Sie können diese vom Framework definierten Symbole nicht ändern oder löschen.

## <a name="_mfcnotes_tn035_including"></a> Einschließen zusätzlicher Headerdateien

Die von AppWizard erstellte Anwendung enthält nur zwei Headerdateien: DIE RESSOURCE. H und AFXRES. H. Nur RESOURCE.H ist eine anwendungsspezifische Datei. In folgenden Fällen müssen Sie möglicherweise zusätzliche schreibgeschützte Headerdateien einschließen:

Die Headerdatei wird von einer externen Quelle bereitgestellt, oder Sie möchten die Headerdatei für mehrere Projekte oder mehrere Bereiche desselben Projekts freigeben.

Die Headerdatei weist Formatierungen und Kommentare auf, die in Visual C++ beim Speichern der Datei nicht geändert oder herausgefiltert werden sollen. So möchten Sie beispielsweise #define-Direktiven beibehalten, die eine symbolische Arithmetik wie die folgende verwenden:

```
#define RED 0
#define BLUE 1
#define GREEN 2
#define ID_COLOR_BUTTON 1001
#define ID_RED_BUTTON (ID_COLOR_BUTTON + RED)
#define ID_BLUE_BUTTON (ID_COLOR_BUTTON + BLUE)
#define ID_GREEN_BUTTON (ID_COLOR_BUTTON + GREEN)
```

Sie können zusätzliche schreibgeschützte Headerdateien einschließen, mithilfe der **Ressourcenincludes** Befehl, um anzugeben der #include-Anweisung als zweite schreibgeschützten Symbol Direktive, wie in:

```
#include "afxres.h"
#include "second.h"
```

Das neue Dateibeziehungsdiagramm sieht nun wie folgt aus:

```
    AFXRES.H
RESOURCE.H     SECOND.H
\       /
\     /
    MYAPP.RC
|
|
    RES\MYAPP.RC2
    AFXRES.RC
    AFXPRINT.RC
```

**Freigeben einer Headerdatei für zwei. RC-Dateien**

Sie können eine Headerdatei für zwei RC-Dateien freigeben, die sich in verschiedenen Projekten oder auch im selben Projekt befinden. Dazu wenden Sie einfach die oben beschriebene Technik für Anweisungen für schreibgeschützte Symbole auf beide RC-Dateien an. Wenn die beiden RC-Dateien für unterschiedliche Anwendungen (unterschiedliche Projekte) gedacht sind, sieht das Ergebnis wie im folgenden Diagramm dargestellt aus:

```
    RESOURCE.H AFXRES.H   RESOURCE.H
(for MYAPP1) SECOND.H   (for MYAPP2)
\       /     \       /
\     /       \     /
    MYAPP1.RC MYAPP2.RC */    \        /     \ */      \      /       \
RES\MYAPP1.RC2  AFXRES.RC     RES\MYAPP2.RC2
    AFXPRINT.RC
```

Der Fall, dass die zweite Headerdatei von zwei RC-Dateien in derselben Anwendung (im selben Projekt) gemeinsam verwendet wird, wird nachfolgend erläutert.

**Verwenden von mehreren Ressourcendateien im selben Projekt**

Visual C++ und der Ressourcencompiler unterstützen mehrere RC-Dateien im selben Projekt, indem eine RC-Datei mit #include in eine andere eingebunden wird. Mehrfache Schachtelung ist zulässig. Es gibt verschiedene Gründe für das Aufteilen der Ressourcen des Projekts in mehrere RC-Dateien:

- Es ist einfacher, eine große Anzahl von Ressourcen für mehrere Projektteammitglieder zu verwalten, wenn Sie die Ressourcen in mehrere RC-Dateien aufteilen. Wenn Sie ein Quellcodeverwaltungs-Paket für das Auschecken von Dateien und das Einchecken von Änderungen verwenden, ermöglicht das Aufteilen der Ressourcen in mehrere RC-Dateien Ihnen eine genauere Steuerung der Verwaltung von Änderungen an den Ressourcen.

- Wenn Sie Präprozessordirektiven wie "#ifdef", "#endif" und "#define" für Teile der Ressourcen verwenden möchten, müssen Sie sie in schreibgeschützten Ressourcen isolieren, die vom Ressourcencompiler kompiliert werden.

- RC-Komponentendateien werden in Visual C++ schneller geladen und gespeichert als eine zusammengesetzte RC-Datei.

- Wenn Sie eine Ressource mit einem Text-Editor in einem lesbaren Format verwalten möchten, sollten Sie sie in einer RC-Datei getrennt von der Datei speichern, die in Visual C++ bearbeitet wird.

- Wenn Sie eine benutzerdefinierte Ressource in einem Binär- oder Textformat speichern müssen, das von einem anderen spezialisierten Daten-Editor interpretiert werden kann, sollten Sie sie in einer separaten RC-Datei speichern, damit Visual C++ das Format nicht in Hexadezimaldaten ändert. Die. WAV (Audio) von Dateiressourcen im MFC Advanced Concepts-Beispiel [SPEAKN](../overview/visual-cpp-samples.md) sind ein gutes Beispiel.

Sie können mit #include eine SECOND.RC in die Kompilierzeitanweisungen im Dialogfeld „Gruppe enthält“ einbinden:

```
#include "res\myapp.rc2"  // non-Visual C++ edited resources
#include "second.rc"  // THE SECOND .RC FILE

#include "afxres.rc"  // Standard components
#include "afxprint.rc"  // printing/print preview resources
```

Das Ergebnis ist im folgenden Diagramm dargestellt:

```
RESOURCE.H     AFXRES.H
\       /
\     /
    MYAPP.RC
|
|
    RES\MYAPP.RC2
    SECOND.RC
    AFXRES.RC
    AFXPRINT.RC
```

Mithilfe von Kompilierzeitanweisung können Sie die in Visual C++ bearbeitbaren und nicht bearbeitbaren Ressourcen in mehreren RC-Dateien organisieren. Einzige Aufgabe der MYAPP.RC-„Masterdatei“ ist dabei die Einbindung der übrigen RC-Dateien mit #include. Wenn Sie eine MAK-Datei eines Visual C++-Projekts verwenden, sollten Sie die RC-"Masterdatei" in das Projekt einschließen, damit alle mit #include eingebundenen Ressourcen mit der Anwendung kompiliert werden.

**Erzwingung von nicht bearbeitbaren Visual C++-Dateien**

Die AppWizard erstellten RES\MYAPP. RC2-Datei ist ein Beispiel für eine Datei, die Ressourcen enthält, die Sie *nicht* möchten versehentlich in Visual C++ eingelesen werden und dann mit Verlust der Formatierungsinformationen zurück. Um dies zu verhindern, fügen Sie die folgenden Zeilen am Anfang der Datei RES\MYAPP.RC2 ein:

```
#ifdef APSTUDIO_INVOKED
#error this file is not editable by Visual C++
#endif //APSTUDIO_INVOKED
```

Wenn Visual C++ kompiliert die. RC-Datei definiert `APSTUDIO_INVOKED` sowie `RC_INVOKED`. Wenn die Struktur der von AppWizard erstellten Datei beschädigt ist und Visual C++ die #error-Zeile oben liest, wird ein schwerwiegender Fehler gemeldet, und das Lesen der RC-Datei wird abgebrochen.

**Verwalten von Symbolen, die von mehreren Visual C++ bearbeiteten gemeinsam verwendet werden. RC-Dateien**

Es sind zwei Aspekte zu beachten, wenn Sie die Ressourcen in mehrere RC-Dateien aufteilen, die Sie separat in Visual C++ bearbeiten möchten:

- Sie möchten dieselben Symbole ggf. für mehrere RC-Dateien verwenden.

- Sie müssen verhindern, dass Visual C++ dieselben numerischen ID-Werte unterschiedlichen Ressourcen (Symbolen) zuweist.

Das folgende Diagramm zeigt die Organisation von RC- und H-Dateien in Bezug auf den ersten Aspekt:

```
    MYAPP.RC */         \ */           \
MYSTRS.H   / MYSHARED.H  \  MYMENUS.H
\    /    /      \   \    \
\  /    /        \   \    \
    MYSTRS.RC MYMENUS.RC
```

In diesem Beispiel werden Zeichenfolgenressourcen in der Ressourcendatei MYSTRS.RC und Menüs in der Ressourcendatei MYMENUS.RC gespeichert. Einige Symbole, z. B. für Befehle, müssen möglicherweise in beiden Dateien genutzt werden. Bei einem ID_TOOLS_SPELL-Symbol kann es sich z. B. um die Menübefehl-ID für das Spell-Element in einem "Tools"-Menü handeln. Es kann sich aber auch um die Zeichenfolgen-ID der Eingabeaufforderung handeln, die vom Framework in der Statusleiste des Hauptfensters der Anwendung angezeigt wird.

Das ID_TOOLS_SPELL-Symbol wird in der gemeinsam genutzten Headerdatei MYSHARED.H gespeichert. Sie verwalten diese gemeinsam genutzte Headerdatei manuell mit einem Text-Editor. Sie wird nicht direkt in Visual C++ bearbeitet. In der zwei Ressource MYSTRS-Dateien. RC und MYMENUS. RC, geben Sie #include MYSHARED. H-nur-Lese-Richtlinien für die "MyApp". RC, mit der **Ressourcenincludes** wie oben beschrieben den Befehl.

Am einfachsten ist es, vorher zu überlegen, welches Symbol gemeinsam genutzt werden soll, bevor Sie versuchen, es zur Identifizierung einer Ressource zu verwenden. Fügen Sie das Symbol der gemeinsam genutzten Headerdatei hinzu, sofern Sie die gemeinsam genutzte Headerdatei noch nicht mit #include in die Anweisungen für schreibgeschützte Symbole für die RC-Datei eingebunden haben, bevor Sie das Symbol verwenden. Wenn Sie sich nicht vorher überlegt haben, das Symbol auf diese Weise freizugeben, müssen Sie die #define-Anweisung für das Symbol manuell (mithilfe eines Text-Editors) von z. B. MYMENUS.H in MYSHARED.H verschieben, bevor Sie sie in MYSTRS.RC verwenden.

Wenn Sie Symbole in mehreren RC-Dateien verwalten, müssen Sie außerdem verhindern, dass Visual C++ dieselben numerischen ID-Werte unterschiedlichen Ressourcen (Symbolen) zuweist. Für jede RC-Datei weist Visual C++ inkrementell IDs in jeder der vier ID-Domänen zu. Zwischen der Bearbeitung von Sitzungen verfolgt Visual C++ die letzte ID, die in jeder der Domänen in der Symbolheaderdatei für die RC-Datei zugewiesen wurde. Nachfolgend sind die APS_NEXT-Werte für eine leere (neue) RC-Datei aufgeführt:

```
#define _APS_NEXT_RESOURCE_VALUE  101
#define _APS_NEXT_COMMAND_VALUE   40001
#define _APS_NEXT_CONTROL_VALUE   1000
#define _APS_NEXT_SYMED_VALUE     101
```

`_APS_NEXT_RESOURCE_VALUE` ist der nächste Symbolwert, der für eine Dialogfeldressource, Menüressource usw. verwendet wird. Der gültige Bereich für Ressourcensymbolwerte ist 1 bis 0x6FFF.

`_APS_NEXT_COMMAND_VALUE` ist der nächste Symbolwert, der für einen Befehlsbezeichner verwendet wird. Der gültige Bereich für Befehlssymbolwerte ist 0x8000 bis 0xDFFF.

`_APS_NEXT_CONTROL_VALUE` ist der nächste Symbolwert, der für ein dialogsteuerelement verwendet wird. Der gültige Bereich für Symbolwerte für Dialogsteuerelemente ist 8 bis 0xDFFF.

`_APS_NEXT_SYMED_VALUE` wird der nächste Symbolwert, der ausgegeben wird, wenn Sie manuell einen Symbolwert zuweisen, den neuen Befehl im Symbolbrowser verwendet.

Visual C++-startet beim Erstellen einer neuen RC-Datei mit Werten, die etwas höher sind als der niedrigste gültige Wert. AppWizard initialisiert diese Werte zudem in einem Format, das für MFC-Anwendungen geeignet ist. Weitere Informationen zu ID-Wertbereiche finden Sie unter [technischer Hinweis 20](../mfc/tn020-id-naming-and-numbering-conventions.md).

Jetzt jedes Mal, wenn Sie eine neue Ressourcendatei, sogar im selben Projekt erstellen, Visual C++ dasselbe definiert `_APS_NEXT_` Werte. Das bedeutet, dass es z. B. beim Hinzufügen von mehreren Dialogfeldern in zwei verschiedenen RC-Dateien sehr wahrscheinlich ist, dass der gleiche #define-Wert verschiedenen Dialogfeldern zugewiesen wird. So kann IDD_MY_DLG1 in der ersten RC-Datei beispielsweise die gleiche Zahl, 101, zugewiesen werden, wie IDD_MY_DLG2 in einer zweiten RC-Datei.

Um dies zu vermeiden, sollten Sie einen separaten numerischen Bereich für jede der vier ID-Domänen in den jeweiligen RC-Dateien reservieren. Zu diesem Zweck manuell zu aktualisieren, die `_APS_NEXT` Werte aller der. RC-Dateien **vor** Sie das Hinzufügen von Ressourcen beginnen. Z. B. wenn die erste. RC-Datei verwendet die standardmäßige `_APS_NEXT` Werte, möglicherweise möchten Sie die folgenden weisen `_APS_NEXT` Werte an den zweiten. RC-Datei:

```
#define _APS_NEXT_RESOURCE_VALUE  2000
#define _APS_NEXT_COMMAND_VALUE   42000
#define _APS_NEXT_CONTROL_VALUE   2000
#define _APS_NEXT_SYMED_VALUE     2000
```

Es ist natürlich immer noch möglich, dass Visual C++ in der ersten RC-Datei so viele IDs zuweist, dass die numerischen Werte die für die zweite RC-Datei reservierten Werte überschneiden. Sie sollten ausreichend große Bereiche reservieren, damit dies nicht geschieht.

**Verwalten von Abhängigkeiten zwischen. RC-VERSION. CPP, und. H-Dateien**

Wenn Visual C++ eine RC-Datei speichert, werden auch Symboländerungen an der entsprechenden RESOURCE.H-Datei gespeichert. Alle CPP-Dateien, die auf Ressourcen in der RC-Datei verweisen, müssen mit #include die RESOURCE.H-Datei einbinden, normalerweise aus der Masterheaderdatei des Projekts. Dies führt zu unerwünschten Nebeneffekten aufgrund des internen Projektmanagements der Entwicklungsumgebung, die Quelldateien auf Headerabhängigkeiten überprüft. So müssten bei jedem Hinzufügen eines neuen Symbols in Visual C++ alle CPP-Dateien, die mit #include RESOURCE.H einbinden, neu kompiliert werden.

Visual C++ verhindert die Abhängigkeit von RESOURCE.H, indem der folgende Kommentar als erste Zeile der RESOURCE.H-Datei hinzugefügt wird:

```
//{{NO_DEPENDENCIES}}
```

Die Entwicklungsumgebung interpretiert diesen Kommentar, indem sie die Änderungen an RESOURCE.H ignoriert, damit abhängige CPP-Dateien nicht neu kompiliert werden müssen.

Visual C++ fügt immer die Kommentarzeile //{{NO_DEPENDENCIES}} zu einer RC-Datei hinzu, wenn die Datei gespeichert wird. In einigen Fällen führt das Umgehen der Buildabhängigkeit von RESOURCE.H möglicherweise zu Laufzeitfehlern, die zum Zeitpunkt der Verknüpfung unentdeckt bleiben. Wenn Sie beispielsweise den Symbolbrowser zum Ändern des numerischen Werts verwenden, der einem Symbol für eine Ressource zugewiesen ist, wird die Ressource zur Anwendungslaufzeit möglicherweise nicht gefunden und ordnungsgemäß geladen, wenn die CPP-Datei, die auf die Ressource verweist, nicht neu kompiliert wird. In solchen Fällen sollten Sie alle kompilieren. CPP-Dateien, die Sie kennen, sind von den symboländerungen in Ressourcen betroffen. H oder Select **Rebuild All**. Wenn Sie die Symbolwerte für eine bestimmte Gruppe von Ressourcen häufig ändern müssen, Sie werden wahrscheinlich ist es einfacher und sicherer zum Aufteilen von diese Symbole in eine separate schreibgeschützte Headerdatei, wie im vorherigen Abschnitt beschrieben [einschließlich Zusätzlicher Headerdateien](#_mfcnotes_tn035_including).

## <a name="_mfcnotes_tn035_set_includes"></a> Enthält wie Visual C++ verwaltet Informationen **

Wie oben erläutert, können Sie mit dem "Gruppe enthält"-Befehl im Menü "Datei" drei Typen von Informationen angeben:

- Symbolheaderdatei

- Direktiven für schreibgeschützte Symbole

- Kompilierzeitanweisungen

Im Folgenden wird beschrieben, wie Visual C++ diese Informationen in einer RC-Datei verwaltet. Sie benötigen diese Informationen nicht für die Verwendung von Visual C++. Sie dienen jedoch einem besseren Verständnis, damit Sie im Umgang mit der Funktion „Gruppe enthält“ sicherer werden.

Jede der drei Arten der Gruppe enthält Informationen befindet sich in der. RC-Datei in zwei Formen: (1) als #include oder andere Anweisungen interpretierbaren vom Ressourcencompiler und (2) als besondere TEXTINCLUDE-Ressourcen interpretierbaren nur von Visual C++.

Der Zweck der TEXTINCLUDE-Ressource ist, legen Sie Daten sicher in einem Formular zu speichern, leicht akzeptabel ist, in Visual C++ sind **Gruppe enthält** Dialogfeld. TEXTINCLUDE ist ein *Ressourcentyp* von Visual C++ definiert. Visual C++ erkennt drei spezifische TEXTINCLUDE-Ressourcen, die die Ressourcen-IDs 1, 2 und 3 aufweisen:

|TEXTINCLUDE-Ressourcen-ID|Typ der "Gruppe enthält"-Informationen|
|-----------------------------|--------------------------------------|
|1|Symbolheaderdatei|
|2|Direktiven für schreibgeschützte Symbole|
|3|Kompilierzeitanweisungen|

Alle drei Typen von "Gruppe enthält"-Informationen werden in den von AppWizard erstellten MYAPP.RC- und RESOURCE.H-Standarddateien dargestellt, wie nachfolgend beschrieben. Die zusätzlichen Token \0 und "" zwischen den BEGIN- und END-Blöcken werden von der RC-Syntax benötigt, um mit 0 endende Zeichenfolgen bzw. das doppelte Anführungszeichen anzugeben.

## <a name="symbol-header-file"></a>Symbolheaderdatei

Bei der Form der Symbolheaderdatei-Informationen, die vom Ressourcencompiler interpretiert werden, handelt es sich um eine einfache #include-Anweisung:

```
#include "resource.h"
```

Die entsprechende TEXTINCLUDE-Ressource ist:

```
1 TEXTINCLUDE DISCARDABLE
BEGIN
"resource.h\0"
END
```

## <a name="read-only-symbol-directives"></a>Direktiven für schreibgeschützte Symbole

Anweisungen für schreibgeschützte Symbole werden oben in der MYAPP.RC in der folgenden vom Ressourcencompiler interpretierbaren Form eingefügt:

```
#include "afxres.h"
```

Die entsprechende TEXTINCLUDE-Ressource ist:

```
2 TEXTINCLUDE DISCARDABLE
BEGIN
   "#include ""afxres.h""\r\n"
   "\0"
END
```

## <a name="compile-time-directives"></a>Kompilierzeitanweisungen

Kompilierzeitdirektiven werden am Ende der MYAPP.RC in der folgenden vom Ressourcencompiler interpretierbaren Form eingefügt:

```
#ifndef APSTUDIO_INVOKED
///////////////////////
//
// From TEXTINCLUDE 3
//
#include "res\myapp.rc2"  // non-Visual C++ edited resources

#include "afxres.rc"  // Standard components
#include "afxprint.rc"  // printing/print preview resources
#endif  // not APSTUDIO_INVOKED
```

Die #ifndef APSTUDIO_INVOKED-Anweisung weist Visual C++ an, Kompilierzeitanweisungen zu überspringen.

Die entsprechende TEXTINCLUDE-Ressource ist:

```
3 TEXTINCLUDE DISCARDABLE
BEGIN
"#include ""res\myapp.rc2""  // non-Visual C++ edited resources\r\n"
"\r\n"
"#include ""afxres.rc""  // Standard components\r\n"
"#include ""afxprint.rc""  // printing/print preview resources\r\n"
"\0"
END
```

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
