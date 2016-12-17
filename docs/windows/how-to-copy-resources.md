---
title: "How to: Copy Resources"
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
  - "vc.resvw.resource.copying"
  - "vs.resvw.resource.copying"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], moving between files"
  - "resources [Visual Studio], copying"
  - "resource files, copying or moving resources between"
  - "resource files, tiling"
  - ".rc files, copying resources between"
  - "rc files, copying resources between"
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Copy Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie haben die Möglichkeit, Ressourcen unverändert von einer Datei in eine andere zu kopieren oder die [Sprache oder Bedingung einer Ressource während des Kopiervorgangs zu ändern](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md).  
  
 Ressourcen können problemlos von einer vorhandenen Ressource oder ausführbaren Datei in die aktuelle Ressourcendatei kopiert werden.  Zu diesem Zweck öffnen Sie beide Dateien, die die Ressourcen enthalten, gleichzeitig und ziehen die Elemente von einer Datei in eine andere bzw. verschieben die Elemente durch Kopieren und Einfügen zwischen den beiden Dateien.  Diese Methode ist sowohl auf Ressourcenskriptdateien \(**.rc**\) als auch auf Ressourcenvorlagendateien \(**.rct**\) und ausführbare Dateien \(**.exe**\) anwendbar.  
  
> [!NOTE]
>  Visual C\+\+ enthält Beispielressourcendateien, die Sie in Ihrer eigenen Anwendung verwenden können.  Weitere Informationen erhalten Sie unter [CLIPART: Allgemeine Ressourcen](assetId:///9bac2891-b6b3-49ec-a287-cec850c707e0).  
  
 Für RC\-Dateien, die [außerhalb des Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md) geöffnet sind, können Sie die Drag & Drop\-Methode verwenden.  
  
### So kopieren Sie Ressourcen durch Drag & Drop zwischen Dateien  
  
1.  Öffnen Sie beide Ressourcendateien eigenständig \(weitere Informationen finden Sie unter [Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts \(eigenständig\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)\).  Öffnen Sie beispielsweise **Source1.rc** und **Source2.rc**.  
  
2.  Klicken Sie in der ersten RC\-Datei auf die Ressource, die Sie kopieren möchten.  Klicken Sie in **Source1.rc** beispielsweise auf **IDD\_DIALOG1**.  
  
3.  Halten Sie STRG gedrückt, und ziehen Sie die Ressource in die zweite RC\-Datei.  Ziehen Sie **IDD\_DIALOG1** z. B. von **Source1.rc** in **Source2.rc**.  
  
    > [!NOTE]
    >  Wenn Sie die Ressource ziehen, ohne STRG gedrückt zu halten, wird sie verschoben und nicht kopiert.  
  
### So kopieren Sie Ressourcen durch "Kopieren" und "Einfügen"  
  
1.  Öffnen Sie beide Ressourcendateien eigenständig \(weitere Informationen finden Sie unter [Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts \(eigenständig\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)\).  Öffnen Sie beispielsweise **Source1.rc** und **Source2.rc**.  
  
2.  Klicken Sie in der Quelldatei, aus der Sie eine Ressource kopieren möchten \(z. B. **Source1.rc**\) mit der rechten Maustaste auf eine Ressource, und wählen Sie den Befehl **Kopieren** aus dem Kontextmenü.  
  
3.  Klicken Sie mit der rechten Maustaste auf die Ressourcendatei, in die Sie die Ressource einfügen möchten \(z. B. **Source2.rc**\).  Wählen Sie im Kontextmenü den Befehl **Einfügen**.  
  
    > [!NOTE]
    >  Zwischen Ressourcendateien im Projekt \(Ressourcenansicht\) und eigenständigen RC\-Dateien \(die in Dokumentfenstern geöffnet werden\) können Sie weder Drag & Drop noch die Befehle Kopieren, Ausschneiden oder Einfügen verwenden.  In früheren Produktversionen war diese Vorgehensweise jedoch möglich.  
  
    > [!NOTE]
    >  Um Konflikte mit Symbolnamen oder \-werten in der vorhandenen Datei zu vermeiden, ändert Visual C\+\+ u. U. den Symbolwert der übertragenen Ressource bzw. den Symbolnamen und Symbolwert, wenn Sie die Ressource in die neue Datei kopieren.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)