---
title: Projektbuildfehler PRJ0008 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0008
dev_langs: C++
helpviewer_keywords: PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1740b0cf1edfc90258de4fe26478298ddf2875c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0008"></a>Projektbuildfehler PRJ0008
Die Datei "File" konnte nicht gelöscht werden.  
  
 **Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess geöffnet ist und nicht schreibgeschützt.**  
  
 Während einer Wiederherstellung oder bereinigen, löscht Visual C++ alle bekannten zwischen- und Ausgabedateien Dateien für den Build, sowie alle Dateien, die in die Platzhalterspezifikationen erfüllen die **Erweiterungen von "Delete" für Bereinigen** Eigenschaft in der [Allgemein Seite mit Konfigurationseinstellungen Eigenschaft](../../ide/general-property-page-project.md).  
  
 Dieser Fehler wird angezeigt, wenn Visual C++ nicht zum Löschen einer Datei kann. Um den Fehler zu beheben, stellen Sie die Datei und das Verzeichnis für den Benutzer Builderstellungsverfahren zurückgreifen beschreibbaren.