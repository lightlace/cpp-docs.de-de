---
title: "Binary Editor"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.binary.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors, Binary"
  - "resources [Visual Studio], editing"
  - "resource editors, Binary editor"
  - "Binary editor"
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
caps.latest.revision: 14
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Binary Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  Der Binär\-Editor ist in Express\-Editionen nicht verfügbar.  
  
 Der Binär\-Editor ermöglicht eine Bearbeitung beliebige Ressourcen auf Binärebene im hexadezimalen Format oder im ASCII\-Format. Außerdem können Sie mit dem [Suchbefehl](../Topic/Find%20Command.md) ASCII\-Zeichenfolgen oder hexadezimale Bytes suchen. Der Binär\-Editor sollte nur dann verwendet werden, wenn Sie von der Visual Studio\-Umgebung nicht unterstützte, benutzerdefinierte Ressourcen oder Ressourcentypen anzeigen oder geringfügige Änderungen daran vornehmen möchten.  
  
 Zum Öffnen von binären Editor wählen Sie im Hauptmenü zuerst **Datei &#124; Neu &#124; Datei** aus, wählen Sie die zu bearbeitende Datei aus, klicken Sie auf den Dropdownpfeil neben der Schaltfläche **Öffnen**, und wählen Sie **Öffnen mit &#124; Binärer Editor** aus.  
  
> [!CAUTION]
>  Das Bearbeiten von Ressourcen, wie Dialogfeldern, Bildern oder Menüs ist im Binär\-Editor äußerst riskant. Eine falsche Bearbeitung kann zu einer Beschädigung der Ressource führen, sodass sie anschließend im systemeigenen Editor nicht mehr einsetzbar ist.  
  
> [!TIP]
>  Indem Sie im Binär\-Editor auf die rechte Maustaste klicken, können Sie in vielen Situationen ein Kontextmenü aufrufen, in dem ressourcenspezifische Befehle enthalten sind. Welche Befehle verfügbar sind, hängt von dem Element ab, auf das Sie mit dem Cursor zeigen. Wenn Sie zum Beispiel mit der Maustaste klicken, während Sie auf den Binär\-Editor zeigen, und im Binär\-Editor Hexadezimalwerte markiert sind, enthält das Kontextmenü die Befehle **Ausschneiden**, **Kopieren** und **Einfügen**.  
  
 Mit dem Binär\-Editor können Sie die folgenden Funktionen ausführen:  
  
-   [Eine Ressource für die Binärbearbeitung öffnen](../mfc/opening-a-resource-for-binary-editing.md)  
  
-   [Binärdaten bearbeiten](../mfc/editing-binary-data.md)  
  
-   [Binärdaten suchen](../mfc/finding-binary-data.md)  
  
-   [Eine neue benutzerdefinierte Ressource oder Datenressource erstellen](../mfc/creating-a-new-custom-or-data-resource.md)  
  
## Verwaltete Ressourcen  
 Mit dem [Bild\-Editor](../mfc/image-editor-for-icons.md) und dem Binär\-Editor ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio\-Ressourcen\-Editoren nicht unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Anforderungen  
 Keine  
  
## Siehe auch  
 [Resource Editors](../mfc/resource-editors.md)