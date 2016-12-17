---
title: "Eigenschaftenseiten (Visual C++)"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.NotAProp.Edit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Buildmakro"
  - "Makros, Projektdatei"
  - "Projekteigenschaften [C++], Standardwerte"
  - "Projekteigenschaften [C++], Festlegen"
  - "Projektdateimakro"
  - "Eigenschaftenseiten, Projekteinstellungen"
  - "Benutzerdefinierte Makros"
  - "Benutzerdefinierte Werte"
  - "Visual C++-Projekte, Eigenschaften"
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# Eigenschaftenseiten (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mithilfe von Eigenschaftenseiten können Sie Einstellungen für Visual Studio\-Projekte angeben.  Klicken Sie zum Öffnen des Dialogfelds **Eigenschaftenseiten** für ein Visual Studio\-Projekt im Menü **Projekt** auf **Eigenschaften**.  
  
 Sie können Projekteinstellungen angeben, damit sie alle Buildkonfigurationen übernehmen. Alternativ können Sie unterschiedliche Projekteigenschaften für jede Buildkonfiguration angeben.  Beispielsweise können Sie bestimmte Einstellungen für die Releasekonfiguration und andere Einstellungen für die Debugkonfiguration festlegen.  
  
 Es werden nicht alle verfügbaren Seiten zwangsläufig im Dialogfeld **Eigenschaftenseiten** angezeigt.  Welche Seiten angezeigt werden, hängt von den Dateitypen im Projekt ab.  
  
 Weitere Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
## Standardeigenschaften im Vergleich mitgeänderten Eigenschaften  
 Beim Verwenden des Dialogfelds **Neues Projekt** zum Erstellen eines Projekts verwendet [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] die angegebene Projektvorlage, um die Projekteigenschaften zu initialisieren.  Daher können die Eigenschaftswerte in der Vorlage als Standardwerte für diesen Projekttyp betrachtet werden.  In anderen Projekttypen weisen die Eigenschaften möglicherweise unterschiedliche Standardwerte auf.  
  
 Der Wert einer Projekteigenschaft wird in Fettdruck angezeigt, wenn er geändert wird.  Eine Projekteigenschaft kann aus den folgenden Gründen geändert werden:  
  
-   Der Anwendungs\-Assistent ändert die Eigenschaft, da ein anderer Eigenschaftswert als der in der Projektvorlage angegebene erforderlich ist.  
  
-   Sie können einen anderen Eigenschaftswert im Dialogfeld **Neues Projekt** angeben.  
  
-   Das Angeben eines anderen Eigenschaftswert erfolgt auf einer Projekteigenschaftsseite.  
  
> [!TIP]
>  Um den endgültigen Satz der Eigenschaftswerte anzuzeigen, die durch MSBuild zum Erstellen Ihres Projekts verwendet werden, prüfen Sie die Präprozessorausgabedatei, die Sie mithilfe dieser Eingabe an der Befehlszeile generieren können: **MSBuild \/preprocess:***preprocessor\_output\_filename*opt *project\_filename*opt  
  
## Zurücksetzen der Eigenschaften  
 Wenn Sie das Dialogfeld **Eigenschaftenseiten** für ein Projekt anzeigen möchten und der Projektknoten im **Projektmappen\-Explorer** ausgewählt ist, können Sie für viele Eigenschaften die Option **Vom übergeordneten Projekt erben oder Projektstandard** auswählen oder den Wert anderweitig ändern.  
  
 Wenn Sie das Dialogfeld **Eigenschaftenseiten** für ein Projekt anzeigen möchten und eine Datei im **Projektmappen\-Explorer** ausgewählt ist, können Sie für viele Eigenschaften die Option **Vom übergeordneten Projekt erben oder Projektstandard** auswählen oder den Wert anderweitig ändern.  Wenn das Projekt jedoch viele Dateien enthält, die Eigenschaftswerte aufweisen, welche sich von den Projektstandardwerten unterscheiden, nimmt das Erstellen des Projekts längere Zeit in Anspruch.  
  
> [!TIP]
>  Klicken Sie zum Aktualisieren des Dialogfelds **Eigenschaftenseiten**, damit es die neuesten Auswahlen anzeigt, auf **Übernehmen**.  
  
 Bei den meisten Projektstandardwerten handelt es sich um Systemstandardwerte \(Plattform\).  Einige Projektstandardwerte werden aus den Stylesheets abgeleitet, die angewendet werden, wenn Sie die Eigenschaften im Abschnitt **Projektstandards** der Konfigurationseigenschaftsseite **Allgemein** für das Projekt aktualisieren.  Weitere Informationen finden Sie unter [Eigenschaftenseite "Allgemein" \(Projekt\)](../ide/general-property-page-project.md).  
  
## Angeben von benutzerdefinierten Werten  
 Sie müssen den Wert für bestimmte Eigenschaften definieren.  Ein benutzerdefinierter Wert kann eine oder mehrere alphanumerische Zeichen oder Projektdatei\-Makronamen enthalten.  Einige dieser Eigenschaften können nur einen benutzerdefinierten Wert verwenden. Andere wiederum können eine durch Semikolons getrennte Liste von mehreren Werten verwenden.  
  
 Um einen benutzerdefinierten Wert für eine Eigenschaft anzugeben oder eine Liste, wenn die Eigenschaft mehrere benutzerdefinierte Werte übernimmt, müssen Sie in der Spalte rechts neben dem Eigenschaftsnamen eine der folgenden Aktionen ausführen:  
  
-   Geben Sie den Wert oder die Liste der Werte ein.  
  
-   Klicken Sie auf den Dropdownpfeil.  Wenn **Bearbeiten** verfügbar ist, klicken Sie darauf, und geben Sie dann in das Textfeld den Wert oder die Liste der Werte ein.  Eine alternative Möglichkeit zum Angeben einer Liste besteht darin, jeden Wert in einer getrennten Zeile im Textfeld einzugeben.  Auf der Eigenschaftsseite werden die Werte als eine durch Semikolons getrennte Liste angezeigt.  
  
     Klicken Sie zum Einfügen eines Projektdateimakros als Wert auf **Makros**, und doppelklicken Sie dann auf den Makronamen.  
  
-   Klicken Sie auf den Dropdownpfeil.  Wenn **Durchsuchen** verfügbar ist, klicken Sie darauf, und wählen Sie dann einen oder mehrere Werte aus.  
  
 Bei einer mehrwertigen Eigenschaft steht die Option **Vom übergeordneten Projekt erben oder Projektstandard** zur Verfügung, wenn Sie auf den Dropdownpfeil in der Spalte rechts neben dem Eigenschaftsnamen klicken und anschließend auf **Bearbeiten** klicken.  Die Option ist standardmäßig ausgewählt.  
  
 Beachten Sie, dass eine Eigenschaftsseite nur die Einstellungen auf der aktuellen Ebene für eine mehrwertige Eigenschaft anzeigt, die aus einer anderen Ebene geerbt werden.  Wenn beispielsweise eine Datei im **Projektmappen\-Explorer** ausgewählt ist und Sie die Eigenschaft für die C\/C\+\+\-Präprozessordefinitionen auswählen, werden Definitionen auf Dateiebene angezeigt, geerbte Definitionen auf Projektebene jedoch nicht.  Klicken Sie zum Anzeigen der Werte auf der aktuellen Ebene und der geerbten Werte auf den Dropdownpfeil in der Spalte rechts neben dem Eigenschaftsnamen, und klicken Sie dann auf **Bearbeiten**.  Beim Verwenden des [Visual C\+\+\-Projektmodells](assetId:///06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f) gilt dieses Verhalten auch für die Objekte in Dateien und Projekten.  Wenn Sie die Werte in einer Eigenschaft auf Dateiebene abfragen, erhalten Sie demnach nicht die Werte für dieselbe Eigenschaft auf der Projektebene.  Sie müssen die Werte der Eigenschaft auf der Projektebene explizit abrufen.  Zudem stammen einige geerbten Werte einer Eigenschaft möglicherweise von einem Stylesheet, auf das nicht programmgesteuert zugegriffen werden kann.  
  
## In diesem Abschnitt  
  
1.  [Dialogfeld "Verweissuchpfad hinzufügen"](assetId:///4520d80d-aa9f-4d11-b92b-2f64a1fd5cb2)  
  
2.  [Erweitert, Manifesttool, Konfigurationseigenschaften, Dialogfeld „\<Projectname\> \-Eigenschaftenseiten“](../ide/advanced-manifest-tool.md)  
  
3.  [Eigenschaftenseiten "Befehlszeile"](../ide/command-line-property-pages.md)  
  
4.  [Eigenschaftenseite für benutzerdefinierten Buildschritt: Allgemein](../ide/custom-build-step-property-page-general.md)  
  
5.  [Hinzufügen von Verweisen](../ide/adding-references-in-visual-cpp-projects.md)  
  
6.  [Eigenschaftenseite "Allgemein" \(Datei\)](../ide/general-property-page-file.md)  
  
7.  [Eigenschaftenseite "Allgemein" \(Projekt\)](../ide/general-property-page-project.md)  
  
8.  [Allgemein, Manifesttool, Konfigurationseigenschaften, Dialogfeld „\<Projectname\> \-Eigenschaftenseiten“](../ide/general-manifest-tool-configuration-properties.md)  
  
9. [Eigenschaftenseiten "HLSL"](../ide/hlsl-property-pages.md)  
  
10. [Eigenschaftenseiten "HLSL": "Erweitert"](../ide/hlsl-property-pages-advanced.md)  
  
11. [Eigenschaftenseiten "HLSL": "Allgemein"](../ide/hlsl-property-pages-general.md)  
  
12. [Eigenschaftenseiten "HLSL": "Ausgabedateien"](../ide/hlsl-property-pages-output-files.md)  
  
13. [Eingabe und Ausgabe, Manifesttool, Konfigurationseigenschaften, Dialogfeld „\<Projectname\>\-Eigenschaftenseiten“](../ide/input-and-output-manifest-tool.md)  
  
14. [Isolated COM, Manifesttool, Konfigurationseigenschaften, Dialogfeld „\<Projectname\>\-Eigenschaftenseiten“](../ide/isolated-com-manifest-tool.md)  
  
15. [Eigenschaftenseiten "Linker"](../ide/linker-property-pages.md)  
  
16. [Eigenschaftenseite "Verwaltete Ressourcen"](../ide/managed-resources-property-page.md)  
  
17. [Eigenschaftenseiten des Manifesttools](../ide/manifest-tool-property-pages.md)  
  
18. [Eigenschaftenseiten "MIDL"](../ide/midl-property-pages.md)  
  
19. [Eigenschaftenseiten "MIDL": "Erweitert"](../ide/midl-property-pages-advanced.md)  
  
20. [Eigenschaftenseiten "MIDL": "Allgemein"](../ide/midl-property-pages-general.md)  
  
21. [Eigenschaftenseiten "MIDL": "Ausgabe"](../ide/midl-property-pages-output.md)  
  
22. [Eigenschaftenseite "NMake"](../ide/nmake-property-page.md)  
  
23. [Eigenschaftenseiten "Ressourcen"](../ide/resources-property-pages.md)  
  
24. [Eigenschaftenseite "VC\+\+\-Verzeichnisse"](../ide/vcpp-directories-property-page.md)  
  
25. [Eigenschaftenseite "Webverweise"](../ide/web-references-property-page.md)  
  
26. [Eigenschaftenseite "Tool zum Generieren von XML\-Daten"](../ide/xml-data-generator-tool-property-page.md)  
  
27. [Eigenschaftenseiten für das Tool XML\-Dokument\-Generator](../ide/xml-document-generator-tool-property-pages.md)  
  
## Siehe auch  
 [Gewusst wie: Erstellen und Entfernen von Projektabhängigkeiten](../Topic/How%20to:%20Create%20and%20Remove%20Project%20Dependencies.md)   
 [Gewusst wie: Erstellen und Bearbeiten von Konfigurationen](../Topic/How%20to:%20Create%20and%20Edit%20Configurations.md)   
 [Bereitstellen von Anwendungen](assetId:///4ff8881d-0daf-47e7-bfe7-774c625031b4)