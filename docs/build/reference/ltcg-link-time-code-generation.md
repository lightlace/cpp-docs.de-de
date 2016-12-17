---
title: "/LTCG (Code zur Verkn&#252;pfungszeit generieren)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.LinkTimeCodeGeneration"
  - "VC.Project.VCConfiguration.WholeProgramOptimization"
  - "VC.Project.VCCLWCECompilerTool.WholeProgramOptimization"
  - "/ltcg"
  - "VC.Project.VCCLCompilerTool.WholeProgramOptimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LTCG (Linkeroption)"
  - "Link-Time-Codegenerierung im C++-Linker"
  - "LTCG (Linkeroption)"
  - "-LTCG (Linkeroption)"
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# /LTCG (Code zur Verkn&#252;pfungszeit generieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LTCG[:INCREMENTAL|:NOSTATUS|:STATUS|:OFF|:PGINSTRUMENT|:PGOPTIMIZE|:PGUPDATE]  
```  
  
## Hinweise  
 :INCREMENTAL \(optional\)  
 Gibt an, dass der Linker Optimierung des gesamten Programms oder Link\-Zeitcodegenerierung \(LTCG, Link\-Time Code Generation\) nur auf die von einer Bearbeitung betroffenen Dateien anwendet, statt auf das gesamte Projekt. Standardmäßig ist dieses Kennzeichen nicht festgelegt, wenn \/LTCG angegeben wird, und das gesamte Projekt wird mit Optimierung des gesamten Programms gelinkt.  
  
 :NOSTATUS &#124; :STATUS \(optional\)  
 Gibt an, ob der Linker eine Statusanzeige ausgibt, die anzeigt, welcher Prozentsatz des Linkvorgangs abgeschlossen ist. Standardmäßig werden diese Statusinformationen nicht angezeigt.  
  
 :OFF \(optional\)  
 Deaktiviert die Link\-Zeitcodegenerierung. Dieses Verhalten entspricht der fehlenden Angabe von \/LTCG in der Befehlszeile.  
  
 :PGINSTRUMENT \(optional\)  
 Diese Option ist veraltet. Verwenden Sie stattdessen **\/LTCG** und **\/GENPROFILE** oder **\/FASTGENPROFILE**, um einen instrumentierten Build für die profilgesteuerte Optimierung zu erstellen.  
  
 Die Daten, die von den instrumentierten Ausführungen erfasst werden, werden verwendet, um ein optimiertes Image zu erstellen. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md). Die Kurzform dieser Option lautet \/LTCG:PGI.  
  
 :PGOPTIMIZE \(optional\)  
 Diese Option ist veraltet. Verwenden Sie stattdessen **\/LTCG** und **\/USEPROFILE** zum Erstellen eines optimierten Images. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md). Die Kurzform dieser Option lautet \/LTCG:PGO.  
  
 :PGUPDATE \(optional\)  
 Diese Option ist veraltet. Verwenden Sie stattdessen **\/LTCG** und **\/USEPROFILE** zum Erstellen eines optimierten Images. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md). Die Kurzform dieser Option lautet \/LTCG:PGU.  
  
 Die Option „\/LTCG“ weist den Linker an, den Compiler aufzurufen und die Optimierung des gesamten Programms auszuführen. Alternativ können Sie auch eine profilgesteuerte Optimierung ausführen. Weitere Informationen finden Sie unter [Profilgesteuerte Optimierung](../../build/reference/profile-guided-optimizations.md).  
  
 Abgesehen von den folgenden Ausnahmen, können Sie der PGO\-Kombination aus „\/LTCG“ und „\/USEPROFILE“ keine Linkeroptionen hinzufügen, die in der vorherigen PGO\-Initialisierungskombination der Optionen „\/LTCG“ und „\/GENPROFILE“ noch nicht angegeben waren:  
  
-   [\/BASE](../../build/reference/base-base-address.md)  
  
-   [\/FIXED](../../build/reference/fixed-fixed-base-address.md)  
  
-   \/LTCG  
  
-   [\/MAP](../../build/reference/map-generate-mapfile.md)  
  
-   [\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)  
  
-   [\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)  
  
-   [\/OUT](../../build/reference/out-output-file-name.md)  
  
-   [\/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)  
  
-   [\/PDB](../../build/reference/pdb-use-program-database.md)  
  
-   [\/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)  
  
-   [\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)  
  
-   [\/VERBOSE](../../build/reference/verbose-print-progress-messages.md)  
  
 Alle Linkeroptionen, die zusammen mit den Optionen „\/LTCG“ und „\/GENPROFILE“ zum Initialisieren von PGO angegeben werden, müssen beim Erstellen von Builds mithilfe von „\/LTCG“ und „\/USEPROFILE“ nicht angegeben werden; sie gelten implizit.  
  
 Im Rest dieses Themas wird „\/LTCG“ im Zusammenhang mit der Link\-Zeitcodegenerierung erörtert.  
  
 „\/LTCG“ ist in [\/GL](../../build/reference/gl-whole-program-optimization.md) impliziert.  
  
 Der Linker ruft die Link\-Zeitcodegenerierung auf, wenn ihm ein Modul übergeben wird, das mithilfe von **\/GL** oder einem MSIL\-Modul kompiliert wurde \(siehe dazu [.NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md)\). Wenn Sie **\/LTCG** beim Übergeben von **\/GL** oder von MSIL\-Modulen an den Linker nicht explizit angeben, erkennt der Linker dies möglicherweise, und startet das Linken mithilfe von **\/LTCG** erneut. Geben Sie **\/LTCG** beim Übergeben von **\/GL** und MSIL\-Modulen an den Linker explizit an, um eine möglichst schnelle Builderstellung zu erreichen.  
  
 Eine noch schnellere Leistung erreichen Sie mit **\/LTCG:INCREMENTAL**. Diese Option weist den Linker an, nur die Menge der Dateien erneut zu optimieren, die von einer Änderung der Quelldatei betroffen sind, statt des gesamten Projekts. Dadurch kann sich die erforderliche Linkzeit erheblich verringern. Dies ist nicht die gleiche Option wie inkrementelles Linken.  
  
 **\/LTCG** ist für die Verwendung mit [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) nicht gültig.  
  
Wenn **\/LTCG** zum Linken von Modulen verwendet wird, die mithilfe von [\/Og](../../build/reference/og-global-optimizations.md), [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder [\/Ox](../../build/reference/ox-full-optimization.md) kompiliert wurden, werden die folgenden Optimierungen ausgeführt:  
  
-   Inlineoptimierung über verschiedene Module hinweg  
  
-   Interprozedurale Registerreservierung \(nur bei 64\-Bit\-Betriebssystemen\)  
  
-   Benutzerdefinierte Aufrufkonvention \(nur x86\)  
  
-   Geringe TLS\-Verschiebung \(nur x86\)  
  
-   Doppelte Stapelausrichtung \(nur x86\)  
  
-   Verbesserte Speichereindeutigkeit \(verbesserte Interferenzinformationen für globale Variablen und Eingabeparameter\)  
  
> [!NOTE]
> Der Linker bestimmt, welche Optimierungen zum Kompilieren der einzelnen Funktionen verwendet wurden, und wendet die gleichen Optimierungen zur Linkzeit an.  
  
Die Verwendung von **\/LTCG** und **\/Ogt** führt zur Optimierung mittels doppelter Ausrichtung.  
  
Wenn **\/LTCG** und **\/Ogs** angegeben werden, erfolgt keine doppelte Ausrichtung. Wenn die meisten Funktionen in einer Anwendung nach Geschwindigkeit und nur wenige Funktionen nach Größe kompiliert werden \(z. B. durch Verwendung des [optimize](../../preprocessor/optimize.md)\-Pragmas\), richtet der Compiler die nach Größe kompilierten Funktionen doppelt aus, wenn Sie Funktionen aufrufen, die eine doppelte Ausrichtung erfordern.  
  
Wenn er alle Aufrufziele einer Funktion identifizieren kann, ignoriert der Compiler die expliziten Aufrufkonventionsmodifizierer der Funktion und versucht, die Aufrufkonvention der Funktion zu optimieren:  
  
-   Übergeben von Parametern in Registern  
  
-   Neuanordnen von Parametern zur Ausrichtung  
  
-   Entfernen nicht verwendeter Parameter  
  
Wenn eine Funktion über einen Funktionszeiger oder außerhalb eines mit **\/GL** kompilierten Moduls aufgerufen wird, versucht der Compiler keine Optimierung der Aufrufkonvention der Funktion.  
  
> [!NOTE]
> Wenn Sie **\/LTCG** und mainCRTStartup neu definieren, kann die Anwendung unvorhergesehenes Verhalten zeigen, das auf die Ausführung von Benutzercode vor Initialisierung globaler Objekte zurückzuführen ist.   Es gibt drei Möglichkeiten, dieses Problem zu beheben: Definieren Sie mainCRTStartup nicht neu, kompilieren Sie die mainCRTStartup enthaltende Datei mit **\/LTCG**, oder initialisieren Sie globale Variablen und Objekte nach Möglichkeit statisch.  
  
## \/ LTCG und MSIL\-Module  
Mit [\/GL](../../build/reference/gl-whole-program-optimization.md) und [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) kompilierte Module können als Eingabe für den Linker verwendet werden, wenn **\/LTCG** angegeben ist.  
  
-   **\/LTCG** akzeptiert systemeigene Objektdateien, gemischte systemeigene\/verwaltete Objektdateien \(kompiliert mit **\/clr**\), reine Objektdateien \(kompiliert mit **\/clr:pure**\) sowie sichere Objektdateien \(kompiliert mit **\/clr:safe**\)  
  
-   **\/LTCG** akzeptiert sichere NETMODULE\-Dateien, die in Visual C\+\+ mit **\/clr:safe \/LN** erstellt werden können, sowie **\/target:module**, kompiliert mit einem beliebigen anderen Visual Studio\-Compiler. NETMODULE\-Dateien, die mit **\/clr** oder **\/clr:pure** erzeugt wurden, werden von **\/LTCG** jedoch nicht akzeptiert.  
  
-   \/LTCG:PGI akzeptiert keine systemeigenen mit **\/GL** und **\/clr**, kompilierten Module und keine reinen \(mithilfe von **\/clr:pure** erzeugten\) Module  
  
#### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Siehe [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Konfigurationseigenschaften** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Allgemein** aus.  
  
4.  Ändern Sie die Eigenschaft **Optimierung des ganzen Programms**.  
  
Sie können **\/LTCG** auch auf bestimmte Builds anwenden, indem Sie **Build**, **Profilgesteuerte Optimierung** auf der Menüleiste oder eine der Optionen für die profilgesteuerte Optimierung im Kontextmenü des Projekts auswählen.  
  
#### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration*>.  
  
## Siehe auch  
[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
[Linkeroptionen](../../build/reference/linker-options.md)