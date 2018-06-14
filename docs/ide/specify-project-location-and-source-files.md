---
title: 'Neues Projekt aus vorhandenen Codeeinstellungen: Quelldateien (Visual C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.location
dev_langs:
- C++
ms.assetid: 29ddffb9-5918-4d72-8c7a-a365f9de96dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d85a7b85996ed307596865a31d55cf4b119e5bd5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338694"
---
# <a name="specify-project-location-and-source-files-create-new-project-from-existing-code-files-wizard"></a>Projektspeicherort und Quelldateien festlegen, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"
Verwenden Sie diese Seite des Assistenten zum Erstellen eines neuen Projekts aus vorhandenen Codedateien, um Folgendes anzugeben:  
  
-   Der Verzeichnispfad des neuen Projekts  
  
-   Die Verzeichnisse, in denen nach vorhandenen Quelldateien gesucht werden soll  
  
-   Die Arten von Dateien, die der Assistent in das neue Projekt importiert  
  
## <a name="task-list"></a>Aufgabenliste  
 [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Projektdateiverzeichnis**  
 Gibt den Verzeichnispfad des neuen Projekts an. Dieser Speicherort befindet sich dort, wo der Assistent alle Dateien (und Unterverzeichnisse) des neuen Projekts ablegt.  
  
 **Browse** (Durchsuchen)  
 Zeigt das Dialogfeld **Projektdateiverzeichnis** an, das Sie beim Angeben des Verzeichnisses unterstützt, das das neue Projekt enthält. Mit diesem Steuerelement können Sie zum gewünschten Ordner navigieren.  
  
 **Projektname**  
 Gibt den Namen des neuen Projekts an. Projektdateien mit Dateierweiterungen wie „.vcxproj“ übernehmen diesen Namen. Vorhandene Codedateien behalten ihren ursprünglichen Namen bei.  
  
 **Dem Projekt Dateien aus diesen Ordnern hinzufügen**  
 Wenn diese Option aktiviert ist, kopiert der Assistent vorhandene Codedateien aus ihren ursprünglichen Verzeichnissen (die im Listenfeld unter diesem Steuerelement angezeigt werden) in das neue Projekt.  
  
 **Unterordner einbeziehen**  
 Legt fest, dass Codedateien aus allen Unterverzeichnissen der in der Spalte **Ordner** aufgeführten Verzeichnisse in das neue Projekt kopiert werden.  
  
 **Ordner**  
 Gibt den Pfad zum Verzeichnis an, das vorhandene Codedateien enthält, die in das neue Projekt kopiert werden. In dieser Spalte werden alle Verzeichnisse aufgelistet, in denen der Assistent nach vorhandenen Codedateien sucht.  
  
 **Add**  
 Zeigt das Dialogfeld **Dateien von diesem Ordner zum Projekt hinzufügen** an, mit dem Sie Verzeichnisse angeben können, in denen der Assistent nach vorhandenen Codedateien sucht.  
  
 **Entfernen**  
 Löscht den Verzeichnispfad, der im Listenfeld links von diesem Steuerelement ausgewählt ist.  
  
 **Dateitypen, die dem Projekt hinzugefügt werden sollen**  
 Gibt die Arten von Dateien an, die der Assistent dem neuen Projekt basierend auf den jeweiligen Dateierweiterungen hinzufügt. Den Erweiterungen wird ein Sternchen als Platzhalterzeichen vorangestellt, und sie werden in der Liste von Dateierweiterungen durch Semikolons getrennt.  
  
 **Alle Dateien im Projektmappen-Explorer anzeigen**  
 Gibt an, dass alle Dateien im neuen Projekt im Fenster des Projektmappen-Explorers sichtbar sind und angezeigt werden. Diese Option ist standardmäßig aktiviert.