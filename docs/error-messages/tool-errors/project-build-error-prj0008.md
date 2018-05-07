---
title: Projektbuildfehler PRJ0008 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0008
dev_langs:
- C++
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4011a27b7e6707f9c9b4e3ed386306b00f2792cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0008"></a>Projektbuildfehler PRJ0008
Die Datei "File" konnte nicht gelöscht werden.  
  
 **Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess geöffnet ist und nicht schreibgeschützt.**  
  
 Während einer Wiederherstellung oder bereinigen, löscht Visual C++ alle bekannten zwischen- und Ausgabedateien Dateien für den Build, sowie alle Dateien, die in die Platzhalterspezifikationen erfüllen die **Erweiterungen von "Delete" für Bereinigen** Eigenschaft in der [Allgemein Seite mit Konfigurationseinstellungen Eigenschaft](../../ide/general-property-page-project.md).  
  
 Dieser Fehler wird angezeigt, wenn Visual C++ nicht zum Löschen einer Datei kann. Um den Fehler zu beheben, stellen Sie die Datei und das Verzeichnis für den Benutzer Builderstellungsverfahren zurückgreifen beschreibbaren.