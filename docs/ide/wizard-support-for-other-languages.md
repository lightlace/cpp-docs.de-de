---
title: "Assistentenunterstützung für andere Sprachen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.EastAsianLanguages
dev_langs: C++
helpviewer_keywords:
- wizards [C++], language support
- language support for MFC projects
- projects [C++], language support
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ef95c252621aa7f725098dfcd08c7b5b3620826
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wizard-support-for-other-languages"></a>Assistentenunterstützung für andere Sprachen
Bei der Installation von Visual Studio wird die setupanwendung erkennt das Gebietsschema, die in Ihrem System aufgeführt und der entsprechenden Sprache-Vorlage oder die Vorlagen für dieses Gebietsschema installiert. Setup installiert für westeuropäische Gebietsschemas, z. B. Englisch, Französisch, Italienisch, Spanisch und Deutsch. Diese Sprachen angezeigt, der **Ressourcensprache** auf in der Liste der [Anwendungstyp](../mfc/reference/application-type-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung.  
  
## <a name="language-templates"></a>Language-Vorlagen  
 Nicht alle Vorlagen sind auf allen Systemen installiert, da die Vorlagen sind ANSI-Codierung basieren und nicht alle Ressourcen auf allen Systemen bearbeitet werden können. Standardmäßig können nicht Sie z. B. japanische Ressourcen auf einem französischen System bearbeiten.  
  
 Wenn Sie Windows 2000 oder höher verwenden, und Sie eine MFC-Anwendung in einer anderen Sprache erstellen möchten, müssen Sie das Vorlagenverzeichnis für die entsprechende Sprache von den Medien für Visual Studio-Installer (Datenträger 1) auf Ihrem System kopieren.  
  
> [!NOTE]
>  Um das Projekt zu bearbeiten, müssen Sie Ihr Gebietsschema des Systems zur entsprechenden Gebietsschema-für die ausgewählte Sprache festlegen.  
  
 Vorlagen sind jeweils einen Ordner im Verzeichnis \Microsoft Visual Studio .NET 2003\Vc7\VCWizards\mfcappwiz\templates\ zugeordnet, wie in der folgenden Tabelle aufgeführt. Kopieren Sie die Vorlage für die gewünschte Sprache für den Zugriff auf den entsprechenden Ordner in das Verzeichnis \mfcappwiz\templates\ auf Ihrem Computer. Nachdem Sie den Ordner kopiert haben, erscheint die Sprache der **Ressourcensprache** auf in der Liste der **Anwendungstyp** Seite des Assistenten für die MFC-Anwendung.  
  
### <a name="language-templates-provided-in-visual-studio-net"></a>Language-Vorlagen in Visual Studio .NET bereitgestellt  
  
|Sprache|Vorlage|  
|--------------|--------------|  
|Chinesisch (traditionell)|1028|  
|Chinesisch (vereinfacht)|2052|  
|Englisch|1033|  
|Französisch|1036|  
|Deutsch|1031|  
|Italienisch|1040|  
|Japanisch|1041|  
|Koreanisch|1042|  
|Spanisch|3082|  
  
## <a name="format-of-visual-c-wizard-generated-files"></a>Format der Visual C++-Assistenten generierte Dateien  
 Visual C++-Assistenten erstellen Projekte im Unicode-Format an, wenn die installierte Sprachversion von Visual Studio nicht das Gebietsschema des Systems übereinstimmt. Wenn die japanische Version von Visual Studio auf einem Computer, die regionale Einstellungen, die auf einer anderen Sprache als Japanisch festgelegt wurde installiert ist, werden Visual C++-Assistenten z. B. Projekte, bestehend aus Unicode-Dateien generiert. Dies tritt häufig auf Computern mit Windows Multi (MUI) Sprachpakete einrichten.  
  
 Dieses Verhalten unterscheidet sich von Systemen, die so eingerichtet, dass das Gebietsschema des Systems identisch mit der jeweiligen Sprachversion von Visual Studio ist. In diesem Fall werden im ANSI-Projektdateien in der Codepage des Systems erstellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Erstellen und Verwalten von Visual C++-Projekten](../ide/creating-and-managing-visual-cpp-projects.md)