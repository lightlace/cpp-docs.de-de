---
title: "Assistentenunterst&#252;tzung f&#252;r andere Sprachen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.EastAsianLanguages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Sprachenunterstützung für MFC-Projekte"
  - "Projekte [C++], Sprachenunterstützung"
  - "Assistenten [C++], Sprachenunterstützung"
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Assistentenunterst&#252;tzung f&#252;r andere Sprachen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei der Installation von Visual Studio wird das im System eingestellte Gebietsschema vom Setupprogramm erkannt, und es werden eine oder mehrere geeignete Sprachvorlagen für dieses Gebietsschema installiert.  Für westeuropäische Gebietsschemas installiert Setup beispielsweise Englisch, Französisch, Italienisch, Spanisch und Deutsch.  Diese Sprachen werden auf der Seite [Anwendungstyp](../mfc/reference/application-type-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten in der Liste **Ressourcensprache** angezeigt.  
  
## Sprachvorlagen  
 Nicht auf allen Systemen werden auch alle Vorlagen installiert, da die Vorlagen auf ANSI\-Codierung basieren. Dies führt dazu, dass nicht alle Ressourcen auch auf allen Systemen bearbeitet werden können.  Beispielsweise können japanische Ressourcen grundsätzlich nicht auf einem französischen System bearbeitet werden.  
  
 Wenn Sie Windows 2000 oder eine höhere Version verwenden und eine MFC\-Anwendung in einer anderen Sprache erstellen möchten, müssen Sie das Vorlagenverzeichnis für die betreffende Sprache von den Visual Studio\-Installationsmedien \(CD 1\) auf Ihr System kopieren.  
  
> [!NOTE]
>  Um das erstellte Projekt zu bearbeiten, müssen Sie als Systemgebietsschema das Gebietsschema einstellen, das der ausgewählten Sprache entspricht.  
  
 Wie Sie der folgenden Tabelle entnehmen können, ist jeder Vorlage ein Ordner im Verzeichnis **\\Microsoft Visual Studio .NET 2003\\Vc7\\VCWizards\\mfcappwiz\\templates\\** zugeordnet.  Um auf die gewünschte Sprachvorlage zuzugreifen, kopieren Sie den entsprechenden Ordner in das Verzeichnis **\\mfcappwiz\\templates\\** auf Ihrem Computer.  Nachdem Sie den Ordner kopiert haben, wird die Sprache auf der Seite **Anwendungstyp** des MFC\-Anwendungs\-Assistenten in der Liste **Ressourcensprache** angezeigt.  
  
### In Visual Studio .NET verfügbare Sprachvorlagen  
  
|Sprache|Vorlage|  
|-------------|-------------|  
|Chinesisch \(traditionell\)|1028|  
|Chinesisch \(vereinfacht\)|2052|  
|Englisch|1033|  
|Französisch|1036|  
|Deutsch|1031|  
|Italienisch|1040|  
|Japanisch|1041|  
|Koreanisch|1042|  
|Spanisch|3082|  
  
## Format der von Visual C\+\+\-Assistenten generierten Dateien  
 Wenn die installierte Sprachversion von Visual Studio nicht mit dem Systemgebietsschema übereinstimmt, generieren die Visual C\+\+\-Assistenten Projekte im Unicode\-Format.  Wenn beispielsweise die japanische Version von Visual Studio auf einem Computer installiert ist, in dessen Ländereinstellungen eine andere Sprache als Japanisch ausgewählt ist, bestehen die von den Visual C\+\+\-Assistenten generierten Projekte aus Unicode\-Dateien.  Dies trifft allgemein auf Computer zu, die mit Windows Multi Language Packs \(MUI\) eingerichtet wurden.  
  
 Dieses Verhalten trifft nicht auf Systeme zu, bei denen das Systemgebietsschema und die Sprachversion von Visual Studio einander entsprechen.  In diesem Fall werden Projektdateien im ANSI\-Format in der Systemcodepage erstellt.  
  
## Siehe auch  
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Erstellen und Verwalten von Visual C\+\+\-Projekten](../ide/creating-and-managing-visual-cpp-projects.md)