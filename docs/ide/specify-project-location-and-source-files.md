---
title: Neues Projekt aus vorhandenem Code - Quelldateien (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.importwiz.location
dev_langs: C++
ms.assetid: 29ddffb9-5918-4d72-8c7a-a365f9de96dd
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 36b20340da6cae933acb0650b3e073e3835a0204
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="specify-project-location-and-source-files-create-new-project-from-existing-code-files-wizard"></a>Projektspeicherort und Quelldateien festlegen, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"
Geben Sie mithilfe dieser Seite des Assistenten für neue Projekt aus vorhandenen Codedateien erstellen:  
  
-   Der Verzeichnispfad des neuen Projekts  
  
-   Die Verzeichnisse, nach vorhandenen Quelldateien gesucht werden soll.  
  
-   Der hochzuladenden Dateien wird vom Assistenten in das neue Projekt importiert.  
  
## <a name="task-list"></a>Aufgabenliste  
 [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Projekt-Dateispeicherort**  
 Gibt den Verzeichnispfad des neuen Projekts an. Dieser Speicherort unterscheidet, in dem der Assistent alle Dateien (und Unterverzeichnisse) des neuen Projekts ablegt.  
  
 **Browse** (Durchsuchen)  
 Zeigt die **Projekt Dateispeicherort** Dialogfelds können Sie das Verzeichnis angeben, die das neue Projekt enthält. Dieses Steuerelement ermöglicht es Ihnen, zum gewünschten Ordner zu navigieren.  
  
 **Projektname**  
 Gibt den Namen des neuen Projekts. Projektdateien, die Datei-Erweiterungen, z. B. vcxproj haben werden, diesen Namen übernehmen. Vorhandenen Codedateien behält ihren ursprünglichen Namen.  
  
 **Hinzufügen von Dateien zum Projekt aus diesen Ordnern**  
 Wenn dieses Kontrollkästchen aktiviert, legt den Assistenten zum Kopieren von vorhandenen Codedateien aus ihren ursprünglichen Verzeichnissen (die in das Listenfeld unterhalb dieses Steuerelements angegeben sind) in das neue Projekt.  
  
 **Unterordner hinzufügen**  
 Gibt an, um Codedateien aus allen Unterverzeichnissen des Verzeichnisses kopieren aufgeführten **Ordner** Spalte in das neue Projekt.  
  
 **Ordner**  
 Gibt den Pfad zum Verzeichnis, das vorhandenen Codedateien zum Kopieren in das neue Projekt enthält. Diese Spalte enthält alle Verzeichnisse, die der Assistent nach vorhandenen Codedateien durchsucht.  
  
 **Add**  
 Zeigt die **Hinzufügen von Dateien zum Projekt aus diesem Ordner** Dialogfeld, das Sie Verzeichnisse angeben kann, die der Assistent nach vorhandenen Codedateien durchsucht.  
  
 **Entfernen**  
 Löscht den Verzeichnispfad an, der im Listenfeld links von diesem Steuerelement ausgewählt ist.  
  
 **Dateitypen, die dem Projekt hinzufügen**  
 Gibt die Arten von Dateien, die der Assistent das neue Projekt basierend auf bestimmten Dateierweiterungen hinzufügen. Erweiterungen, die mit dem Platzhalterzeichen vorangestellt werden und in der Liste der Dateierweiterungen durch ein Semikolon getrennt sind.  
  
 **Alle Dateien im Projektmappen-Explorer anzeigen**  
 Gibt an, dass alle Dateien in das neue Projekt im Projektmappen-Explorer-Fenster sichtbar sind und angezeigt werden. Diese Option ist standardmäßig aktiviert.