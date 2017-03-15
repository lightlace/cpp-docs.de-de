---
title: "How to: Use Resource Templates | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "language-specific template files"
  - "resource templates"
  - "resources [Visual Studio], creating"
  - "rct files"
  - "templates, resource templates"
  - "resources [Visual Studio], templates"
  - ".rct files"
ms.assetid: bdfe7060-f98e-4859-8285-9c8570360e9d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# How to: Use Resource Templates
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Ressourcenvorlage ist eine benutzerdefinierte Ressource, die Sie als RCT\-Datei gespeichert haben.  Eine Ressourcenvorlage kann dann als Ausgangspunkt für die Erstellung weiterer Ressourcen dienen.  Ressourcenvorlagen sparen Zeit bei der Entwicklung von zusätzlichen Ressourcen oder Gruppen von Ressourcen, die Funktionen wie Standardsteuerelemente oder andere wiederkehrende Elemente gemeinsam nutzen.  Zum Beispiel können Sie eine Hilfeschaltfläche und ein Symbol eines Firmenlogos in mehrere Dialogfelder einfügen.  Um dies schnell zu tun, erstellen Sie eine neue Dialogfeldvorlage, und passen Sie sie mit dem Logo und der Hilfeschaltfläche an.  
  
 Nachdem Sie die Ressourcenvorlage angepasst haben, müssen Sie die Änderungen im Vorlagenordner \(oder an einem anderen im Includepfad angegebenen Speicherort\) speichern, damit die neue Ressourcenvorlage unter ihrem Ressourcentyp im Dialogfeld [Ressource hinzufügen](../windows/add-resource-dialog-box.md) angezeigt wird.  Sie können die neue Ressourcenvorlage dann beliebig oft verwenden.  
  
> [!NOTE]
>  Sie können sprachspezifische Vorlagendateien in Unterverzeichnissen des zentralen Vorlagenverzeichnisses platzieren.  Sie können z. B. rein englischsprachige Vorlagendateien unter \\\<Ressourcenvorlagenverzeichnis\>\\1033 platzieren.  
  
### So erstellen Sie eine Vorlage für Ressourcen  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf Ihr Projekt.  
  
2.  Wählen Sie im Kontextmenü die Option **Hinzufügen** aus, und klicken Sie danach auf **Neues Element hinzufügen**.  
  
3.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** im Bereich **Vorlagen:** die Option **Ressourcenvorlagendatei \(.rct\)**.  
  
4.  Geben Sie einen Namen und Speicherort für die neue RCT\-Datei an, und klicken Sie auf **Öffnen**.  
  
5.  Die neue RCT\-Datei wird dem Projekt hinzugefügt und im Projektmappen\-Explorer unter dem Ordner **Ressourcen** angezeigt.  
  
     Sie können jetzt auf die RCT\-Datei doppelklicken, um sie in einem Dokumentfenster zu öffnen, und ihr dann Ressourcen hinzufügen \(klicken Sie mit der rechten Maustaste auf die Datei im Dokumentfenster, und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü\).  Dann können Sie diese Ressourcen anpassen und die RCT\-Datei speichern.  
  
    > [!NOTE]
    >  Wenn Sie eine neue RCT\-Datei erstellen, sucht Visual Studio diese unter \\Programme\\Microsoft Visual Studio 9.0\\VC\\VCResourceTemplates unter \\Programme\\Microsoft Visual Studio 9.0\\VC\\VCResourceTemplates\\*LCID* \(z. B. 1033 für Englisch\) *oder* an einer anderen Stelle im [Includepfad](../windows/how-to-specify-include-directories-for-resources.md).  Wenn Sie es vorziehen, die RCT\-Dateien in einem anderen Dateiordner zu speichern, z. B. \\Eigene Dokumente, müssen Sie diesen Ordner lediglich zum Includepfad hinzufügen und Visual Studio findet die RCT\-Datei.  
  
### So konvertieren Sie eine vorhandene RC\-Datei in eine RCT\-Datei  
  
1.  [Öffnen Sie die RC\-Datei als eigenständige Datei](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
2.  Klicken Sie im Menü **Datei** auf **\<*Dateiname*\> speichern unter**.  
  
3.  Geben Sie einen Speicherort an, und klicken Sie auf **OK**.  
  
### So erstellen Sie eine neue Ressource aus einer Vorlage  
  
1.  Klicken Sie im Bereich [Ressourcenansicht](../windows/resource-view-window.md) mit der rechten Maustaste auf die RC\-Datei, und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü aus.  
  
2.  Klicken Sie im Dialogfeld **Ressource hinzufügen** auf das Pluszeichen \(**\+**\) neben einer Ressource, um den Ressourcenknoten zu erweitern und alle für diese Ressource verfügbaren Vorlagen anzuzeigen.  
  
3.  Doppelklicken Sie auf die Vorlage, die Sie verwenden möchten.  
  
4.  Ändern Sie die hinzugefügte Ressource nach Bedarf im zugehörigen Ressourcen\-Editor.  
  
     Der Ressourcen\-Editor stellt automatisch eine eindeutige Ressourcen\-ID bereit.  Sie können die [Ressourceneigenschaften](../windows/changing-the-properties-of-a-resource.md) je nach Bedarf überarbeiten.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.*  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)