---
title: "Vorgehensweise: Organisieren von Projektausgabedateien für Builds | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++, output files
- output files, organizing
ms.assetid: 521d95ea-2dcc-4da0-b5eb-ac3e57941446
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 648321c41fe02541eeb746bae24236c40dc5325e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-organize-project-output-files-for-builds"></a>Gewusst wie: Organisieren von Projektausgabedateien für Builds
In diesem Thema werden empfohlene Vorgehensweisen zum Organisieren von Projektausgabedateien beschrieben. Wenn Projektausgabedateien falsch eingerichtet werden, können Buildfehler auftreten. Außerdem werden in diesem Thema die Vor- und Nachteile der einzelnen Möglichkeiten zum Organisieren von Projektausgabedateien erörtert.  
  
## <a name="referencing-clr-assemblies"></a>Verweisen auf CLR-Assemblys  
  
#### <a name="to-reference-assemblies-with-using"></a>So verweisen Sie mit #using auf Assemblys  
  
1.  Sie können direkt aus dem Code heraus auf eine Assembly verweisen, indem Sie eine #using-Direktive wie `#using <System.Data.dll>` verwenden. Weitere Informationen finden Sie unter [#using-Direktive](../preprocessor/hash-using-directive-cpp.md).  
  
     Die angegebene Datei kann eine DLL-, EXE, .NETMODULE oder OBJ-Datei sein, solange sie in MSIL ist. Die Komponente, auf die verwiesen wird, kann in einer beliebigen Sprache erstellt sein. Mit dieser Option erhalten Sie Zugriff auf Intellisense, da die Metadaten aus MSIL extrahiert werden. Die fragliche Datei muss sich im Pfad für das Projekt befinden, ansonsten wird das Projekt nicht kompiliert, und Intellisense ist nicht verfügbar. Eine einfache Möglichkeit, zu bestimmen, ob die Datei im Pfad befindet, mit der Maustaste wird das #using Zeile, und wählen Sie die **geöffneten Dokument** Befehl. Wenn die Datei nicht gefunden werden kann, erhalten Sie eine Benachrichtigung.  
  
     Wenn Sie nicht den vollständigen Pfad zur Datei eingeben möchten, können Sie mithilfe der **/AI** -Compileroption den Suchpfad für Bearbeiten #using verweisen. Weitere Informationen finden Sie unter [/AI (Metadatenverzeichnisse festlegen)](../build/reference/ai-specify-metadata-directories.md).  
  
#### <a name="to-reference-assemblies-with-fu"></a>So verweisen Sie mit /FU auf Assemblys  
  
1.  Anstelle von Verweisen auf eine Assembly direkt aus einer Codedatei an, wie oben beschrieben, können Sie die **/FU** -Compileroption. Der Vorteil dieses Verfahrens besteht darin, dass Sie nicht jeder einzelnen Datei eine separate, auf eine bestimmte Assembly verweisende #using-Anweisung hinzufügen müssen.  
  
     Um diese Option festzulegen, öffnen Sie die **Eigenschaftenseiten** für das Projekt. Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **C/C++-** Knoten, und wählen **erweitert**. Fügen Sie neben der gewünschten Assemblys **Force #using**. Weitere Informationen finden Sie unter [/FU (Name der expliziten #using-Datei)](../build/reference/fu-name-forced-hash-using-file.md).  
  
#### <a name="to-reference-assemblies-with-add-new-reference"></a>So verweisen Sie mit "Neuen Verweis hinzufügen" auf Assemblys  
  
1.  Dies ist die einfachste Möglichkeit, CLR-Assemblys zu nutzen. Zuerst stellen Sie sicher, dass das Projekt kompiliert mit der **"/ CLR"** -Compileroption. Klicken Sie im mit der rechten Maustaste auf das Projekt aus der **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **Verweise**. Die **Eigenschaftenseiten** Dialogfeld wird angezeigt.  
  
2.  Aus der **Eigenschaftenseiten** wählen Sie im Dialogfeld **neuen Verweis hinzufügen**. Daraufhin wird ein Dialogfeld angezeigt, in dem alle im aktuellen Projekt verfügbaren .NET-Assemblys, COM-Assemblys und sonstigen Assemblys aufgelistet werden. Wählen Sie die gewünschte Assembly aus, und klicken Sie auf **OK**.  
  
     Sobald ein Projektverweis festgelegt ist, werden die entsprechenden Abhängigkeiten automatisch behandelt. Da eine Assembly Metadaten enthält, ist es auch nicht erforderlich, den Elementen, die von verwalteten Assemblys verwendet werden, eine Headerdatei oder einen Prototyp hinzuzufügen.  
  
## <a name="referencing-native-dlls-or-static-libraries"></a>Verweisen auf systemeigene DLLs oder statische Bibliotheken  
  
#### <a name="to-reference-native-dlls-or-static-libraries"></a>So verweisen Sie auf systemeigene DLLs oder statische Bibliotheken  
  
1.  Verweisen Sie mit der #include-Direktive auf die entsprechende Headerdatei im Code. Die Headerdatei muss sich im include-Pfad befinden oder dem aktuellen Projekt angehören. Weitere Informationen finden Sie unter [#include-Direktive (C/C++)](../preprocessor/hash-include-directive-c-cpp.md).  
  
2.  Sie können auch Projektabhängigkeiten festlegen. Das Festlegen von Projektabhängigkeiten garantiert zwei Dinge: Zum einen gewährleistet es, dass Projekte in der richtigen Reihenfolge erstellt werden, damit ein Projekt immer die benötigten abhängigen Dateien findet. Zum anderen wird implizit das Ausgabeverzeichnis des abhängigen Projekts zum Pfad hinzugefügt, damit Dateien zum Zeitpunkt der Verknüpfung mühelos gefunden werden können.  
  
3.  Um die Anwendung bereitzustellen, müssen Sie die DLL an einer geeigneten Stelle platzieren. Folgende Möglichkeiten stehen zur Auswahl:  
  
    1.  In demselben Pfad wie die ausführbare Datei.  
  
    2.  Eine beliebige Stelle im Systempfad (der **Pfad** Umgebungsvariable).  
  
    3.  In der parallelen Assembly. Weitere Informationen finden Sie unter [Erstellen von C/C++-Seite-an-Seite-Assemblys](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## <a name="working-with-multiple-projects"></a>Arbeiten mit mehreren Projekten  
 Projekte werden standardmäßig so erstellt, dass alle Ausgabedateien in einem Unterverzeichnis des Projektverzeichnisses erstellt werden. Das Verzeichnis wird basierend auf der Buildkonfiguration benannt (z. B. Debug- oder Release). Damit nebengeordnete Projekte erfolgreich aufeinander verweisen können, müssen in jedem Projekt die Ausgabeverzeichnisse des jeweils anderen Projekts dem Pfad hinzugefügt werden. Dies erfolgt beim Festlegen der Projektabhängigkeiten automatisch. Wenn Sie allerdings keine Abhängigkeiten verwenden, müssen Sie bei der Behandlung dieses Aspekts mit Sorgfalt vorgehen, da die Verwaltung von Builds sehr komplex werden kann. Wenn ein Projekt beispielsweise über Debug- und Releasekonfigurationen verfügt und eine externe Bibliothek aus einem nebengeordneten Projekt umfasst, muss je nach Konfiguration, die erstellt wird, eine andere Bibliotheksdatei verwendet werden.  Eine feste Programmierung dieser Pfade kann sich also als kompliziert erweisen.  
  
 Alle wichtigen Ausgabedateien (z. B. ausführbare Dateien, Incremental Linker-Dateien und PDB-Dateien) werden in ein gemeinsames Projektmappenverzeichnis kopiert. Zur Vereinfachung der Verknüpfung und Bereitstellung werden demnach bei der Arbeit mit einer Lösung, die mehrere C++-Projekte mit äquivalenten Konfigurationen umfasst, alle Ausgabedateien zentral zusammengefasst. Wenn Sie diese Dateien zusammenhalten, können Sie sicher sein, dass die Anwendung/Bibliothek erwartungsgemäß funktioniert (da gewährleistet ist, dass sich die Dateien im Pfad befinden).  
  
 Bei der Bereitstellung in einer Produktionsumgebung kann der Speicherort der Ausgabedateien ein ernstes Problem darstellen. Während der Ausführung von Projekten in der IDE müssen die Pfade zu den enthaltenen Bibliotheken nicht notwendigerweise mit denjenigen in der Produktionsumgebung übereinstimmen. Wenn der Code beispielsweise `#using "../../lib/debug/mylib.dll"` umfasst und Sie dann mylib.dll an einer anderen relativen Position bereitstellen, generiert die Anwendung zur Laufzeit einen Fehler.  Um dies zu verhindern, sollten Sie in #include-Anweisungen in Ihrem Code keine relativen Pfade verwenden. Es wird empfohlen sicherzustellen, dass die erforderlichen Dateien sich im Projektbuildpfad befinden und dass die entsprechenden Produktionsdateien korrekt platziert sind.  
  
#### <a name="how-to-specify-where-output-files-go"></a>So geben Sie den Speicherort von Ausgabedateien an  
  
1.  Der Speicherort der Projektausgabe Einstellungen finden Sie in des Projekts **Eigenschaftenseiten**. Erweitern Sie den Knoten neben **Konfigurationseigenschaften** , und wählen Sie **allgemeine**. Neben der Ausgabespeicherort angegeben **Ausgabeverzeichnis**. Weitere Informationen finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../ide/general-property-page-project.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Visual C++-Projekttypen](../ide/visual-cpp-project-types.md)