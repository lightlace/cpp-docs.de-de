---
title: "Projektspeicherort und Quelldateien festlegen, Assistent &quot;Neues Projekt aus vorhandenen Codedateien erstellen&quot;"
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
  - "vc.appwiz.importwiz.location"
dev_langs: 
  - "C++"
ms.assetid: 29ddffb9-5918-4d72-8c7a-a365f9de96dd
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Projektspeicherort und Quelldateien festlegen, Assistent &quot;Neues Projekt aus vorhandenen Codedateien erstellen&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese Seite des Assistenten Neues Projekt aus vorhandenen Codedateien erstellen, um Folgendes anzugeben:  
  
-   Verzeichnispfad des neuen Projekts  
  
-   Verzeichnisse, in denen nach vorhandenen Quelldateien gesucht wird  
  
-   Dateitypen, die der Assistent in das neue Projekt importiert  
  
## Aufgabenliste  
 [Gewusst wie: Erstellen eines C\+\+\-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## UIElement-Liste  
 **Projektdateiverzeichnis**  
 Gibt den Verzeichnispfad des neuen Projekts an.  Dieses Verzeichnis entspricht dem Speicherort, an dem der Assistent alle Dateien \(und Unterverzeichnisse\) des neuen Projekts ablegt.  
  
 **Durchsuchen**  
 Zeigt das Dialogfeld **Projektdateiverzeichnis** an, in dem Sie das Verzeichnis für das neue Projekt angeben können.  Dieses Steuerelement ermöglicht es Ihnen, zum gewünschten Ordner zu navigieren.  
  
 **Projektname**  
 Gibt den Namen des neuen Projekts an.  Projektdateien mit Dateierweiterungen wie .vcxproj übernehmen diesen Namen.  Vorhandene Codedateien behalten ihren ursprünglichen Namen bei.  
  
 **Dem Projekt Dateien aus diesen Ordnern hinzufügen**  
 Falls diese Option aktiviert ist, wird der Assistent angewiesen, vorhandene Codedateien aus ihren ursprünglichen Verzeichnissen \(die unterhalb dieses Steuerelements im Listenfeld angegeben sind\) in das neue Projekt zu kopieren.  
  
 **Unterordner einbeziehen**  
 Gibt an, dass Codedateien aus allen Unterverzeichnissen des Verzeichnisses, das in der Spalte **Ordner** aufgeführt ist, in das neue Projekt kopiert werden.  
  
 **Ordner**  
 Gibt den Pfad zum Verzeichnis an, das vorhandene Codedateien enthält, die in das neue Projekt kopiert werden sollen.  Diese Spalte enthält alle Verzeichnisse, die der Assistent nach vorhandenen Codedateien durchsucht.  
  
 **add**  
 Zeigt das Dialogfeld **Dateien von diesem Ordner zum Projekt hinzufügen** an, in dem Sie Verzeichnisse angeben können, die vom Assistenten nach vorhandenen Codedateien durchsucht werden.  
  
 **Entfernen**  
 Löscht den Verzeichnispfad, der im Listenfeld links von diesem Steuerelement ausgewählt ist.  
  
 **Dateitypen, die dem Projekt hinzugefügt werden sollen**  
 Gibt die Dateitypen an, die dem neuen Projekt vom Assistenten auf der Grundlage der vorgegebenen Dateierweiterungen hinzugefügt werden.  Dateierweiterungen wird ein Platzhalter in Form eines Sternchens vorangestellt, und mehrere Dateierweiterungen in der Liste werden durch ein Semikolon getrennt.  
  
 **Alle Dateien im Projektmappen\-Explorer anzeigen**  
 Gibt an, dass alle Dateien im neuen Projekt sichtbar sind und im Fenster Projekt\-Explorer angezeigt werden.  Diese Option ist standardmäßig aktiviert.